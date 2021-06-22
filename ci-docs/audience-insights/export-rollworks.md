---
title: Eksportowanie danych usługi Customer Insights do usługi RollWorks
description: Dowiedz się, jak skonfigurować połączenie i eksport do programu RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dce5d51ca4587b4d7a0644cc701c1826854882b5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124102"
---
# <a name="export-segments-to-rollworks-preview"></a>Eksportowanie segmentów do usługi RollWorks (wersja zapoznawcza)

Wyeksportuj segmenty ujednoliconych profilów klientów do usługi RollWorks i użyj ich w celach reklamowych. 

## <a name="prerequisites-for-a-connection"></a>Wymagania wstępne dla połączenia

-   Użytkownik ma konto [Kontakt administracyjny usługi RollWorks](https://www.rollworks.com/) i odpowiednie dane logowania administratora.
-   Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.
-   Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- Do usługi RollWorks można wyeksportować do 250 000 profili.
- Do usługi RollWorks nie można eksportować segmentów o liczbie mniejszej niż 100 profilów. 
- Eksportowanie do usługi RollWorks jest ograniczone do segmentów.
- Wyeksportowanie do 250 000 profilów do usługi RollWorks może potrwać do 10 minut. 
- Liczba profilów, które można eksportować usługi RollWorks, jest ograniczona i zależy od kontraktu użytkownika z usługą RollWorks.

## <a name="set-up-connection-to-rollworks"></a>Skonfiguruj połączenie z usługą RollWorks

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **RollWorks**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.

1. Wybierz opcję **Połącz**, aby inicjować połączenie z usługą RollWorks.

1. Wybierz opcję **Uwierzytelnij za pomocą usługi RollWorks** i podaj swoje poświadczenia administratora dla usługi RollWorks.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi RollWorks. Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.

1. Wprowadź **Identyfikator raklamodawcy w usłudze RollWorks** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta. Wymagane jest wyeksportowanie segmentów do usługi RollWorks.

1. Wybierz segmenty, które chcesz wyeksportować. Wybierz segment obejmujący co najmniej 100 członków. Nie można eksportować mniejszych segmentów. Dodatkowo maksymalny rozmiar eksportowanego segmentu wynosi 250 000 członków na operację eksportu. 

1. Wybierz pozycję **Zapisz**.

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab). Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Włączenie rozwiązania Dynamics 365 Customer Insights do przekazywania danych do usługi RollWorks umożliwia przesyłanie danych poza granicą zgodności z przepisami Dynamics 365 Customer Insights, w tym potencjalnie poufnych danych, takich jak dane osobowe. Microsoft przesyła takie dane zgodnie z instrukcjami użytkownika, ale użytkownik musi zagwarantować, że usługa RollWorks będzie spełniać wszelkie zobowiązania dotyczące prywatności lub bezpieczeństwa, jakie może mieć użytkownik. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).

Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.
