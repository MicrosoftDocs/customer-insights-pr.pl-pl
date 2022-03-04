---
title: Użycie wymiarów demograficznych do podziału danych behawioralnych (filtrowanych wymiarów)
description: Użyj filtrowanych ujednoliconych wymiarów profilu w celu włączania właściwości profilu klienta wyników analiz odbiorców.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 95395e09bc0ba5ba93138957c62105f31c709e91
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8233060"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>Użycie wymiarów demograficznych do podziału danych behawioralnych

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Używając ujednoliconych wymiarów demograficznych profilu, użytkownicy wyników analiz interakcji mogą uzyskać dostęp do właściwości profilu wyników analiz odbiorcy. Tych właściwości można wtedy użyć w interaktywnych analizach danych behawioralnych, uwzględniając dane przechwytywane przez wyniki analiz interakcji we własnej witrynie internetowej lub aplikacji mobilnej.

>[!NOTE]
> Wgląd w zaangażowanie obejmuje obecnie rozmiary właściwości zdarzenia. Więcej informacji: [Wyświetlanie i tworzenie wymiarów](dimensions.md)

## <a name="prerequisite"></a>Warunek wstępny

- Środowisko wyników analiz interakcji, w którym dane profilu klienta połączone ze środowiskiem wyników analiz odbiorców, gdzie segmenty i profile klientów są tworzone. Więcej informacji: [Utwórz łącze między wynikami analiz odbiorców i wynikami analiz interakcji](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> Po utworzeniu łącza między środowiskami wyników analiz odbiorcy i interakcji można używać tylko danych dotyczących właściwości profilu klienta, które mogą być przydatne jako wymiary w wynikach analiz interakcji. Aby uzyskać więcej informacji, przejdź do artykułu [Włącz wyniki analiz odbiorcy ujednoliconych atrybutów i segmentów profilów](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments).

## <a name="create-a-new-custom-report"></a>Utwórz nowy niestandardowy raport

1. W lewym okienku wybierz opcję **Niestandardowy** > **Nowy raport**, a następnie wybierz żądaną metrykę. (W tym przykładzie wybraliśmy raport **Wyświetlenia strony na godzinę**.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="Wybierz metrykę.":::

2. W edytorze wizualizacji wybierz pozycję **Rozmiary**, a następnie wybierz **Demograficzne** w rozwijanym menu **Typ wymiaru**.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="Wybierz demograficzne.":::

3. Wybierz wymiar **Sygnał.Klient.*xxx***. (W tym przykładzie przedstawiono dane Sygnał.Klient.Kraj.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="Wybierz wymiar.":::
  
## <a name="limitations"></a>Ograniczenia

W tech chwili można użyć tylko wymiarów demograficznych do podziału danych behawioralnych.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
