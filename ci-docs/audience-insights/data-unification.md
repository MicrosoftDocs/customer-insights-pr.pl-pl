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
ms.custom: intro-internal
ms.openlocfilehash: bf1bbcd31333c8a557b59b001112042a1783546ab0cd2af394d8af2953a493f4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032771"
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