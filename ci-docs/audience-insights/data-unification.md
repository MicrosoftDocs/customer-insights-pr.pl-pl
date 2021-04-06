---
title: Ujednolicenie danych
description: Dowiedz się, jak ujednolicić pozyskane dane.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 73d8006c670268420f8cd6a2b37cb214ba1bbd6c
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597892"
---
# <a name="data-unification-overview"></a><span data-ttu-id="616de-103">Omówienie ujednolicenia danych</span><span class="sxs-lookup"><span data-stu-id="616de-103">Data unification overview</span></span>

<span data-ttu-id="616de-104">Po [skonfigurowaniu źródeł danych](data-sources.md) można ujednolicić dane.</span><span class="sxs-lookup"><span data-stu-id="616de-104">After [setting up the data sources](data-sources.md), you can unify the data.</span></span> <span data-ttu-id="616de-105">W przypadku ujednolicenia danych przedstawiono trzy etapy: **Mapowanie**, **Dopasowywanie** i **Scalanie**.</span><span class="sxs-lookup"><span data-stu-id="616de-105">Data unification includes three steps: **Map**, **Match**, and **Merge**.</span></span>

<span data-ttu-id="616de-106">Proces ujednolicenia danych pozwala na ujednolicenie wcześniej rozłącznych źródeł danych w jeden główny zestaw danych, który zapewnia ujednolicony widok klientów.</span><span class="sxs-lookup"><span data-stu-id="616de-106">The data unification process lets you unify once-disparate data sources into a single master dataset that provides a unified view of your customers.</span></span> <span data-ttu-id="616de-107">Etapy zjednoczenia są obowiązkowe i są wykonywane w następującej kolejności:</span><span class="sxs-lookup"><span data-stu-id="616de-107">Unification stages are mandatory, and performed in the following order:</span></span>

1. [<span data-ttu-id="616de-108">Mapowanie</span><span class="sxs-lookup"><span data-stu-id="616de-108">Map</span></span>](map-entities.md)
2. [<span data-ttu-id="616de-109">Dopasowywanie</span><span class="sxs-lookup"><span data-stu-id="616de-109">Match</span></span>](match-entities.md)
3. [<span data-ttu-id="616de-110">Scal</span><span class="sxs-lookup"><span data-stu-id="616de-110">Merge</span></span>](merge-entities.md)

<span data-ttu-id="616de-111">Po zakończeniu ujednolicenia danych można opcjonalnie</span><span class="sxs-lookup"><span data-stu-id="616de-111">After completing the data unification, you can optionally</span></span>

- <span data-ttu-id="616de-112">[skonfigurować relacje między encjami](relationships.md) w celu utworzenia rozbudowanych segmentów</span><span class="sxs-lookup"><span data-stu-id="616de-112">[set up relationships between entities](relationships.md) to create sophisticated segments</span></span>
- <span data-ttu-id="616de-113">[wzbogacić dane](enrichment-hub.md) w celu zdobycia szerszego zakresu informacji o klientach</span><span class="sxs-lookup"><span data-stu-id="616de-113">[enrich your data](enrichment-hub.md) to get a wider range of insights about your customers</span></span>
- <span data-ttu-id="616de-114">[zdefiniować działania](activities.md) na podstawie niektórych pozyskanych atrybutów</span><span class="sxs-lookup"><span data-stu-id="616de-114">[define activities](activities.md) from some of the ingested attributes</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]