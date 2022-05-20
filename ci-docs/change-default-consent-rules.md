---
title: Zarządzanie domyślnymi regułami wyrażania zgody w segmentach
description: Korzystając z funkcji zarządzania zgodami, można wyłączyć lub zmienić domyślne reguły wyrażania zgody, jeśli włączono zastępowanie.
ms.date: 12/01/2021
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 764eeca9d99c95a34d9bd4c11d79f8b8e90701e2
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755229"
---
# <a name="disable-or-change-default-consent-rules"></a>Wyłączanie lub zmienianie domyślnych reguł wyrażania zgody

Jeśli organizacja korzysta z funkcji [zarządzania zgodami](consent-management/overview.md) w połączeniu z Dynamics 365 Customer Insights, [administratorzy mogą wymuszać reguły wyrażania zgody](activate-consent.md) w segmentach. 

Dzięki wymuszanym regułom zgody w obszarze segmentu każdy segment informuje o stanie sprawdzania zgody i o regułach. Jeśli zastępowanie jest dozwolone, domyślne reguły wyrażana zgody są wyłączone w przypadku określonych segmentów. Każdy twórca segmentu może dodać więcej reguł zgody do domyślnych reguł w danym segmencie. 

## <a name="for-administrators"></a>Dla administratorów

:::image type="content" source="consent-management/media/consent-rules-segment.png" alt-text="Kreator segmentów z opcjami reguł wyrażania zgody.":::

**Aby dezaktywować domyślne reguły wyrażania zgody:**

1. W powiadomieniu **Reguły wyrażania zgody** wybierz opcję **Zobacz szczegóły**. 

1. Ustaw przełącznik **Domyślne reguły wyrażania zgody** na **Wył.**

**Aby dodać więcej reguł wyrażania zgody:**

1. W powiadomieniu **Reguły wyrażania zgody** wybierz opcję **Zobacz szczegóły**. 

1. Wybierz opcję **Dodaj reguły wyrażania zgody** i wybierz regułę zgody z listy rozwijanej **Wybierz typ danych dotyczących zgody**.

1. Wybierz opcję **Zapisz**, aby zastosować nową regułę do segmentu.

## <a name="for-contributors"></a>Dla współpracowników

Aby stworzyć segment bez wymuszonych reguł zgody, musisz współpracować z administratorem, który wyłączy je w twoim segmencie. Możesz jednak dodać swoje własne zasady zgody do segmentów, które posiadasz i którymi zarządzasz.

Jest to proces składający się z trzech kroków: 
1. [Utwórz segment](segments.md) w Customer Insights i go zapisz. 

1. Podziel się nazwą segmentu ze swoim administratorem i poproś go o [włączenie nadpisów dla twojego segmentu](activate-consent.md). 

1. Otwórz ponownie swoje segmenty. W powiadomieniu **Reguły zgody** wybierz **Zobacz szczegóły** i dodaj reguły zgody, które chcesz zastosować. Następnie **zapisz** i **uruchom** segment.



[!INCLUDE [footer-include](includes/footer-banner.md)] 
