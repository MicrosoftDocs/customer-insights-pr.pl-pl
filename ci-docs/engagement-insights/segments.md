---
title: Wyświetlanie i tworzenie segmentów
description: Jak tworzyć, edytować i usuwać segmenty oraz gdzie ich używać.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: cedcd58373428dd35ba29ce8fdd00007257f8fa59b0d25bc584b4e832df13604
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036161"
---
# <a name="view-and-create-segments"></a>Wyświetlanie i tworzenie segmentów

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Segmenty pozwalają na identyfikację podzbiorów odwiedzających na podstawie cech lub interakcji z witryną. Segmenty umożliwiają stosowanie filtrów i analizę tych podzbioru. Analiza może pomóc w badaniu i reagowaniu na trendy w Twojej firmie. 

:::image type="content" source="media/segments-page.png" alt-text="Zrzut ekranu aplikacji Wyniki analiz interakcji pokazujący listę istniejących segmentów w obszarze roboczym.":::

## <a name="view-segments"></a>Wyświetl segmenty

1. Przejdź do **Dane** lewym okienku nawigacji. 

1. Wybierz kartę **Segmenty**, aby wyświetlić listę wszystkich segmentów w obszarze roboczym. 

## <a name="create-a-segment"></a>Utwórz segment

Segmenty składają się z reguł i warunków połączonych z operatorami logicznymi. Warunki mają zastosowanie filtrów do wybranego wymiaru. Każdy segment może mieć do pięciu wymiarów.

Poniższy przykład przedstawia segment z dwoma warunkami w jednej regule. Filtruje on wszystkie zdarzenia na stronach internetowych, gdzie przeglądarką jest Chrome, a systemami operacyjnymi są iOS lub Android.

:::image type="content" source="media/segment-sample.png" alt-text="Przykładowe segmenty z dwoma warunkami w regule do filtrowania zdarzeń na stronie internetowej.":::

W tej sekcji opisano sposób tworzenia *pustego segmentu* od podstaw.

1. Przejdź do **Dane** > **Segmenty**.

1. Wybierz opcję **Nowy segment**.

1. W **Bibliotece zasobów** wybierz atrybut, według którego ma być filtrowany. Obecnie segmenty można tworzyć tylko na podstawie rozmiarów.

1. Wybierz operatora i wartość dla zaznaczonego atrybutu. Obsługiwane są następujące operacje.
   - **jest**: wymaga dokładnego dopasowania, aby uwzględniało wartości. Używa wartości **równa się** dla jednej wartości lub **dowolne z**, aby objąć wiele wartości.
   - **nie jest**: wymaga dokładnego dopasowania w celu wykluczenia wartości. Używa wartości **równa się** dla jednej wartości lub **dowolne z**, aby objąć wiele wartości.
   - **zaczyna się od**: ciąg, od którego zaczynają się pasujące wartości.
   - **kończy się na**: ciąg, na którym kończą się pasujące wartości.
   - **zawiera**: ciąg zawierający pasujące wartości.

1. Aby dodać do grupy więcej warunków, można użyć dwóch operatorów logicznych. Atrybuty rzutowane są uwzględniane podczas używania operatorów zestawów.
   - **AND** operator: oba warunki muszą być spełnione w procesie segmentacji. Ta opcja jest najbardziej przydatna podczas definiowania warunków między różnymi encjami.
   - **OR** operator: jeden z warunków musi zostać osiągnięty jako część procesu segmentacji. Ta opcja jest najbardziej przydatna podczas definiowania wielu warunków dla tej samej encji.

1. Wybierz **Zapisz** i wprowadź nazwę segmentu. 

Segment zostanie wyświetlony na stronie Segmenty i będzie można go zastosować do wszystkich raportów i lejków w obszarze roboczym.

## <a name="use-a-segment-in-a-report-or-funnel"></a>Korzystanie z segmentu w raporcie lub lejku

Możesz zastosować segmenty do raportu lub lejka, aby filtrować je w oparciu o warunki określone w segmencie. Nie można jednak stosować segmentów do raportu użycia w czasie rzeczywistym.

:::image type="content" source="media/segment-reports-filter.png" alt-text="Raport widoków strony z rozwiniętą listą rozwijaną, na której można wybrać segmenty, które mają być stosowane.":::

Aby zastosować segment, otwórz raport lub lejek. Wybierz opcję **Dodaj warunek** i wybierz pozycję **Filtruj według segmentu**. Wybierz z listy segment, który chcesz zastosować. Segment zostanie zastosowany w raporcie. Jeśli wykres nie obsługuje segmentu, jest to błąd.
 
Raport lub lejek można *zastosować do maksymalnie trzech segmentów*.

## <a name="edit-a-segment"></a>Edytuj segment

1. Przejdź do **Dane** > **Segmenty**.
1. Wybierz segment z listy, aby go otworzyć. 
1. Zmień lub dodaj wartości zgodnie z potrzebami.
1. Wybierz pozycję **Zapisz**, aby zastosować zmiany.

## <a name="change-the-name-of-a-segment"></a>Zmień nazwę segmentu

1. Przejdź do **Dane** > **Segmenty**.
1. Z listy segmentów wybierz pozycję **Więcej... [...]**. 
1. Z listy rozwijanej wybierz pozycję **Edytuj nazwę**.
1. Wprowadź nową nazwę i wybierz **Zmień nazwę**.

## <a name="delete-a-segment"></a>Usuń segment

1. Przejdź do **Dane** > **Segmenty**.
1. Z listy segmentów wybierz pozycję **Więcej... [...]**. 
1. Z listy rozwijanej wybierz pozycję **Usuń**.
1. Wybierz **Usuń**, aby potwierdzić.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
