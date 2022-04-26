---
title: Łącznik usługi Power BI
description: Dowiedz się, jak używać łącznika Dynamics 365 Customer Insights w Power BI.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 06c5bed74b82f9ae2a764a2eb363348e0edab531
ms.sourcegitcommit: 4b2ad63aa7a4d4f31b573870bccbc40befe5f8fd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/07/2022
ms.locfileid: "8552069"
---
# <a name="connector-for-power-bi-preview"></a>Łącznik dla Power BI (wersja zapoznawcza)

Utwórz wizualizacje danych za pomocą narzędzia Power BI Desktop. Tworzenie dodatkowych wyników analiz i raportów przy użyciu ujednoliconych danych klientów.

## <a name="prerequisites"></a>Wymagania wstępne

- Posiadasz ujednolicone profile klientów.
- Na komputerze została zainstalowana najnowsza wersja programu [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/). [Więcej informacji o Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konfigurowanie łącznika dla Power BI

1. W Power BI Desktop wybierz **Plik** > **Pobierz dane**.

1. Wybierz **Zobacz więcej** i wyszukaj **Dynamics 365 Customer Insights**

1. Wybierz pozycję **Połącz**.

1. **Zaloguj się**, korzystając z tego samego konta organizacyjnego, które będzie używane dla Customer Insights i wybierz **Połącz**.
   > [!NOTE]
   > Konto wskazywane w tym kroku służy do pobierania danych z Customer Insights i nie musi być tym samym, do którego użytkownik jest zalogowany w programie Power BI. Aby zresetować konto używane do pobierania danych, otwórz Power BI i przejdź do **Plik** > **Opcje** > **Ustawienia** > **Ustawienia źródeł danych**. Z listy źródeł danych wybierz **Logowanie w Dynamics 365 Customer Insights** i wybierz **Wyczyść uprawnienia**.  

1. W oknie dialogowym **Nawigator**. zobaczysz listę wszystkich środowisk, do których masz dostęp. Rozwiń środowisko i otwórz dowolny z folderów (encje, miary, segmenty, wzbogacenia). Na przykład otwórz folder **Encje**, aby wyświetlić wszystkie encje, które można importować.

   ![Nawigator łącznika Power BI.](media/power-bi-navigator.png "Nawigator łącznika Power BI")

1. Zaznacz pola wyboru obok encji, które mają zostać dodane i **Załaduj**. Możesz wybrać wiele encji z wielu środowisk.

1. Podczas ładowania encji zostanie wyświetlone okno dialogowe ładowania. Kiedy wszystkie wybrane encje zostaną załadowane, można użyć funkcji Power BI do wizualizacji danych.

## <a name="large-data-sets"></a>Duże zestawy danych

Łącznik Customer Insights dla Power BI jest przeznaczony do pracy z zestawami danych zawierającymi do 1.000.000 profilów klientów. Importowanie większych zestawów danych może się udać, ale zajmie dużo czasu. Ponadto proces może przekroczyć limit czasu z powodu ograniczeń Power BI. Aby uzyskać więcej informacji, zobacz [Power BI: Rekomendacje dotyczące dużych zestawów danych](/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Praca z podzbiorem danych

Weź pod uwagę pracę z podzbiorem danych programu. Można na przykład utworzyć [segmenty](segments.md) zamiast eksportowania wszystkich rekordów klientów do Power BI.

## <a name="troubleshooting"></a>Rozwiązywanie problemów

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Środowisko Customer Insights nie jest wyświetlane w programie Power BI

Środowiska, które mają więcej niż jedną [relację](relationships.md) zdefiniowaną między dwoma identycznymi jednostkami w szczegółowych informacjach o odbiorcach, nie będą dostępne w łączniku usługi Power BI.

Możesz zidentyfikować i usunąć zduplikowane relacje.

1. W odbiorcy danych przejdź do strony **Dane** > **Relacje** w środowisku, w którym nie ma Power BI.
2. Zidentyfikuj zduplikowane relacje:
   - Sprawdź, czy istnieje więcej niż jedna relacja zdefiniowana między tymi samymi dwoma obiektami.
   - Sprawdź, czy istnieje relacja utworzona między dwiema jednostkami, które są objęte procesem unifikacji. Istnieje domniemana relacja między wszystkimi jednostkami uwzględnionymi w procesie unifikacji.
3. Usuń wszystkie zidentyfikowane zduplikowane relacje.

Po usunięciu zduplikowanych relacji spróbuj ponownie skonfigurować łącznik usługi Power BI. Środowisko powinno być teraz dostępne.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Błędy w polach daty podczas ładowania jednostek w Power BI Desktop

Podczas ładowania jednostek zawierających pola z formatem daty, takich jak MM/DD/RRRR, można napotkać błędy z powodu niedopasowanych formatów ustawień regionalnych. Ta niezgodność ma miejsce, gdy plik Power BI Desktop jest ustawiony na inne ustawienia regionalne niż angielski (Stany Zjednoczone), ponieważ pola daty w szczegółowych informacjach odbiorcy są zapisywane w formacie amerykańskim.

Plik Power BI Desktop ma jedno ustawienie ustawień regionalnych, które jest stosowane podczas pobierania danych. Pola pobierają te daty interpretowane poprawnie, ustawiają ustawienia regionalne pliku .BPI do języka angielskiego (Stany Zjednoczone). [Dowiedz się, jak zmienić ustawienia regionalne pliku Power BI Desktop](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
