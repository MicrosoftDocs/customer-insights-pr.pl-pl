---
title: Eksportowanie danych usługi Customer Insights do usługi Constant Contact
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi Constant Contact.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8841945814397ffa70c56638a8bed25499c1a06f
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226416"
---
# <a name="export-segments-to-constant-contact-preview"></a>Eksportowanie segmentów do usługi Constant Contact (wersja zapoznawcza)

Wyeksportuj segmenty ujednoliconych profilów klientów do usługi Constant Contact i użyj ich w działaniach marketingowych. 

## <a name="prerequisites-for-a-connection"></a>Wymagania wstępne dla połączenia

-   Użytkownik ma konto [Kontakt administracyjny usługi Constant Contact](https://www.constantcontact.com/account-home) i odpowiednie dane logowania administratora.
-   Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.
-   Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- W ramach każdego eksportu do usługi Constant Contact można wyeksportować maksymalnie 1 mln profilów klientów.
- Eksportowanie do usługi Constant Contact jest ograniczone do segmentów.
- Eksportowanie do 1 mln profilów klientów do usługi Constant Contactr może zająć do 1 godziny. 
- Liczba profilów klientów, które można eksportować do usługi Constant Contact, zależy od kontraktu z usługą Constant Contactl i jest ograniczona.

## <a name="set-up-connection-to-constant-contact"></a>Konfiguracja połączenia z usługą Constant Contact

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Constant Contact**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.

1. Wybierz opcję **Połącz**, aby inicjować połączenie z usługą Constant Contact.

1. Wybierz pozycję **Uwierzytelnij przy stałym kontakcie** i podaj poświadczenia administratora dla stałego kontaktu. 

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Constant Contact. Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.

1. Wprowadź swój [**Identyfikator listy usługi Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists). Otwórz listę w usłudze Constant Contact, aby znaleźć identyfikator listy w adresie URL.

1. W sekcji **Dopasowywanie danych** w polu **E-mail** wybierz pole reprezentujące adres e-mail klienta. Wymagane jest wyeksportowanie segmentów do usługi Constant Contact.

1. Można też eksportować imię i Nazwisko jako dodatkowe pola, aby utworzyć bardziej spersonalizowane wiadomości e-mail. Wybierz opcję **Dodaj atrybut**, aby zamapować te pola.

1. Wybierz segmenty, które chcesz wyeksportować.

1. Wybierz pozycję **Zapisz**.

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab). Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Włączenie rozwiązania Dynamics 365 Customer Insights do przekazywania danych do usługi Constant Contact umożliwia przesyłanie danych poza granicą zgodności z przepisami Dynamics 365 Customer Insights, w tym potencjalnie poufnych danych, takich jak dane osobowe. Microsoft przesyła takie dane zgodnie z instrukcjami użytkownika, ale użytkownik musi zagwarantować, że usługa Constant Contact będzie spełniać wszelkie zobowiązania dotyczące prywatności lub bezpieczeństwa, jakie może mieć użytkownik. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).

Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.
