---
title: Łącznik Power Automate | Microsoft Docs
description: Utwórz przepływy w Microsoft Power Automate z poziomu Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268837"
---
# <a name="power-automate-connector-preview"></a>Łącznik Power Automate (wersja zapoznawcza)

Wyzwalaj automatyczne występowanie określonych zdarzeń przy zmianie danych i zarządzaj bardziej skomplikowanymi przepływami bezpośrednio w [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Wyzwalacze Power Automate

Użyj wyzwalaczy do tworzenia przepływów w chmurze i automatyzacji powtarzalnych zadań, takich jak powiadomienia lub bardziej zaawansowane akcje. 

- Wyzwól, kiedy odświeżanie źródła danych zakończy się niepowodzeniem. 
- Wyzwól, kiedy odświeżanie źródła danych zakończy się sukcesem.
- Wyzwól, kiedy w segmencie nastąpi przekroczenie progu. Wyzwalacz jest ograniczony do przekraczania progu.
- Wyzwól, kiedy w miarze biznesowej nastąpi przekroczenie progu. Wyzwalacz jest ograniczony do przekraczania progu.
- Wyzwalaj, gdy zostanie ukończone pełne odświeżanie (źródła danych, segmenty, miary,...).
- Wyzwalaj po zakończeniu odświeżania procesu unifikacji (mapowanie, dopasowanie, scalanie).

[Skonfiguruj wyzwalacze w Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Akcje Power Automate
Łącznik Power Automate dostarcza innych akcji niż dostępne wyzwalacze. Aby uzyskać więcej informacji, zobacz [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Utwórz przepływ Power Automate

1. W analizach odbiorców przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.

1. Na kafelku **Power Automate** wybierz **Konfiguracja**.

1. Zostanie otwarty łącznik Customer Insights (wersja zapoznawcza) w usłudze Power Automate. **Zaloguj się** do Power Automate.

1. Wybierz jeden z dostępnych przycisków i dodaj kolejne kroki do nowego przepływu. Aby uzyskać więcej informacji, zobacz temat [Tworzenie przepływu w chmurze w Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).

Przykłady korzystania z przepływów: 
- Opublikuj wiadomość w kanale Microsoft Teams, jeśli odświeżanie źródła danych nie powiedzie się. 
- Wyślij wiadomość e-mail do właścicieli danych, gdy zostanie przekroczony próg w segmencie.



[!INCLUDE[footer-include](../includes/footer-banner.md)]