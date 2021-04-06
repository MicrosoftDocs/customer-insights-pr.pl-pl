---
title: Eksportowanie danych aplikacji Customer Insights do rozwiązania AdRoll
description: Dowiedz się, jak skonfigurować połączenie z rozwiązaniem AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697087"
---
# <a name="connector-for-adroll-preview"></a>Łącznik dla rozwiązania AdRoll (wersja zapoznawcza)

Eksportuj segmenty ujednoliconych profilów klientów do rozwiązania AdRoll i używaj ich w celach reklamowych. 

## <a name="prerequisites"></a>Wymagania wstępne

-   Masz [konto rozwiązania AdRoll](https://www.adroll.com/) i odpowiadające mu poświadczenia administratora.
-   Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.
-   Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="connect-to-adroll"></a>Połącz z usługą AdRoll

1. Przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.

1. W obszarze **AdRoll** wybierz **Konfiguruj**.

1. W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej exportu rozpoznawalną nazwę.

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Okienko konfiguracji dla połączenia z rozwiązaniem AdRoll.":::

1. Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.

1. Wybierz opcję **Połącz**, aby zainicjować połączenie z rozwiązaniem AdRoll.

1. Wybierz opcję **Uwierzytelnij za pomocą rozwiązania AdRoll** i podaj poświadczenia administratora dla rozwiązania AdRoll. 

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Wprowadź swój **identyfikator reklamodawcy w usłudze AdRoll**, [AdRoll — możliwości reklamy](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).

1. Wybierz **Dalej**, aby skonfigurować eksport.

## <a name="configure-the-connector"></a>Skonfiguruj łącznik

1. W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta. Wyeksportowanie segmentów do rozwiązania AdRoll jest wymagane.

1. Wybierz segmenty, które chcesz wyeksportować. Wybierz segment obejmujący co najmniej 100 członków. Nie można eksportować mniejszych segmentów. Dodatkowo maksymalny rozmiar eksportowanego segmentu wynosi 250 000 członków na operację eksportu. 

1. Wybierz pozycję **Zapisz**.

## <a name="export-the-data"></a>Eksportowanie danych

Możesz [eksportować dane na żądanie](export-destinations.md). Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab).

## <a name="known-limitations"></a>Znane ograniczenia

- Do rozwiązania AdRoll możesz wyeksportować łącznie do 250 000 profilów na operację eksportu.
- Nie można eksportować segmentów obejmujących mniej niż 100 profilów do rozwiązania AdRoll. 
- Eksport do rozwiązania AdRoll jest ograniczony do segmentów.
- Wyeksportowanie do 250 000 profilów do rozwiązania AdRoll może potrwać do 10 minut. 
- Liczba profilów, które można eksportować do rozwiązania AdRoll, jest zależna od kontraktu z rozwiązaniem AdRoll i ograniczana na jego podstawie.

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu aplikacji Dynamics 365 Customer Insights w celu transmisji danych do usługi AdRoll można przesyłać dane spoza granicy zgodności dla aplikacji Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft prześle takie dane na Twoje polecenie, ale Ty ponosisz odpowiedzialność za zapewnienie, że usługa AdRoll spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).

Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.
