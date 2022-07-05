---
title: Tworzenie segmentu na podstawie modelu przewidywania
description: Tworzenie segmentów w oparciu o encję wyjściową modelu przewidywania.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: d67594f2467c1a0fde84b1ba0bd1afa4025e7b71
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081378"
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

1. Wybierz pionowy wielokropek obok modelu, który chcesz przejrzeć, i wybierz opcję **Wyświetl**.

1. Na stronie wyników wybierz opcję **Utwórz segment**. Aby uzyskać więcej informacji na temat strony wyników, przejrzyj artykuł o modelu.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Zrzut ekranu strony wyników przewidywania z wyróżnieniem akcji Utwórz segment.":::

1. Tworzenie nowego segmentu w oparciu o encję wyjściową wybranego modelu. Aby uzyskać więcej informacji, zobacz [Tworzenie segmentów i zarządzanie nimi](segments.md).