---
title: Łącznik Power Automate (wersja zapoznawcza) | Microsoft Docs
description: Tworzenie przepływów w usłudze Microsoft Power Automate z poziomu aplikacji Dynamics 365 Customer Insights.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196131"
---
# <a name="power-automate-connector-preview"></a>Łącznik Power Automate (wersja zapoznawcza)

Wyzwalaj automatyczne występowanie określonych zdarzeń przy zmianie danych i zarządzaj bardziej skomplikowanymi przepływami bezpośrednio w [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Znane ograniczenia

- Maksymalnie 100 rozmów na 60 sekund. Użyj [parametru $skip](/connectors/customerinsights/#get-items-from-an-entity), aby wielokrotnie wywołać punkt końcowy interfejsu API.

## <a name="power-automate-triggers"></a>Wyzwalacze Power Automate

Użyj wyzwalaczy do tworzenia przepływów w chmurze i automatyzacji powtarzalnych zadań, takich jak powiadomienia lub bardziej zaawansowane akcje. Użyj wyzwolenia, gdy:

- Odświeżanie źródła danych nie powiodło się.
- Odświeżenie źródła danych powiodło się.
- W segmencie nastąpiło przekroczenie progu. Wyzwalacz jest ograniczony do przekraczania progu.
- W miarze biznesowej nastąpi przekroczenie progu. Obsługiwane są tylko miary biznesowe bez wymiaru. Wyzwalacz jest ograniczony do przekraczania progu.
- Pełne zaplanowane odświeżenie zostało zakończone. Ten wyzwalanie nie działa w przypadku ręcznego odświeżania.
- Po zakończeniu odświeżania procesu ujednolicenia.

[Skonfiguruj wyzwalacze w Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Akcje Power Automate

Łącznik Power Automate dostarcza innych akcji niż dostępne wyzwalacze. Aby uzyskać więcej informacji, zobacz [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Utwórz przepływ Power Automate

1. Przejdź do **Admin** > **Połączenia**.

1. Na kafelku **Power Automate** wybierz **Konfiguracja**.

1. Zostanie otwarty łącznik Customer Insights (wersja zapoznawcza) w usłudze Power Automate. **Zaloguj się** do Power Automate.

1. Wybierz jeden z dostępnych przycisków i dodaj kolejne kroki do nowego przepływu. Aby uzyskać więcej informacji, zobacz temat [Tworzenie przepływu w chmurze w Power Automate](/power-automate/get-started-logic-flow).

Przykłady korzystania z przepływów: 
- Opublikuj wiadomość w kanale Microsoft Teams, jeśli odświeżanie źródła danych nie powiedzie się. 
- Wyślij wiadomość e-mail do właścicieli danych, gdy zostanie przekroczony próg w segmencie.

[!INCLUDE [footer-include](includes/footer-banner.md)]
