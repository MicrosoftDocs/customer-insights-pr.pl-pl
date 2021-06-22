---
title: Segmenty w analizie odbiorców
description: Omówienie segmentów oraz sposobu ich tworzenia i zarządzania nimi.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6cb7bd62bf0f61e6dc5811b20e5011e4a086c743
ms.sourcegitcommit: 84283d523a891298fca8aaf629d9f9ab2a1bc067
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/27/2021
ms.locfileid: "6111400"
---
# <a name="segments-overview"></a>Omówienie segmentów

Segmenty umożliwiają grupowanie klientów na podstawie atrybutów demograficznych, transakcyjnych i behawioralnych. W celu realizacji celów biznesowych można korzystać z segmentów w celu ukierunkowania kampanii promocyjnych, działań sprzedaży i akcji obsługi klienta.

Profile klientów zgodne z filtrami definicji segmentu są określane mianem *członków* segmentu. Niektóre [ograniczenia dotyczące usług](service-limits.md) mają zastosowanie.

## <a name="create-a-new-segment"></a>Utwórz nowy segment

Istnieje wiele sposobów utworzenia nowego segmentu: 

- Złożony segment z konstruktorem segmentów: [pusty segment](segment-builder.md#create-a-new-segment)
- Proste segmenty z jednym operatorem: [szybki segment](segment-builder.md#quick-segments)
- Oparty na sztucznej inteligencji sposób na znalezienie podobnych klientów: [podobni klienci](find-similar-customer-segments.md)
- Sugestie oparte na SI, bazujące na miarach lub atrybutach: [sugerowane segmenty w celu usprawnienia działań](suggested-segments.md)
- Sugestie na bazie działań: [sugerowane segmenty oparte na działaniach klienta](suggested-segments-activity.md)

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

Można odświeżyć wszystkie segmenty naraz, wybierając **Odśwież wszystko** na stronie **Segmenty** lub odświeżyć jeden lub wiele segmentów po ich zaznaczeniu i wybraniu **Odśwież** z opcji. Alternatywnie można skonfigurować cykliczne odświeżanie w **Administracja** > **System** > **Harmonogram**.

> [!TIP]
> Istnieje [sześć typów stanu](system.md#status-types) zadań/procesów. Ponadto większość procesów [zależy od innych procesów podrzędnych](system.md#refresh-policies). Istnieje możliwość wybrania stanu procesu w celu wyświetlenia szczegółowych informacji o postępie w całym zadaniu. Po wybraniu opcji **Zobacz szczegółowe informacje** dla jednego z zadań zadania, można znaleźć więcej informacji: czas przetwarzania, Data ostatniego przetwarzania oraz wszystkie błędy i ostrzeżenia skojarzone z zadaniem.

## <a name="export-segments"></a>Eksportowanie segmentów

Segment można wyeksportować ze strony segmentów lub ze [strony eksportowania](export-destinations.md). 

1. Przejdź do strony **Segmenty**.

1. Wybierz **Pokaż więcej [...]** dla segmentu, który chcesz wyeksportować.

1. Wybierz **Zarządzaj eksportami** z listy rozwijanej akacji.

1. Zostanie otwarta strona **Eksportty (wersja zapoznawcza) dla segmentu**. Możesz zobaczyć wszystkie skonfigurowane eksporty pogrupowane według eksportów, które zawierają bieżący segment lub go nie zawierają.

   1. Aby dodać wybrany segment do eksportu, wybierz eksport z listy i wybierz opcję **Dodaj segment**.

   1. Aby utworzyć nowy eksport dla wybranego segmentu, wybierz opcję **Dodaj eksport**. Aby uzyskać więcej informacji o tworzeniu eksportów, zobacz [Konfiguracja nowego eksportu](export-destinations.md#set-up-a-new-export).

1. Wybierz opcję **Wstecz**, aby powrócić do strony głównej segmentów.

## <a name="view-processing-history-and-segment-members"></a>Wyświetlanie historii przetwarzania i członków segmentu

Istnieje możliwość wyświetlenia skonsolidowanych danych o segmencie dzięki przejrzeniu jego szczegółów.

Na stronie **Segmenty** zaznacz segment, który chcesz przejrzeć.

W górnej części strony znajduje się wykres trendów zawierający wizualizacje zmian w licznikach członków. Umieść wskaźnik myszy nad punktami danych, aby wyświetlić liczbę członków w określonym dniu.

Użytkownik może aktualizować horyzont czasowy wizualizacji.

> [!div class="mx-imgBorder"]
> ![Zakres czasu segmentu](media/segment-time-range.png "Zakres czasu segmentu")

W dolnej części znajduje się lista członków segmentu.

> [!NOTE]
> Pola wyświetlane na tej liście są oparte na atrybutach encji segmentu.
>
>Lista jest podglądem pasujących składników segmentu i zawiera pierwsze 100 rekordów segmentu, dzięki czemu można szybko oceniać i przejrzeć w razie potrzeby jego definicje. Aby wyświetlić wszystkie pasujące rekordy, należy [wyeksportować segment](export-destinations.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
