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
ms.custom: intro-internal
ms.openlocfilehash: b73046844f6009a2b163b5eaadf5f63f75cda1d8
ms.sourcegitcommit: b78c9680b213204e6b0ed47f0147205083f6a98f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "6539174"
---
# <a name="predictions-overview"></a>Omówienie przewidywania

Dynamics 365 Customer Insights posiada wiele opcji, które wykorzystują sztuczną inteligencję i uczenie maszynowe do przewidywania danych. 

## <a name="out-of-box-models"></a>Modele out-of-box

Najłatwiejszym sposobem na rozpoczęcie przewidywania danych są predefiniowane modele, często określane jako modele out-of-box. Wymagają one jedynie określonych danych i struktury, aby szybko generować spostrzeżenia. Obecnie są dostępne następujące modele: 
- [Wartość okresu istnienia klienta](predict-customer-lifetime-value.md): informacje o potencjalnych przychodach klienta w czasie całej interakcji z firmą. 
- [Rekomendacje produktu](predict-product-recommendation.md): sugeruje zestawy rekomendacji produktu w oparciu o zachowanie klientów o podobnych wzorcach zakupu.
- [Rezygnacja z subskrypcji](predict-subscription-churn.md): Przewidywanie, czy klient jest zagrożony zaprzestaniem korzystania z produktów lub usług subskrypcyjnych Twojej firmy.
- [Rezygnacja z transakcji](predict-transactional-churn.md): brak możliwości zakupu produktów lub usług przez klienta w określonym horyzoncie czasowym.

## <a name="azure-machine-learning-integration"></a>Integracja uczenia maszynowego Azure

Jeśli organizacja korzysta już ze scenariuszy uczenia maszynowego opartych na eksperymentach uczenia maszynowego Azure, funkcja niestandardowych modeli w Customer Insights pomaga połączyć kropki. Twórz przepływy pracy, które pomogą Ci wybrać dane, z których chcesz wygenerować spostrzeżenia i zmapować wyniki do Twoich ujednoliconych profili klientów. Aby uzyskać więcej informacji, zobacz [Niestandardowe modele uczenia maszynowego](custom-models.md).

## <a name="ai-builder-prediction"></a>Przewidywanie AI Builder

Czasami zestawy danych są niekompletne i brakuje pewnych wartości. Customer Insights może pomóc w odszukaniania brakujących wartościach encji Klient i segmentów. Aby uzyskać więcej informacji, zobacz [Uzupełnij swoje dane częściowe o przewidywania](predictions.md).
