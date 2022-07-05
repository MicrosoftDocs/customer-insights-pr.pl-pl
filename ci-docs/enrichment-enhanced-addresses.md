---
title: Wzbogacanie profilów klientów o ulepszone adresy (zawiera film wideo)
description: Wzbogacaj i normalizuj informacje adresowe z profili klientów za pomocą modeli firmy Microsoft.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 01f1c917c75e932cc69f4c7251e57524fc859dce
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081229"
---
# <a name="enrich-customer-profiles-with-enhanced-addresses"></a>Wzbogacanie profilów klientów o ulepszone adresy

Adresy w Twoich danych mogą być nieustrukturyzowane, niekompletne lub nieprawidłowe. Użyj modeli firmy Microsoft do normalizacji i wzbogacenia adresów do [formatu Common Data Model](/common-data-model/schema/core/applicationcommon/address) w celu lepszej dokładności i głębszej analizy.

Możesz także [wzbogacić adresy w źródłach danych](data-sources-enrichment.md), aby poprawić dokładność dopasowania w procesie ujednolicania danych. 

## <a name="how-we-enhance-addresses"></a>Jak wzbogacamy adresy

Nasz model jest procesem dwuetapowym, który wzbogaca adres. Najpierw analizuje adres, aby zidentyfikować jego składniki i umieszcza je w formacie ustrukturyzowanym. Następnie użyjemy interfejsu AI do poprawiania, ukończenia i standardyzacji wartości adresu.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

### <a name="example"></a>Przykład

Informacje o adresie mogą mieć niestandardowy format i zawierać błędy pisowni. Model może rozwiązać te problemy i utworzyć spójne adresy w ujednoliconych profilach klientów.

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>Ograniczenia

Poprawione adresy działają tylko z wartościami, które już istnieją w pozyskanych danych adresów. Model nie potrafi:

1. Zweryfikować, czy adres jest poprawny.
2. Sprawdzić, czy któraś z wartości, na przykład kodów pocztowy lub nazwa ulicy, jest prawidłowa.
3. Zmienić wartości, które nie są przez niego rozpoznawane.

W modelu do poprawiania adresów są używane techniki oparte na uczeniu maszynowym. Tak jak w przypadku każdego modelu opartego na uczeniu maszynowym nie jest zagwarantowana 100-procentowa dokładność.

## <a name="supported-countries-or-regions"></a>Obsługiwane kraje lub regiony

Obecnie oferujemy wzbogacenie adresów w tych krajach lub regionach:

- Australia
- Kanada
- Francja
- Niemcy
- Włochy
- Japonia
- Zjednoczone Królestwo
- Stany Zjednoczone

## <a name="configure-the-enrichment"></a>Konfiguracja wzbogacania

1. Przejdź do **Dane** > **Wzbogacenie** i wybierz kartę **Odkrywanie**.

1. Wybierz opcję **Wzbogać dane** na kafelku **Ulepszone adresy**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Zrzut ekranu kafelka Ulepszone adresy.":::

1. Przejrzyj omówienie, a następnie wybierz **Dalej**.

1. Wybierz **Zestaw danych klienta** i wybierz profil i segment, który chcesz wzbogacić. Można wybrać encję *Klient*, aby wzbogacić wszystkie profile klientów, lub wybierz jednostkę segmentu, aby wzbogacić tylko profile klientów zawarte w tym segmencie.

1. Wybierz sposób formatowania adresów w Twoich zestawach danych. Wybierz **Adres z pojedynczym atrybutem**, jeśli adresy w Twoich danych zawierają tylko jedno pole. Wybierz **Adres z wieloma atrybutami**, jeśli adresy w Twoich danych zawierają więcej niż jedno pole.

1. Wybierz opcję **Dalej** i zamapuj pola adresu z ujednoliconej encji klienta.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Strona ulepszonego mapowania pola adresu.":::

   > [!NOTE]
   > Kraj/region jest obowiązkowy zarówno w adresach jednoatrybutowych, jak i wieloatrybutowych. Adresy nie zawierające prawidłowych lub obsługiwanych wartości kraju/regionu nie zostaną wzbogacone.

1. Wybierz **Dalej**, by zakończyć mapowanie pól.

1. Podaj **Nazwę** dla wzbogacenia oraz **Obiekt wyjściowy**.

1. Wybierz opcję **Zapisz wzbogacenie** po przejrzeniu wybranych opcji.

## <a name="view-enrichment-results"></a>Wyświetlanie wyników wzbogacenia

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Liczba klientów wzbogaconych według pola** zapewnia szczegółowe informacje na temat pokrycia każdego wzbogaconego pola.

### <a name="overview-card"></a>Karta przeglądowa

Na karcie **przeglądowej zmiany klientów** są szczegółowe informacje dotyczące zakresu wzbogacania:

- **Adresy przetwarzane i zmieniane**: Liczba profili klientów z adresami, które zostały pomyślnie wzbogacone.
- **Adresy przetwarzane i niezmieniane**: Liczba profili klientów z adresami, które zostały rozpoznane, ale nie zostały zmienione. Zazwyczaj zdarza się to, jeśli dane wejściowe są prawidłowe i nie można ich poprawić przez wzbogacenie.
- **Adresy nieprzetworzone i niezmienione**: Liczba profili klientów z adresami, które nie zostały rozpoznane. Zwykle w przypadku danych wejściowych, które są nieprawidłowe lub nieobsługiwane przez wzbogacenie.

## <a name="next-steps"></a>Następne kroki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
