---
title: Wzbogać profile klientów danymi firmy Microsoft
description: Użyj własnościowych danych firmy Microsoft, aby wzbogacić dane klientów o funkcje marek i zainteresowań.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: be042dd139607849b795c903fa58da2edb9ff589
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064904"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Wzbogać profile klientów dzięki koligacjom marki i zainteresowań (wersja zapoznawcza)

Użyj własnościowych danych firmy Microsoft, aby wzbogacić dane klientów o sympatie do marek i zainteresowania. Koligacje te są określane na podstawie danych pochodzących od osób o cechach demograficznych podobnych do cech klientów. Informacje te ułatwiają zrozumienie i segmentację klientów na podstawie ich koligacji z określonymi markami i zainteresowaniami.

W statystykach odbiorców przejdź do **Dane** > **Wzbogacanie** do [konfiguruj i wyświetl wzbogacenia](enrichment-hub.md).

Aby skonfigurować wzbogacanie koligacji marki, przejdź do karty **Odkryj** i wybierz **Wzbogacaj dane** na kafelku **Marki**.

Aby skonfigurować wzbogacanie koligacji zainteresowań, przejdź do karty **Odkryj** i wybierz **Wzbogacaj dane** na kafelku **Zainteresowania**.

   > [!div class="mx-imgBorder"]
   > ![Kafelki Marki i Zainteresowania](media/BrandsInterest-tile-Hub.png "Kafelki Marki i Zainteresowania")

## <a name="how-we-determine-affinities"></a>Jak określa się sympatie

Microsoft korzysta z danych wyszukiwania dostępnych w trybie online w celu sympatii dla marek i zainteresowań w różnych segmentach demograficznych (zdefiniowanych według wieku, płci lub lokalizacji). Wielkość wyszukiwania online dla marki lub zainteresowań określa stopień sympatii ze strony segmentu demograficznego, w porównaniu z innymi segmentami, dla tej marki lub zainteresowania.

## <a name="affinity-level-and-score"></a>Poziom sympatii i wynik

Na każdym wzbogaconym profilu klienta podajemy dwie powiązane wartości - poziom podobieństwa i wynik podobieństwa. Te wartości pomagają określić, jak silne jest podobieństwo segmentu demograficznego tego profilu, marki lub zainteresowań w porównaniu z innymi segmentami demograficznymi.

*Poziom sympatii* składa się z czterech poziomów, a *wynik sympatii* jest obliczany w skali 100-punktowej, mapowej na poziomy a automatycznie.


|Poziom sympatii |Wynik sympatii  |
|---------|---------|
|Bardzo wysoko     | 85–100       |
|Wysoka     | 70–84        |
|Średnie     | 35–69        |
|Niska     | 1–34        |

W zależności od stopnia szczegółowości pomiaru podobieństwa można użyć poziomu sympatii lub wyniku. Wynik a ponadto pozwala na dokładniejsze kontrolowanie danych.

## <a name="supported-countriesregions"></a>Obsługiwane kraje/regiony

Obecnie obsługujemy następujące opcje kraju/regionu: Australia, Kanada (angielski), Francja, Niemcy, Zjednoczone Królestwo lub Stany Zjednoczone (angielski).

Aby wybrać kraj, należy otworzyć **Wzbogacenie marek** lub **Wzbogacenie zainteresowań** a następnie wybrać **Zmień** obok **Kraj/region**. W okienku **Ustawienia kraju/regionu** wybierz jedną z opcji i wybierz **Zastosuj**.

### <a name="implications-related-to-country-selection"></a>Implikacje dotyczące wyboru kraju

- Podczas [wybierania własnej marki](#define-your-brands-or-interests) system oferuje sugestie dotyczące wybranego kraju lub regionu.

- [Wybierając branżę](#define-your-brands-or-interests), otrzymasz najbardziej odpowiednie marki lub zainteresowania w oparciu o wybrany kraj lub region.

- Podczas [wzbogacania profilów](#refresh-enrichment) wzbogacimy wszystkie profile klientów, dla których pobierzemy dane o wybranych profilach zainteresowaniach. Obejmuje profile, które nie znajdują się w wybranym kraju lub regionie. Na przykład jeśli wybrano Niemcy, wzbogacimy profile zlokalizowane w Stanach Zjednoczonych, jeśli w Stanach Zjednoczonych dostępne są dane dotyczące wybranych źródeł i zainteresowań.

## <a name="configure-enrichment"></a>Konfigurowanie wzbogacenia

Porady pomagają w konfigurowaniu wzbogacania. 

### <a name="define-your-brands-or-interests"></a>Zdefiniuj swoje marki i zainteresowania

Wybierz jedną z następujących opcji:

- **Branża**: System identyfikuje najlepsze marki lub zainteresowania istotne dla Twojej branży i wzmacnia nimi dane klientów.
- **Wybierz własne**: Wybierz maksymalnie pięć elementów z listy marek lub zainteresowań, które są najbardziej interesujące dla Twojej organizacji.

Aby dodać markę lub zainteresowanie, wprowadź ją w obszarze wprowadzania, aby uzyskać sugestie na podstawie pasujących terminów. Jeśli nie ukazujemy szukanej marki lub zainteresowania, wyślij nam opinię przy użyciu łącza **Sugeruj**.

### <a name="review-enrichment-preferences"></a>Przejrzyj preferencje wzbogacania

Przejrzyj domyślne preferencje wzbogacania i zaktualizuj je w razie potrzeby.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Zrzut ekranu okna preferencji dotyczących wzbogacenia.":::

### <a name="select-entity-to-enrich"></a>Wybierz encję do wzbogacenia

Wybierz **Obiekt wzbogacany** i wybierz zestaw danych, który chcesz wzbogacić danymi firmy z firmy Microsoft. Można wybrać encję Klient, aby wzbogacić wszystkie profile klientów, lub wybierz jednostkę segmentu, aby wzbogacić tylko profile klientów zawarte w tym segmencie.

### <a name="map-your-fields"></a>Zamapuj swoje pola

Mapuj pola z ujednoliconej encji klienta, aby zdefiniować segment demograficzny, którego system ma używać do wzbogacania danych klientów. Zamapuj kraj / region i przynajmniej atrybuty Data urodzenia lub Płeć. Ponadto musisz zamapować co najmniej jeden z następujących atrybutów: Miejscowość (i Województwo) albo Kod pocztowy. Wybierz **Edytuj**, aby zdefiniować mapowanie pól i wybierz **Zastosuj** po zakończeniu. Wybierz **Zapisz**, aby zakończyć mapowanie pola.

Obsługiwane są następujące formaty i wartości, wielkość liter w przypadku wartości nie ma znaczenia:

- **Data urodzenia**: Zaleca się, aby data urodzenia była konwertowana na typ DateTime podczas pozyskiwania danych. Można też użyć ciągu w formacie [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "rrrr-mm-dd" lub "RRRR-MM-ddTHH:mm:SSZ".
- **Płeć**: męska, żeńska, nieznane
- **Kod pocztowy**: Pięciocyfrowe kody pocztowe dla Stanów Zjednoczonych, standardowy kod pocztowy wszędzie indziej
- **Miasto**: Nazwa miasta w języku angielskim
- **Stan/Prowincja**: Dwuliterowy skrót dla Stanów Zjednoczonych i Kanady. Dwuliterowy lub trzyliterowy skrót dla Australii. Nie dotyczy Francji, Niemiec lub Wielkiej Brytanii.
- **Kraj/region**:

  - US: Stany Zjednoczone Ameryki, Stany Zjednoczone, USA, US i Ameryka
  - CA: Kanada, CA
  - GB: Zjednoczone Królestwo, UK, Wielka Brytania, GB, Zjednoczone Królestwo Wielkiej Brytanii i Irlandii Północnej, Zjednoczone Królestwo Wielkiej Brytanii
  - AU: Australia, AU, Związek Australijski
  - FR: Francja, FR, Republika Francuska
  - DE: Niemcy, niemiecki, Deutschland, Allemagne, DE, Republika Federalna Niemiec, Republika Niemiec

## <a name="review-and-name-the-enrichment"></a>Przeglądanie i nazywanie wzbogacania

Na koniec można przejrzeć te informacje i podać nazwę dla wzbogacania.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Strona przeglądania i nazywania zainteresowań.":::

## <a name="refresh-enrichment"></a>Odświeżenie wzbogacenia

Należy uruchomić wzbogacenie po skonfigurowaniu marek, zainteresowań i mapowania pól dla demografii. Aby rozpocząć proces, wybierz **Uruchom** na stronie konfiguracji marki lub zainteresowań. Oprócz tego można zezwolić systemowi na automatyczne uruchamianie wzbogacenia w ramach zaplanowanego odświeżenia.
W zależności od rozmiaru danych klientów może upłynąć kilka minut, aby można było wykonać wzbogacanie systemu.

> [!TIP]
> Istnieje [sześć typów stanu](system.md#status-types) zadań/procesów. Ponadto większość procesów [zależy od innych procesów podrzędnych](system.md#refresh-policies). Istnieje możliwość wybrania stanu procesu w celu wyświetlenia szczegółowych informacji o postępie w całym zadaniu. Po wybraniu opcji **Zobacz szczegółowe informacje** dla jednego z zadań zadania, można znaleźć więcej informacji: czas przetwarzania, Data ostatniego przetwarzania oraz wszystkie błędy i ostrzeżenia skojarzone z zadaniem.

## <a name="enrichment-results"></a>Wyniki wzbogacenia

Po uruchomieniu procesu wzbogacenia przejdź do **Moje wzbogacenia**, aby przejrzeć całkowitą liczbę wzbogaconych klientów i podział marek lub zainteresowań we wzbogaconych profilach klientów.

:::image type="content" source="media/my-enrichments.png" alt-text="Podgląd wyników po uruchomieniu procesu wzbogacania":::

Przejrz wzbogacone dane, zaznaczając **Przejrzyj wzbogacone dane** na wykresie. Wzbogacone dane dla marki przechodzą do encji **BrandAffinityFromMicrosoft**. Dane dotyczące zainteresowań znajdują się w encji **InterestAffinityFromMicrosoft**. Te encje są również wymienione w grupie **Wzbogacanie** w **Dane** > **Encje**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Zobacz dane dotyczące wzbogacenia na karcie klienta

Koligacje marki i zainteresowań można również wyświetlać na kartach poszczególnych klientów. Przejdź do **Klienci** i wybierz profil klienta. Na karcie klienta znajdziesz wykresy dotyczące marek lub zainteresowań, z którymi ludzie z danego profilu demograficznego mogą mieć powiązania.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Karta klienta ze wzbogaconymi danymi":::

## <a name="next-steps"></a>Następne kroki

Kompiluj na wierzchu wzbogaconych danych klientów. Utwórz [Segmenty](segments.md), [Miary](measures.md), a nawet [eksportuj dane](export-destinations.md), aby zapewnić klientom spersonalizowane rozwiązania.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
