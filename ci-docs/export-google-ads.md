---
title: Eksportowanie danych Customer Insights do usługi Google ads
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi Google Ads.
ms.date: 03/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3e0eb91be97d69a999e90708d29c572f0055527e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646916"
---
# <a name="export-segments-to-google-ads-preview"></a>Eksportowanie segmentów do usługi Google Ads (wersja zapoznawcza)

Wyeksportuj segmenty ujednoliconych profili klientów do listy odbiorców Google Ads i wykorzystaj je do reklam w wyszukiwarce Google, poczcie Gmail, serwisie YouTube i sieci reklamowej Google Display Network. 


## <a name="prerequisites-for-connection"></a>Wymagania wstępne dla połączenia

-   Użytkownik ma [konto usługi Google Ads](https://ads.google.com/) i odpowiadające mu poświadczenia administratora.
-   Spełniasz wymagania [zasad dopasowania do klienta](https://support.google.com/adspolicy/answer/6299717).
-   Spełniasz wymagania [rozmiarów list marketingowych](https://support.google.com/google-ads/answer/7558048).
-   Posiadasz [skonfigurowane segmenty](segments.md).
-   Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pola reprezentujące adres e-mail, telefon, identyfikator reklamodawcy mobilnego, identyfikator użytkownika innej firmy lub adres.

## <a name="known-limitations"></a>Znane ograniczenia

- Eksport do Google Ads jest ograniczony do segmentów.
- Eksportowanie segmentów z łącznie 1 mln profilów klientów może zająć do 30 minut z powodu ograniczeń po stronie dostawcy. 
- Dopasowanie w usłudze Google Ads może potrwać do 48 godzin.

## <a name="set-up-connection-to-google-ads"></a>Konfiguruj połączenie z usługą Google Ads

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Google Ads**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wpisz **[Identyfikator klienta usługi Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.

1. Wybierz **Uwierzytelnianie za pomocą usługi Google Ads** i przekaż swoje poświadczenia w usłudze Google AD.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**. 

## <a name="configure-an-export"></a>Konfigurowanie eksportu

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Google Ads. Jeśli nie widzisz tej nazwy sekcji, to znaczy, że nie masz dostępu do żadnych połączeń tego typu.

1. Jeśli chcesz utworzyć nową grupę odbiorców, pozostaw pole identyfikatora odbiorców Google puste. Automatycznie utworzymy nowy adres odbiorcy koncie Google Ads i użyjemy nazwy wyeksportowanego segmentu. Jeśli chcesz zaktualizować istniejące reklamy Google odbiorcy, wprowadź swój [identyfikator odbiorcy Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)

1. W sekcji **Dopasowywanie danych** wybierz co najmniej jedno pole danych do wyeksportowania i wybierz pole reprezentujące odpowiednie pola danych w obszarze Customer Insights.

1. Wybierz segmenty, które chcesz wyeksportować. 

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab). 

Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Google Ads można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że Google Ads spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.


[!INCLUDE [footer-include](includes/footer-banner.md)]
