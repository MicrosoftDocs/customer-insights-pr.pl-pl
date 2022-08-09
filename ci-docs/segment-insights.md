---
title: Informacje o segmentach (wersja zapoznawcza)
description: Uzyskiwanie wglądu w istniejące segmenty w celu wyświetlenia różnic i cech wspólnych.
ms.date: 06/10/2020
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-segment-insights
- customerInsights
ms.openlocfilehash: ccb33594a3a92e87d307f3300c77772ef8b4a82f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171016"
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

1. Po zakończeniu analizy znajdź szczegółowe informacje w **Segmenty** > **Insights (wersja zapoznawcza)**.

   :::image type="content" source="media/segment-overlap.png" alt-text="Informacje szczegółowe dotyczące nakładania się na siebie segmentów.":::

1. Aby wyświetlić wyniki analizy, należy wybrać szczegółowe informacje:

   - Liczba członków nakładających się na segmenty wybrane do analizy.
   - Liczba członków zawartych w jednym z segmentów, ale nie w pozostałych segmentach.
   - Jeśli podczas konfigurowania analizy nakładania się wybrano pola, pozostaną one na odpowiednich kartach. Możesz użyć rozwijanego filtra, aby wybrać dowolny interesujący Cię poziom atrybutu, a tabela na dole wyświetli odpowiednie dane.

## <a name="segment-differentiators"></a>Wyróżniki segmentów

Elementy odróżniające segmenty pomagają dowiedzieć się, co odróżnia segment od pozostałej części klientów lub innego segmentu. Wybierz segment, a system zidentyfikuje atrybuty profilu i miary, które wyróżniają wybrany segment.

### <a name="run-a-differentiator-analysis"></a>Uruchamianie analizy elementów odróżniających

1. Przejdź do **Segmenty**, a następnie wybierz kartę **Insights (wersja zapoznawcza)**.

1. Wybierz **Nowy**, i wybierz opcję **Wyróżniki** w okienku **Wybierz typ szczegółowych informacji**.

1. Wybierz segment, który chcesz przeanalizować jako **Segment podstawowy**, i wybierz **Dalej**.

1. Wybierz **Wszyscy klienci** lub **Segment pomocniczy**, aby porównać z nim segment podstawowy i wybierz **Dalej**.

1. Lub wybierz co najmniej jedno pole, aby skoncentrować analizę na określonych atrybutach i wybierz **Dalej**.

1. Podaj nazwę analizy wyróżników, opcjonalną nazwę wyświetlaną i opis.

1. Wybierz **Zapisz**, aby uruchomić analizę. Analiza wyróżników się jest gotowa, gdy stan zmieni się z Odświeżanie na Sukces.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Wyświetlanie i optymalizowanie analizy elementów odróżniających

1. Po zakończeniu analizy przejdź do **Segmenty** > **Insights (wersja zapoznawcza)**.

   :::image type="content" source="media/segment-differentiators.png" alt-text="Informacje szczegółowe dotyczące elementów odróżniających segmenty.":::

1. Aby wyświetlić wyniki analizy, należy wybrać szczegółowe informacje. Analiza elementów odróżniających zawiera dwie karty. Karta **Atrybuty** wyświetla atrybuty profilu, które są uważane za elementy odróżniające. Karta **Miary** wyświetla elementy odróżniające. Na każdej karcie znajdują się następujące informacje:

   - Uporządkowana lista elementów odróżniających, uporządkowana według wyniku różnicy.
   - **Wynik różnicy** dla każdego elementu odróżniającego. Wynik różnicy reprezentuje stopień zróżnicowania atrybutów między dwoma segmentami. Im wyższy jest wynik różnicy, tym większe są różnice atrybutów między dwoma segmentami. Wybierz wynik, aby otworzyć okienko **Wynik różnicy** wraz z rozkładami wartości dla tego atrybutu.

## <a name="manage-segment-insights"></a>Zarządzanie szczegółowymi informacjami dotyczącymi segmentów

Przejdź do widoku **Segmenty** > **insights (wersja zapoznawcza),** aby wyświetlić informacje na temat segmentów i zarządzać nimi. Wybierz statystyki segmentów, aby wyświetlić dostępne działania.

- **Wyświetlanie** analizy analizy
- **Edytuj** szczegółowe informacje, aby zmienić jej właściwości
- **Odśwież** szczegółowe informacje, aby ponownie uruchomić analizę
- **Zmień nazwę** szczegółowych informacji
- **Usuń** szczegółowe informacje

[!INCLUDE [footer-include](includes/footer-banner.md)]
