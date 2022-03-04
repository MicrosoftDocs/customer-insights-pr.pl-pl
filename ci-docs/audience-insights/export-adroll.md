---
title: Eksportowanie danych aplikacji Customer Insights do rozwiązania AdRoll
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi AdRoll.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3a318750077c71a17e5a47c40722f6153e6640f3
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227633"
---
# <a name="export-segments-to-adroll-preview"></a>Eksportowanie segmentów do usługi AdRoll (wersja zapoznawcza)

Eksportuj segmenty ujednoliconych profilów klientów do rozwiązania AdRoll i używaj ich w celach reklamowych. 

## <a name="prerequisites-for-a-connection"></a>Wymagania wstępne dla połączenia

-   Masz [konto rozwiązania AdRoll](https://www.adroll.com/) i odpowiadające mu poświadczenia administratora.
-   Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.
-   Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- Jednocześnie można wyeksportować do 250 000 profilów klientów do usługi AdRoll.
- Nie można eksportować segmentów, w których jest mniej niż 100 profilów klientów, do usługi AdRoll. 
- Eksport do rozwiązania AdRoll jest ograniczony do segmentów.
- Eksportowanie do 250 000 profilów klientów do usługi AdRoll może zająć do 10 minut. 
- Liczba profilów klientów, które można eksportować do usługi AdRoll, zależy od kontraktu z usługą AdRoll i jest ograniczona.

## <a name="set-up-connection-to-adroll"></a>Skonfiguruj połączenie z usługą AdRoll

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **AdRoll**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.

1. Wybierz opcję **Połącz**, aby zainicjować połączenie z rozwiązaniem AdRoll.

1. Wybierz opcję **Uwierzytelnij za pomocą rozwiązania AdRoll** i podaj poświadczenia administratora dla rozwiązania AdRoll. 

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi AdRoll. Jeśli nie widzisz tej nazwy sekcji, to znaczy, że nie masz dostępu do żadnych połączeń tego typu.

1. Wprowadź identyfikator **Reklamodawcy AdRoll**. Aby uzyskać więcej informacji, zobacz [Profile reklamodawców AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

1. W sekcji **Dopasowywanie danych** w polu **E-mail** wybierz pole reprezentujące adres e-mail klienta. Wyeksportowanie segmentów do rozwiązania AdRoll jest wymagane.

1. Wybierz segmenty, które chcesz wyeksportować. Wybierz segment obejmujący co najmniej 100 członków. Nie można eksportować mniejszych segmentów. Dodatkowo maksymalny rozmiar eksportowanego segmentu wynosi 250 000 członków na operację eksportu. 

1. Wybierz pozycję **Zapisz**.

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab). 

Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu aplikacji Dynamics 365 Customer Insights w celu transmisji danych do usługi AdRoll można przesyłać dane spoza granicy zgodności dla aplikacji Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft prześle takie dane na Twoje polecenie, ale Ty ponosisz odpowiedzialność za zapewnienie, że usługa AdRoll spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).

Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.
