---
title: Łącznik Power Automate | Microsoft Docs
description: Utwórz przepływy w Microsoft Power Automate z poziomu Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406548"
---
# <a name="power-automate-connector-preview"></a>Łącznik Power Automate (wersja zapoznawcza)

Wyzwalaj automatyczne występowanie określonych zdarzeń przy zmianie danych i zarządzaj bardziej skomplikowanymi przepływami bezpośrednio w [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Wyzwalacze Power Automate

Użytkownik może korzystać z różnorodnych wyzwalaczy, które umożliwiają tworzenie przepływów w celu automatyzacji powtarzalnych zadań, takich jak powiadomienia lub bardziej zaawansowane akcje. 

- Wyzwól, kiedy odświeżanie źródła danych zakończy się niepowodzeniem. 
- Wyzwól, kiedy odświeżanie źródła danych zakończy się sukcesem.
- Wyzwól, kiedy w segmencie nastąpi przekroczenie progu. Wyzwalacz jest ograniczony do przekraczania progu.
- Wyzwól, kiedy w miarze biznesowej nastąpi przekroczenie progu. Wyzwalacz jest ograniczony do przekraczania progu.
- Wyzwalaj, gdy zostanie ukończone pełne odświeżanie (źródła danych, segmenty, miary,...).
- Wyzwalaj po zakończeniu odświeżania procesu unifikacji (mapowanie, dopasowanie, scalanie).

[Skonfiguruj wyzwalacze w Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Akcje Power Automate
Łącznik Power Automate dostarcza innych akcji niż dostępne wyzwalacze. Aby uzyskać więcej informacji, zobacz [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Tworzenie przepływu Power Automate w statystykach odbiorców

1. W analizach odbiorców przejdź do **Administrator** > **System**.

1. Na stronie **System** wybierz kartę **Status**.

1. W sekcji **Źródła danych** wybierz **Przepływy** i wybierz **Utwórz przepływ** z listy rozwijanej.
   > [!div class="mx-imgBorder"]
   > ![Łącznik Power Automate pokazujący akcję utworzenia przepływu](media/power-automate-connector-create-flow.png "Łącznik Power Automate pokazujący akcję utworzenia przepływu")

1. W Power Automate wybierz jeden z dostępnych wyzwalaczy, aby utworzyć preferowany przepływ. W przypadku tworzenia pierwszego przepływu należy najpierw uwierzytelnić się przy użyciu łącznika Power Automate.
