---
title: Omówienie przewidywania
description: Scenariusze i opcje przewidywania, które obejmuje aplikacja Dynamics 365 Customer Insights.
ms.date: 03/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 32240c8c43751d8514d38b392f23ef4138d50ee2
ms.sourcegitcommit: 3c7cdfc8bd83ca236e4777240e08a541dc955d34
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2022
ms.locfileid: "9411844"
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

> [!TIP]
> Zaleca się regularne odświeżanie wraz z zaktualizowanymi danymi modeli, aby upewnić się, że są one dokładne w celu poinformowania o tym sprawy dotyczącej użytkowania firmy. Dane są odświeżane ad hoc, gdy systemowe źródła danych zostaną korzystające z nowych lub zaktualizowanych źródeł danych. Jednak w takim przypadku modele będą używać tylko rescore i nadal będą korzystać z istniejących danych szkoleniowych.
>
> Możesz skonfigurować **Harmonogram aktualizacji**, ustawiając harmonogram ponownego uczenia modelu w środowisku konfiguracji. Model przeszkoli się i ponownie oceni zgodnie z tym harmonogramem, który możesz zmienić w dowolnym momencie.

## <a name="azure-machine-learning-integration"></a>Integracja uczenia maszynowego Azure

Jeśli organizacja korzysta już ze scenariuszy uczenia maszynowego opartych na eksperymentach uczenia maszynowego Azure, funkcja niestandardowych modeli w Customer Insights pomaga połączyć kropki. Twórz przepływy pracy, które pomogą Ci wybrać dane, z których chcesz wygenerować spostrzeżenia i zmapować wyniki do Twoich ujednoliconych profili klientów. Aby uzyskać więcej informacji, zobacz [Niestandardowe modele uczenia maszynowego](custom-models.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
