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
# <a name="data-unification"></a>Ujednolicenie danych

Po [skonfigurowaniu źródeł danych](data-sources.md) można ujednolicić dane. W przypadku ujednolicenia danych przedstawiono trzy etapy: **Mapowanie**, **Dopasowywanie** i **Scalanie**.

Proces ujednolicenia danych pozwala na ujednolicenie wcześniej rozłącznych źródeł danych w jeden główny zestaw danych, który zapewnia ujednolicony widok klientów. Etapy zjednoczenia są obowiązkowe i są wykonywane w następującej kolejności:

1. [Mapowanie](map-entities.md)
2. [Dopasowywanie](match-entities.md)
3. [Scal](merge-entities.md)

Po zakończeniu ujednolicenia danych można opcjonalnie

- [skonfigurować relacje między encjami](relationships.md) w celu utworzenia rozbudowanych segmentów
- [wzbogacić dane](enrichment-hub.md) w celu zdobycia szerszego zakresu informacji o klientach
- [zdefiniować działania](activities.md) na podstawie niektórych pozyskanych atrybutów
