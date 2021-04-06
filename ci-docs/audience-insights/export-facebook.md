---
title: Eksportowanie danych Customer Insights do usługi Menedżer reklam Facebook
description: Informacje o konfigurowaniu połączenia z Menedżerem Facebook Ads.
ms.date: 06/05/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3e2b52fe743563e4bf61d870cbf1718e6c752a67
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596696"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>Łącznik dla Menedżera Facebook Ads (wersja zapoznawcza)

Eksportuj segmenty zunifikowanych profilów klientów do Menedżera Facebook Ads, aby tworzyć kampanie Facebook i Instagram.

## <a name="prerequisites"></a>Wymagania wstępne

- Musisz posiadać [**konto reklam Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), obejmujące [**konto firmowe Facebook**](https://business.facebook.com/).
- Musisz być Administratorem [**konta reklam Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="connect-to-facebook-ads-manager"></a>Połącz z Menedżerem Facebook Ads

1. Przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.

1. W obszarze **Menedżer Facebook Ads** wybierz **Konfiguruj**.

1. W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej exportu rozpoznawalną nazwę.

1. Wybierz **Kontynuuj z Facebook**, aby zalogować się do swojego konta Facebook Ad.

1. Zezwalaj na uprawnienie **ads_management** po uwierzytelnieniu za pomocą Facebook.

1. Wybierz **Konto Facebook Ads**, z którym chcesz pracować.

1. Wybierz **Istniejącego odbiorcę niestandardowego** z listy rozwijanej lub utwórz **Nowego odbiorcę niestandardowego**. Aby uzyskać więcej informacji, zobacz temat [**Odbiorcy w Menedżerze Facebook Ads**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).

1. Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.

1. Wybierz **Dalej**, aby skonfigurować eksport.

## <a name="configure-the-connector"></a>Skonfiguruj łącznik

1. W polu **Wybierz identyfikator klucza** wybierz **E-mail**, **Nazwisko i adres** lub **Telefon**, aby przesłać do Menedżera Facebook Ads.

1. Mapowanie odpowiednich atrybutów ze swojej zunifikowanej encji klienta dla wybranego identyfikatora klucza.
   > [WSKAZÓWKA] Największa szansa dopasowania pojawia się w przypadku wybrania opcji **E-mail** jako identyfikatora klucza. Dodanie dodatkowych identyfikatorów może poprawić dopasowanie.

1. Wybierz **Dodaj atrybut**, aby zamapować dodatkowe atrybuty na wysyłanie do Menedżera Facebook Ads. Atrybuty Menedżera Facebook Ads Ads są mapowane na poniższe przyjazne nazwy użytkowników: **FN** = **Imię**, **LN** = **Nazwisko**, **FI** = **Pierwszy inicjał**, **PHONE** = **Telefon**, **GEN** = **Płeć**, **DOB** = **Data urodzenia**, **ST** = **Stan**, **CT** = **Miasto**, **ZIP** = **Kod pocztowy**, **COUNTRY** = **Kraj / Region**

1. Wybierz segmenty, które chcesz wyeksportować.

1. Wybierz pozycję **Zapisz**.

## <a name="export-the-data"></a>Eksportowanie danych

Możesz [eksportować dane na żądanie](export-destinations.md). Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab).

## <a name="known-limitations"></a>Znane ograniczenia

- Do 10 milionów profili klientów na eksport do Menedżera reklam na Facebook 
- Eksport do Menedżera reklam na Facebook jest ograniczony do segmentów
- Eksportowanie segmentów zawierających łącznie 10 milionów profili może zająć do 90 minut

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Włączając Dynamics 365 Customer Insights przesyłanie danych do menedżera reklam Facebook, zezwalasz na przesyłanie danych poza granice zgodności dla Dynamics 365 Customer Insights, w tym potencjalnie wrażliwych danych, takich jak Dane Osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że reklamy Facebook spełniają wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.


[!INCLUDE[footer-include](../includes/footer-banner.md)]