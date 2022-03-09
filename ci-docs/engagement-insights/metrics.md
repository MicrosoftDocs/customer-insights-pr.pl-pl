---
title: Wyświetlanie i tworzenie metryk
description: Jak tworzyć, edytować i usuwać metryki.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7e8c96f38af74f25080a40fd92e73f05c71320a8
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229829"
---
# <a name="view-and-create-metrics"></a>Wyświetlanie i tworzenie metryk

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Metryki pomagają zrozumieć zachowanie osób odwiedzających tę stronę. Agregują one właściwości zdarzeń i mierzą statystyki oraz wydajność Twoich właściwości internetowych.  

Załóżmy, że w witrynie internetowej prowadzisz promocję marketingową. Możesz wykorzystać metryki do śledzenia liczby unikalnych odwiedzających lub użytkowników, którzy weszli na Twoją stronę w czasie trwania promocji. Analizowanie metryk pomaga lepiej zrozumieć odbiorców. Połączenie metryk z [wymiarów](dimensions.md) [raportu niestandardowego](custom-reports.md) pozwala na określenie zachowań w celu zrozumienia użytkowników. Na przykład, możesz podzielić odwiedzających na nowych i powracających, aby zidentyfikować różnice w zainteresowaniach i intencjach pomiędzy tymi grupami.

## <a name="view-metrics"></a>Wyświetlanie metryk

Wyniki analiz interakcji obejmują powszechnie stosowane agregacje właściwości zdarzeń jako metryki systemowe: 

- Odwiedzający
- Wizyty
- Wyświetlenia strony
- Kliknięcia

Te metryki systemowe są oparte na istniejących właściwościach zdarzeń w zdarzeniach podstawowych.

1. Przejdź do **Dane** lewym okienku nawigacji. 
1. Wybierz kartę **Metryki**, aby wyświetlić listę wszystkich metryk w obszarze roboczym. 
   > [!NOTE]
   > Metryki generowane przez system są tylko do odczytu. Nie można ich edytować ani usuwać. Możliwe jest tworzenie i edytowanie wyłącznie metryk niestandardowych.

## <a name="create-a-metric"></a>Utwórz metrykę

Metryki mogą tworzyć administratorzy środowiska i obszaru roboczego. Właściwości zdarzenia muszą zostać wysłane do obszaru roboczego przed utworzeniem metryki. Metryki można tworzyć na podstawie właściwości zdarzenia wysyłanych według zdarzeń podstawowych lub można używać zestawu SDK sieci Web do wysyłania [niestandardowych właściwości zdarzenia](advanced-SDK-implementation.md).

1. Przejdź do **Dane** > **Metryki**.
1. Wybierz opcję **Nowa metryka**, aby otworzyć sesje dialogowe **Biblioteka zasobów** i **Nowa metryka bez tytułu**.

   :::image type="content" source="media/new-metric.png" alt-text="Dodawanie metryk do zdarzenia.":::

1. W sesji dialogowej **Nowa metryka bez tytułu** wybierz listę rozwijaną **Format** i wybierz typ danych **Liczba całkowita** lub **Double**. Liczba całkowita. W opcji Double można wybrać jedno i trzy miejsca dziesiętne.

   :::image type="content" source="media/create-new-metric.png" alt-text="Tworzenie nowej metryki.":::
   
5. W okienku **Biblioteka zasobów** znajdź właściwość zdarzenia, która ma być bazą metryki.
6. Wybierz **znak plus (+)** obok właściwości, aby użyć go w formule. Możesz utworzyć formułę tylko na podstawie jednej właściwości. 
7. Wybierz jedną z poniższych funkcji agregacji. 

   - Suma: łączna wartość wszystkich wartości 
   - Wartość średnia: wartość średnia wszystkich wartości
   - Liczba: łączna liczba wartości
   - Liczność unikatowych wartości: łączna liczba unikatowych wartości

   Po zdefiniowaniu metryki wyświetlany jest podgląd aktywności dla metryki z ostatniej godziny.

1. Wybierz pozycję **Zapisz**. 
1. Wprowadź nazwę metryki, a następnie wybierz pozycję **Zapisz**.

Zanim będzie można wykorzystać metrykę do [tworzenia raportów niestandardowych](custom-reports.md), może minąć nawet minuta.

## <a name="edit-a-metric"></a>Edytowanie metryki

Można edytować tylko metryki niestandardowe.

1. Przejdź do **Dane** > **Metryki**.
1. Wybierz metrykę z listy.
1. Zmienianie definicji metryki
1. Wybierz pozycję **Zapisz**.

## <a name="change-the-name-of-a-metric"></a>Zmień nazwę metryki

Można zmienić tylko nazwę metryk niestandardowych.

1. Przejdź do **Dane** > **Metryki**.
1. Wybierz **Więcej [...]** dla metryki i wybierz opcję **Edytuj nazwę**.
1. Zmień nazwę. 
1. Wybierz **Zmień nazwę**.

## <a name="delete-a-metric"></a>Usuwanie metryki

Można usuwać tylko metryki niestandardowe.

1. Przejdź do **Dane** > **Metryki**.
1. Wybierz **Więcej [...]** dla metryki i wybierz opcję **Usuń**.

   :::image type="content" source="media/delete-metric.png" alt-text="Usuwanie metryk do zdarzenia.":::

1. Aby potwierdzić usunięcie, wybierz opcję **Usuń**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
