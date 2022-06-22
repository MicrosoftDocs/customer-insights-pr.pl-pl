---
title: Rozszerzanie danych firmowych
description: Wzbogać i normalizuj dane firmy za pomocą modeli Microsoft.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4247d59806468907d93fc7848231ec5a2985580e
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953962"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Wzbogacanie profilów firmy o ulepszone dane firmowe

Używaj modeli Microsoft i skompilowanych danych firmy w celu poprawiania, uzupełnienia i standaryzowania profilów firm. Do poprawiania dokładności i wiedzy użyjemy [formatu Common Data Model](/common-data-model/schema/core/applicationcommon/account).

Możesz także [wzbogacić dane firmy w źródłach danych](data-sources-enrichment.md), aby poprawić dokładność dopasowania w procesie ujednolicania danych.

W przypadku firm publicznych w Stanach Zjednoczonych dostępne są informacje, takie jak przychody, symbol giełdowy, branża i nie tylko.  

## <a name="how-we-enhance-company-data"></a>Jak rozszerzamy dane firmowe

Nasz model jest procesem dwuetapowym, który rozszerza profil firmy. W pierwszej kolejności normalizuje nazwę firmy. Na przykład nazwa *Microsoft Corp* zostanie poprawiona i ustandaryzowana do *Microsoft Corporation*. Próbuje znaleźć dopasowanie w skompilowanych danych Microsoft. W przypadku znalezionego dopasowania profil firmy wzbogacamy informacjami ze skompilowanych danych firmy, w tym nazwą firmy.

### <a name="example"></a>Przykład

Informacje o firmie mogą nie być zgodne ze standardowym formatem i mogą zawierać błędy pisowni. Model próbuje rozwiązać te problemy i utworzyć spójne informacje.

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>Ograniczenia

Model nie potrafi:

- Potwierdź tożsamość firmy. Nie sprawdzamy, czy informacją wejściową jest istniejąca organizacja, czy też firma używa jako danych wyjściowych jako nazwy standardowej.
- Kompleksowo obejmuje firmy w skali globalnej. Skompilowane przez Microsoft dane firmy mają zasięg globalny, ale oferują większość usług w Australii, Kanadzie, Wielkiej Brytanii i Stanach Zjednoczonych.
- Globalne standaryzowanie adresów firmowych. Obecnie obsługujemy standaryzowanie adresów w następujących krajach lub regionach: Australia, Kanada, Francja, Niemcy, Włochy, Japonia, Wielka Brytania i Stany Zjednoczone.
- Gwarantowana dokładność lub odświeżenie danych. Jako że informacje biznesowe często się zmieniają, nie możemy zagwarantować, że podane ulepszone dane firmy są zawsze dokładne lub aktualne.

## <a name="configure-the-enrichment"></a>Konfiguracja wzbogacania

1. Przejdź do **Dane** > **Wzbogacenie** i wybierz kartę **Odkrywanie**.

1. Wybierz opcję **Wzbogać moje dane** na kafelku **Rozszerzone dane firm**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Kafelek wzbogacania w centrum wzbogacania danych firmowych.":::

1. Przejrzyj omówienie, a następnie wybierz **Dalej**.

1. Wybierz **Zestaw danych klienta** i wybierz profil i segment, który chcesz wzbogacić. Można wybrać encję *Klient*, aby wzbogacić wszystkie profile klientów, lub wybierz jednostkę segmentu, aby wzbogacić tylko profile klientów zawarte w tym segmencie.

1. Wybierz typy pól z profilów firmy, które powinny być używane do dopasowywania ze skompilowanych danych Microsoft. Ten wybór będzie miał wpływ na pola mapowania, do których użytkownik będzie miał dostęp w następnym kroku.

1. Wybierz **Dalej**.

1. Zamapuj pola firmy na dane firmy z Microsoft. Aby uzyskać większą dokładność dopasowania, należy dodać więcej pól.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Krok mapowania danych podczas konfigurowania wzbogacania firmy.":::

1. Wybierz **Dalej**, by zakończyć mapowanie pól.

1. Podaj **Nazwę** dla wzbogacenia oraz **Obiekt wyjściowy**.

1. Wybierz opcję **Zapisz wzbogacenie** po przejrzeniu wybranych opcji.

1. Wybierz przycisk **Uruchom**, aby rozpocząć proces wzbogacenia lub zamknąć, aby powrócić do strony **Wzbogacanie**.

## <a name="enrichment-results"></a>Wyniki wzbogacenia

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>Karta przeglądowa

Na kafelku **przeglądowej zmiany klientów** są szczegółowe informacje dotyczące zakresu wzbogacania

- **Firmy przetwarzane i zmieniane**: Liczba profili firm klientów, które zostały pomyślnie wzbogacone.
- **Firmy przetwarzane i niezmienianie**: Liczba profili firm klientów, które zostały rozpoznane, ale nie zostały zmienione. Zazwyczaj zdarza się to, jeśli dane wejściowe są prawidłowe i nie można ich poprawić przez wzbogacenie.
- **Firmy nieprzetworzone i niezmienione**: Liczba profili firm klientów, które nie zostały rozpoznane. Jest tak zwykle w przypadku danych wejściowych, które są nieprawidłowe lub nieobsługiwane przez wzbogacenie.

## <a name="next-steps"></a>Następne kroki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
