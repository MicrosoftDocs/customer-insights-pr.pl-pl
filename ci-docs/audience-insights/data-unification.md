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
ms.openlocfilehash: 44f97696ec91dc488dd6a7528e186abb99c8288b
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269665"
---
# <a name="data-unification-overview"></a>Omówienie ujednolicenia danych

Po [skonfigurowaniu źródeł danych](data-sources.md) można ujednolicić dane. W przypadku ujednolicenia danych przedstawiono trzy etapy: **Mapowanie**, **Dopasowywanie** i **Scalanie**.

Proces ujednolicenia danych pozwala na ujednolicenie wcześniej rozłącznych źródeł danych w jeden główny zestaw danych, który zapewnia ujednolicony widok klientów. Etapy zjednoczenia są obowiązkowe i są wykonywane w następującej kolejności:

1. [Mapowanie](map-entities.md)
2. [Dopasowywanie](match-entities.md)
3. [Scal](merge-entities.md)

Po zakończeniu ujednolicenia danych można opcjonalnie

- [skonfigurować relacje między encjami](relationships.md) w celu utworzenia rozbudowanych segmentów
- [wzbogacić dane](enrichment-hub.md) w celu zdobycia szerszego zakresu informacji o klientach
- [zdefiniować działania](activities.md) na podstawie niektórych pozyskanych atrybutów


[!INCLUDE[footer-include](../includes/footer-banner.md)]