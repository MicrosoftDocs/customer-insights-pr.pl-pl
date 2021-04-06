---
title: Informacje o segmencie w istniejących segmentach
description: Uzyskiwanie wglądu w istniejące segmenty w celu wyświetlenia różnic i cech wspólnych.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 90ebcaab896c628b04e751ad9857e924749895e7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595347"
---
# <a name="segment-insights-preview"></a>Informacje o segmentach (wersja zapoznawcza)

Odkryj dodatkowe informacje i spostrzeżenia o istniejących segmentach. Dowiedz się, co odróżnia dwa segmenty lub co mają ze sobą wspólnego.

## <a name="segment-overlap"></a>Nakładanie się na siebie segmentów

Analiza nakładania się na siebie segmentów wskazuje, ilu klientów i którzy są wspólni dla dwóch lub więcej segmentów. Na przykład, jak segment często występujących klientów pokrywa się z segmentem, który zawiera klientów, którzy są zadowoleni z usługi lub produktu.
Można również przeanalizować sposób zmiany nakładania się dla poszczególnych atrybutów.

### <a name="run-an-overlap-analysis"></a>Uruchamianie analizy nakładania się

1. Przejdź do **Segmenty**, a następnie wybierz kartę **Insights (wersja zapoznawcza)**.

1. Wybierz **Nowy**, i wybierz opcję **Nakładanie się** w okienku **Wybierz typ szczegółowych informacji**.

1. Wybierz segmenty i wybierz **Dalej**.

1. Można też wybrać jedno lub kilka pól, aby analizować nakładanie się dla każdej możliwej wartości pola i wybrać **Dalej**.

1. W tym celu należy określić nazwę analizy nakładania się, opcjonalną nazwę wyświetlaną, oraz opis.

1. Wybierz **Zapisz**, aby uruchomić analizę. Analiza nakładania się jest gotowa, gdy stan zmieni się z Odświeżanie na Sukces.

### <a name="view-and-optimize-an-overlap-analysis"></a>Wyświetlanie i optymalizowanie analizy nakładania się

Po zakończeniu analizy znajdź szczegółowe informacje w **Segmenty** > **Insights (wersja zapoznawcza)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Informacje szczegółowe dotyczące nakładania się na siebie segmentów":::

Aby wyświetlić wyniki analizy, należy wybrać szczegółowe informacje:

- Liczba członków nakładających się na segmenty wybrane do analizy.
- Liczba członków zawartych w jednym z segmentów, ale nie w pozostałych segmentach.
- Jeśli podczas konfigurowania analizy nakładania się wybrano pola, pozostaną one na odpowiednich kartach. Można użyć listy rozwijanej filtrów w celu wybrania dowolnego poziomu atrybutów, a w tabeli znajdującej się u dołu zostaną wyświetlone odpowiednie dane.

## <a name="segment-differentiators"></a>Wyróżniki segmentów

Elementy odróżniające segmenty pomagają dowiedzieć się, co odróżnia segment od pozostałej części klientów lub innego segmentu. Wystarczy wybrać segment, a system zidentyfikuje atrybuty profilu i miary odróżniające wybrany segment.

### <a name="run-a-differentiator-analysis"></a>Uruchamianie analizy elementów odróżniających

1. Przejdź do **Segmenty**, a następnie wybierz kartę **Insights (wersja zapoznawcza)**.

1. Wybierz **Nowy**, i wybierz opcję **Nakładanie się** w okienku **Wybierz typ szczegółowych informacji**.

1. Wybierz segment, który chcesz przeanalizować jako **Segment podstawowy**, i wybierz **Dalej**.

1. Wybierz **Wszyscy klienci** lub **Segment pomocniczy**, aby porównać z nim segment podstawowy i wybierz **Dalej**.

1. Lub wybierz co najmniej jedno pole, aby skoncentrować analizę na określonych atrybutach i wybierz **Dalej**.

1. W tym celu należy określić nazwę analizy nakładania się, opcjonalną nazwę wyświetlaną, oraz opis.

1. Wybierz **Zapisz**, aby uruchomić analizę. Analiza nakładania się jest gotowa, gdy stan zmieni się z Odświeżanie na Sukces.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Wyświetlanie i optymalizowanie analizy elementów odróżniających

Po zakończeniu analizy znajdź szczegółowe informacje w **Segmenty** > **Insights (wersja zapoznawcza)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Informacje szczegółowe dotyczące elementów odróżniających segmenty":::

Aby wyświetlić wyniki analizy, należy wybrać szczegółowe informacje. Analiza elementów odróżniających zawiera dwie karty. Karta **Atrybuty** wyświetla atrybuty profilu, które są uważane za elementy odróżniające. Karta **Miary** wyświetla elementy odróżniające. Na każdej karcie znajdują się następujące informacje:

- Uporządkowana lista elementów odróżniających, uporządkowana według wyniku różnicy.
- **Wynik różnicy** dla każdego elementu odróżniającego. Wynik różnicy reprezentuje stopień zróżnicowania atrybutów między dwoma segmentami. Im wyższy jest wynik różnicy, tym większe są różnice atrybutów między dwoma segmentami. Wybierz wynik, aby otworzyć okienko **Wynik różnicy** wraz z rozkładami wartości dla tego atrybutu.

## <a name="manage-segment-insights"></a>Zarządzanie szczegółowymi informacjami dotyczącymi segmentów

Na pasku poleceń można korzystać z następujących opcji szczegółowych informacji:

- **Wstecz**, aby wrócić do listy szczegółowych informacji
- **Odśwież**, aby ponownie uruchomić analizę
- **Usuń**, aby usunąć te szczegółowe informacje


[!INCLUDE[footer-include](../includes/footer-banner.md)]