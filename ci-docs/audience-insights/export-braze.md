---
title: Eksportuj dane Customer Insights do Braze
description: Dowiedz się, jak skonfigurować połączenie i eksportować do programu Braze.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8d7cf95c1f157c771b2d655346464e5af03d73b9
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2022
ms.locfileid: "8524177"
---
# <a name="export-segment-lists-to-braze-preview"></a>Eksportowanie list segmentów do Braze (wersja zapoznawcza)

Eksportuj segmenty ujednoliconych profili klientów do Braze i wykorzystuj je do działań marketingowych.

## <a name="prerequisites"></a>Wymagania wstępne

-   Użytkownik ma [konto Braze](https://www.braze.com/) i odpowiednie poświadczenia administratora.
-   Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.
-   Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail i identyfikator klienta Braze. 

## <a name="known-limitations"></a>Znane ograniczenia

- Eksportowanie do Braze jest ograniczone do segmentów.
- Eksportowanie do 1 mln profilów klientów do usługi Braze może zająć do 40 minut. 
- Liczba profilów klientów, które można eksportować do usługi Braze, zależy od kontraktu z usługą Braze i jest ograniczona.

## <a name="set-up-connection-to-braze"></a>Skonfiguruj połączenie z usługą Braze

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Braze**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Podaj [klucz interfejsu Braze API](https://www.braze.com/docs/api/basics/), aby kontynuować logowanie. 

1. Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.

1. Wybierz opcję **Połącz**, aby zainicjować połączenie z Braze.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji Braze. Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.  

3. W sekcji **Dopasowanie danych** w polu **E-mail** wybierz pole reprezentujące adres e-mail klienta, w polu „Identyfikator klienta” wybierz pole reprezentujące identyfikator Braze klienta. Wymagane jest wyeksportowanie segmentów do Braze. Segmenty w Braze zostaną utworzone z taką samą nazwą segmentu jak w Dynamics 365 Customer Insights. Można wybrać dodatkowe, opcjonalne pola służące do dopasowania danych. 

1. Wybierz pozycję **Zapisz**.

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab). Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Braze można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft przekaże takie dane na twoje polecenie, ale to ty jesteś odpowiedzialny za zapewnienie, że Braze spełnia wszelkie zobowiązania dotyczące prywatności i bezpieczeństwa, jakie możesz mieć. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).

Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.
