---
title: Odświeżenie przyrostowe dla Power Query i źródła danych Azure Data Lake
description: Odświeżanie nowych i zaktualizowanych danych w przypadku dużych źródeł danych opartych na Power Query lub źródłach danych Azure data lake.
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: bff27bf7fec2bcb741846ae76bb1f616f459136c
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/14/2022
ms.locfileid: "9012038"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Odświeżenie przyrostowe dla Power Query i źródła danych Azure Data Lake

Ten artykuł omawia konfigurację odświeżania przyrostowego dla źródeł danych opartych na usłudze Power Query lub Azure Data Lake.

Odświeżanie przyrostowe dla źródeł danych daje następujące korzyści:

- **Szybsze odświeżenia** — Odświeżane są tylko te dane, które zostały zmienione. Można na przykład odświeżyć tylko ostatnie pięć dni z historycznego zestawu danych.
- **Zwiększona niezawodność** — Wraz z mniejszą liczbą odświeżeń nie jest konieczne długie utrzymywanie połączeń z nietrwałymi systemami źródłowymi, co zmniejsza ryzyko problemów z połączeniem.
- **Zmniejszone zużycie zasobów** — Odświeżanie tylko podzbioru wszystkich danych zwiększa efektywność korzystania z zasobów obliczeniowych i obniża zużycie środowiska.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Konfiguracja odświeżenia przyrostowego dla danych opartych na Power Query

Customer Insights pozwalają na odświeżanie przyrostowe dla źródeł danych zaimportowanych za pomocą usługi Power Query, która obsługuje pozyskiwanie przyrostowe. Na przykład bazy danych Azure SQL z polami Data i godzina, które wskazują, kiedy rekordy danych były ostatnio aktualizowane.

1. [Tworzenie nowego źródła danych na podstawie usługi Power Query](connect-power-query.md).

1. Wybierz źródło danych, które obsługuje odświeżanie przyrostowe, na przykład [Azure SQL Database](/power-query/connectors/azuresqldatabase).

1. Wybierz encje lub tabele, które mają zostać pozyskane.

1. Wykonaj kroki przekształcenia i wybierz **Dalej**.

1. W oknie dialogowym **Konfigurowanie odświeżania przyrostowego** wybierz **Konfiguruj**, aby otworzyć **Ustawienia odświeżania przyrostowego**. W przypadku wybrania **Pomiń** źródło danych będzie odświeżać cały zestaw danych.
   > [!TIP]
   > Można również zastosować odświeżanie przyrostowe później, edytując istniejące źródło danych.

1. W **Ustawienia odświeżania przyrostowego** skonfigurujesz odświeżanie przyrostowe dla wszystkich encji wybranych podczas tworzenia źródła danych.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Konfiguracja ustawień odświeżania przyrostowego.":::

1. Wybierz encję i wprowadź następujące informacje szczegółowe:

   - **Zdefiniuj klucz podstawowy**: Wybierz klucz podstawowy encji lub tabeli.
   - **Zdefiniuj pole "Ostatnia aktualizacja"**: W tym polu są wyświetlane tylko atrybuty typu Data i godzina. Wybierz atrybut wskazujący datę ostatniej aktualizacji rekordu. Będzie on używany do identyfikowania rekordów, które mieszczą się w horyzont czasowy odświeżania przyrostowego.
   - **Sprawdzaj aktualizacje co**: Określ, jak długo ma trwać horyzont czasowy odświeżania przyrostowego.

1. Wybierz **Zapisz**, aby zakończyć tworzenie źródła danych. Początkowe odświeżanie danych będzie pełnym odświeżaniem. Następnie przyrostowe odświeżanie danych będzie mieć miejsce zgodnie z konfiguracją podaną w poprzednim kroku.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Konfiguracja odświeżenia przyrostowego dla źródeł danych Azure Data Lake

Funkcja Customer Insights umożliwia odświeżanie przyrostowe danych dla źródeł danych połączonych z usługą Azure Data Lake Storage. Aby użyć odświeżenia przyrostowego i odświeżania dla encji, należy skonfigurować tę encję podczas dodawania źródła danych Azure Data Lake lub później podczas edytowania źródła danych. Folder danych encji musi zawierać następujące foldery:

- **FullData**: z plikami danych zawierającymi początkowe rekordy
- **IncrementalData**: Folder z folderami hierarchii dat/godzin w formacie **rrrr/mm/dd/hh** zawierający aktualizacje przyrostowe. **hh** reprezentuje godzinę aktualizacji w czasie UTC i zawiera foldery **Upsert** i **Usunięcia**. **Upserts** zawierają pliki danych wraz z aktualizacjami istniejących rekordów lub nowych rekordów. **Usunięcia** zawierają pliki danych, których rekordy należy usunąć.

1. W przypadku dodawania lub edytowania źródła danych, przejdź do okienka **Atrybuty** encji.

1. Przejrzyj atrybuty. Upewnij się, że atrybut utworzony lub ostatnio zaktualizowany został ustawiony przy użyciu **formatu danych** *data/godzina* i **typu semantycznego** *Kalendarz.Data*. W razie potrzeby dokonaj edycji atrybutu i wybierz opcję **Wykonane**.

1. W okienku **Wybierz encje** dokonaj edycji encji. Pole wyboru **Pozyskiwanie przyrostowe** jest zaznaczone.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="Konfigurowanie encji w źródle danych dla odświeżania przyrostowego.":::

   1. Przejdź do folderu głównego zawierającego pliki CSV lub .parquet po pełne dane, przeniesienia przyrostowe danych i usunięcia przyrostowe danych.
   1. Wprowadź rozszerzenie dla pełnych danych oraz plików (\.csv or \.parquet).
   1. Wybierz pozycję **Zapisz**.

1. Dla daty **ostatniej aktualizacji** wybierz atrybut sygnatury czasowej daty.

1. Jeśli **klucz podstawowy** nie jest wybrany, wybierz klucz podstawowy. Klucz podstawowy jest atrybutem unikalnym dla danej encji. Aby atrybut był prawidłowym kluczem podstawowym, nie może zawierać zduplikowanych wartości, brakujących wartości ani wartości null. Atrybuty typu ciąg, liczba całkowita i GUID są obsługiwane jako klucze podstawowe.

1. Wybierz **Zamknij**, by zapisać i zamknąć okienko.

1. Kontynuuj dodawanie i edytowanie źródła danych.

[!INCLUDE [footer-include](includes/footer-banner.md)]
