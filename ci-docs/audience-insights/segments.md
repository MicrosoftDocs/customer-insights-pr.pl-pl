---
title: Segmenty w analizie odbiorców
description: Omówienie segmentów oraz sposobu ich tworzenia i zarządzania nimi.
ms.date: 03/30/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: 340a7b7326f5b4a8cbde8683b8d41cb53dc557b0
ms.sourcegitcommit: 0bd5f53e4e7e37359afd087ee16b779a6b3a9183
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/30/2022
ms.locfileid: "8508579"
---
# <a name="segments-overview"></a>Omówienie segmentów

Segmenty umożliwiają grupowanie klientów na podstawie atrybutów demograficznych, transakcyjnych i behawioralnych. W celu realizacji celów biznesowych można korzystać z segmentów w celu ukierunkowania kampanii promocyjnych, działań sprzedaży i akcji obsługi klienta.

Profile klientów zgodne z filtrami definicji segmentu są określane mianem *członków* segmentu. Niektóre [ograniczenia dotyczące usług](/dynamics365/customer-insights/service-limits) mają zastosowanie.

## <a name="create-a-new-segment"></a>Utwórz nowy segment

Istnieje wiele sposobów utworzenia nowego segmentu: 

# <a name="individual-consumers-b-to-c"></a>[Klienci indywidualni (B2C)](#tab/b2c)

- Złożony segment z konstruktorem segmentów: [Tworzenie własnego](segment-builder.md#create-a-new-segment) 
- Proste segmenty z jednym operatorem: [szybki segment](segment-builder.md#quick-segments) 
- Oparty na sztucznej inteligencji sposób na znalezienie podobnych klientów: [podobni klienci](find-similar-customer-segments.md) 
- Sugestie oparte na SI, bazujące na miarach lub atrybutach: [sugerowane segmenty w celu usprawnienia działań](suggested-segments.md) 
- Sugestie na bazie działań: [sugerowane segmenty oparte na działaniach klienta](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[Klienci biznesowi (B2B)](#tab/b2b)

- Złożony segment z konstruktorem segmentów: [Tworzenie własnego](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>Zarządzanie istniejącymi segmentami

Przejdź na stronę **Segmenty**, aby wyświetlić wszystkie zapisane segmenty i zarządzać nimi.

Każdy segment jest reprezentowany przez wiersz zawierający dodatkowe informacje o segmencie.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Wybrany segment z listą rozwijaną opcji i dostępnymi opcjami.":::

Po wybraniu segmentu są dostępne następujące akcje:

- **Wyświetlanie** szczegółowych informacji o segmencie, w tym trendu liczby członków podgląd składników segmentu.
- **Edytuj** segment, aby zmienić jego właściwości.
- **Utwórz duplikat** segmentu. Można od razu edytować jego właściwości lub po prostu zapisać duplikat.
- **Odśwież** segment, aby uwzględnić najnowsze dane.
- **Aktywuj** lub **Dezaktywuj** segment. Segmenty mogą być w dwóch stanach — aktywnym lub nieaktywnym. Te stany są przydatne przy edytowaniu segmentu. W przypadku nieaktywnych segmentów definicja segmentu istnieje, ale nie zawiera jeszcze żadnych klientów. W przypadku aktywowania segmentu jego stan zmieni się z "nieaktywny" na "aktywny" i rozpocznie wyszukiwanie klientów zgodnych z definicją segmentu. Jeśli skonfigurowano [zaplanowane odświeżanie](system.md#schedule-tab), segment nieaktywne mają **Stan** wyświetlany jako **Pominięty**, co oznacza, że nie wystąpiła jeszcze próba odświeżenia. W przypadku aktywowania nieaktywnego segmentu zostanie on odświeżony i będzie uwzględniony w zaplanowanych odświeżeniach.
  Alternatywnie można użyć funkcji **Zaplanuj później** na liście rozwijanej **Aktywuj/Zdezaktywuj**, aby określić przyszłą datę i godzinę aktywacji i dezaktywacji konkretnego segmentu.
- **Zmień nazwę** segmentu.
- **Pobierz** listę członków jako plik .CSV.
- **Zarządzanie eksportami**, aby zobaczyć segmenty związane z eksportem i zarządzać nimi. [Dowiedz się więcej o eksportach.](export-destinations.md)
- **Usuń** segment.

## <a name="refresh-segments"></a>Odśwież segmenty

Można odświeżyć wszystkie segmenty naraz, wybierając **Odśwież wszystko** na stronie **Segmenty** lub odświeżyć jeden lub wiele segmentów po ich zaznaczeniu i wybraniu **Odśwież** z opcji. Alternatywnie można skonfigurować cykliczne odświeżanie w **Administracja** > **System** > **Harmonogram**. Podczas konfigurowania odświeżania cyklicznego mają zastosowanie następujące reguły:
- Wszystkie segmenty z typem **Dynamiczny** lub **Rozszerzenie** zostaną automatycznie odświeżone w ustawionym rytmie. Po zakończeniu odświeżania **Stan** wskazuje, czy podczas odświeżania segmentu wystąpiły jakieś problemy. **Ostatnio odświeżono** wskazuje czas ostatniego udanego odświeżenia. Jeśli wystąpi błąd, wybierz błąd, aby wyświetlić szczegółowe informacje o tym, co się stało.
- Segmenty o typie **Statyczny** *nie będą* odświeżane automatycznie. **Ostatnio odświeżono** wskazuje znacznik czasu ostatniego uruchomienia lub ręcznego odświeżania segmentów statycznych.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="export-segments"></a>Eksportowanie segmentów

Segment można wyeksportować ze strony segmentów lub ze [strony eksportowania](export-destinations.md). 

1. Przejdź do strony **Segmenty**.

1. Wybierz **Pokaż więcej [...]** dla segmentu, który chcesz wyeksportować.

1. Z listy rozwijanej akcji wybierz opcję **Zarządzanie eksportami**.

1. Zostanie otwarta strona **Eksportty (wersja zapoznawcza) dla segmentu**. Można wyświetlić wszystkie skonfigurowane eksporty pogrupowane według tego, czy zawierają bieżący segment, czy nie.

   1. Aby dodać wybrany segment do eksportu, **edytuj** odpowiedni eksport, aby wybrać odpowiedni segment, a następnie zapisz. W środowiskach dla poszczególnych klientów można zamiast tego wybrać eksport z listy i wybrać opcję **Dodaj segment**, aby osiągnąć ten sam efekt.

   1. Aby utworzyć nowy eksport dla wybranego segmentu, wybierz opcję **Dodaj eksport**. Aby uzyskać więcej informacji o tworzeniu eksportów, zobacz [Konfiguracja nowego eksportu](export-destinations.md#set-up-a-new-export).

1. Wybierz opcję **Wstecz**, aby powrócić do strony głównej segmentów.

## <a name="view-processing-history-and-segment-members"></a>Wyświetlanie historii przetwarzania i członków segmentu

Istnieje możliwość wyświetlenia skonsolidowanych danych o segmencie dzięki przejrzeniu jego szczegółów.

Na stronie **Segmenty** zaznacz segment, który chcesz przejrzeć.

W górnej części strony znajduje się wykres trendów zawierający wizualizacje zmian w licznikach członków. Umieść wskaźnik myszy nad punktami danych, aby wyświetlić liczbę członków w określonym dniu.

Użytkownik może aktualizować horyzont czasowy wizualizacji.

> [!div class="mx-imgBorder"]
> ![Zakres czasu segmentu.](media/segment-time-range.png "Zakres czasu segmentu")

W dolnej części znajduje się lista członków segmentu.

> [!NOTE]
> Pola wyświetlane na tej liście są oparte na atrybutach encji segmentu.
>
>Lista jest podglądem pasujących składników segmentu i zawiera pierwsze 100 rekordów segmentu, dzięki czemu można szybko oceniać i przejrzeć w razie potrzeby jego definicje. Aby wyświetlić wszystkie pasujące rekordy, należy [wyeksportować segment](export-destinations.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
