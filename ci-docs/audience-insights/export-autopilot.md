---
title: Eksportowanie danych Customer Insights do usługi Autopilot
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi Autopilot.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4cceb64484e8e257a90b8cbaedff4419659bb399
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618442"
---
# <a name="export-segments-to-autopilot-preview"></a>Eksportowanie segmentów do programu Autopilot (wersja zapoznawcza)

Eksportuj segmenty ujednoliconych profili klientów do Autopilota i używaj ich do marketingu e-mailowego w Autopilocie. 

## <a name="prerequisites-for-a-connection"></a>Wymagania wstępne dla połączenia

-   Użytkownik ma [konto usługi Autopilot](https://www.autopilothq.com/) i odpowiadające mu poświadczenia administratora.
-   Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.
-   Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- W ramach każdego eksportu do rozwiązania Autopilot można wyeksportować łącznie 100 000 profilów klientów.
- Eksport do Autopilot jest ograniczony do segmentów.
- Eksportowanie do 100 000 profilów klientów do rozwiązania Autopilot może zająć do kilku godzin. 
- Liczba profilów klientów, które można eksportować do rozwiązania Autopilot, zależy od kontraktu z rozwiązaniem Autopilot i jest ograniczona.

## <a name="set-up-connection-to-autopilot"></a>Skonfiguruj połączenie z usługą Autopilot

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Autopilot**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wprowadź [klucz interfejsu API Autopilot](https://autopilot.docs.apiary.io/#).

1. Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.

1. Wybierz opcję **Połącz**, aby zainicjować połączenie z Autopilot.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Autopilot. Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.

1. W sekcji **Dopasowywanie danych** w polu **E-mail** wybierz pole reprezentujące adres e-mail klienta. Powtórz te kroki dla innych pól opcjonalnych, takich jak **Imię**, **Nazwisko**.

1. Wybierz segmenty, które chcesz wyeksportować. Zdecydowanie **zalecamy, aby nie eksportować łącznie ponad 100 000 profili klientów** do Autopilota. 

1. Wybierz pozycję **Zapisz**.

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab). Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Autopilot można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że Autopilot spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
