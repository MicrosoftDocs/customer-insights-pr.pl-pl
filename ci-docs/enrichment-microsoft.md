---
title: Wzbogać profile klientów dzięki danych o różnych zainteresowaniach i danych od firmy Microsoft (wersja zapoznawcza)
description: Używanie danych stanowiących własność Microsoft do wzbogacania danych klientów przy użyciu koligacji i wskaźnika Share of Voice.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: e1827adca10a3b193c02a20c4abccacf73194a77
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081505"
---
# <a name="enrich-customer-profiles-with-brands-and-interests-data-from-microsoft-preview"></a>Wzbogać profile klientów dzięki danych o różnych zainteresowaniach i danych od firmy Microsoft (wersja zapoznawcza)

Użyj danych stanowiących własność Microsoft do wzbogacania danych klientów przy użyciu sympatii do marki, sympatii do zainteresowań i wskaźnika Share of Voice (SoV). Sympatie te oraz wskaźnik SoV opierają się na danych od osób, które mają cechy demograficzne podobne do Twoich klientów. Te informacje pomogą Ci lepiej zrozumieć i segmentować klientów na podstawie ich sympatii do poszczególnych marek i zainteresowań lub odpowiednich wskaźników SoV.

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

## <a name="configure-the-enrichment"></a>Konfiguracja wzbogacania

1. Przejdź do **Dane** > **Wzbogacenie** i wybierz kartę **Odkrywanie**.

   - Aby skonfigurować wzbogacanie za pomocą sympatii do marki i wskaźnika SoV, wybierz opcję **Wzbogać moje dane** na kafelku **Marki**.

   - Aby skonfigurować wzbogacanie za pomocą sympatii zainteresowania i wskaźnika SoV, wybierz opcję **Wzbogać moje dane** na kafelku **Zainteresowania**.

   > [!div class="mx-imgBorder"]
   > ![Kafelki marek i zainteresowań.](media/BrandsInterest-tile-Hub.png "Kafelki marek i zainteresowań")

1. Przejrzyj omówienie, a następnie wybierz **Dalej**.

1. Aby zmienić kraj lub region, wybierz opcję **Zmień** obok opcji **Kraj/Region**. W okienku ustawień **Kraj/Region** wybierz [obsługiwany kraj/region](#supported-countriesregions) i wybierz opcję **Zastosuj**.

   > [!NOTE]
   > Podczas wybierania własnej marki system oferuje sugestie dotyczące wybranego kraju lub regionu. Wybierając branżę, otrzymasz najbardziej odpowiednie marki lub zainteresowania w oparciu o wybrany kraj lub region.

1. Wybierz do pięciu marek lub zainteresowań, używając jednej lub obu tych opcji:

   - **Branża**: wybierz branżę z listy rozwijanej, a następnie wybierz jedną z najlepszych opcji lub zainteresowań tej branży.
   - **Wybierz swoją**: Wprowadź markę lub interes, który jest istotny dla Twojej organizacji, a następnie wybierz spośród pasujących propozycji. Jeśli nie ukazujemy szukanej marki lub zainteresowania, wyślij nam opinię przy użyciu łącza **Sugeruj**.

1. Wybierz opcję **Dalej** i przejrzyj domyślne preferencje dotyczące wzbogacenia i zaktualizuj je zgodnie z potrzebami.

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Zrzut ekranu okna preferencji dotyczących wzbogacenia.":::

1. Wybierz **Dalej**.

1. Wybierz **Zestaw danych klienta** i wybierz profil i segment, który chcesz wzbogacić o dane dotyczące tożsamości z Microsoft. Można wybrać encję *Klient*, aby wzbogacić wszystkie profile klientów, lub wybierz jednostkę segmentu, aby wzbogacić tylko profile klientów zawarte w tym segmencie.

1. Wybierz **Dalej**.

1. Zamapuj pola z ujednoliconego obiektu klienta na dane firmy Microsoft.

   > [!NOTE]
   > Wymagane są atrybuty Data urodzenia lub płeć. Wymagany jest co najmniej kod pocztowy lub kraj/region i miejscowość (i województwo). Zaleca się, aby data konwersji oznaczała konwersję na typ data/godzina podczas in pozyskiwania danych. Alternatywnie, może to być ciąg w formacie [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html): „rrrr-MM-dd” or „rrrr-MM-ddTHH:mm:ss”.

1. Wybierz **Dalej**, by zakończyć mapowanie pól.

1. Podaj nazwę wzbogacenia. **Nazwa encji wyjściowej** jest wybierana automatycznie.

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="Strona przeglądania i nazywania zainteresowań.":::

1. Wybierz opcję **Zapisz wzbogacenie** po przejrzeniu wybranych opcji.

1. Wybierz przycisk **Uruchom**, aby rozpocząć proces wzbogacenia lub zamknąć, aby powrócić do strony **Wzbogacanie**.

   Podczas wzbogacania profili, wzbogacimy wszystkie profile klientów, dla których otrzymamy dane dla wybranych marek i zainteresowań, w tym profile, które nie znajdują się w wybranym kraju lub regionie. Na przykład jeśli wybrano Niemcy, wzbogacimy profile zlokalizowane w Stanach Zjednoczonych, jeśli w Stanach Zjednoczonych dostępne są dane dotyczące wybranych źródeł i zainteresowań.

## <a name="view-enrichment-results"></a>Wyświetlanie wyników wzbogacenia

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="Podgląd wyników po uruchomieniu procesu wzbogacania.":::

Wyniki zawierają wykresy **Poziom koligacji** lub **Share of Voice**.

Encje utworzone ze wzbogacań są wymienione w grupie **Wzbogacanie** w **Dane** > **Encje**. Wzbogacone dane dotyczące marek trafiają do encji **BrandAffinityFromMicrosoft** i **BrandShareOfVoiceFromMicrosoft**. Dane dotyczące zainteresowań znajdują się w encjach **InterestAffinityFromMicrosoft** i **InterestShareOfVoiceFromMicrosoft**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Zobacz dane dotyczące wzbogacenia na karcie klienta

Wskaźnik SoV marek i zainteresowań można wyświetlać na kartach poszczególnych klientów. Przejdź do **Klienci** i wybierz profil klienta. Na karcie klienta znajdziesz wykresy dotyczące wskaźników SoV marek lub zainteresowań oparte na osobach z profilu demograficznego klienta.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Karta klienta ze wzbogaconymi danymi.":::

## <a name="next-steps"></a>Następne kroki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
