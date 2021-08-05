---
title: Limity usługi
description: Opis ograniczeń i ograniczeń.
ms.date: 07/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 81253332cbea3110c0b3804db3a4d03b514f92d4
ms.sourcegitcommit: 9a99e48e96dfb3d895db428f37c30ae55eea66b7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/14/2021
ms.locfileid: "6604382"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Ograniczenia dotyczące funkcji analiz odbiorców w Dynamics 365 Customer Insights

W tym artykule opisano wbudowane limity usługi Customer Insights, które zostały zaprojektowane w celu zapewnienia niezawodności i stabilności usługi. Wszelkie żądania wprowadzenia zmian można wykonać za pośrednictwem [Forum pomysłów](https://go.microsoft.com/fwlink/?linkid=2074172). 
 
| Obszar  | Limity  | Notatki |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenty i miary | 100 segmentów lub miar. | Łączna liczba [aktywnych segmentów](segments.md) i [miar](measures.md) nie może przekroczyć 100.  |
| Relacje | 20 poziomów głębokości relacji w ścieżkach jednostek. | Podczas tworzenia [segmentów](segments.md) lub [miar](measures.md) przy użyciu interfejsu konstruktora ścieżki jednostki mogą mieć maksymalnie do 20 przeskoków relacji między jednostką początkową a docelową.  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]