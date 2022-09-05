---
title: Ograniczenia dotyczące usług w Customer Insights
description: Opis limitów i ograniczeń w usłudze Customer Insights SaaS.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 421e1aa41a54a4b8c34ac27fc7c02e510d2bb588
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387169"
---
# <a name="service-limits-in-customer-insights"></a>Ograniczenia dotyczące usług w Customer Insights

 Customer Insights ma wbudowane limity zaprojektowane w celu zapewnienia niezawodności i stabilności usługi. Wszelkie żądania wprowadzenia zmian można wykonać za pośrednictwem [Forum pomysłów](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Obszar  | Limity  | Uwagi |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenty, miary i przewidywania | 300  | Łączna liczba [segmentów](segments.md), [miar](measures.md) i [przewidywań](predictions.md) nie może przekraczać 300.  |
| Relacje | 20 poziomów głębokości relacji w ścieżkach jednostek. | Podczas tworzenia [segmentów](segments.md) lub [miar](measures.md) przy użyciu interfejsu konstruktora ścieżki jednostki mogą mieć maksymalnie do 20 przeskoków relacji między jednostką początkową a docelową.  |

## <a name="fair-scheduling-of-jobs"></a>Uczciwie planowanie zadań

Customer Insights to usługa SaaS, która korzysta z udostępnionych zasobów platformy Azure. Klienci nie tylko mają różne obciążenia pracy, ale również różne harmonogramy. Aby zapewnić uczciwy dostęp do podstawowych zasobów, zapewnić uczciwą kolejność procesów systemowych. Przykłady procesów systemowych to zadania związane z rozsyłaniem danych, aktualizacjami segmentów lub obliczaniem miary. Uczciwa funkcja planowania zapewnia ochronę przed kolejką zasobów w przypadku nagłego wzrostu liczby zadań. Jednocześnie Customer Insights nie gwarantuje, że wszystkie zadania przetwarzane w kolejce są przetwarzane równocześnie.

[!INCLUDE [footer-include](includes/footer-banner.md)]
