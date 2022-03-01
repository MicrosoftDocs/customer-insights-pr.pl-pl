---
title: Eksportowanie danych Customer Insights do usługi Autopilot
description: Dowiedz się, jak skonfigurować połączenie z Autopilot.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269251"
---
# <a name="connector-for-autopilot-preview"></a>Łącznik dla usługi Autopilot (wersja zapoznawcza)

Eksportuj segmenty ujednoliconych profili klientów do Autopilota i używaj ich do marketingu e-mailowego w Autopilocie. 

## <a name="prerequisites"></a>Wymagania wstępne

-   Użytkownik ma [konto usługi Autopilot](https://www.autopilothq.com/) i odpowiadające mu poświadczenia administratora.
-   Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.
-   Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="connect-to-autopilot"></a>Połącz z usługą Autopilot

1. Przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.

1. W **Autopilot** wybierz **Konfiguruj**.

1. W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej exportu rozpoznawalną nazwę.

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Okienko konfiguracji dla połączenia z Autopilot.":::

1. Wprowadź **klucz interfejsu API Autopilot** [klucz interfejsu API Autopilot](https://autopilot.docs.apiary.io/#).

1. Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.

1. Wybierz opcję **Połącz**, aby zainicjować połączenie z Autopilot.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Wybierz **Dalej**, aby skonfigurować eksport.

## <a name="configure-the-connector"></a>Skonfiguruj łącznik

1. W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta. Powtórz te kroki dla innych pól opcjonalnych, takich jak **Imię**, **Nazwisko**.

1. Wybierz segmenty, które chcesz wyeksportować. Zdecydowanie **zalecamy, aby nie eksportować łącznie ponad 100 000 profili klientów** do Autopilota. 

1. Wybierz pozycję **Zapisz**.

## <a name="export-the-data"></a>Eksportowanie danych

Możesz [eksportować dane na żądanie](export-destinations.md). Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab).

## <a name="known-limitations"></a>Znane ograniczenia

- Możesz wyeksportować łącznie do 100 000 profili do Autopilota.
- Eksport do Autopilot jest ograniczony do segmentów.
- Eksportowanie do 100 000 profili do Autopilota może zająć do kilku godzin. 
- Liczba profilów, które można eksportować do Autopilot, jest zależna od kontraktu i ograniczona jego Autopilot.

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Autopilot można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że Autopilot spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.


[!INCLUDE[footer-include](../includes/footer-banner.md)]