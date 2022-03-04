---
title: Eksportowanie danych usługi Customer Insights do Klaviyo
description: Dowiedz się, jak skonfigurować połączenie i wyeksportować je do usługi Klaviyo.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 027aee70d9fdab0a92d7fd99209a6ac2ca3cc361
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225481"
---
# <a name="export-segment-lists-to-klaviyo-preview"></a>Eksportowanie list segmentów do Klaviyo (wersja zapoznawcza)

Eksportuj segmenty ujednoliconych profili klientów do Klaviyo i wykorzystaj je w działaniach marketingowych.

## <a name="prerequisites"></a>Wymagania wstępne

-   Użytkownik ma [konto Klaviyo](https://www.klaviyo.com/) i odpowiednie uprawnienia administratora.
-   Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.
-   Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- W ramach każdego eksportu do usługi Klaviyo można wyeksportować maksymalnie 100 000 profilów klientów.
- Eksport do Klaviyo jest ograniczony do segmentów.
- Eksportowanie do 1 mln profilów klientów do usługi Klaviyo może zająć do 20 minut. 
- Liczba profilów klientów, które można eksportować do usługi Klaviyo, zależy od kontraktu z usługą Klaviyo i jest ograniczona.

## <a name="set-up-connection-to-klaviyo"></a>Skonfiguruj połączenie z usługą Klaviyo

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Klaviyo**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Aby kontynuować logowanie, należy podać [klucz interfejsu API Klaviyo](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys). 

1. Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.

1. Wybierz opcję **Połącz**, aby zainicjować połączenie z Klaviyo.

1. Wybierz pozycję **Uwierzytelnij za pomocą Klaviyo** i podaj poświadczenia administratora dla Klaviyo.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.

1. W polu **Połączenie do eksportu** wybierz połączenie z sekcji Klaviyo. Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.

1. Wprowadź [**Identyfikator listy usługi Klaviyo**](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).     

3. W sekcji **Dopasowywanie danych** w polu **E-mail** wybierz pole reprezentujące adres e-mail klienta. Jest on niezbędny do eksportu segmentów do Klaviyo.

1. Wybierz pozycję **Zapisz**.

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab). Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Włączenie Dynamics 365 Customer Insights w celu przekazywania danych do usługi Klaviyo umożliwia przesyłanie danych poza granice obszaru zgodności dla Dynamics 365 Customer Insights, w tym potencjalnie poufne dane, takie jak dane osobiste. Microsoft będzie przekazywać takie dane zgodnie z Twoimi instrukcjami, ale to Ty jesteś odpowiedzialny za zapewnienie, że Klaviyo spełnia wszelkie zobowiązania dotyczące prywatności i bezpieczeństwa, jakie możesz mieć. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).

Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.
