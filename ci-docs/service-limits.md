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
ms.openlocfilehash: eba7871faf304d5945191b5b9bc215243b4f8a05
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483695"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Limity dotyczące usług w funkcjach aplikacji Customer Insights

W tym artykule opisano wbudowane limity usługi Customer Insights, które zostały zaprojektowane w celu zapewnienia niezawodności i stabilności usługi. Wszelkie żądania wprowadzenia zmian można wykonać za pośrednictwem [Forum pomysłów](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Wyniki analiz odbiorców

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Ograniczenia dotyczące funkcji analiz odbiorców w Dynamics 365 Customer Insights

| Obszar  | Limity  | Notatki |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenty i miary | 100 segmentów lub miar. | Łączna liczba [aktywnych segmentów](audience-insights/segments.md) i [miar](audience-insights/measures.md) nie może przekroczyć 100.  |
| Relacje | 20 poziomów głębokości relacji w ścieżkach jednostek. | Podczas tworzenia [segmentów](audience-insights/segments.md) lub [miar](audience-insights/measures.md) przy użyciu interfejsu konstruktora ścieżki jednostki mogą mieć maksymalnie do 20 przeskoków relacji między jednostką początkową a docelową.  |


## <a name="engagement-insights"></a>Szczegółowe informacje o zaangażowaniu

### <a name="workspace-and-event-quotas"></a>Limity przydziałów obszarów roboczych i zdarzeń

Rozwiązanie analizy interakcji to niezwykle skalowalny program obsługujący jeszcze więcej zdarzeń na sekundę. Podczas wyświetlania publicznej wersji zapoznawczej zdarzenia mają wartość progową ilości. Istnieje także ograniczenie liczby obszarów roboczych w organizacji.

### <a name="engagement-insights-limits"></a>Limity analiz interakcji

- Maksymalna liczba zdarzeń na obszar roboczy = 100 zdarzeń na sekundę

- Maksymalna liczba wierszy na obszar roboczy w organizacji = 100

Przekroczenie progu może spowodować utratę danych w raportach tworzonych w oparciu o te zdarzenia. W celu zwiększenia ilości danych można [skontaktować się z pomocą techniczną](https://go.microsoft.com/fwlink/?linkid=2145734), zanim zostanie przekroczony limit. Będziemy z Tobą współpracować, aby określić potrzebę zwiększenia objętości i wesprzeć Twoją prośbę.


[!INCLUDE[footer-include](includes/footer-banner.md)]