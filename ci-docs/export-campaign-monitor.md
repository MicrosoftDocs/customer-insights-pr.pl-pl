---
title: Eksportowanie segmentów do usługi Campaign Monitor (wersja zapoznawcza)
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi Campaign Monitor.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ea7431d4df5143724b5ecf2a2d747ed164fe2c29
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081592"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Eksportowanie segmentów do usługi Campaign Monitor (wersja zapoznawcza)

Wyeksportuj segmenty ujednoliconych profilów klientów do usługi Campaign Monitor i użyj ich w działaniach marketingowych.

## <a name="prerequisites"></a>Wymagania wstępne

-   Użytkownik ma konto [Kontakt administracyjny usługi Campaign Monitor](https://www.campaignmonitor.com/) i odpowiednie dane logowania administratora.
-   Masz [skonfigurowane segmenty](segments.md) w Customer Insights.
-   Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- W ramach każdego eksportu do usługi Campaign Monitor można wyeksportować maksymalnie 1 mln profilów klientów.
- Eksportowanie do usługi Campaign Monitor jest ograniczone do segmentów.
- Eksportowanie do 1 mln profilów klientów do usługi Campaign Monitor może zająć do 20 minut. 
- Liczba profilów klientów, które można eksportować do usługi Campaign Monitor, zależy od kontraktu z usługą Campaign Monitor i jest ograniczona.

## <a name="set-up-connection-to-campaign-monitor"></a>Konfiguracja połączenia z usługą Campaign Monitor

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Campaign Monitor**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.

1. Wybierz opcję **Połącz**, aby inicjować połączenie z usługą Campaign Monitor.

1. Wybierz opcję **Uwierzytelnij z usługą Campaign Monitor** i podaj swoje poświadczenia administratora dla usługi Campaign Monitor.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Campaign Monitor. Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.

1. Wprowadź swój [**Identyfikator listy usługi Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).    
   Najpierw [Wygeneruj klucz interfejsu API](https://www.campaignmonitor.com/api/getting-started/) na podstawie **Ustawień klienta** w usłudze Campaign Monitor, aby wyświetlić identyfikator listy interfejsów API.  

1. W sekcji **Dopasowywanie danych** w polu **E-mail** wybierz pole reprezentujące adres e-mail klienta. Wymagane jest wyeksportowanie segmentów do usługi Campaign Monitor.

1. Wybierz pozycję **Zapisz**.

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab). Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Włączenie rozwiązania Dynamics 365 Customer Insights do przekazywania danych do usługi Campaign Monitor umożliwia przesyłanie danych poza granicą zgodności z przepisami Dynamics 365 Customer Insights, w tym potencjalnie poufnych danych, takich jak dane osobowe. Microsoft przesyła takie dane zgodnie z instrukcjami użytkownika, ale użytkownik musi zagwarantować, że usługa Campaign Monitor będzie spełniać wszelkie zobowiązania dotyczące prywatności lub bezpieczeństwa, jakie może mieć użytkownik. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).

Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.
