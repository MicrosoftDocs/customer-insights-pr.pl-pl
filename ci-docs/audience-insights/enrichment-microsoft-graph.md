---
title: Wzbogacanie profili klientów za pomocą Microsoft Graph
description: Użyj danych własności z programu Microsoft Graph, aby wzbogacić dane klientów z koligacjami marki i zainteresowań.
ms.date: 09/28/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4f93a2337815f76b98185ecb3755e08443031748
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406560"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Wzbogać profile klientów dzięki koligacjom marki i zainteresowań (wersja zapoznawcza)

Użyj danych własności z programu Microsoft Graph, aby wzbogacić dane klientów z koligacjami marki i zainteresowań. Koligacje te są określane na podstawie danych pochodzących od osób o cechach demograficznych podobnych do cech klientów. Informacje te ułatwiają zrozumienie i segmentację klientów na podstawie ich koligacji z określonymi markami i zainteresowaniami.

W statystykach odbiorców przejdź do **Dane** > **Wzbogacanie** do [konfiguruj i wyświetl wzbogacenia](enrichment-hub.md).

Aby skonfigurować wzbogacanie koligacji marki, przejdź do karty **Odkryj** i wybierz **Wzbogacaj dane** na kafelku **Marki**.

Aby skonfigurować wzbogacanie koligacji zainteresowań, przejdź do karty **Odkryj** i wybierz **Wzbogacaj dane** na kafelku **Zainteresowania**.

   > [!div class="mx-imgBorder"]
   > ![Kafelki Marki i Zainteresowania](media/BrandsInterest-tile-Hub.png "Kafelki Marki i Zainteresowania")

## <a name="about-microsoft-graph"></a>Informacje na temat Microsoft Graph

Korzystamy z danych wyszukiwania online z Microsoft Graph, aby znaleźć koligacje marki i zainteresowania między różnymi segmentami demograficznymi (określonymi według wieku, płci lub lokalizacji). Wielkość wyszukiwania online dla marki lub zainteresowań określa stopień sympatii ze strony segmentu demograficznego, w porównaniu z innymi segmentami, dla tej marki lub zainteresowania.

[Informacje na temat Microsoft Graph](https://docs.microsoft.com/graph/overview).

## <a name="affinity-score-and-confidence"></a>Wyniki koligacji i wiarygodność

**Wynik koligacji** jest obliczany w skali 100-stopniowej, gdzie 100 reprezentuje segment, który ma najwyższą koligację dla danej marki lub zainteresowania.

**Zaufanie koligacji** jest obliczane na skali 100-punktowej. Wskazuje on poziom ufności systemu, w to, że segment ma koligację dla konkretnej marki lub zainteresowania. Poziom ufności jest określany na podstawie rozmiaru segmentu oraz stopnia szczegółowości segmentu. Wielkość segmentu jest określona przez ilość danych dla danego segmentu. Stopień szczegółowości segmentu jest określany przez liczbę atrybutów (wiek, płeć, lokalizacja) dostępnych w profilu.

Nie normalizujemy wyników zestawu danych. W związku z tym użytkownik może nie widzieć wszystkich możliwych wartości wyników koligacji dla zestawu danych. Na przykład w danych nie może istnieć wzbogacony profil klienta z wynikiem koligacji 100. Jest to możliwe jeśli żadni klienci nie istnieją w segmencie demograficznym, który otrzymał 100 dla danej marki lub zainteresowania.

> [!TIP]
> Podczas [tworzenia segmentów](segments.md) przy użyciu wyników koligacji należy przejrzeć zestawienie wyników koligacji dla swojego zestawu danych przed podjęciem decyzji na temat odpowiednich progów punktów. Na przykład wynik koligacji równy 10 można uznać za znaczący w zestawie danych, który ma najwyższy wynik koligacji o wartości 25 dla danej marki lub zainteresowania.

## <a name="supported-countriesregions"></a>Obsługiwane kraje/regiony

Obecnie obsługujemy następujące opcje kraju/regionu: Australia, Kanada (angielski), Francja, Niemcy, Zjednoczone Królestwo lub Stany Zjednoczone (angielski).

Aby wybrać kraj, należy otworzyć **Wzbogacenie marek** lub **Wzbogacenie zainteresowań** a następnie wybrać **Zmień** obok **Kraj/region**. W okienku **Ustawienia kraju/regionu** wybierz jedną z opcji i wybierz **Zastosuj**.

### <a name="implications-related-to-country-selection"></a>Implikacje dotyczące wyboru kraju

- Kiedy [wybierasz własne marki](#define-your-brands-or-interests), zapewnimy sugestie na podstawie wybranego kraju/regionu.

- Podczas [wybierania branży](#define-your-brands-or-interests) będziemy identyfikować najpopularniejsze marki lub zainteresowania oparte na wybranym kraju/regionie.

- Kiedy [mapujesz pola](#map-your-fields), jeśli pole Kraj/region nie jest zamapowane, użyjemy danych z Microsoft Graph w wybranym kraju/regionie, aby wzbogacić profile klientów. Użyjemy tego wyboru również do wzbogacenia profili klientów, w których nie są dostępne dane o kraju/regionie.

- Kiedy [wzbogacasz profile](#refresh-enrichment), wzbogacimy wszystkie profile klientów, dla których dysponujemy danymi Microsoft Graph na wybrane marki i zainteresowania, w tym profilami, które nie są dostępne w wybranym kraju/regionie. Jeśli na przykład wybrano Niemcy, wzbogacimy profile zlokalizowane w Stanach Zjednoczonych, jeśli posiadamy dane Microsoft Graph dostępne dla wybranych marek i zainteresowań w USA.

## <a name="configure-enrichment"></a>Konfigurowanie wzbogacenia

Konfigurowanie wzbogacania marek lub zainteresowań składa się z dwóch kroków:

### <a name="define-your-brands-or-interests"></a>Zdefiniuj swoje marki i zainteresowania

Wybierz jedną z następujących opcji:

- **Branża**: System identyfikuje najlepsze marki lub zainteresowania istotne dla Twojej branży i wzmacnia nimi dane klientów.
- **Wybierz własne**: Wybierz maksymalnie pięć elementów z listy marek lub zainteresowań, które są najbardziej interesujące dla Twojej organizacji.

Aby dodać markę lub zainteresowanie, wprowadź ją w obszarze wprowadzania, aby uzyskać sugestie na podstawie pasujących terminów. Jeśli nie ukazujemy szukanej marki lub zainteresowania, wyślij nam opinię przy użyciu łącza **Sugeruj**.

### <a name="map-your-fields"></a>Zamapuj swoje pola

Mapowanie pól ze zunifikowanej encji klienta na co najmniej dwa atrybuty w celu zdefiniowania segmentu demograficznego, który ma zostać użyty do wzbogacenia danych klienta. Wybierz **Edytuj**, aby zdefiniować mapowanie pól i wybierz **Zastosuj** po zakończeniu. Wybierz **Zapisz**, aby zakończyć mapowanie pola.

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
