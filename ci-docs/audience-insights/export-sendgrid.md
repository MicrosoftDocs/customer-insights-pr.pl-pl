---
title: Eksportowanie danych Customer Insights do usługi SendGrid
description: Dowiedz się, jak skonfigurować połączenie z SendGrid.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268745"
---
# <a name="connector-for-sendgrid-preview"></a>Łącznik dla usługi SendGrid (wersja zapoznawcza)

Eksportuj segmenty ujednoliconych profili klientów do list kontaktów SendGrid i używaj ich do kampanii i marketingu e-mailowego w SendGrid. 

## <a name="prerequisites"></a>Wymagania wstępne

-   Użytkownik ma [konto usługi SendGrid](https://sendgrid.com/) i odpowiadające mu poświadczenia administratora.
-   Istnieją listy kontaktów w SendGrid i odpowiadające im identyfikatory. Aby uzyskać więcej informacji, zobacz temat [SendGrid — Zarządzanie kontaktami](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.
-   Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="connect-to-sendgrid"></a>Nawiązywanie połączenia z usługą SendGrid

1. Przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.

1. W **SendGrid** wybierz **Konfiguruj**.

1. W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej exportu rozpoznawalną nazwę.

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Okienko konfiguracji eksportowania siatki SendGrid.":::

1. Wprowadź **Klucz interfejsu API SendGrid** [Klucz interfejsu API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Wprowadź **[Identyfikator listy SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.

1. Wybierz opcję **Połącz**, aby zainicjować połączenie z SendGrid.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Wybierz **Dalej**, aby skonfigurować eksport.

## <a name="configure-the-connector"></a>Skonfiguruj łącznik

1. W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta. Powtórz te kroki dla innych pól opcjonalnych, takich jak **Imię**, **Nazwisko**, **Kraj/Region**, **Stan**, **Miasto** i **Kod pocztowy**.

1. Wybierz segmenty, które chcesz wyeksportować. Zdecydowanie **zalecamy, aby nie eksportować łącznie ponad 100 000 profili klientów** do SendGrid. 

1. Wybierz pozycję **Zapisz**.

## <a name="export-the-data"></a>Eksportowanie danych

Możesz [eksportować dane na żądanie](export-destinations.md). Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab).

## <a name="known-limitations"></a>Znane ograniczenia

- Łącznie do 100'000 profili do SendGrid.
- Eksport do SendGrid jest ograniczony do segmentów.
- Eksportowanie do 100 000 profili do SendGrid może zająć do kilku godzin. 
- Liczba profilów, które można eksportować do SendGrid, jest zależna od kontraktu i ograniczona jego SendGrid.

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi SendGrid można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że SendGrid spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.


[!INCLUDE[footer-include](../includes/footer-banner.md)]