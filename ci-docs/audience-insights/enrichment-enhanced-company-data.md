---
title: Rozszerzanie danych firmowych
description: Wzbogać i normalizuj dane firmy za pomocą modeli Microsoft.
ms.date: 01/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e9cf93f28ba6918c72039670e42d26c8aaa7f922
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376367"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Wzbogacanie profilów firmy o ulepszone dane firmowe

Używaj modeli Microsoft i skompilowanych danych firmy w celu poprawiania, uzupełnienia i standaryzowania profilów firm. Do poprawiania dokładności i wiedzy użyjemy [formatu Common Data Model](/common-data-model/schema/core/applicationcommon/account).

Możesz także [wzbogacić dane firmy w źródłach danych](data-sources-enrichment.md), aby poprawić dokładność dopasowania w procesie ujednolicania danych. 

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

Istnieje kilka ograniczeń dotyczących rozszerzonych danych. Pozycje na poniższej liście nie są obsługiwane przez model.

1.  Potwierdź tożsamość firmy. Nie sprawdzamy, czy informacją wejściową jest istniejąca organizacja, czy też firma używa jako danych wyjściowych jako nazwy standardowej.
2.  Kompleksowo obejmuje firmy w skali globalnej. Skompilowane przez Microsoft dane firmy mają zasięg globalny, ale oferują większość usług w Australii, Kanadzie, Wielkiej Brytanii i Stanach Zjednoczonych.
3.  Globalne standaryzowanie adresów firmowych. Obecnie obsługujemy standaryzowanie adresów w następujących krajach lub regionach: Australia, Kanada, Francja, Niemcy, Włochy, Japonia, Wielka Brytania i Stany Zjednoczone.
4.  Gwarantowana dokładność lub odświeżenie danych. Jako że informacje biznesowe często się zmieniają, nie możemy zagwarantować, że podane ulepszone dane firmy są zawsze dokładne lub aktualne.

## <a name="configure-the-enrichment"></a>Konfiguracja wzbogacania

1. Przejdź do **Dane** > **Wzbogacanie**.

1. Wybierz opcję **Wzbogać moje dane** na kafelku **Rozszerzone dane firm**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Kafelek wzbogacania w centrum wzbogacania danych firmowych.":::

1. Wybierz **Zestaw danych klienta** i wybierz encję zawierającą adresy, które chcesz wzbogacić. Można wybrać encję *Klient*, aby wzbogacić adresy we wszystkich profilach klientów lub wybrać encję segmentu, która wzbogaci adresy tylko w profilach klientów zawartych w tym segmencie.

1. Wybierz typy pól z profilów firmy, które powinny być używane do dopasowywania ze skompilowanych danych Microsoft. Ten wybór będzie miał wpływ na pola mapowania, do których użytkownik będzie miał dostęp w następnym kroku.

1.  Mapuj pola firmy z ujednoliconej encji klienta. Im więcej kluczowych identyfikatorów i pól mapuje się, tym wyższe jest prawdopodobieństwo dopasowania.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Krok mapowania danych podczas konfigurowania wzbogacania firmy.":::

1. Wybierz **Dalej**, by zakończyć mapowanie pól.

1. Podaj nazwę dla wzbogacania oraz encję wyjściową.

1. Wybierz opcję **Zapisz wzbogacenie** po przejrzeniu wybranych opcji.

## <a name="enrichment-results"></a>Wyniki wzbogacenia

Aby rozpocząć proces wzbogacania, wybierz **Uruchom** na pasku poleceń. Można również zezwolić, aby system automatycznie uruchamiał wzbogacenie w ramach [zaplanowanego odświeżenia](system.md#schedule-tab). Czas przetwarzania zależy od rozmiaru danych klienta.

Po zakończeniu procesu wzbogacania można przejrzeć dane nowo wzbogacone profile klientów w **Moje wzbogacenia**. Ponadto znajdziesz tam czas ostatniej aktualizacji i liczbę wzbogaconych profilów.

Możesz zobaczyć przykładowe dane wzbogacone w kafelku **Podglądu wzbogaconych klientów**. Wybierz opcję **Zobacz więcej** i wybierz kartę **Dane**, aby uzyskać dostęp do szczegółowego widoku każdego z wzbogaconych profilów.

### <a name="overview-card"></a>Karta przeglądowa

Na karcie przeglądowej są szczegółowe informacje dotyczące zakresu wzbogacania. 

* **Firmy przetwarzane i zmieniane**: Liczba profili firm klientów, które zostały pomyślnie wzbogacone.

* **Firmy przetwarzane i niezmienianie**: Liczba profili firm klientów, które zostały rozpoznane, ale nie zostały zmienione. Zazwyczaj zdarza się to, jeśli dane wejściowe są prawidłowe i nie można ich poprawić przez wzbogacenie.

* **Firmy nieprzetworzone i niezmienione**: Liczba profili firm klientów, które nie zostały rozpoznane. Jest tak zwykle w przypadku danych wejściowych, które są nieprawidłowe lub nieobsługiwane przez wzbogacenie.

## <a name="next-steps"></a>Następne kroki

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
