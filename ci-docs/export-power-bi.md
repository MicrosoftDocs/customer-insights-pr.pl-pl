---
title: Łącznik Power BI (wersja zapoznawcza)
description: Dowiedz się, jak używać łącznika Dynamics 365 Customer Insights w Power BI.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 656a695b8b3f1ec2b5fbaad69feba7f1f0b73dee
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196683"
---
# <a name="power-bi-connector-preview"></a>Łącznik Power BI (wersja zapoznawcza)

Tworzenie wizualizacji danych za pomocą Microsoft Power BI Desktop. Tworzenie dodatkowych wyników analiz i raportów przy użyciu ujednoliconych danych klientów.

## <a name="prerequisites"></a>Wymagania wstępne

- Profile z funkcji Unified Customer Profile.
- Na komputerze została zainstalowana najnowsza wersja programu [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/). [Więcej informacji o Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konfigurowanie łącznika dla Power BI

1. W Power BI Desktop wybierz **Plik** > **Pobierz dane**.

1. Wybierz **Zobacz więcej** i wyszukaj **Dynamics 365 Customer Insights**

1. Wybierz pozycję **Połącz**.

1. **Zaloguj się**, korzystając z tego samego konta organizacyjnego, które będzie używane dla Customer Insights i wybierz **Połącz**.
   > [!NOTE]
   > Konto wskazywane w tym kroku służy do pobierania danych z Customer Insights i nie musi być tym samym, do którego użytkownik jest zalogowany w programie Power BI. Aby zresetować konto używane do pobierania danych, otwórz Power BI i przejdź do **Plik** > **Opcje** > **Ustawienia** > **Ustawienia źródeł danych**. Z listy źródeł danych wybierz **Logowanie w Dynamics 365 Customer Insights** i wybierz **Wyczyść uprawnienia**.  

1. W oknie dialogowym **Nawigatora** wyświetl listę wszystkich środowisk, do których użytkownik ma dostęp. Rozwiń środowisko i otwórz dowolny z folderów (encje, miary, segmenty, wzbogacenia). Na przykład otwórz folder **Encje**, aby wyświetlić wszystkie encje, które można importować.

   :::image type="content" source="media/power-bi-navigator.png" alt-text="Nawigator łącznika Power BI.":::

1. Zaznacz pola wyboru obok encji, które mają zostać dodane i **Załaduj**. Możesz wybrać wiele encji z wielu środowisk.

   Okno dialogowe wczytywania wyświetla się podczas wczytywania elementów. Kiedy wszystkie wybrane encje zostaną załadowane, można użyć funkcji Power BI do wizualizacji danych.

## <a name="large-data-sets"></a>Duże zestawy danych

Łącznik Customer Insights dla Power BI jest przeznaczony do pracy z zestawami danych zawierającymi do 1.000.000 profilów klientów. Importowanie większych zestawów danych może działać, ale zajmuje dużo czasu i może przekroczyć limit czasu z powodu ograniczeń usługi Power BI. Aby uzyskać więcej informacji, zobacz [Power BI: Rekomendacje dotyczące dużych zestawów danych](/power-bi/admin/service-premium-what-is#large-datasets).

### <a name="work-with-a-subset-of-data"></a>Praca z podzbiorem danych

Weź pod uwagę pracę z podzbiorem danych programu. Można na przykład utworzyć [segmenty](segments.md) zamiast eksportowania wszystkich rekordów klientów do Power BI.

## <a name="troubleshooting"></a>Rozwiązywanie problemów

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Środowisko Customer Insights nie jest wyświetlane w programie Power BI

Środowiska, w których zdefiniowano więcej niż jedną [relację](relationships.md) między dwiema identycznymi encjami w Customer Insights, nie będą dostępne w łączniku Power BI.

Zidentyfikuj i usuń zduplikowane relacje.

1. Przejdź do **Dane** > **Relacje** w środowisku, którego brakuje w Power BI.
1. Zidentyfikuj zduplikowane relacje:
   - Sprawdź, czy istnieje więcej niż jedna relacja zdefiniowana między tymi samymi dwoma obiektami.
   - Sprawdź, czy istnieje relacja utworzona między dwiema jednostkami, które są objęte procesem unifikacji. Istnieje domniemana relacja między wszystkimi jednostkami uwzględnionymi w procesie unifikacji.
1. Usuń wszystkie zidentyfikowane zduplikowane relacje.

Po usunięciu zduplikowanych relacji spróbuj ponownie skonfigurować łącznik usługi Power BI.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Błędy w polach daty podczas ładowania jednostek w Power BI Desktop

Podczas ładowania jednostek zawierających pola z formatem daty, takich jak MM/DD/RRRR, można napotkać błędy z powodu niedopasowanych formatów ustawień regionalnych. Ta niezgodność występuje, gdy plik Power BI Desktop zawiera ustawienia regionalne inny niż angielski (Stany Zjednoczone), ponieważ pola dat w Customer Insights są zapisywane w formacie amerykańskim.

Plik Power BI Desktop ma jedno ustawienie ustawień regionalnych, które jest stosowane podczas pobierania danych. Aby naprawić błędy dat, [ustaw ustawienia regionalne pliku .BPI](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop) na angielski (Stany Zjednoczone).

[!INCLUDE [footer-include](includes/footer-banner.md)]
