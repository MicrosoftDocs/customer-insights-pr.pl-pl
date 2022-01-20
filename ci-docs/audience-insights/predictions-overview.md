---
title: Przegląd obsługiwanych scenariuszy prognozowania
description: Scenariusze i opcje przewidywania, które obejmuje aplikacja Dynamics 365 Customer Insights.
ms.date: 12/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 5972d5b191ded7db14e2ebe9a4a26570a8ea60ba
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2022
ms.locfileid: "7978026"
---
# <a name="predictions-overview"></a>Omówienie przewidywania

Dynamics 365 Customer Insights posiada wiele opcji, które wykorzystują sztuczną inteligencję i uczenie maszynowe do przewidywania danych. 

## <a name="out-of-box-models"></a>Modele out-of-box

Najłatwiejszym sposobem na rozpoczęcie przewidywania danych są predefiniowane modele, często określane jako modele out-of-box. Wymagają one jedynie określonych danych i struktury, aby szybko generować spostrzeżenia. Obecnie są dostępne następujące modele: 

# <a name="individual-consumers-b-to-c"></a>[Klienci indywidualni (B2C)](#tab/b2c)

- [Wartość okresu istnienia klienta](predict-customer-lifetime-value.md): informacje o potencjalnych przychodach klienta w czasie całej interakcji z firmą.
- [Rekomendacje produktu](predict-product-recommendation.md): sugeruje zestawy rekomendacji produktu w oparciu o zachowanie klientów o podobnych wzorcach zakupu.
- [Rezygnacja z subskrypcji](predict-subscription-churn.md): Przewidywanie, czy klient jest zagrożony zaprzestaniem korzystania z produktów lub usług subskrypcyjnych Twojej firmy.
- [Rezygnacja z transakcji](predict-transactional-churn.md): brak możliwości zakupu produktów lub usług przez klienta w określonym horyzoncie czasowym.
- [Analiza nastrojów](sentiment-analysis.md): Przeanalizuj nastroje opinii klientów i zidentyfikuj często wymieniane aspekty biznesowe.

# <a name="business-accounts-b-to-b"></a>[Klienci biznesowi (B2B)](#tab/b2b)

- [Rezygnacja z transakcji](predict-transactional-churn.md): brak możliwości zakupu produktów lub usług przez klienta w określonym horyzoncie czasowym.

---


## <a name="azure-machine-learning-integration"></a>Integracja uczenia maszynowego Azure

Jeśli organizacja korzysta już ze scenariuszy uczenia maszynowego opartych na eksperymentach uczenia maszynowego Azure, funkcja niestandardowych modeli w Customer Insights pomaga połączyć kropki. Twórz przepływy pracy, które pomogą Ci wybrać dane, z których chcesz wygenerować spostrzeżenia i zmapować wyniki do Twoich ujednoliconych profili klientów. Aby uzyskać więcej informacji, zobacz [Niestandardowe modele uczenia maszynowego](custom-models.md).

## <a name="ai-builder-prediction"></a>Przewidywanie AI Builder

Czasami zestawy danych są niekompletne i brakuje pewnych wartości. Customer Insights może pomóc w odszukaniania brakujących wartościach encji Klient i segmentów. Aby uzyskać więcej informacji, zobacz [Uzupełnij swoje dane częściowe o przewidywania](predictions.md).
