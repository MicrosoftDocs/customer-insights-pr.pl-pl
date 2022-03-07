---
title: Korzystanie z segmentów wyników analiz odbiorców w celu filtrowania raportów wyników analiz interakcji
description: Użyj segmentów wyników analiz odbiorców w interaktywnych analizach danych behawioralnych przechwytywanych przez wyniki analiz interakcji w witrynie internetowej klienta.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: bdd5641bb17384725491f22f70ae967ad90b1696
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461071"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>Korzystanie z segmentów wyników analiz odbiorców w celu filtrowania raportów wyników analiz interakcji

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Za pomocą wyników analiz interakcji można użyć segmentów wyników analiz odbiorców w interaktywnych analizach danych behawioralnych przechwytywanych przez wyniki analiz interakcji w swoich witrynach internetowych.

## <a name="prerequisite"></a>Warunek wstępny

- Środowisko wyników analiz interakcji, w którym dane segmentów wyników analiz odbiorców są połączone ze środowiskiem wyników analiz odbiorców, gdzie segmenty i profile klientów są tworzone. Więcej informacji: [Utwórz łącze między wynikami analiz odbiorców i wynikami analiz interakcji](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>Tworzenie segmentów wyników analiz odbiorców 

> [!IMPORTANT]
> Aby segmenty wyników analiz odbiorców wyświetlały się w wynikach analiz interakcji, należy [Uruchomić scalanie i procesy podrzędne](../audience-insights/merge-entities.md). Procesy podrzędne są ważne, ponieważ generują unikatową tabelę przygotowującą segmenty wyników analiz odbiorcy, które będą udostępniane wynikom analiz interakcji. (Jeśli zaplanowano odświeżanie sytemu, spowoduje to automatyczne uwzględnienie procesów podrzędnych.)

Możesz używać segmentów wyników analiz odbiorcy w gotowych lub utworzonych niestandardowych raportach wyników analiz interakcji. Aby uzyskać więcej informacji, przejdź do [Gotowe raportu profilów](profile-reports.md) i [Tworzenie i edytowanie niestandardowych raportów](custom-reports.md).

**Korzystanie z segmentów wyników analiz odbiorców w raportach wyników analiz interakcji**

1. Na stronie **Obszar roboczy** wybierz pozycję **Dane**, a następnie wybierz kartę **Segmenty**.

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="Wybierz kartę Segmenty.":::

   >[!NOTE]
   > Wybranie segmentu wyników analiz odbiorcy umożliwia przejście do wyników analiz odbiorcy, w których można sprawdzić, w jaki sposób segment został utworzony z punktu widzenia reguł i logiki. Aby uzyskać więcej informacji na temat segmentów wyników analiz odbiorcy, przejdź do strony [Wyświetlanie i tworzenie segmentów](../audience-insights/segments.md).

2. Wybierz gotowy raport lub [utwórz raport niestandardowy](custom-reports.md), a następnie wybierz opcję **Dodaj warunek**. (W tym przykładzie wybraliśmy raport **Wyświetlenia strony**.)

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="Dodaj warunek.":::

3. Wybierz opcję **Filtruj według segmentu**, rozwiń listę **Typ segmentu**, a następnie wybierz opcję **Demograficzne**.

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="Wybierz demograficzny typ segmentu.":::

4. Rozwiń listę **Nazwa segmentu**, a następnie wybierz segment wyników analiz odbiorców.

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text="Wybierz segment.":::

5. Można zastosować co najmniej jeden segment, w tym segmenty behawioralne (wyniki analiz interakcji) oraz segmenty demograficzne (wyniki analiz odbiorców). 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="Raport o wyświetleniach strony ograniczony do segmentów klientów w Stanach Zjednoczonych i strony głównej.":::

Na powyższej ilustracji wybrane zostały segmenty **Klienci ze Stanów Zjednoczonych** i **Strona główna**, co ogranicza raport **Wyświetlenia strony** do wyświetlania tylko tych dwóch segmentów. 


>[!NOTE]
> Możesz używać segmentów wyników analiz odbiorcy do filtrowania gotowych lub niestandardowych raportów i lejków w wynikach analiz interakcji. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]