---
title: Łącznik Power Automate | Microsoft Docs
description: Tworzenie przepływów w usłudze Microsoft Power Automate z poziomu aplikacji Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ce2477d957a1792e0436a0dfc15a33621b1c89a9
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976101"
---
# <a name="power-automate-connector-preview"></a>Łącznik Power Automate (wersja zapoznawcza)

Wyzwalaj automatyczne występowanie określonych zdarzeń przy zmianie danych i zarządzaj bardziej skomplikowanymi przepływami bezpośrednio w [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Wyzwalacze Power Automate

Użyj wyzwalaczy do tworzenia przepływów w chmurze i automatyzacji powtarzalnych zadań, takich jak powiadomienia lub bardziej zaawansowane akcje. 

- Wyzwól, kiedy odświeżanie źródła danych zakończy się niepowodzeniem. 
- Wyzwól, kiedy odświeżanie źródła danych zakończy się sukcesem.
- Wyzwól, kiedy w segmencie nastąpi przekroczenie progu. Wyzwalacz jest ograniczony do przekraczania progu.
- Wyzwól, kiedy w miarze biznesowej nastąpi przekroczenie progu. Obsługiwane są tylko miary biznesowe bez wymiaru. Wyzwalacz jest ograniczony do przekraczania progu.
- Wyzwalaj, gdy zostanie ukończone pełne odświeżanie (źródła danych, segmenty, miary,...).
- Wyzwalaj po zakończeniu odświeżania procesu unifikacji (mapowanie, dopasowanie, scalanie).

[Skonfiguruj wyzwalacze w Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Akcje Power Automate
Łącznik Power Automate dostarcza innych akcji niż dostępne wyzwalacze. Aby uzyskać więcej informacji, zobacz [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Utwórz przepływ Power Automate

1. W analizach odbiorców przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.

1. Na kafelku **Power Automate** wybierz **Konfiguracja**.

1. Zostanie otwarty łącznik Customer Insights (wersja zapoznawcza) w usłudze Power Automate. **Zaloguj się** do Power Automate.

1. Wybierz jeden z dostępnych przycisków i dodaj kolejne kroki do nowego przepływu. Aby uzyskać więcej informacji, zobacz temat [Tworzenie przepływu w chmurze w Power Automate](/power-automate/get-started-logic-flow).

Przykłady korzystania z przepływów: 
- Opublikuj wiadomość w kanale Microsoft Teams, jeśli odświeżanie źródła danych nie powiedzie się. 
- Wyślij wiadomość e-mail do właścicieli danych, gdy zostanie przekroczony próg w segmencie.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
