---
title: Wzbogacenie profilów firmy z Dun & Bradstreet
description: Ogólne informacje na temat wzbogacenia innych firm z Dun & Bradstreet.
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: ecbbf2c94020bf395f4eb70a99a63cea335af2dd
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653727"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Wzbogacenie profilów firmy z Dun & Bradstreet (wersja zapoznawcza)

Firma Dun & Bradstreet dostarcza dane komercyjne, analizy i szczegółowe informacje dla firm. Dzięki niej klienci z ujednoliconymi profilami klientów dla firm mogą wzbogacać swoje dane. Wzbogacenie zawiera atrybuty, takie jak numer DUNS, wielkość firmy, lokalizacja, branża i inne.

## <a name="prerequisites"></a>Wymagania wstępne

Aby skonfigurować wzbogacenie Dun & Bradstreet, muszą być spełnione następujące warunki wstępne:

- Masz aktywną licencję [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights).
- Istnieją [ujednolicone profile klientów](customer-profiles.md) dla firm.
- Połączenie [Dun & Bradstreet](connections.md) jest konfigurowane przez administratora. Można je utworzyć, jeśli masz uprawnienia [administratora](permissions.md#admin) i poświadczenia z Dun & Bradstreet Connect. 

## <a name="setting-up-your-dun--bradstreet-project"></a>Konfigurowanie projektu Dun & Bradstreet

Jako licencjonowany użytkownik Dun & Bradstreet [możesz skonfigurować projekt Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). 


1. Zaloguj się w [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Aby pobrać poświadczenia, [przywróć hasło](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Pobierz [nasz plik z szablonami csv](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv), który będzie używany do mapowania pól szczegółowych informacji i odbiorcy na odpowiadające im pola Dun & Bradstreet. 

1. Przekaż plik w kroku **przekazywania danych** procesu tworzenia projektu Dun & Bradstreet. 

1. Wybierz poziome kropki poniżej odpowiedniego **źródła** w nowo utworzonym projekcie Dun & Bradstreet w celu zobaczenia dostępnych opcji.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Zrzut ekranu przedstawiający kropki w projekcie Dun & Bradstreet.":::

1. Wybierz pozycję **Pobierz szczegóły S3**. Przechowaj te informacje w bezpiecznym miejscu. Trzeba będzie [skonfigurować połączenie do wzbogacania](#configure-a-connection-for-dun--bradstreet) w szczegółowych danych dotyczących odbiorcy. 

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Zrzut ekranu przedstawiający wybór informacji s3 w projekcie Dun & Bradstreet.":::



## <a name="configure-the-enrichment"></a>Konfiguracja wzbogacania

1. W analizach odbiorców przejdź do **Dane** > **Wzbogacenie**.

1. Wybierz opcję **Wzbogać moje dane** na kafelku Dun & Bradstreet i wybierz opcję **Wprowadzenie**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Zrzut ekranu kafelka Dun & Bradstreet.":::

1. Wybierz [połączenie](connections.md) z listy rozwijanej. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie. Jeśli użytkownik jest administratorem połączenia, może utworzyć połączenie. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Dun & Bradstreet**. 

1. Wybierz opcję **Połącz z Dun & Bradstreet** w celu potwierdzenia połączenia.

1. Wybierz **Następny** i wybierz **Zestaw danych klienta**, który chcesz wzbogacić o dane firmy z projektu Dun & Bradstreet. Można wybrać encję **Klient**, aby wzbogacić wszystkie profile klientów, lub wybierz jednostkę segmentu, aby wzbogacić tylko ujednolicone profile klientów zawarte w tym segmencie.

1. Wybierz **Dalej** i określ, jakiego typu pola z twoich profili zunifikowanych są używane do wyszukiwania dopasowanych danych firmy z projektu Dun & Bradstreet. Wymagane są albo pola **Numer DUNS**, albo **Nazwa firmy** i **Kraj**. Pole kraju obsługuje [dwu- lub trzyliterowe kody kraju](https://www.iso.org/iso-3166-country-codes.html), nazwę kraju w języku angielskim, nazwę kraju w języku macierzystym i prefiks telefonu. Niektóre typowe warianty kraju to:

   * US: Stany Zjednoczone Ameryki, Stany Zjednoczone, USA, Ameryka.
   * CA: Kanada.
   * GB: Zjednoczone Królestwo, UK, Wielka Brytania, GB, Zjednoczone Królestwo Wielkiej Brytanii i Irlandii Północnej, Zjednoczone Królestwo Wielkiej Brytanii.
   * AU: Australia, Związek Australijski.
   * FR: Francja, Republika Francuska.
   * DE: Niemcy, German, Deutschland, Allemagne, Republika Federalna Niemiec, Republika Niemiecka.

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Okienko mapowania pól Dun & Bradstreet.":::

1. Wybierz **Dalej**, by zakończyć mapowanie pól.

1. Po przejrzeniu wybranych opcji podaj nazwę wzbogacania i wybierz opcję **Zapisz wzbogacenie**.


## <a name="configure-a-connection-for-dun--bradstreet"></a>Konfigurowanie połączenia dla Dun & Bradstreet 

Aby skonfigurować połączenia, użytkownik musi być administratorem. Wybierz **Dodaj połączenie** podczas konfigurowania wzbogacenia *lub* przejdź do **Admin** > **Połączenia** i wybierz **Ustaw** na kafelku Dun & Bradstreet.

1. Wybierz **Rozpocznij**. 

1. Wprowadź nazwę połączenia w polu **Wyświetlana nazwa**.

1. Podaj prawidłowe poświadczenia Dun & Bradstreet i szczegóły projektu Dun & Bradstreet *Region, Ścieżka folderu upuszczania i Nazwa folderu upuszczania*. Te [informacje pochodzą](#setting-up-your-dun--bradstreet-project) z projektu Dun & Bradstreet.

1. Przejrzyj i wyraź zgodę na **Zasady ochrony prywatności danych**, wybierając przycisk **I agree (Wyrażam zgodę)**.

1. Wybierz opcję **Weryfikuj**, aby sprawdzić poprawność konfiguracji.

1. Po zakończeniu weryfikacji wybierz opcję **Zapisz**.
   
   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Strona konfiguracji połączenia Dun & Bradstreet.":::

## <a name="enrichment-results"></a>Wyniki wzbogacenia

Po odświeżeniu wzbogacenia można zapoznać się z nowo wzbogaconymi danymi firmowymi w ramach [Moje wzbogacenia](enrichment-hub.md). Możesz sprawdzić czas ostatniej aktualizacji oraz liczbę wzbogaconych profilów.

Aby uzyskać dostęp do szczegółowego widoku poszczególnych wzbogaconych profilów, należy zaznaczyć **Wyświetl wzbogacone dane**.

## <a name="next-steps"></a>Następne kroki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu Dynamics 365 Customer Insights do transmisji danych do Dun & Bradstreet można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft przekaże takie dane na twoje polecenie, ale to ty jesteś odpowiedzialny za zapewnienie, że Dun & Bradstreet spełnia wszelkie zobowiązania dotyczące prywatności i bezpieczeństwa, jakie możesz mieć. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć wzbogacanie, aby przestać używać tej funkcji.


[!INCLUDE[footer-include](includes/footer-banner.md)]
