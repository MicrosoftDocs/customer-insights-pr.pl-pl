---
title: Wzbogać profile klientów danymi firmy Microsoft
description: Używanie danych stanowiących własność Microsoft do wzbogacania danych klientów przy użyciu koligacji i wskaźnika Share of Voice.
ms.date: 11/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 346c79d0a4d5cd5c47e91c195a48d3a153db0dc0
ms.sourcegitcommit: 9d3c9e4eb2ce20996a4f4fb44c42e3fe020c5b48
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2021
ms.locfileid: "7793717"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Wzbogacanie profilów klientów przy użyciu koligacji i wskaźnika Share of Voice (wersja zapoznawcza)

Użyj danych stanowiących własność Microsoft do wzbogacania danych klientów przy użyciu sympatii do marki, sympatii do zainteresowań i wskaźnika Share of Voice (SoV). Sympatie te oraz wskaźnik SoV opierają się na danych od osób, które mają cechy demograficzne podobne do Twoich klientów. Te informacje pomogą Ci lepiej zrozumieć i segmentować klientów na podstawie ich sympatii do poszczególnych marek i zainteresowań lub odpowiednich wskaźników SoV.

W statystykach odbiorców przejdź do **Dane** > **Wzbogacanie** do [konfiguruj i wyświetl wzbogacenia](enrichment-hub.md).

Aby skonfigurować wzbogacanie za pomocą sympatii do marki i wskaźnika SoV, przejdź na kartę **Odnajdowanie** i wybierz opcję **Wzbogać moje dane** na kafelku **Marki**.

Aby skonfigurować wzbogacanie za pomocą sympatii do zainteresowań i wskaźnika SoV, przejdź na kartę **Odnajdowanie** i wybierz opcję **Wzbogać moje dane** na kafelku **Zainteresowania**.

   > [!div class="mx-imgBorder"]
   > ![Kafelki marek i zainteresowań.](media/BrandsInterest-tile-Hub.png "Kafelki marek i zainteresowań")

## <a name="how-we-determine-affinities-and-sov"></a>Jak określamy sympatie i wskaźnik SoV

Używamy udostępnianych przez Microsoft danych wyszukiwania online do wyszukiwania sympatii i wskaźnika SoV w różnych segmentach danych demograficznych (zdefiniowanych według wieku, płci lub lokalizacji). Wolumin wyszukiwania online dotyczącego marki lub zainteresowania stanowi podstawę do określenia wskaźnika sympatii lub SoV. Każdy z nich udostępnia jednak inną perspektywę interpretacji informacji o klientach.

- Sympatia to wskaźnik porównawczy między segmentami danych demograficznych. Tych informacji można użyć w celu zidentyfikowania segmentów demograficznych o najwyższym poziomie sympatii do danej marki lub zainteresowania w porównaniu z innymi segmentami.

- Share of Voice to wskaźnik porównawczy w obrębie wybranych marek lub zainteresowań. Tych informacji można użyć w celu zidentyfikowania marki lub zainteresowania, które w danym segmencie demograficznym ma najwyższy wskaźnik Share of Voice w porównaniu z innymi wybranymi markami lub zainteresowaniami.

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

## <a name="share-of-voice-sov"></a>Wskaźnik Share of Voice (SoV)

Wskaźnik SoV jest obliczany na 100-punktowej skali. Suma wskaźników SoV dla wszystkich marek lub zainteresowań w każdym wzbogaconym profilu klienta wynosi 100. W przeciwieństwie do sympatii wskaźnik SoV jest względny w stosunku do wybranego przez Ciebie marek i zainteresowań. Na przykład wartości SoV dla pozycji „Microsoft” mogą być inne, jeśli wybrano marki („Microsoft”, „GitHub”) w porównaniu z („Microsoft”, „LinkedIn”).

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

Wybierz pozycję **Wzbogacona encja** i wybierz zestaw danych, który chcesz wzbogacić danymi od Microsoft. Można wybrać encję Klient, aby wzbogacić wszystkie profile klientów, lub wybierz jednostkę segmentu, aby wzbogacić tylko profile klientów zawarte w tym segmencie.

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

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Wyniki wzbogacenia

Po uruchomieniu procesu wzbogacenia przejdź do **Moje wzbogacenia**, aby przejrzeć całkowitą liczbę wzbogaconych klientów i podział marek lub zainteresowań we wzbogaconych profilach klientów.

:::image type="content" source="media/my-enrichments.png" alt-text="Podgląd wyników po uruchomieniu procesu wzbogacania.":::

Skorzystaj z wykresu z liczbą wzbogaconych profilów klientów w czasie oraz podglądami wzbogaconych encji. Przejrzyj wzbogacone dane, wybierając pozycję **Zobacz więcej** na wykresach **Poziom sympatii** lub **Wskaźnik Share of Voice**. Wzbogacone dane dotyczące marek trafiają do encji **BrandAffinityFromMicrosoft** i **BrandShareOfVoiceFromMicrosoft**. Dane dotyczące zainteresowań znajdują się w encjach **InterestAffinityFromMicrosoft** i **InterestShareOfVoiceFromMicrosoft**. Te encje są również wymienione w grupie **Wzbogacanie** w **Dane** > **Encje**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Zobacz dane dotyczące wzbogacenia na karcie klienta

Wskaźnik SoV marek i zainteresowań można wyświetlać na kartach poszczególnych klientów. Przejdź do **Klienci** i wybierz profil klienta. Na karcie klienta znajdziesz wykresy dotyczące wskaźników SoV marek lub zainteresowań oparte na osobach z profilu demograficznego klienta.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Karta klienta ze wzbogaconymi danymi.":::

## <a name="next-steps"></a>Następne kroki

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
