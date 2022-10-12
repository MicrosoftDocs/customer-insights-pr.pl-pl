---
title: Tworzenie segmentu na podstawie modelu przewidywania
description: Tworzenie segmentów w oparciu o encję wyjściową modelu przewidywania.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: ed9c6247a1f9148628dc9b5217484e98a576224e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610433"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>Tworzenie segmentu na podstawie modelu przewidywania (wersja zapoznawcza)

Wyniki przewidywań mogą być czasem stosowane tylko dla podzbioru klientów. Należy zwiększyć personalizację rekomendacji, tworząc segmenty z wyników modeli przewidywania. Można na przykład przekazać konkretne rekomendacje klientom, którzy preferują określony typ usługi.

## <a name="prerequisites"></a>Wymagania wstępne

- Co najmniej [Uprawnienia współautora](permissions.md) w Customer Insights.

- Rekomendacja produktu, rezygnacja z transakcji, rezygnacja z subskrypcji lub model wartości okresu istnienia klientów skonfigurowany w usłudze Customer Insights. Przejrzyj wymagania, aby skonfigurować różne modele:

  - [Model rekomendacji produktów](predict-product-recommendation.md)
  - [Model rezygnacji z subskrypcji](predict-subscription-churn.md)
  - [Model rezygnacji transakcyjnej](predict-transactional-churn.md)
  - [Model wartości okresu istnienia klienta](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>Tworzenie segmentu klienta na podstawie przewidywań

1. Wybierz **Analizy** > **Przewidywania** i wybierz kartę **Moje przewidywania**.

1. Wybierz model, który chcesz przejrzeć, a następnie wybierz pozycję **Wyświetl**.

1. Na stronie wyników wybierz opcję **Utwórz segment**. Aby uzyskać więcej informacji na temat strony wyników, przejrzyj artykuł o modelu.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Zrzut ekranu strony wyników przewidywania z wyróżnieniem akcji Utwórz segment.":::

1. Tworzenie nowego segmentu, używając atrybutów z encji wyjściowej wybranego modelu. Aby uzyskać więcej informacji, zobacz [Tworzenie segmentów i zarządzanie nimi](segments.md).

> [!TIP]
> Na stronie **Segmenty** można także utworzyć segment dla modelu przewidywania modelu, wybierając opcję **Nowy** i wybierając opcję **Utwórz z** >  **Analizy**. Aby uzyskać więcej informacji, zobacz [Tworzenie nowego segmentu za pomocą szybkich segmentów](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
