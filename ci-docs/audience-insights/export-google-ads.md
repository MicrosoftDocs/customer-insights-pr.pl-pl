---
title: Eksportowanie danych Customer Insights do usługi Google ads
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c23c8b4e6758df08e04bf1e3ae0cba4dee06fe2b
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305353"
---
# <a name="export-segments-to-google-ads-preview"></a>Eksportowanie segmentów do usługi Google Ads (wersja zapoznawcza)

Wyeksportuj segmenty ujednoliconych profili klientów do listy odbiorców Google Ads i wykorzystaj je do reklam w wyszukiwarce Google, poczcie Gmail, serwisie YouTube i sieci reklamowej Google Display Network. 

## <a name="prerequisites-for-connection"></a>Wymagania wstępne dla połączenia

-   Użytkownik ma [konto usługi Google Ads](https://ads.google.com/) i odpowiadające mu poświadczenia administratora.
-   Masz [zatwierdzony token dewelopera Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token). 
-   Spełniasz wymagania [zasad dopasowania do klienta](https://support.google.com/adspolicy/answer/6299717).
-   Spełniasz wymagania [rozmiarów list marketingowych](https://support.google.com/google-ads/answer/7558048).
-   W Google Ads istnieją już odbiorcy i odpowiadające im identyfikatory. Aby uzyskać więcej informacji, zobacz temat [Odbiorcy Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Posiadasz [skonfigurowane segmenty](segments.md).
-   Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pola reprezentujące adresy e-mail, imię i nazwisko.

## <a name="known-limitations"></a>Znane ograniczenia

- Do 1 miliona profili na eksport do Google Ads.
- Eksport do Google Ads jest ograniczony do segmentów.
- Eksportowanie segmentów zawierających łącznie 1 milion profili może zająć do 5 minut ze względu na ograniczenia po stronie dostawcy. 
- Dopasowanie w usłudze Google Ads może potrwać do 48 godzin.

## <a name="set-up-connection-to-google-ads"></a>Konfiguruj połączenie z usługą Google Ads

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Google Ads**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wpisz **[Identyfikator klienta usługi Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Wprowadź **[zatwierdzony token dewelopera usługi Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.

1. Wybierz **Uwierzytelnianie za pomocą usługi Google Ads** i przekaż swoje poświadczenia w usłudze Google AD.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**. 

## <a name="configure-an-export"></a>Konfigurowanie eksportu

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Google Ads. Jeśli nie widzisz tej nazwy sekcji, to znaczy, że nie masz dostępu do żadnych połączeń tego typu.

1. Wprowadź **[identyfikator odbiorcy usługi Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** i wybierz pozycję **Połącz**, aby zainicjować połączenie z usługą Google Ads.

1. W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta. Powtórz te same kroki dla pól **Imię** i **Nazwisko**.

1. Wybierz segmenty, które chcesz wyeksportować. W sumie do maksymalnie 1 000 000 profilów klientów można wyeksportować do Google Ads.

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab). 

Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Google Ads można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że Google Ads spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
