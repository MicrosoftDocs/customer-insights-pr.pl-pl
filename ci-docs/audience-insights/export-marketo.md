---
title: Eksportowanie danych Customer Insights do usługi Marketo
description: Dowiedz się, jak skonfigurować połączenie z Marketo.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 74d19a0448123904210c26f7b8760d00296c9cfd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597984"
---
# <a name="connector-for-marketo-preview"></a>Łącznik dla usługi Marketo (wersja zapoznawcza)

Eksportuj segmenty ujednoliconych profili klientów w celu generowania kampanii, prowadzenia marketingu e-mailowego i korzystania z określonych grup klientów w Marketo.

## <a name="prerequisites"></a>Wymagania wstępne

-   Użytkownik ma [konto usługi Marketo](https://login.marketo.com/) i odpowiadające mu poświadczenia administratora.
-   W Marketo istnieją już listy i odpowiadające im identyfikatory. Aby uzyskać więcej informacji, zobacz [listy Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Posiadasz [skonfigurowane segmenty](segments.md).
-   Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="connect-to-marketo"></a>Nawiązywanie połączenia z usługą Marketo

1. Przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.

1. W **Marketo** wybierz **Konfiguruj**.

1. W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej exportu rozpoznawalną nazwę.

1. Wprowadź **[Identyfikator klienta Marketo, klucz tajny klienta i nazwa hosta punktu końcowego REST](https://developers.marketo.com/rest-api/authentication/)**.

1. Wprowadź **[Identyfikator listy Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 

1. Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność**, a następnie wybierz **Połącz**, aby zainicjować połączenie z Marketo.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Eksportuj zrzut ekranu dla połączenia z Marketo":::

1. Wybierz **Dalej**, aby skonfigurować eksport.

## <a name="configure-the-connector"></a>Skonfiguruj łącznik

1. W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta. 

1. Można też eksportować **imię**, **Nazwisko**, **Miasto**, **Stan** i **Kraj/region** jako dodatkowe pola, aby utworzyć bardziej spersonalizowane wiadomości e-mail. Wybierz opcję **Dodaj atrybut**, aby zamapować te pola.

1. Wybierz segmenty, które chcesz wyeksportować. W sumie do maksymalnie 1 000 000 profilów klientów można wyeksportować do Marketo.

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Wybieranie pól i segmentów do wyeksportowania do Marketo":::

1. Wybierz pozycję **Zapisz**.

## <a name="export-the-data"></a>Eksportowanie danych

Możesz [eksportować dane na żądanie](export-destinations.md). Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab). W programie Marketo można znaleźć segmenty na [listach Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

## <a name="known-limitations"></a>Znane ograniczenia

- Do 1 miliona profili na eksport do Marketo.
- Eksport do Marketo jest ograniczony do segmentów.
- Eksportowanie segmentów razem z profilem 1 000 000 może potrwać do 3 godzin. 
- Liczba profilów, które można eksportować do Marketo, jest zależna od kontraktu i ograniczona jego Marketo.

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Marketo można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że Marketo spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.


[!INCLUDE[footer-include](../includes/footer-banner.md)]