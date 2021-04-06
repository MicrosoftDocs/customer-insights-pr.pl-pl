---
title: Eksportowanie danych Customer Insights do usługi Mailchimp
description: Dowiedz się, jak skonfigurować połączenie z Mailchimp.
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598214"
---
# <a name="connector-for-mailchimp-preview"></a>Łącznik dla usługi Mailchimp (wersja zapoznawcza)

Wyeksportowane segmenty zunifikowanych profilów klientów umożliwiają MailChimp tworzenie biuletynów i kampanii za pośrednictwem poczty e-mail.

## <a name="prerequisites"></a>Wymagania wstępne

-   Użytkownik ma [konto usługi Mailchimp](https://mailchimp.com/) i odpowiadające mu poświadczenia administratora.
-   W Mailchimp istnieją już odbiorcy i odpowiadające im identyfikatory. Aby uzyskać więcej informacji, zobacz temat [Odbiorcy Mailchimp](https://mailchimp.com/help/create-audience/).
-   Posiadasz [skonfigurowane segmenty](segments.md)
-   Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="connect-to-mailchimp"></a>Połącz z usługą Mailchimp

1. Przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.

1. W **Mailchimp** wybierz **Konfiguruj**.

1. W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej exportu rozpoznawalną nazwę.

1. Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.

1. Wprowadź **[identyfikator odbiorcy usługi Mailchimp](https://mailchimp.com/help/find-audience-id/)** i wybierz pozycję **Połącz**, aby zainicjować połączenie z usługą Mailchimp.

1. Wybierz **Uwierzytelnianie za pomocą usługi Mailchimp** i przekaż swoje poświadczenia w usłudze Mailchimp.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Eksportuj zrzut ekranu dla połączenia z Mailchimp":::

1. Wybierz **Dalej**, aby skonfigurować eksport.

## <a name="configure-the-connector"></a>Skonfiguruj łącznik

1. W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta. 

1. Można też eksportować **imię** i **Nazwisko** jako dodatkowe pola, aby utworzyć bardziej spersonalizowane wiadomości e-mail. Wybierz opcję **Dodaj atrybut**, aby zamapować te pola.

1. Wybierz segmenty, które chcesz wyeksportować. W sumie do maksymalnie 1 000 000 profilów klientów można wyeksportować do Mailchimp.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Wybieranie pól i segmentów do wyeksportowania do Mailchimp":::

1. Wybierz pozycję **Zapisz**.

## <a name="export-the-data"></a>Eksportowanie danych

Możesz [eksportować dane na żądanie](export-destinations.md). Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab). W Mailchimp można znaleźć segmenty na [odbiorcy Mailchimp](https://mailchimp.com/help/create-audience/).

## <a name="known-limitations"></a>Znane ograniczenia

- Do 1 miliona profili na eksport do Mailchimp.
- Eksport do Mailchimp jest ograniczony do segmentów.
- Eksportowanie segmentów zawierających łącznie 1 milion profili może zająć do trzech godzin ze względu na ograniczenia po stronie dostawcy. 
- Liczba profilów, które można eksportować do Mailchimp, jest zależna od kontraktu i ograniczona jego Mailchimp.

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Mailchimp można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że Mailchimp spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.


[!INCLUDE[footer-include](../includes/footer-banner.md)]