---
title: Wzbogacanie profili firm o zewnętrzne wzbogacenie Leadspace
description: Ogólne informacje o wzbogacaniu strony trzeciej Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ccf4f661ecffb281556a4545b1f26ee809c697cd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895926"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Wzbogacanie profili firm z Leadspace (wersja zapoznawcza)

Leadspace jest firmą badawczą, która dostarcza platformę danych klientów typu B2B. Dzięki niej klienci z ujednoliconymi profilami klientów dla firm mogą wzbogacać swoje dane. Wzbogacanie zawiera więcej atrybutów, takich jak wielkość firmy, lokalizacja, branża i inne.

## <a name="prerequisites"></a>Wymagania wstępne

Aby skonfigurować Leadspce muszą być spełnione następujące wymagania wstępne:

- Użytkownik ma aktywną licencję Leadspace.
- Istnieją [ujednolicone profile klientów](customer-profiles.md) dla firm.
- Połączenie Leadspace zostało już skonfigurowane przez administratora lub użytkownik ma uprawnienia [administratora](permissions.md#administrator) i „klucz bezterminowy” (nazywany **tokenem Leadspace**). Aby uzyskać szczegółowe informacje na temat produktu, należy bezpośrednio skontaktować się z [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/).

## <a name="configure-the-enrichment"></a>Konfiguracja wzbogacania

1. W analizach odbiorców przejdź do **Dane** > **Wzbogacenie**.

1. Wybierz **Wzbogać moje dane** na kafelku Leadspace i wybierz **Rozpocznij**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Zrzut ekranu kafelka Leadspace.":::

1. Wybierz [połączenie](connections.md) z listy rozwijanej. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie. Jeśli użytkownik jest administratorem, może on utworzyć połączenie, wybierając opcję **Dodaj połączenie** i wybierając **Leadspace**. 

1. Wybierz opcję **Połącz z Leadspace**, aby potwierdzić wybrane połączenie.

1. Wybierz opcję **Dalej** i wybierz **Zestaw danych klienta**, który chcesz wzbogacić danymi firmy z Leadspace. Można wybrać encję **Klient**, aby wzbogacić wszystkie profile klientów, lub wybierz jednostkę segmentu, aby wzbogacić tylko profile klientów zawarte w tym segmencie.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Zrzut ekranu podczas wybierania zestawu danych klienta.":::

1. Wybierz opcję **Dalej** i zdefiniuj, jakiego typu pola z ujednoliconych profilów powinny być używane do wyszukiwania pasujących danych firmowych z Leadspace. Pole **Nazwa firmy** jest wymagane. Aby zwiększyć dokładność dopasowania, można dodać maksymalnie dwa inne pola, **Witrynę sieci Web firmy** i **Lokalizację firmy**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Okienko mapowania pola Leadspace.":::

1. Wybierz **Dalej**, by zakończyć mapowanie pól.

1. Po przejrzeniu wybranych opcji podaj nazwę wzbogacania i wybierz opcję **Zapisz wzbogacenie**.


## <a name="configure-the-connection-for-leadspace"></a>Konfigurowanie połączenia dla Leadspace 

Aby skonfigurować połączenia, użytkownik musi być administratorem. Wybierz opcję **Dodaj połączenie** podczas konfigurowania wzbogacania *lub* wybierz pozycję **Admin** > **Połączenia** i wybierz opcję **Konfiguruj** na kafelku Leadspace.

1. Wybierz **Rozpocznij** 

1. Wprowadź nazwę połączenia w polu **Wyświetlana nazwa**.

1. Podaj prawidłowy token rozwiązania firmy Leadspace.

1. Sprawdź poprawność i wyraź zgodę na **Prywatność danych i zgodność z przepisami** zaznaczając pole wyboru **Zgadzam się**

1. Wybierz opcję **Weryfikuj**, aby sprawdzić poprawność konfiguracji.

1. Po zakończeniu weryfikacji wybierz opcję **Zapisz**.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Strona konfiguracji połączenia Leadspace.":::

## <a name="enrichment-results"></a>Wyniki wzbogacenia

Po odświeżeniu wzbogacenia można zapoznać się z nowo wzbogaconymi danymi firmowymi w ramach [Moje wzbogacenia](enrichment-hub.md). Możesz sprawdzić czas ostatniej aktualizacji oraz liczbę wzbogaconych profilów.

Aby uzyskać dostęp do szczegółowego widoku poszczególnych wzbogaconych profilów, należy zaznaczyć **Wyświetl wzbogacone dane**.

Aby uzyskać więcej informacji, zobacz [Interfejsy API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Następne kroki

Kompiluj na wierzchu wzbogaconych danych klientów. Utwórz [segmenty](segments.md), [miary](measures.md), a nawet [eksportuj dane](export-destinations.md), aby zapewnić klientom spersonalizowane rozwiązania.

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Leadspace można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że Leadspace spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć wzbogacanie, aby przestać używać tej funkcji.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
