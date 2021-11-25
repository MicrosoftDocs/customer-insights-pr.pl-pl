---
title: Limity usługi w Dynamics 365 Customer Insights
description: Opis ograniczeń i ograniczeń.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eb25e050b8aa768e6e1d8d4c5adce6095cccc346
ms.sourcegitcommit: 31a9b531dacd3a6465b3030c704ff5c085b7e122
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2021
ms.locfileid: "7791994"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Limity dotyczące usług w funkcjach aplikacji Customer Insights

W tym artykule opisano wbudowane limity usługi Customer Insights, które zostały zaprojektowane w celu zapewnienia niezawodności i stabilności usługi. Wszelkie żądania wprowadzenia zmian można wykonać za pośrednictwem [Forum pomysłów](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Wyniki analiz odbiorców

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Ograniczenia dotyczące funkcji analiz odbiorców w Dynamics 365 Customer Insights

| Obszar  | Limity  | Uwagi |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenty, miary i przewidywania | 300  | Łączna liczba [segmentów](audience-insights/segments.md), [miar](audience-insights/measures.md) i [przewidywań](audience-insights/predictions.md) nie może przekraczać 300.  |
| Relacje | 20 poziomów głębokości relacji w ścieżkach jednostek. | Podczas tworzenia [segmentów](audience-insights/segments.md) lub [miar](audience-insights/measures.md) przy użyciu interfejsu konstruktora ścieżki jednostki mogą mieć maksymalnie do 20 przeskoków relacji między jednostką początkową a docelową.  |


## <a name="engagement-insights"></a>Szczegółowe informacje o zaangażowaniu

### <a name="workspace-and-event-quotas"></a>Limity przydziałów obszarów roboczych i zdarzeń

Rozwiązanie analizy interakcji to niezwykle skalowalny program obsługujący jeszcze więcej zdarzeń na sekundę. Podczas wyświetlania publicznej wersji zapoznawczej zdarzenia mają wartość progową ilości. Istnieje także ograniczenie liczby obszarów roboczych w organizacji.

### <a name="engagement-insights-limits"></a>Limity analiz interakcji

- Maksymalna liczba zdarzeń na obszar roboczy = 100 zdarzeń na sekundę

- Maksymalna liczba wierszy na obszar roboczy w organizacji = 100

Przekroczenie progu może spowodować utratę danych w raportach tworzonych w oparciu o te zdarzenia. W celu zwiększenia ilości danych można [skontaktować się z pomocą techniczną](https://go.microsoft.com/fwlink/?linkid=2145734), zanim zostanie przekroczony limit. Będziemy z Tobą współpracować, aby określić potrzebę zwiększenia objętości i wesprzeć Twoją prośbę.


[!INCLUDE[footer-include](includes/footer-banner.md)]
