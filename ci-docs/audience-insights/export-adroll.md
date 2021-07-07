---
title: Eksportowanie danych aplikacji Customer Insights do rozwiązania AdRoll
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 67bfa23d56b26ae592efa4d7197713664bb02623
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304846"
---
# <a name="export-segments-to-adroll-preview"></a>Eksportowanie segmentów do usługi AdRoll (wersja zapoznawcza)

Eksportuj segmenty ujednoliconych profilów klientów do rozwiązania AdRoll i używaj ich w celach reklamowych. 

## <a name="prerequisites-for-a-connection"></a>Wymagania wstępne dla połączenia

-   Masz [konto rozwiązania AdRoll](https://www.adroll.com/) i odpowiadające mu poświadczenia administratora.
-   Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.
-   Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- Jednocześnie do AdRoll można eksportować maksymalnie 250 000 profili.
- Nie można eksportować segmentów obejmujących mniej niż 100 profilów do rozwiązania AdRoll. 
- Eksport do rozwiązania AdRoll jest ograniczony do segmentów.
- Wyeksportowanie do 250 000 profili do rozwiązania AdRoll może potrwać do 10 minut. 
- Liczba profili, które możesz wyeksportować do AdRoll jest zależna od Twojej umowy z AdRoll.

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

3. W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta. Wyeksportowanie segmentów do rozwiązania AdRoll jest wymagane.

1. Wybierz segmenty, które chcesz wyeksportować. Wybierz segment obejmujący co najmniej 100 członków. Nie można eksportować mniejszych segmentów. Dodatkowo maksymalny rozmiar eksportowanego segmentu wynosi 250 000 członków na operację eksportu. 

1. Wybierz pozycję **Zapisz**.

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab). 

Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu aplikacji Dynamics 365 Customer Insights w celu transmisji danych do usługi AdRoll można przesyłać dane spoza granicy zgodności dla aplikacji Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft prześle takie dane na Twoje polecenie, ale Ty ponosisz odpowiedzialność za zapewnienie, że usługa AdRoll spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).

Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.
