---
title: Wzbogać profile klientów danymi firmy Microsoft
description: Użyj własnościowych danych firmy Microsoft, aby wzbogacić dane klientów o funkcje marek i zainteresowań.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 1b11c325649b91ebb47cde924227eacedae64b7a
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305169"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Wzbogać profile klientów dzięki koligacjom marki i zainteresowań (wersja zapoznawcza)

Użyj własnościowych danych firmy Microsoft, aby wzbogacić dane klientów o sympatie do marek i zainteresowania. Te sympatie są oparte na danych pochodzących od osób o demografii podobnej do Twoich klientów. Informacje te ułatwiają zrozumienie i segmentację klientów na podstawie ich koligacji z określonymi markami i zainteresowaniami.

W statystykach odbiorców przejdź do **Dane** > **Wzbogacanie** do [konfiguruj i wyświetl wzbogacenia](enrichment-hub.md).

Aby skonfigurować wzbogacanie koligacji marki, przejdź do karty **Odkryj** i wybierz **Wzbogacaj dane** na kafelku **Marki**.

Aby skonfigurować wzbogacanie koligacji zainteresowań, przejdź do karty **Odkryj** i wybierz **Wzbogacaj dane** na kafelku **Zainteresowania**.

   > [!div class="mx-imgBorder"]
   > ![Kafelki marek i zainteresowań](media/BrandsInterest-tile-Hub.png "Kafelki marek i zainteresowań")

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

Aby wybrać kraj lub region, otwórz **Wzbogacanie marek** lub **Wzbogacanie zainteresowań** i wybierz **Zmień** obok **Kraj/Region**. W okienku **Ustawienia kraju/regionu** wybierz jedną z opcji i wybierz **Zastosuj**.

### <a name="implications-related-to-country-selection"></a>Implikacje dotyczące wyboru kraju

- Podczas [wybierania własnej marki](#define-your-brands-or-interests) system oferuje sugestie dotyczące wybranego kraju lub regionu.

- [Wybierając branżę](#define-your-brands-or-interests), otrzymasz najbardziej odpowiednie marki lub zainteresowania w oparciu o wybrany kraj lub region.

- Podczas [wzbogacania profili](#refresh-enrichment), wzbogacimy wszystkie profile klientów, dla których otrzymamy dane dla wybranych marek i zainteresowań, w tym profile, które nie znajdują się w wybranym kraju lub regionie. Na przykład jeśli wybrano Niemcy, wzbogacimy profile zlokalizowane w Stanach Zjednoczonych, jeśli w Stanach Zjednoczonych dostępne są dane dotyczące wybranych źródeł i zainteresowań.

## <a name="configure-enrichment"></a>Konfigurowanie wzbogacenia

Porady pomagają w konfigurowaniu wzbogacania. 

### <a name="define-your-brands-or-interests"></a>Zdefiniuj swoje marki i zainteresowania

Wybierz do pięciu marek lub zainteresowań, używając jednej lub obu tych opcji:

- **Branża**: wybierz branżę z listy rozwijanej, a następnie wybierz jedną z najlepszych opcji lub zainteresowań tej branży.
- **Wybierz swoją**: Wprowadź markę lub interes, który jest istotny dla Twojej organizacji, a następnie wybierz spośród pasujących propozycji. Jeśli nie ukazujemy szukanej marki lub zainteresowania, wyślij nam opinię przy użyciu łącza **Sugeruj**.

### <a name="review-enrichment-preferences"></a>Przejrzyj preferencje wzbogacania

Przejrzyj domyślne preferencje wzbogacania i zaktualizuj je w razie potrzeby.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Zrzut ekranu okna preferencji dotyczących wzbogacenia.":::

### <a name="select-entity-to-enrich"></a>Wybierz encję do wzbogacenia

Wybierz **Obiekt wzbogacany** i wybierz zestaw danych, który chcesz wzbogacić danymi firmy z firmy Microsoft. Można wybrać encję Klient, aby wzbogacić wszystkie profile klientów, lub wybierz jednostkę segmentu, aby wzbogacić tylko profile klientów zawarte w tym segmencie.

### <a name="map-your-fields"></a>Zamapuj swoje pola

Mapuj pola z ujednoliconej encji klienta, aby zdefiniować segment demograficzny, którego system ma używać do wzbogacania danych klientów. Zamapuj kraj / region i przynajmniej atrybuty Data urodzenia lub Płeć. Ponadto musisz zamapować co najmniej jeden z następujących atrybutów: Miejscowość (i Województwo) albo Kod pocztowy. Wybierz **Edytuj**, aby zdefiniować mapowanie pól i wybierz **Zastosuj** po zakończeniu. Wybierz **Zapisz**, aby zakończyć mapowanie pola.

Obsługiwane są następujące formaty i wartości, wielkość liter w przypadku wartości nie ma znaczenia:

- **Data urodzenia**: Zaleca się, aby data urodzenia była konwertowana na typ DateTime podczas pozyskiwania danych. Alternatywnie, może to być ciąg w formacie [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html): „rrrr-MM-dd” or „rrrr-MM-ddTHH:mm:ss”.
- **Płeć**: męska, żeńska, nieznane.
- **Kod pocztowy**: pięciocyfrowe kody ZIP dla Stanów Zjednoczonych, standardowy kod pocztowy wszędzie indziej.
- **Miasto**: Nazwa miasta w języku angielskim.
- **Stan/Prowincja**: Dwuliterowy skrót dla Stanów Zjednoczonych i Kanady. Dwuliterowy lub trzyliterowy skrót dla Australii. Nie dotyczy Francji, Niemiec lub Wielkiej Brytanii.
- **Kraj/region**:

  - US: Stany Zjednoczone Ameryki, Stany Zjednoczone, USA, US i Ameryka
  - CA: Kanada, CA
  - GB: Zjednoczone Królestwo, UK, Wielka Brytania, GB, Zjednoczone Królestwo Wielkiej Brytanii i Irlandii Północnej, Zjednoczone Królestwo Wielkiej Brytanii
  - AU: Australia, AU, Związek Australijski (Commonwealth of Australia)
  - FR: Francja, FR, Republika Francuska
  - DE: Niemcy, niemiecki, Deutschland, Allemagne, DE, Republika Federalna Niemiec, Republika Niemiec

## <a name="review-and-name-the-enrichment"></a>Przeglądanie i nazywanie wzbogacania

Na koniec można przejrzeć te informacje i podać nazwę dla wzbogacania.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Strona przeglądania i nazywania zainteresowań.":::

## <a name="refresh-enrichment"></a>Odświeżenie wzbogacenia

Należy uruchomić wzbogacenie po skonfigurowaniu marek, zainteresowań i mapowania pól dla demografii. Aby rozpocząć proces, wybierz **Uruchom** na stronie konfiguracji marki lub zainteresowań. Oprócz tego można zezwolić systemowi na automatyczne uruchamianie wzbogacenia w ramach zaplanowanego odświeżenia.

W zależności od rozmiaru danych klientów może upłynąć kilka minut, aby można było wykonać wzbogacanie systemu.

> [!TIP]
> Istnieje [sześć typów stanu](system.md#status-types) zadań/procesów. Ponadto większość procesów [zależy od innych procesów podrzędnych](system.md#refresh-policies). Istnieje możliwość wybrania stanu procesu w celu wyświetlenia szczegółowych informacji o postępie w całym zadaniu. Po wybraniu opcji **Zobacz szczegóły** dla jednego z zadań, zobaczysz dodatkowe informacje: czas przetwarzania, data ostatniego przetwarzania i wszystkie błędy i ostrzeżenia związane z zadaniem.

## <a name="enrichment-results"></a>Wyniki wzbogacenia

Po uruchomieniu procesu wzbogacenia przejdź do **Moje wzbogacenia**, aby przejrzeć całkowitą liczbę wzbogaconych klientów i podział marek lub zainteresowań we wzbogaconych profilach klientów.

:::image type="content" source="media/my-enrichments.png" alt-text="Podgląd wyników po uruchomieniu procesu wzbogacania":::

Przejrz wzbogacone dane, zaznaczając **Przejrzyj wzbogacone dane** na wykresie. Wzbogacone dane dla marki przechodzą do encji **BrandAffinityFromMicrosoft**. Dane dotyczące zainteresowań znajdują się w encji **InterestAffinityFromMicrosoft**. Te encje są również wymienione w grupie **Wzbogacanie** w **Dane** > **Encje**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Zobacz dane dotyczące wzbogacenia na karcie klienta

Koligacje marki i zainteresowań można również wyświetlać na kartach poszczególnych klientów. Przejdź do **Klienci** i wybierz profil klienta. Na karcie klienta znajdziesz wykresy dotyczące marek lub zainteresowań, z którymi ludzie z danego profilu demograficznego mogą mieć powiązania.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Karta klienta ze wzbogaconymi danymi":::

## <a name="next-steps"></a>Następne kroki

Kompiluj na wierzchu wzbogaconych danych klientów. Twórz [Segmenty](segments.md) i [Miary](measures.md) oraz [eksportuj dane](export-destinations.md) w celu świadczenia klientom spersonalizowanych usług.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
