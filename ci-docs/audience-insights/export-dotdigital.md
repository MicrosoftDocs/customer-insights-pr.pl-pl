---
title: Eksportowanie danych Customer Insights do usługi DotDigital
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi DotDigital.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f9302e17c07238d837dcafb82baecb5aedda17de
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231631"
---
# <a name="export-segments-to-dotdigital-preview"></a>Eksportowanie segmentów do usługi DotDigital (wersja zapoznawcza)

Eksportuj segmenty ujednoliconych profili klientów do książek adresowych DotDigital i wykorzystuj je do prowadzenia kampanii, marketingu e-mailowego i budowania segmentów klientów za pomocą DotDigital. 

## <a name="prerequisites-for-a-connection"></a>Wymagania wstępne dla połączenia

-   Masz [konto DotDigital](https://dotdigital.com/) i utworzono [użytkownika interfejsu API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user). Do utworzenia połączenia potrzebne są poświadczenia użytkownika interfejsu API
-   Istnieją książki adresowe w DotDigital i odpowiadające im identyfikatory. Identyfikator można znaleźć w adresie URL podczas wybierania i otwierania książki adresowej. Aby uzyskać więcej informacji, zobacz temat [Książka adresowa DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.
-   Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- Do 1 mln profilów klientów na eksport do usługi DotDigital.
- Eksport do DotDigital jest ograniczony do segmentów.
- Eksportowanie segmentów z łącznie 1 mln profilów klientów może zająć do 3 godzin z powodu ograniczeń po stronie dostawcy. 
- Liczba profilów klientów, które można eksportować do usługi DotDigital, zależy od kontraktu z usługą DotDigital i jest ograniczona.

## <a name="set-up-connection-to-dotdigital"></a>Konfiguruj połączenie z usługą DotDigital

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **DotDigital**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wprowadź **nazwę użytkownika i hasło usługi DotDigital**. 

1. Wprowadź **[Identyfikator książki adresowej DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.

1. Wybierz opcję **Połącz**, aby zainicjować połączenie z DotDigital.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**. 

## <a name="configure-an-export"></a>Konfigurowanie eksportu

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi DotDigital. Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.


1. W sekcji **Dopasowywanie danych** w polu **E-mail** wybierz pole reprezentujące adres e-mail klienta. Powtórz te kroki dla innych pól opcjonalnych, takich jak **Imię**, **Nazwisko**, **Imię i nazwisko**, **Płeć** i **Kod pocztowy**.

1. Wybierz segmenty, które chcesz wyeksportować. W sumie do maksymalnie 1 000 000 profilów klientów można wyeksportować do DotDigital.

1. Wybierz pozycję **Zapisz**.

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab). Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand). 
 
W DotDigital można teraz znaleźć segmenty w [książkach adresowych DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).


## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi DotDigital można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że DotDigital spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
