---
title: Wzbogacenie profilów firmy z Dun & Bradstreet (wersja zapoznawcza)
description: Ogólne informacje na temat wzbogacenia innych firm z Dun & Bradstreet.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: e89b64774dcb519a071dd3d403473807a50e7f33
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237917"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>Wzbogacenie profilów firmy z Dun & Bradstreet (wersja zapoznawcza)

Firma Dun & Bradstreet dostarcza dane komercyjne, analizy i szczegółowe informacje dla firm. Dzięki niej klienci z ujednoliconymi profilami klientów dla firm mogą wzbogacać swoje dane. Wzbogacenie zawiera atrybuty, takie jak numer DUNS, wielkość firmy, lokalizacja, branża i inne.

## <a name="prerequisites"></a>Wymagania wstępne

- Aktywna licencja [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights).
- [Ujednolicone profile klientów](customer-profiles.md) dla firm.
- [Projekt](#set-up-your-dun--bradstreet-project) Dun & Bradstreet jest ustawiony.
- [Połączenie](connections.md) Dun & Bradstreet jest [konfigurowane](#configure-a-connection-for-dun--bradstreet) przez administratora.

## <a name="set-up-your-dun--bradstreet-project"></a>Skonfiguruj projekt Dun & Bradstreet

Jako licencjonowany użytkownik Dun & Bradstreet [możesz skonfigurować projekt Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Zaloguj się w [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Aby pobrać poświadczenia, [przywróć hasło](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Pobierz [nasz plik z szablonami csv](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv), który będzie używany do mapowania pól szczegółowych informacji i odbiorcy na odpowiadające im pola Customer Insights.

1. Przekaż plik w kroku **przekazywania danych** procesu tworzenia projektu Dun & Bradstreet.

1. Wybierz poziome kropki poniżej odpowiedniego **źródła** w nowo utworzonym projekcie Dun & Bradstreet w celu zobaczenia dostępnych opcji.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Zrzut ekranu przedstawiający kropki w projekcie Dun & Bradstreet.":::

1. Wybierz pozycję **Pobierz szczegóły S3**. Przechowaj te informacje w bezpiecznym miejscu. Trzeba będzie [skonfigurować połączenie do wzbogacania](#configure-a-connection-for-dun--bradstreet) w szczegółowych danych Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Zrzut ekranu przedstawiający wybór informacji s3 w projekcie Dun & Bradstreet.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Konfigurowanie połączenia dla Dun & Bradstreet

Musisz być [administratorem](permissions.md#admin) w Customer Insights i mieć poświadczenia z Dun & Bradstreet Connect.

1. Wybierz **Dodaj połączenie** podczas konfigurowania wzbogacenia lub przejdź do **Admin** > **Połączenia** i wybierz **Ustaw** na kafelku Dun & Bradstreet.

1. Wprowadź nazwę połączenia.

1. Podaj prawidłowe poświadczenia Dun & Bradstreet i szczegóły projektu Dun & Bradstreet *Region, Ścieżka folderu upuszczania i Nazwa folderu upuszczania*. Te [informacje pochodzą](#set-up-your-dun--bradstreet-project) z projektu Dun & Bradstreet.

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Wybierz **Weryfikuj**, aby sprawdzić poprawność konfiguracji, a następnie wybierz opcję **Zapisz**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Strona konfiguracji połączenia Dun & Bradstreet.":::

## <a name="supported-countries-or-regions"></a>Obsługiwane kraje lub regiony

Obecnie są dostępne opcje dla następujących krajów/regionów: Kanada (angielski) lub Stany Zjednoczone (angielski).

## <a name="configure-the-enrichment"></a>Konfiguracja wzbogacania

1. Przejdź do **Dane** > **Wzbogacenie** i wybierz kartę **Odkrywanie**.

1. Wybierz opcję **Wzbogać moje dane** na kafelku Dun & Bradstreet **Dane firm**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Zrzut ekranu kafelka Dun & Bradstreet.":::

1. Przejrzyj omówienie, a następnie wybierz **Dalej**.

1. Wybierz połączenie i potwierdź. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wybierz **Dalej**.

1. Wybierz **Zestaw danych klienta** i wybierz profil i segment, który chcesz wzbogacić o dane firmy z Dun & Bradstreet. Można wybrać encję *Klient*, aby wzbogacić wszystkie profile klientów, lub wybierz jednostkę segmentu, aby wzbogacić tylko profile klientów zawarte w tym segmencie.

1. Określ, jakiego typu pola z twoich profili zunifikowanych powinny być używane do wyszukiwania pasujących danych firmy z Dun & Bradstreet. Wymagane jest co najmniej jedno z pól **Nazwa i adres**, **Telefon** lub **Wiadomość e-mail**.

1. Wybierz **Dalej**

1. Zamapuj pola na dane firmy z Dun & Bradstreet. Wymagane są albo pola **Numer DUNS**, albo **Nazwa firmy** i **Kraj**.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Okienko mapowania pól Dun & Bradstreet.":::

1. Wybierz **Dalej**, by zakończyć mapowanie pól.

1. Podaj **Nazwę** dla wzbogacenia oraz **Nazwa encji wyjściowej**.

1. Wybierz opcję **Zapisz wzbogacenie** po przejrzeniu wybranych opcji.

1. Wybierz przycisk **Uruchom**, aby rozpocząć proces wzbogacenia lub zamknąć, aby powrócić do strony **Wzbogacanie**.

## <a name="view-enrichment-results"></a>Wyświetlanie wyników wzbogacenia

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Następne kroki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
