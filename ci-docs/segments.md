---
title: Omówienie segmentów
description: Omówienie segmentów oraz sposobu ich tworzenia i zarządzania nimi.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: 195a7c733f047c24f9f47a151c1cb623fe34d055
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246306"
---
# <a name="segments-overview"></a>Omówienie segmentów

Segmenty umożliwiają grupowanie klientów na podstawie atrybutów demograficznych, transakcyjnych i behawioralnych. W celu realizacji celów biznesowych można korzystać z segmentów w celu ukierunkowania kampanii promocyjnych, działań sprzedaży i akcji obsługi klienta.

Profile klientów zgodne z filtrami definicji segmentu są określane mianem *członków* segmentu. Niektóre [ograniczenia dotyczące usług](/dynamics365/customer-insights/service-limits) mają zastosowanie.

## <a name="create-a-segment"></a>Utwórz segment

Wybierz sposób tworzenia segmentu na podstawie wartości odbiorcy.

# <a name="individual-consumers-b-to-c"></a>[Klienci indywidualni (B2C)](#tab/b2c)

- Złożone segmenty z budowniczym segmentów: [Tworzenie własnego](segment-builder.md)
- Proste segmenty z jednym operatorem: [szybki segment](segment-quick.md)
- Oparty na sztucznej inteligencji sposób na znalezienie podobnych klientów: [podobni klienci](find-similar-customer-segments.md)
- Sugestie oparte na SI, bazujące na miarach lub atrybutach: [Sugerowane segmenty na podstawie miar](suggested-segments.md)
- Sugestie na bazie działań: [sugerowane segmenty oparte na działaniach klienta](suggested-segments-activity.md)

# <a name="business-accounts-b-to-b"></a>[Klienci biznesowi (B2B)](#tab/b2b)

- Proste lub złożone segmenty z budowniczym segmentów: [Tworzenie własnego](segment-builder.md)

---

## <a name="manage-existing-segments"></a>Zarządzanie istniejącymi segmentami

Przejdź na stronę **Segmenty**, aby wyświetlić utworzone segmenty, ich stan, liczbę członków i czas ostatniego odświeżania danych. Możesz posortować listę segmentów według dowolnej kolumny lub skorzystać z pola wyszukiwania, aby znaleźć segment, którym chcesz zarządzać.

Wybierz segment, aby wyświetlić dostępne działania.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Wybrany segment z listą rozwijaną opcji i dostępnymi opcjami." lightbox="media/segments-selected-segment.png":::

- [**Wyświetlanie**](#view-segment-details) szczegółowych informacji o segmencie, w tym trendu liczby członków i podgląd składników segmentu.
- **Pobierz** listę członków jako plik .CSV.
- **Edytuj** segment, aby zmienić jego właściwości.
- **Utwórz duplikat** segmentu. Można od razu edytować właściwości tej aplikacji lub zapisać duplikat.
- [**Odśwież**](#refresh-segments) segment, aby uwzględnić najnowsze dane.
- **Aktywuj** lub **Dezaktywuj** segment. Nieaktywne segmenty nie zostaną odświeżone podczas [zaplanowanego odświeżenia](schedule-refresh.md), a segment nieaktywne mają **Stan** wyświetlany jako **Pominięty**, co oznacza, że nie wystąpiła jeszcze próba odświeżenia. Aktywne segmenty są odświeżane w zależności od ich typu: statycznego lub dynamicznego.
- **Jako statyczny** lub **Jako dynamiczny** należy dynamiczną typ segmentu. Segmenty statyczne należy odświeżać ręcznie. Segmenty dynamiczne są automatycznie odświeżane podczas odświeżania systemu.
- [**Znajdź podobnych klientów**](find-similar-customer-segments.md) z danego segmentu.
- **Zmień nazwę** segmentu.
- **Otaguj**, aby [zarządzać etykietami](work-with-tags-columns.md#manage-tags) dla segmentu.
- [**Zarządzanie eksportami**](#export-segments), aby zobaczyć segmenty związane z eksportem i zarządzać nimi. [Dowiedz się więcej o eksportach.](export-destinations.md)
- **Usuń** segment.
- **Kolumny** w [celu dostosowania wyświetlanych kolumn](work-with-tags-columns.md#customize-columns).
- **Filtruj**, aby [filtrować etykiety](work-with-tags-columns.md#filter-on-tags).
- **Wyszukaj nazwę**, aby wyszukać według nazwy segmentu.

## <a name="view-segment-details"></a>Wyświetlanie szczegółowych informacji o segmencie

Na stronie **Segmenty** wybierz segment, aby wyświetlić historię przetwarzania oraz członków segmentu.

W górnej części strony znajduje się wykres trendów zawierający wizualizacje zmian w licznikach członków. Umieść wskaźnik myszy nad punktami danych, aby wyświetlić liczbę członków w określonym dniu. Zmień ramy czasowe wizualizacji.

:::image type="content" source="media/segment-time-range.png" alt-text="Zakres czasu segmentu.":::

W dolnej części znajduje się lista członków segmentu.

> [!NOTE]
> Pola wyświetlane na tej liście są oparte na atrybutach encji segmentu.
>
>Lista jest podglądem pasujących składników segmentu i zawiera pierwsze 100 rekordów segmentu, dzięki czemu można szybko oceniać i przejrzeć w razie potrzeby jego definicje. Aby wyświetlić wszystkie pasujące rekordy, [wyeksportuj segment](export-destinations.md).

## <a name="refresh-segments"></a>Odśwież segmenty

Segmenty mogą być odświeżane w harmonogramie automatycznym lub ręcznie odświeżane na żądanie. Aby ręcznie odświeżyć jeden lub więcej segmentów, zaznacz je i wybierz **Odśwież**.

Aby [zaplanować automatyczne odświeżanie](schedule-refresh.md), przejdź do strony **Administrator** > **System** > **Harmonogram**. Obowiązują następujące zasady:

- Wszystkie segmenty z typem **Dynamiczny** lub **Rozszerzenie** zostaną automatycznie odświeżone w ustawionym rytmie. Po zakończeniu odświeżania **Stan** wskazuje, czy podczas odświeżania segmentu wystąpiły jakiekolwiek problemy. **Ostatnio odświeżono** wskazuje czas ostatniego udanego odświeżenia. Jeśli wystąpi błąd, wybierz błąd, aby wyświetlić szczegółowe informacje o tym, co się stało.
- Segmenty o typie **Statyczny** *nie będą* odświeżane automatycznie. **Ostatnio odświeżono** wskazuje znacznik czasu ostatniego uruchomienia lub ręcznego odświeżania segmentów statycznych.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Eksportowanie segmentów

Eksportuj segmenty do innych aplikacji, aby dalej wykorzystywać dane. Segment można wyeksportować ze strony segmentów lub ze [strony eksportowania](export-destinations.md).

1. Na stronie **Segmenty** zaznacz segment, który chcesz przejrzeć.

1. Wybierz **Zarządzaj eksportem**. Zostanie otwarta strona **Eksportty (wersja zapoznawcza) dla segmentu**. Wyświetl wszystkie skonfigurowane eksporty pogrupowane według tego, czy zawierają bieżący segment, czy nie.

   1. Aby dodać wybrany segment do eksportu, **edytuj** odpowiedni eksport, aby wybrać odpowiedni segment, a następnie zapisz. W środowiskach dla poszczególnych klientów można wybrać eksport z listy i wybrać opcję **Dodaj segment**, aby osiągnąć ten sam efekt.

   1. Aby utworzyć nowy eksport dla wybranego segmentu, wybierz opcję **Dodaj eksport**. Aby uzyskać więcej informacji o tworzeniu eksportów, zobacz [Konfiguracja nowego eksportu](export-destinations.md#set-up-a-new-export).

1. Wybierz opcję **Wstecz**, aby powrócić do strony głównej segmentów.

## <a name="track-usage-of-a-segment"></a>Śledzenie użycia segmentu

Jeśli używasz segmentów w aplikacjach, które są oparte na tej samej organizacji Microsoft Dataverse, która jest połączona z Customer Insights, możesz śledzić użycie segmentu. W [przypadku segmentów usługi Customer Insights używanych w Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile) system informuje o poszczególnych segmentach.

Podczas edytowania segmentu, który jest używany w środowisku Customer Insights lub podczas podróży klienta w Marketing, baner w [Konstruktorze segmentów](segment-builder.md) informuje o zależnościach. Szczegóły zależności można sprawdzić bezpośrednio na bannerze lub wybierając opcję **Użycie** w konstruktorze segmentów.

W **okienku użycia segmentu** są dostępne szczegółowe informacje dotyczące korzystania z tego segmentu w aplikacjach opartych na Dataverse. W przypadku segmentów używanych w miejscu klientów można znaleźć łącze do inspekcji fragmentów danych w programie Marketing, w którym jest używany ten segment. Jeśli masz uprawnienia dostępu do aplikacji Marketing, zobacz tam więcej szczegółów.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Okienko boczne ze szczegółami użycia segmentu w konstruktorze segmentów.":::

Podczas próby usunięcia tego segmentu system informuje o śledzenia segmentu. Jeśli segment, który chcesz usunąć, jest używany w procesie pozyskiwania klientów w marketingu, proces ten zostanie zatrzymany dla wszystkich użytkowników w segmencie. Jeśli materiały sprzedażowe są częścią kampanii marketingowej, usunięcie będzie miało wpływ na samą kampanię. Jednak mimo ostrzeżeń nadal można usunąć ten segment.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Okno dialogowe potwierdzenia usuwania segmentu, gdy segment jest używany w aplikacji Dataverse.":::

### <a name="supported-apps"></a>Obsługiwane interfejsy API

Użycie jest obecnie śledzone w następujących aplikacjach opartych na następujących Dataverse:

- [Procesy pozyskiwania klientów w Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

[!INCLUDE [footer-include](includes/footer-banner.md)]
