---
title: Segmenty oparte na danych wyjściowych przewidywania
description: Tworzenie segmentów w oparciu o encję wyjściową modelu przewidywania.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741442"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="1dd05-103">Tworzenie segmentu na podstawie modelu przewidywania (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="1dd05-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="1dd05-104">Wyniki przewidywań mogą być czasem stosowane tylko dla podzbioru klientów.</span><span class="sxs-lookup"><span data-stu-id="1dd05-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="1dd05-105">Należy zwiększyć personalizację rekomendacji, tworząc segmenty z wyników modeli przewidywania.</span><span class="sxs-lookup"><span data-stu-id="1dd05-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="1dd05-106">Można na przykład przekazać konkretne rekomendacje klientom, którzy preferują określony typ usługi.</span><span class="sxs-lookup"><span data-stu-id="1dd05-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="1dd05-107">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="1dd05-107">Prerequisites</span></span>

- <span data-ttu-id="1dd05-108">Co najmniej [Uprawnienia współautora](permissions.md) w Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1dd05-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="1dd05-109">Rekomendacja produktu, rezygnacja z transakcji, rezygnacja z subskrypcji lub model wartości okresu istnienia klientów skonfigurowany w usłudze Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1dd05-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="1dd05-110">Przejrzyj wymagania, aby skonfigurować różne modele:</span><span class="sxs-lookup"><span data-stu-id="1dd05-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="1dd05-111">Model rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="1dd05-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="1dd05-112">Model rezygnacji z subskrypcji</span><span class="sxs-lookup"><span data-stu-id="1dd05-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="1dd05-113">Model rezygnacji transakcyjnej</span><span class="sxs-lookup"><span data-stu-id="1dd05-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="1dd05-114">Model wartości okresu istnienia klienta</span><span class="sxs-lookup"><span data-stu-id="1dd05-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="1dd05-115">Tworzenie segmentu klienta na podstawie przewidywań</span><span class="sxs-lookup"><span data-stu-id="1dd05-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="1dd05-116">Wybierz **Analizy** > **Przewidywania** i wybierz kartę **Moje przewidywania**.</span><span class="sxs-lookup"><span data-stu-id="1dd05-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="1dd05-117">Wybierz pionowy wielokropek obok modelu, który chcesz przejrzeć, i wybierz opcję **Wyświetl**.</span><span class="sxs-lookup"><span data-stu-id="1dd05-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="1dd05-118">Na stronie wyników wybierz opcję **Utwórz segment**.</span><span class="sxs-lookup"><span data-stu-id="1dd05-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="1dd05-119">Aby uzyskać więcej informacji na temat strony wyników, przejrzyj artykuł o modelu.</span><span class="sxs-lookup"><span data-stu-id="1dd05-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Zrzut ekranu strony wyników przewidywania z wyróżnieniem akcji Utwórz segment.":::

1. <span data-ttu-id="1dd05-121">Tworzenie nowego segmentu w oparciu o encję wyjściową wybranego modelu.</span><span class="sxs-lookup"><span data-stu-id="1dd05-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="1dd05-122">Aby uzyskać więcej informacji, zobacz [Tworzenie segmentów i zarządzanie nimi](segments.md).</span><span class="sxs-lookup"><span data-stu-id="1dd05-122">For more information, see [Create and manage segments](segments.md).</span></span>