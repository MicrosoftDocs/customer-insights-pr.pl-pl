---
title: Eksportowanie danych usługi Customer Insights do usługi Omnisend
description: Dowiedz się, jak skonfigurować połączenie i eksport do programu Omnisend.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5496efa075fa3474c579366d143ea55e86ec3995
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/08/2021
ms.locfileid: "7619041"
---
# <a name="export-segments-to-omnisend-preview"></a>Eksportowanie segmentów do programu Omnisend (wersja zapoznawcza)

Wyeksportuj segmenty ujednoliconych profilów klientów do usługi Omnisend i użyj ich w działaniach marketingowych.

## <a name="prerequisites"></a>Wymagania wstępne

-   Użytkownik ma konto [Kontakt administracyjny usługi Omnisend](https://www.omnisend.com/) i odpowiednie dane logowania administratora.
-   Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.
-   Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- W przypadku eksportu do usługi Omnisend można wyeksportować do 1 mln profilów klientów, co może potrwać do 4 godzin.
- Eksportowanie do usługi Omnisend jest ograniczone do segmentów.
- Liczba profilów klientów, które można eksportować do usługi Omnisend, zależy od kontraktu z usługą Omnisend i jest ograniczona.

## <a name="set-up-connection-to-omnisend"></a>Skonfiguruj połączenie z usługą Omnisend

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Omnisend**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Domyślnie to tylko administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wprowadź [klucz interfejsu API Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).

1. Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.

1. Wybierz opcję **Połącz**, aby inicjować połączenie z usługą Omnisend.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Omnisend. Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.

1. W sekcji **Dopasowywanie danych** w polu **E-mail** wybierz pole reprezentujące adres e-mail klienta. Wymagane jest wyeksportowanie segmentów do usługi Omnisend. Opcjonalnie możesz wyeksportować Imię, Nazwisko, Adres, Kraj/region, Województwo, Miasto i Kod pocztowy aby utworzyć bardziej spersonalizowane wiadomości e-mail. Wybierz opcję **Dodaj atrybut**, aby zamapować te pola.

1. Wybierz pozycję **Zapisz**.

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab). Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Włączenie rozwiązania Dynamics 365 Customer Insights do przekazywania danych do usługi Ommisend umożliwia przesyłanie danych poza granicą zgodności z przepisami Dynamics 365 Customer Insights, w tym potencjalnie poufnych danych, takich jak dane osobowe. Microsoft przesyła takie dane zgodnie z instrukcjami użytkownika, ale użytkownik musi zagwarantować, że usługa Ommisend będzie spełniać wszelkie zobowiązania dotyczące prywatności lub bezpieczeństwa, jakie może mieć użytkownik. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).

Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.
