---
title: Eksportowanie danych Customer Insights do usługi DotDigital
description: Dowiedz się, jak skonfigurować połączenie z DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed6bd40e8575fc90258f79f60abffe54f136d274
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644461"
---
# <a name="connector-for-dotdigital-preview"></a>Łącznik dla usługi DotDigital (wersja zapoznawcza)

Eksportuj segmenty ujednoliconych profili klientów do książek adresowych DotDigital i wykorzystuj je do prowadzenia kampanii, marketingu e-mailowego i budowania segmentów klientów za pomocą DotDigital. 

## <a name="prerequisites"></a>Wymagania wstępne

-   Użytkownik ma [konto usługi DotDigital](https://dotdigital.com/) i odpowiadające mu poświadczenia administratora.
-   Istnieją książki adresowe w DotDigital i odpowiadające im identyfikatory. Identyfikator można znaleźć w adresie URL podczas wybierania i otwierania książki adresowej. Aby uzyskać więcej informacji, zobacz temat [Książka adresowa DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.
-   Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="connect-to-dotdigital"></a>Nawiązywanie połączenia z DotDigital

1. Przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.

1. W **DotDigital** wybierz **Konfiguruj**.

1. W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej exportu rozpoznawalną nazwę.

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Okienko konfiguracji dla eksportu DotDigital.":::

1. Wprowadź **Nazwę użytkownika i hasło DotDigital**.

1. Wprowadź **[Identyfikator książki adresowej DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.

1. Wybierz opcję **Połącz**, aby zainicjować połączenie z DotDigital.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Wybierz **Dalej**, aby skonfigurować eksport.

## <a name="configure-the-connector"></a>Skonfiguruj łącznik

1. W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta. Powtórz te kroki dla innych pól opcjonalnych, takich jak **Imię**, **Nazwisko**, **Imię i nazwisko**, **Płeć** i **Kod pocztowy**.

1. Wybierz segmenty, które chcesz wyeksportować. W sumie do maksymalnie 1 000 000 profilów klientów można wyeksportować do DotDigital.

1. Wybierz pozycję **Zapisz**.

## <a name="export-the-data"></a>Eksportowanie danych

Możesz [eksportować dane na żądanie](export-destinations.md). Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab). W DotDigital można teraz znaleźć segmenty w [książkach adresowych DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

## <a name="known-limitations"></a>Znane ograniczenia

- Do 1 miliona profili na eksport do DotDigital.
- Eksport do DotDigital jest ograniczony do segmentów.
- Eksportowanie segmentów zawierających łącznie 1 milion profili może zająć do 3 godzin ze względu na ograniczenia po stronie dostawcy. 
- Liczba profilów, które można eksportować do DotDigital, jest zależna od kontraktu i ograniczona jego DotDigital.

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi DotDigital można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że DotDigital spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.
