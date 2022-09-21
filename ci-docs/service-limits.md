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
ms.openlocfilehash: c3863b1a72fd92ddc87755699feda11371ec9214
ms.sourcegitcommit: dfba60e17ae6dc1e2e3830e6365e2c1f87230afd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2022
ms.locfileid: "9463232"
---
# <a name="service-limits-in-customer-insights"></a>Ograniczenia dotyczące usług w Customer Insights

 Customer Insights ma wbudowane limity zaprojektowane w celu zapewnienia niezawodności i stabilności usługi. Wszelkie żądania wprowadzenia zmian można wykonać za pośrednictwem [Forum pomysłów](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Obszar  | Limity  | Uwagi |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenty, miary i przewidywania | 300  | Łączna liczba [segmentów](segments.md), [miar](measures.md) i [przewidywań](predictions-overview.md) nie może przekraczać 300.  |
| Relacje | 20 poziomów głębokości relacji w ścieżkach jednostek. | Podczas tworzenia [segmentów](segments.md) lub [miar](measures.md) przy użyciu interfejsu konstruktora ścieżki jednostki mogą mieć maksymalnie do 20 przeskoków relacji między jednostką początkową a docelową.  |
|Pozyskiwanie danych| Jednoczesne oceny źródeł danych Power Query są ograniczone. | Aplikacja Customer Insights ma takie same [ograniczenia odświeżania jak Dataflows w PowerBI.com](/power-query/power-query-online-limits#refresh-limits). |

## <a name="fair-scheduling-of-jobs"></a>Uczciwie planowanie zadań

Customer Insights to usługa SaaS, która korzysta z udostępnionych zasobów platformy Azure. Klienci nie tylko mają różne obciążenia pracy, ale również różne harmonogramy. Aby zapewnić uczciwy dostęp do podstawowych zasobów, zapewnić uczciwą kolejność procesów systemowych. Przykłady procesów systemowych to zadania związane z rozsyłaniem danych, aktualizacjami segmentów lub obliczaniem miary. Uczciwa funkcja planowania zapewnia ochronę przed kolejką zasobów w przypadku nagłego wzrostu liczby zadań. Jednocześnie Customer Insights nie gwarantuje, że wszystkie zadania przetwarzane w kolejce są przetwarzane równocześnie.

[!INCLUDE [footer-include](includes/footer-banner.md)]
