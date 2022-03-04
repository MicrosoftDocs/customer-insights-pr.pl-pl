---
title: Limity usługi w Dynamics 365 Customer Insights
description: Opis ograniczeń i ograniczeń.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350420"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Limity dotyczące usług w funkcjach aplikacji Customer Insights

W tym artykule opisano wbudowane limity usługi Customer Insights, które zostały zaprojektowane w celu zapewnienia niezawodności i stabilności usługi. Wszelkie żądania wprowadzenia zmian można wykonać za pośrednictwem [Forum pomysłów](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Audience Insights

| Obszar  | Limity  | Uwagi |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenty, miary i przewidywania | 300  | Łączna liczba [segmentów](audience-insights/segments.md), [miar](audience-insights/measures.md) i [przewidywań](audience-insights/predictions.md) nie może przekraczać 300.  |
| Relacje | 20 poziomów głębokości relacji w ścieżkach jednostek. | Podczas tworzenia [segmentów](audience-insights/segments.md) lub [miar](audience-insights/measures.md) przy użyciu interfejsu konstruktora ścieżki jednostki mogą mieć maksymalnie do 20 przeskoków relacji między jednostką początkową a docelową.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
