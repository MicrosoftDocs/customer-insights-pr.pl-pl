---
title: Eksportowanie segmentów do programu SendGrid (wersja zapoznawcza)
description: Dowiedz się, jak skonfigurować połączenie i eksport do programu SendGrid.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 669f0fb48b095f6a9faeebf257ee9df3d1c580c7
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081665"
---
# <a name="export-segments-to-sendgrid-preview"></a>Eksportowanie segmentów do programu SendGrid (wersja zapoznawcza)

Eksportuj segmenty ujednoliconych profili klientów do list kontaktów SendGrid i używaj ich do kampanii i marketingu e-mailowego w SendGrid. 

## <a name="prerequisites-for-a-connection"></a>Wymagania wstępne dla połączenia

-   Użytkownik ma [konto usługi SendGrid](https://sendgrid.com/) i odpowiadające mu poświadczenia administratora.
-   Istnieją listy kontaktów w SendGrid i odpowiadające im identyfikatory. Aby uzyskać więcej informacji, zobacz temat [SendGrid — Zarządzanie kontaktami](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Masz [skonfigurowane segmenty](segments.md) w Customer Insights.
-   Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- Do 100 000 profilów klientów łącznie do usługi SendGrid.
- Eksport do SendGrid jest ograniczony do segmentów.
- Eksportowanie do 100 000 profilów klientów do rozwiązania SendGrid może zająć do kilku godzin. 
- Liczba profilów klientów, które można eksportować do usługi SendGrid, zależy od kontraktu z usługą SendGrid i jest ograniczona.

## <a name="set-up-connection-to-sendgrid"></a>Skonfiguruj połączenie z usługą SendGrid

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **SendGrid**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wprowadź **Klucz interfejsu API SendGrid** [Klucz interfejsu API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.

1. Wybierz opcję **Połącz**, aby zainicjować połączenie z SendGrid.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi SendGrid. Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.

1. Wprowadź **[Identyfikator listy SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. W sekcji **Dopasowywanie danych** w polu **E-mail** wybierz pole reprezentujące adres e-mail klienta. Powtórz te kroki dla innych pól opcjonalnych, takich jak **Imię**, **Nazwisko**, **Kraj/Region**, **Stan**, **Miasto** i **Kod pocztowy**.

1. Wybierz segmenty, które chcesz wyeksportować. Zdecydowanie **zalecamy, aby nie eksportować łącznie ponad 100 000 profili klientów** do SendGrid. 

1. Wybierz pozycję **Zapisz**.

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab). Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi SendGrid można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że SendGrid spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.


[!INCLUDE [footer-include](includes/footer-banner.md)]
