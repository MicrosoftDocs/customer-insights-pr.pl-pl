---
title: Eksportowanie danych Customer Insights do usługi DotDigital
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d08504856e1c673ef32433b83bf491d7f4e8cee4
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976859"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a>Eksportowanie list segmentów do usługi DotDigital (wersja zapoznawcza)

Eksportuj segmenty ujednoliconych profili klientów do książek adresowych DotDigital i wykorzystuj je do prowadzenia kampanii, marketingu e-mailowego i budowania segmentów klientów za pomocą DotDigital. 

## <a name="prerequisites-for-a-connection"></a>Wymagania wstępne dla połączenia

-   Użytkownik ma [konto usługi DotDigital](https://dotdigital.com/) i odpowiadające mu poświadczenia administratora.
-   Istnieją książki adresowe w DotDigital i odpowiadające im identyfikatory. Identyfikator można znaleźć w adresie URL podczas wybierania i otwierania książki adresowej. Aby uzyskać więcej informacji, zobacz temat [Książka adresowa DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.
-   Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- Do 1 miliona profili na eksport do DotDigital.
- Eksport do DotDigital jest ograniczony do segmentów.
- Eksportowanie segmentów zawierających łącznie 1 milion profili może zająć do 3 godzin ze względu na ograniczenia po stronie dostawcy. 
- Liczba profilów, które można eksportować do DotDigital, jest zależna od kontraktu i ograniczona jego DotDigital.

## <a name="set-up-connection-to-dotdigital"></a>Konfiguruj połączenie z usługą DotDigital

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **DotDigital**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wprowadź **Nazwę użytkownika i hasło DotDigital**.

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


1. W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta. Powtórz te kroki dla innych pól opcjonalnych, takich jak **Imię**, **Nazwisko**, **Imię i nazwisko**, **Płeć** i **Kod pocztowy**.

1. Wybierz segmenty, które chcesz wyeksportować. W sumie do maksymalnie 1 000 000 profilów klientów można wyeksportować do DotDigital.

1. Wybierz pozycję **Zapisz**.

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab). Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand). 
 
W DotDigital można teraz znaleźć segmenty w [książkach adresowych DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).


## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi DotDigital można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że DotDigital spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
