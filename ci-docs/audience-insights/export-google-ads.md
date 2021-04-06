---
title: Eksportowanie danych Customer Insights do usługi Google ads
description: Dowiedz się, jak skonfigurować połączenie z reklamą usługi Google ads.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d9a25af3913e755cccec745c532b35aef3cccf9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598260"
---
# <a name="connector-for-google-ads-preview"></a>Łącznik dla usługi Google Ads (wersja zapoznawcza)

Eksportuj segmenty ujednoliconych profili klientów na listę odbiorców Google Ads i używaj ich do reklamowania się w wyszukiwarce Google, Gmailu, YouTube i sieci reklamowej Google. 

## <a name="prerequisites"></a>Wymagania wstępne

-   Użytkownik ma [konto usługi Google Ads](https://ads.google.com/) i odpowiadające mu poświadczenia administratora.
-   W Google Ads istnieją już odbiorcy i odpowiadające im identyfikatory. Aby uzyskać więcej informacji, zobacz temat [Odbiorcy Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Posiadasz [skonfigurowane segmenty](segments.md)
-   Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pola reprezentujące adresy e-mail, imię i nazwisko

## <a name="connect-to-google-ads"></a>Połącz z usługą Google Ads

1. Przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.

1. W **Google Ads** wybierz **Konfiguruj**.

1. W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej exportu rozpoznawalną nazwę.

1. Wpisz **[Identyfikator klienta usługi Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Wprowadź **[zatwierdzony token dewelopera usługi Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.

1. Wprowadź **[identyfikator odbiorcy usługi Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** i wybierz pozycję **Połącz**, aby zainicjować połączenie z usługą Google Ads.

1. Wybierz **Uwierzytelnianie za pomocą usługi Google Ads** i przekaż swoje poświadczenia w usłudze Google AD.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Eksportuj zrzut ekranu dla połączenia z Google Ads":::

1. Wybierz **Dalej**, aby skonfigurować eksport.

## <a name="configure-the-connector"></a>Skonfiguruj łącznik

1. W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta. Powtórz te same kroki dla pól **Imię** i **Nazwisko**.

1. Wybierz segmenty, które chcesz wyeksportować. W sumie do maksymalnie 1 000 000 profilów klientów można wyeksportować do Google Ads.

1. Wybierz pozycję **Zapisz**.

## <a name="export-the-data"></a>Eksportowanie danych

Możesz [eksportować dane na żądanie](export-destinations.md). Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab). W usłudze Google Ads można teraz znaleźć segmenty w [Odbiorcy Google ads](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>Znane ograniczenia

- Do 1 miliona profili na eksport do Google Ads.
- Eksport do Google Ads jest ograniczony do segmentów.
- Eksportowanie segmentów zawierających łącznie 1 milion profili może zająć do 5 minut ze względu na ograniczenia po stronie dostawcy. 
- Dopasowanie w usłudze Google Ads może potrwać do 48 godzin.

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Google Ads można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że Google Ads spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.


[!INCLUDE[footer-include](../includes/footer-banner.md)]