---
title: Ujednolicenie danych
description: Dowiedz się, jak ujednolicić pozyskane dane.
ms.date: 04/16/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 24321e9e11f9fd4e800526673726e5146ed33674
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406556"
---
# <a name="data-unification"></a><span data-ttu-id="fc2e8-103">Ujednolicenie danych</span><span class="sxs-lookup"><span data-stu-id="fc2e8-103">Data unification</span></span>

<span data-ttu-id="fc2e8-104">Po [skonfigurowaniu źródeł danych](data-sources.md) można ujednolicić dane.</span><span class="sxs-lookup"><span data-stu-id="fc2e8-104">After [setting up the data sources](data-sources.md), you can unify the data.</span></span> <span data-ttu-id="fc2e8-105">W przypadku ujednolicenia danych przedstawiono trzy etapy: **Mapowanie**, **Dopasowywanie** i **Scalanie**.</span><span class="sxs-lookup"><span data-stu-id="fc2e8-105">Data unification includes three steps: **Map**, **Match**, and **Merge**.</span></span>

<span data-ttu-id="fc2e8-106">Proces ujednolicenia danych pozwala na ujednolicenie wcześniej rozłącznych źródeł danych w jeden główny zestaw danych, który zapewnia ujednolicony widok klientów.</span><span class="sxs-lookup"><span data-stu-id="fc2e8-106">The data unification process lets you unify once-disparate data sources into a single master dataset that provides a unified view of your customers.</span></span> <span data-ttu-id="fc2e8-107">Etapy zjednoczenia są obowiązkowe i są wykonywane w następującej kolejności:</span><span class="sxs-lookup"><span data-stu-id="fc2e8-107">Unification stages are mandatory, and performed in the following order:</span></span>

1. [<span data-ttu-id="fc2e8-108">Mapowanie</span><span class="sxs-lookup"><span data-stu-id="fc2e8-108">Map</span></span>](map-entities.md)
2. [<span data-ttu-id="fc2e8-109">Dopasowywanie</span><span class="sxs-lookup"><span data-stu-id="fc2e8-109">Match</span></span>](match-entities.md)
3. [<span data-ttu-id="fc2e8-110">Scal</span><span class="sxs-lookup"><span data-stu-id="fc2e8-110">Merge</span></span>](merge-entities.md)

<span data-ttu-id="fc2e8-111">Po zakończeniu ujednolicenia danych można opcjonalnie</span><span class="sxs-lookup"><span data-stu-id="fc2e8-111">After completing the data unification, you can optionally</span></span>

- <span data-ttu-id="fc2e8-112">[skonfigurować relacje między encjami](relationships.md) w celu utworzenia rozbudowanych segmentów</span><span class="sxs-lookup"><span data-stu-id="fc2e8-112">[set up relationships between entities](relationships.md) to create sophisticated segments</span></span>
- <span data-ttu-id="fc2e8-113">[wzbogacić dane](enrichment-hub.md) w celu zdobycia szerszego zakresu informacji o klientach</span><span class="sxs-lookup"><span data-stu-id="fc2e8-113">[enrich your data](enrichment-hub.md) to get a wider range of insights about your customers</span></span>
- <span data-ttu-id="fc2e8-114">[zdefiniować działania](activities.md) na podstawie niektórych pozyskanych atrybutów</span><span class="sxs-lookup"><span data-stu-id="fc2e8-114">[define activities](activities.md) from some of the ingested attributes</span></span>
