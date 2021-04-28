---
title: Eksportowanie danych Customer Insights do usługi Marketo
description: Dowiedz się, jak skonfigurować połączenie i eksport do programu Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759834"
---
# <a name="export-segments-to-marketo-preview"></a>Eksportowanie segmentów do programu Marketo (wersja zapoznawcza)

Eksportuj segmenty ujednoliconych profili klientów w celu generowania kampanii, prowadzenia marketingu e-mailowego i korzystania z określonych grup klientów w Marketo.

## <a name="prerequisites-for-connection"></a>Wymagania wstępne dla połączenia

-   Użytkownik ma [konto usługi Marketo](https://login.marketo.com/) i odpowiadające mu poświadczenia administratora.
-   W Marketo istnieją już listy i odpowiadające im identyfikatory. Aby uzyskać więcej informacji, zobacz [listy Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Posiadasz [skonfigurowane segmenty](segments.md).
-   Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- Do 1 miliona profili na eksport do Marketo.
- Eksport do Marketo jest ograniczony do segmentów.
- Eksportowanie segmentów razem z profilem 1 000 000 może potrwać do 3 godzin. 
- Liczba profilów, które można eksportować do Marketo, jest zależna od kontraktu i ograniczona jego Marketo.

## <a name="set-up-connection-to-marketo"></a>Skonfiguruj połączenie z usługą Marketo

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Marketo**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wprowadź **[Identyfikator klienta Marketo, klucz tajny klienta i nazwa hosta punktu końcowego REST](https://developers.marketo.com/rest-api/authentication/)**.

1. Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność**, a następnie wybierz **Połącz**, aby zainicjować połączenie z Marketo.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Marketo. Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.

1. Wprowadź **[Identyfikator listy Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 

1. W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta. 

1. Opcjonalnie możesz wyeksportować **Imię**, **Nazwisko**, **Miejscowość**, **Województwo** i **Kraj/region**, aby utworzyć bardziej spersonalizowane wiadomości e-mail. Wybierz opcję **Dodaj atrybut**, aby zamapować te pola.

1. Wybierz segmenty, które chcesz wyeksportować. W sumie do maksymalnie 1 000 000 profilów klientów można wyeksportować do Marketo.

1. Wybierz pozycję **Zapisz**.

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab). Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand). W programie Marketo można znaleźć segmenty na [listach Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).


## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Marketo można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że Marketo spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.


[!INCLUDE[footer-include](../includes/footer-banner.md)]