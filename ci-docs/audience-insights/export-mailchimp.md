---
title: Eksportowanie danych Customer Insights do usługi Mailchimp
description: Dowiedz się, jak skonfigurować połączenie i eksport do programu Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 35848998e738c7ecc1642f2b75912ff78d85f79e
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976168"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a>Eksportowanie list segmentów do usługi Mailchimp (wersja zapoznawcza)

Wyeksportowane segmenty zunifikowanych profilów klientów umożliwiają MailChimp tworzenie biuletynów i kampanii za pośrednictwem poczty e-mail.

## <a name="prerequisites-for-connection"></a>Wymagania wstępne dla połączenia

-   Użytkownik ma [konto usługi Mailchimp](https://mailchimp.com/) i odpowiadające mu poświadczenia administratora.
-   W Mailchimp istnieją już odbiorcy i odpowiadające im identyfikatory. Aby uzyskać więcej informacji, zobacz temat [Odbiorcy Mailchimp](https://mailchimp.com/help/create-audience/).
-   Posiadasz [skonfigurowane segmenty](segments.md)
-   Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- Do 1 miliona profili na eksport do Mailchimp.
- Eksport do Mailchimp jest ograniczony do segmentów.
- Eksportowanie segmentów z 1 milionem profili może potrwać do trzech godzin. 
- Liczba profilów, które można eksportować do Mailchimp, jest zależna od kontraktu i ograniczona jego Mailchimp.

## <a name="set-up-connection-to-mailchimp"></a>Skonfiguruj połączenie z usługą Mailchimp

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Autopilot**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.

1. Wybierz opcję **Połącz**, aby inicjować połączenie z usługą Mailchimp.

1. Wybierz **Uwierzytelnianie za pomocą usługi Mailchimp** i przekaż swoje poświadczenia w usłudze Mailchimp.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**. 

## <a name="configure-the-connector"></a>Skonfiguruj łącznik

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane**> **Eksporty**.

1. Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Mailchimp. Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.

1. Wpisz swój **[Identyfikator odbiorcy usługi MailChimp](https://mailchimp.com/help/find-audience-id/)**

3. W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta. 

1. Opcjonalnie możesz wyeksportować **Imię** i **Nazwisko**, aby utworzyć bardziej spersonalizowane wiadomości e-mail. Wybierz opcję **Dodaj atrybut**, aby zamapować te pola.

1. Wybierz segmenty, które chcesz wyeksportować. W sumie do maksymalnie 1 000 000 profilów klientów można wyeksportować do Mailchimp.

1. Wybierz pozycję **Zapisz**.

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab). Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Mailchimp można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że Mailchimp spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
