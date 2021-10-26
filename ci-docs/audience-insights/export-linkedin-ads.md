---
title: Eksportowanie danych usługi Customer Insights do usługi LinkedIn Ads
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi LinkedIn Ads.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 948a7e980df5714034009c92282e78cf2bdcb231
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618304"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Eksportowanie segmentów do usługi LinkedIn Ads (wersja zapoznawcza)

Eksportuj segmenty ujednoliconych profili klientów do LinkedIn Ads, aby tworzyć dopasowane grupy Matched Audiences. Wykorzystaj dopasowane grupy Matched Audiences do targetowania firm i kontaktów.

## <a name="prerequisites"></a>Wymagania wstępne

-   Użytkownik ma [konto LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) i odpowiednie dane logowania administratora.
-   Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.
-   Profile klientów w wyeksportowanych segmentach zawierają pole z adresem e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- W ramach każdego eksportu do usługi LinkedIn Ads można wyeksportować maksymalnie 100 000 profilów klientów.
- Eksportowanie do usługi LinkedIn Ads jest ograniczone do segmentów.
- Eksportowanie do 100 000 profilów klientów do usługi LinkedIn Ads może zająć do 10 minut. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>Skonfiguruj połączenie z usługą LinkedIn Ads

1. W analizie odbiorcy przejdź do pozycji **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **LinkedIn Ads**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Należy podać [Identyfikator konta LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).

1. Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.

1. Wybierz opcję **Połącz**, aby inicjować połączenie z usługą Campaign Monitor.

1. Wybierz opcję **Uwierzytelnij za pomocą usługi LinkedIn** i podaj swoje poświadczenia administratora dla usługi LinkedIn Campaign Manager.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi LinkedIn Ads. Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.

1. Możesz określić, czy chcesz eksportować dane, aby [ukierunkowywać kontakty](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting), czy [ukierunkowywać przedsiębiorstwa](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) w usłudze LinkedIn. 

1. W sekcji **Dopasowywanie danych**, aby ukierunkowywać kontakty, wybierz co najmniej jedno pole reprezentujące adres e-mail klienta, identyfikator Apple Ad ID, identyfikator Google Ad ID, identyfikator użytkownika Google lub imię i nazwisko. Jeśli wybierzesz kierowanie do firm, wybierz co najmniej jedno pole reprezentujące nazwę firmy, domenę poczty e-mail, adres URL strony LinkedIn, symbol giełdowy lub witrynę internetową. W celu dalszego zdefiniowania eksportu można wybrać pola dodatkowe. 

1. Wybierz segmenty, które chcesz wyeksportować. Matched Audiences w LinkedIn Campaign Manager zostaną automatycznie utworzone z nazwą segmentów, które wybrałeś do eksportu. W przypadku każdego z segmentów będzie to oddzielne dopasowanie odbiorcy. 

1. Wybierz pozycję **Zapisz**.

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab). Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Włączenie rozwiązania Dynamics 365 Customer Insights do przekazywania danych do usługi LinkedIn Ads umożliwia przesyłanie danych poza granicą zgodności z przepisami Dynamics 365 Customer Insights, w tym potencjalnie poufnych danych, takich jak dane osobowe. Microsoft przesyła takie dane zgodnie z instrukcjami użytkownika, ale użytkownik musi zagwarantować, że usługa LinkedIn Ads będzie spełniać wszelkie zobowiązania dotyczące prywatności lub bezpieczeństwa, jakie może mieć użytkownik. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).

Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.
