---
title: Eksportowanie Customer Insights do magazynu obiektów Microsoft Advertising
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124531"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Eksportowanie segmentów do programu Microsoft Advertising (wersja zapoznawcza)

Eksport segmentów Customer Insights do Microsoft Advertising w celu stworzenia grup odbiorców Customer Match. Grupy odbiorców mogą być wykorzystania w kampaniach reklamowych.

## <a name="prerequisites"></a>Wymagania wstępne

-   Użytkownik ma [konto Microsoft Advertising](https://ads.microsoft.com/) i odpowiednie dane logowania administratora.
-   Zaakceptowałeś warunki korzystania z Customer Match. 
-   [Segmenty skonfigurowane](segments.md) w wynikach analizy danych odbiorców.
-   Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole z adresem e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- Do programu Microsoft Advertising można wyeksportować maksymalnie 500 tysięcy profili.
- Eksportowanie do usługi Microsoft Advertising jest ograniczone do segmentów.
- Wyeksportowanie do 500 tysięcy profilów do usługi Microsoft Advertising może potrwać do 10 minut. 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>Skonfiguruj połączenie z usługą Microsoft Advertising

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Microsoft Advertising**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Wartość domyślna to administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.

1. Wybierz opcję **Połącz**, aby inicjować połączenie z usługą Microsoft Advertising.

1. Wybierz opcję **Uwierzytelnij z usługą Microsoft Advertising** i podaj swoje poświadczenia administratora dla usługi Microsoft Advertising.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Microsoft Advertising. Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.

1. Wybierz segmenty do eksportu. Odbiorcy Customer Match w Microsoft Advertising są automatycznie tworzeni z nazwą segmentów wybranych do eksportu. W przypadku każdego z segmentów będzie to Customer Match odbiorcy. 

1. Wprowadź swój **Identyfikator klienta i konta Microsoft Advertising**. Możesz znaleźć ID klienta (`cid`) i ID konta (`aid`) w parametrach adresu URL po zalogowaniu w Microsoft Advertising.

1. W sekcji **Dopasowywanie danych** w polu **E-mail** wybierz pole w ujednoliconym profilu klienta z adresem e-mail klienta. Wymagane jest wyeksportowanie segmentów do usługi Microsoft Advertising.

1. Wybierz pozycję **Zapisz**.

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab). Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Włączenie rozwiązania Dynamics 365 Customer Insights do przekazywania danych do usługi Microsoft Advertising umożliwia przesyłanie danych poza granicą zgodności z przepisami Dynamics 365 Customer Insights, w tym potencjalnie poufnych danych, takich jak dane osobowe. Microsoft przesyła takie dane zgodnie z instrukcjami użytkownika, ale użytkownik musi zagwarantować, że usługa Microsoft Advertising będzie spełniać wszelkie zobowiązania dotyczące prywatności lub bezpieczeństwa, jakie może mieć użytkownik. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).

Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.
