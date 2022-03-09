---
title: Ulepszenia wzbogacania adresu (zawiera wideo)
description: Wzbogacaj i normalizuj informacje adresowe z profili klientów za pomocą modeli firmy Microsoft.
ms.date: 01/19/2022
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
ms.openlocfilehash: 067757019078d3a46b224ba259d2d097dfbbe381
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353649"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Wzbogacenie profili klientów za pomocą ulepszonych adresów

Adresy w Twoich danych mogą być nieustrukturyzowane, niekompletne lub nieprawidłowe. Użyj modeli firmy Microsoft do normalizacji i wzbogacenia adresów do [formatu Common Data Model](/common-data-model/schema/core/applicationcommon/address) w celu lepszej dokładności i głębszej analizy.

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

Funkcja ulepszania adresów współpracuje tylko z wartościami, które już istnieją w sprawdzanych danych adresów. Model nie potrafi: 

1. Zweryfikować, czy adres jest poprawny.
2. Sprawdzić, czy któraś z wartości, na przykład kodów pocztowy lub nazwa ulicy, jest prawidłowa.
3. Zmienić wartości, które nie są przez niego rozpoznawane.

W modelu do poprawiania adresów są używane techniki oparte na uczeniu maszynowym. Chociaż stosujemy wysoki próg ufności, kiedy model zmienia wartość wejściową, jak w przypadku każdego modelu opartego na uczeniu maszynowym, 100-procentowa dokładność nie jest gwarantowana.

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

Adresy muszą zawierać wartość kraju/regionu. Nie są przetwarzane adresy krajów lub regionów, które nie są obsługiwane, ani adresy, które nie mają podanego kraju lub regionu.

## <a name="configure-the-enrichment"></a>Konfiguracja wzbogacania

1. Przejdź do **Dane** > **Wzbogacanie**.

1. Wybierz opcję **Wzbogać dane** na kafelku **Ulepszone adresy**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Zrzut ekranu kafelka Ulepszone adresy.":::

1. Wybierz **Zestaw danych klienta** i wybierz encję zawierającą adresy, które chcesz wzbogacić. Można wybrać encję *Klient*, aby wzbogacić adresy we wszystkich profilach klientów lub wybrać encję segmentu, która wzbogaci adresy tylko w profilach klientów zawartych w tym segmencie.

1. Wybierz sposób formatowania adresów w Twoich zestawach danych. Wybierz **Adres z pojedynczym atrybutem**, jeśli adresy w Twoich danych zawierają tylko jedno pole. Wybierz **Adres z wieloma atrybutami**, jeśli adresy w Twoich danych zawierają więcej niż jedno pole.

   > [!NOTE]
   > Kraj/region jest obowiązkowy zarówno w adresach jednoatrybutowych, jak i wieloatrybutowych. Adresy nie zawierające prawidłowych lub obsługiwanych wartości kraju/regionu nie zostaną wzbogacone.

1.  Zamapuj pola adresu z ujednoliconej encji klienta.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Strona ulepszonego mapowania pola adresu.":::

1. Wybierz **Dalej**, by zakończyć mapowanie pól.

1. Podaj nazwę dla wzbogacania oraz encję wyjściową.

1. Wybierz opcję **Zapisz wzbogacenie** po przejrzeniu wybranych opcji.

## <a name="enrichment-results"></a>Wyniki wzbogacenia

Aby rozpocząć proces wzbogacania, wybierz **Uruchom** na pasku poleceń. Można również zezwolić, aby system automatycznie uruchamiał wzbogacenie w ramach [zaplanowanego odświeżenia](system.md#schedule-tab). Czas przetwarzania zależy od rozmiaru danych klienta.

Po zakończeniu procesu wzbogacania można przejrzeć dane nowo wzbogacone profile klientów w **Moje wzbogacenia**. Ponadto znajdziesz tam czas ostatniej aktualizacji i liczbę wzbogaconych profilów.

Możesz zobaczyć przykładowe dane wzbogacone w kafelku **Podglądu wzbogaconych klientów**. Wybierz opcję **Zobacz więcej** i wybierz kartę **Dane**, aby uzyskać dostęp do szczegółowego widoku każdego z wzbogaconych profilów.

### <a name="overview-card"></a>Karta przeglądowa

Na karcie przeglądowej są szczegółowe informacje dotyczące zakresu wzbogacania. 

* **Adresy przetwarzane i zmieniane**: Liczba profili klientów z adresami, które zostały pomyślnie wzbogacone.

* **Adresy przetwarzane i niezmieniane**: Liczba profili klientów z adresami, które zostały rozpoznane, ale nie zostały zmienione. Zazwyczaj zdarza się to, jeśli dane wejściowe są prawidłowe i nie można ich poprawić przez wzbogacenie.

* **Adresy nieprzetworzone i niezmienione**: Liczba profili klientów z adresami, które nie zostały rozpoznane. Zwykle w przypadku danych wejściowych, które są nieprawidłowe lub nieobsługiwane przez wzbogacenie.

## <a name="next-steps"></a>Następne kroki

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
