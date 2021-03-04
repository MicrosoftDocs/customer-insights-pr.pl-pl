---
title: Odświeżanie przyrostowe dla źródeł danych opartych na Power Query
description: Odświeżanie nowych i zaktualizowanych danych dla dużych źródeł danych na podstawie Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d4b01be75d25fa0e120904924a193171eefec579
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268561"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Odświeżanie przyrostowe dla źródeł danych opartych na Power Query

Odświeżanie przyrostowe dla źródeł danych daje następujące korzyści:

- **Szybsze odświeżenia** — Odświeżane są tylko te dane, które zostały zmienione. Można na przykład odświeżyć tylko ostatnie pięć dni z historycznego zestawu danych.
- **Zwiększona niezawodność** — Wraz z mniejszą liczbą odświeżeń nie jest konieczne długie utrzymywanie połączeń z nietrwałymi systemami źródłowymi, co zmniejsza ryzyko problemów z połączeniem.
- **Zmniejszone zużycie zasobów** — Odświeżanie tylko podzbioru wszystkich danych zwiększa efektywność korzystania z zasobów obliczeniowych i obniża zużycie środowiska.

## <a name="configure-incremental-refresh"></a>Konfiguruj odświeżanie przyrostowe

Informacje o odbiorcach umożliwiają przyrostowe odświeżanie źródeł danych importowanych za pomocą dodatku Power Query, które obsługują pozyskiwanie przyrostowe. Na przykład bazy danych Azure SQL z polami Data i godzina, które wskazują, kiedy rekordy danych były ostatnio aktualizowane.

1. [Utwórz nowe źródło danych na podstawie Power Query](connect-power-query.md).

1. Podaj nazwę źródła danych.

1. Wybierz źródło danych, które obsługuje odświeżanie przyrostowe, na przykład Azure SQL Database.

1. Wybierz encje lub tabele, które mają zostać pozyskane.

1. Wykonaj kroki przekształcenia i wybierz **Dalej**.

1. W oknie dialogowym **Konfigurowanie odświeżania przyrostowego** wybierz **Konfiguruj**, aby otworzyć **Ustawienia odświeżania przyrostowego**. W przypadku wybrania **Pomiń** źródło danych będzie odświeżać cały zestaw danych.
   > [!TIP]
   > Można również zastosować odświeżanie przyrostowe później, edytując istniejące źródło danych.

1. W **Ustawienia odświeżania przyrostowego** skonfigurujesz odświeżanie przyrostowe dla wszystkich encji wybranych podczas tworzenia źródła danych.

   > [!div class="mx-imgBorder"]
   > ![Konfigurowanie encji w źródle danych dla odświeżania przyrostowego](media/incremental-refresh-settings.png "Konfigurowanie encji w źródle danych dla odświeżania przyrostowego")

1. Wybierz encję i wprowadź następujące informacje szczegółowe:

   - **Zdefiniuj klucz podstawowy**: Wybierz klucz podstawowy encji lub tabeli.
   - **Zdefiniuj pole "Ostatnia aktualizacja"**: W tym polu są wyświetlane tylko atrybuty typu Data i godzina. Wybierz atrybut wskazujący datę ostatniej aktualizacji rekordu. Będzie on używany do identyfikowania rekordów, które mieszczą się w horyzont czasowy odświeżania przyrostowego.
   - **Sprawdzaj aktualizacje co**: Określ, jak długo ma trwać horyzont czasowy odświeżania przyrostowego.

1. Wybierz **Zapisz**, aby zakończyć tworzenie źródła danych. Początkowe odświeżanie danych będzie pełnym odświeżaniem. Następnie przyrostowe odświeżanie danych będzie mieć miejsce zgodnie z konfiguracją podaną w poprzednim kroku.


[!INCLUDE[footer-include](../includes/footer-banner.md)]