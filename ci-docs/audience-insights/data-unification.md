---
title: Tworzenie ujednoliconego widoku klientów
description: Przejdź przez proces ujednolicania swoich danych, aby utworzyć jeden główny zestaw danych profilów klientów.
ms.date: 10/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-unify
ms.openlocfilehash: 694bfd0e407975af64ca0971a73fe4c3f5ba5a23
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648084"
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