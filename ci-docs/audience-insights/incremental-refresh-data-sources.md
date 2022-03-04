---
title: Odświeżenie przyrostowe dla danych opartych na źródłach danych Power Query
description: Odświeżanie nowych i zaktualizowanych danych w przypadku dużych źródeł danych w zależności od wersji Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 62632efda3c0c7e53fcdd8864b053ba93e2918bc
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353695"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Odświeżenie przyrostowe dla danych opartych na Power Query

Ten artykuł omawia konfigurację odświeżania przyrostowego dla źródeł danych opartych na usłudze Power Query.

Odświeżanie przyrostowe dla źródeł danych daje następujące korzyści:

- **Szybsze odświeżenia** — Odświeżane są tylko te dane, które zostały zmienione. Można na przykład odświeżyć tylko ostatnie pięć dni z historycznego zestawu danych.
- **Zwiększona niezawodność** — Wraz z mniejszą liczbą odświeżeń nie jest konieczne długie utrzymywanie połączeń z nietrwałymi systemami źródłowymi, co zmniejsza ryzyko problemów z połączeniem.
- **Zmniejszone zużycie zasobów** — Odświeżanie tylko podzbioru wszystkich danych zwiększa efektywność korzystania z zasobów obliczeniowych i obniża zużycie środowiska.

## <a name="configure-incremental-refresh"></a>Konfiguruj odświeżanie przyrostowe

Szczegółowe dane o odbiorcach pozwalają na odświeżanie przyrostowe dla źródeł danych zaimportowanych za pomocą usługi Power Query, która obsługuje pozyskiwanie przyrostowe. Na przykład bazy danych Azure SQL z polami Data i godzina, które wskazują, kiedy rekordy danych były ostatnio aktualizowane.

1. [Tworzenie nowego źródła danych na podstawie usługi Power Query](connect-power-query.md).

1. Podaj **nazwę** źródła danych.

1. Wybierz źródło danych, które obsługuje odświeżanie przyrostowe, na przykład [Azure SQL Database](/power-query/connectors/azuresqldatabase).

1. Wybierz encje lub tabele, które mają zostać pozyskane.

1. Wykonaj kroki przekształcenia i wybierz **Dalej**.

1. W oknie dialogowym **Konfigurowanie odświeżania przyrostowego** wybierz **Konfiguruj**, aby otworzyć **Ustawienia odświeżania przyrostowego**. W przypadku wybrania **Pomiń** źródło danych będzie odświeżać cały zestaw danych.
   > [!TIP]
   > Można również zastosować odświeżanie przyrostowe później, edytując istniejące źródło danych.

1. W **Ustawienia odświeżania przyrostowego** skonfigurujesz odświeżanie przyrostowe dla wszystkich encji wybranych podczas tworzenia źródła danych.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Konfigurowanie encji w źródle danych dla odświeżania przyrostowego.":::

1. Wybierz encję i wprowadź następujące informacje szczegółowe:

   - **Zdefiniuj klucz podstawowy**: Wybierz klucz podstawowy encji lub tabeli.
   - **Zdefiniuj pole "Ostatnia aktualizacja"**: W tym polu są wyświetlane tylko atrybuty typu Data i godzina. Wybierz atrybut wskazujący datę ostatniej aktualizacji rekordu. Będzie on używany do identyfikowania rekordów, które mieszczą się w horyzont czasowy odświeżania przyrostowego.
   - **Sprawdzaj aktualizacje co**: Określ, jak długo ma trwać horyzont czasowy odświeżania przyrostowego.

1. Wybierz **Zapisz**, aby zakończyć tworzenie źródła danych. Początkowe odświeżanie danych będzie pełnym odświeżaniem. Następnie przyrostowe odświeżanie danych będzie mieć miejsce zgodnie z konfiguracją podaną w poprzednim kroku.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
