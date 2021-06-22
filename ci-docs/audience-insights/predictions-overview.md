---
title: Przegląd obsługiwanych scenariuszy prognozowania
description: Scenariusze i opcje przewidywania, które obejmuje aplikacja Dynamics 365 Customer Insights.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095737"
---
# <a name="predictions-overview"></a><span data-ttu-id="edb22-103">Omówienie przewidywania</span><span class="sxs-lookup"><span data-stu-id="edb22-103">Predictions overview</span></span>

<span data-ttu-id="edb22-104">Dynamics 365 Customer Insights posiada wiele opcji, które wykorzystują sztuczną inteligencję i uczenie maszynowe do przewidywania danych.</span><span class="sxs-lookup"><span data-stu-id="edb22-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="edb22-105">Modele out-of-box</span><span class="sxs-lookup"><span data-stu-id="edb22-105">Out-of-box models</span></span>

<span data-ttu-id="edb22-106">Najłatwiejszym sposobem na rozpoczęcie przewidywania danych są predefiniowane modele, często określane jako modele out-of-box.</span><span class="sxs-lookup"><span data-stu-id="edb22-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="edb22-107">Wymagają one jedynie określonych danych i struktury, aby szybko generować spostrzeżenia.</span><span class="sxs-lookup"><span data-stu-id="edb22-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="edb22-108">Obecnie są dostępne następujące modele:</span><span class="sxs-lookup"><span data-stu-id="edb22-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="edb22-109">[Wartość okresu istnienia klienta](predict-customer-lifetime-value.md): informacje o potencjalnych przychodach klienta w czasie całej interakcji z firmą.</span><span class="sxs-lookup"><span data-stu-id="edb22-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="edb22-110">[Rekomendacje produktu](predict-product-recommendation.md): sugeruje zestawy rekomendacji produktu w oparciu o zachowanie klientów o podobnych wzorcach zakupu.</span><span class="sxs-lookup"><span data-stu-id="edb22-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="edb22-111">[Rezygnacja z subskrypcji](predict-subscription-churn.md): Przewidywanie, czy klient jest zagrożony zaprzestaniem korzystania z produktów lub usług subskrypcyjnych Twojej firmy.</span><span class="sxs-lookup"><span data-stu-id="edb22-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="edb22-112">[Rezygnacja z transakcji](predict-transactional-churn.md): brak możliwości zakupu produktów lub usług przez klienta w określonym horyzoncie czasowym.</span><span class="sxs-lookup"><span data-stu-id="edb22-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="edb22-113">Integracja uczenia maszynowego Azure</span><span class="sxs-lookup"><span data-stu-id="edb22-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="edb22-114">Jeśli organizacja korzysta już ze scenariuszy uczenia maszynowego opartych na eksperymentach uczenia maszynowego Azure, funkcja niestandardowych modeli w Customer Insights pomaga połączyć kropki.</span><span class="sxs-lookup"><span data-stu-id="edb22-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="edb22-115">Twórz przepływy pracy, które pomogą Ci wybrać dane, z których chcesz wygenerować spostrzeżenia i zmapować wyniki do Twoich ujednoliconych profili klientów.</span><span class="sxs-lookup"><span data-stu-id="edb22-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="edb22-116">Aby uzyskać więcej informacji, zobacz [Niestandardowe modele uczenia maszynowego](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="edb22-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="edb22-117">Przewidywanie AI Builder</span><span class="sxs-lookup"><span data-stu-id="edb22-117">AI Builder prediction</span></span>

<span data-ttu-id="edb22-118">Czasami zestawy danych są niekompletne i brakuje pewnych wartości.</span><span class="sxs-lookup"><span data-stu-id="edb22-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="edb22-119">Customer Insights może pomóc w odszukaniania brakujących wartościach encji Klient i segmentów.</span><span class="sxs-lookup"><span data-stu-id="edb22-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="edb22-120">Aby uzyskać więcej informacji, zobacz [Uzupełnij swoje dane częściowe o przewidywania](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="edb22-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
