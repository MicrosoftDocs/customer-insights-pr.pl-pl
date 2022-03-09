---
title: Wzbogacanie za pomocą strony trzeciej – HERE Technologies
description: Ogólne informacje o wzbogacaniu strony trzeciej HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 1b46e8913c6d288b93cdf32e195b5e9387916e70
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230395"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Wzbogacenie profili klientów za pomocą HERE Technologies (wersja zapoznawcza)

HERE Technologies to firma oferująca platformę lokalizacyjną, która dostarcza dane i usługi zorientowane na lokalizację. Dzięki usługom wzbogacania danych HERE Technologies możesz dokładniej zrozumieć lokalizację swoich klientów dzięki normalizacji adresu, ekstrakcji szerokości i długości geograficznej i nie tylko.

## <a name="prerequisites"></a>Wymagania wstępne

Aby skonfigurować wzbogacenia HERE Technologies, muszą zostać spełnione następujące wymagania wstępne:

- Masz aktywną subskrypcję HERE Technologies. Aby uzyskać subskrypcję, możesz zasubskrybować [tutaj](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) lub [skontaktować się bezpośrednio z HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Dowiedz się więcej o wzbogacaniu lokalizacji HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- [Połączenie](connections.md) HERE jest dostępne *lub* jeśli masz uprawnienia[administratora](permissions.md#administrator) i klucz interfejsu API HERE.

## <a name="configure-the-enrichment"></a>Konfiguracja wzbogacania

1. Przejdź do **Dane** > **Wzbogacanie**. 

1. Wybierz **Wzbogać moje dane** na kafelku HERE Technologies i wybierz **Rozpocznij**.

   > [!div class="mx-imgBorder"]
   > ![Kafelek HERE Technologies.](media/HERE-tile.png "Kafelek HERE Technologies")

1. Wybierz [połączenie](connections.md) z listy rozwijanej. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie. Jeśli użytkownik jest administratorem, może on utworzyć połączenie, wybierając opcję **Dodaj połączenie**. Z listy rozwijanej wybierz pozycję **HERE Technologies**. 

1. Wybierz opcję **Połącz z HERE Technologies**, aby potwierdzić wybrane połączenie.

1.  Wybierz opcję **Dalej** i wybierz **Zestaw danych klienta**, który chcesz wzbogacić danymi lokalizacji z HERE Technologies. Można wybrać encję **Klient**, aby wzbogacić wszystkie profile klientów, lub wybierz jednostkę segmentu, aby wzbogacić tylko profile klientów zawarte w tym segmencie.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Zrzut ekranu podczas wybierania zestawu danych klienta.":::

1. Wybierz, jeśli chcesz zmapować pola na adres podstawowy i/lub pomocniczy. Można oddzielnie określić mapowanie pól dla obu adresów i wzbogacić profile dla obu adresów. Na przykład jeśli istnieje adres domowy i służbowy. Wybierz **Dalej**.

1. Zdefiniuj, które pola z ujednoliconych profili mają być używane do wyszukiwania pasujących danych o lokalizacji z HERE Technologies. Pola **Ulica 1** i **Kod pocztowy** są wymagane dla wybranego adresu głównego i / lub dodatkowego. Aby zwiększyć dokładność dopasowania, można dodać więcej pól.

   > [!div class="mx-imgBorder"]
   > ![Strona konfiguracji wzbogacenia HERE Technologies.](media/enrichment-HERE-configuration.png "Strona konfiguracji wzbogacenia HERE Technologies")

1. Wybierz **Dalej**, by zakończyć mapowanie pól.

1. Podaj nazwę wzbogacenia. 

1. Wybierz opcję **Zapisz wzbogacenie** po przejrzeniu wybranych opcji.

## <a name="configure-the-connection-for-here-technologies"></a>Konfigurowanie połączenia dla HERE Technologies 

Aby skonfigurować połączenia, użytkownik musi być administratorem. Wybierz opcję **Dodaj połączenie** podczas konfigurowania wzbogacania *lub* wybierz pozycję **Admin** > **Połączenia** i wybierz opcję **Konfiguruj** na kafelku HERE Technologies.

1. Wprowadź nazwę połączenia w polu **Wyświetlana nazwa**.

1. Podaj prawidłowy klucz interfejsu API technologii HERE Technologies.

1. Przejrzyj i wyraź zgodę na **Zasady ochrony prywatności danych**, wybierając przycisk **I agree (Wyrażam zgodę)**.

1. Wybierz opcję **Weryfikuj**, aby sprawdzić poprawność konfiguracji.

1. Po zakończeniu weryfikacji wybierz opcję **Zapisz**.

   > [!div class="mx-imgBorder"]
   > ![Strona konfiguracji połączenia HERE Technologies.](media/enrichment-HERE-connection.png "Strona konfiguracji połączenia HERE Technologies")

## <a name="enrichment-results"></a>Wyniki wzbogacenia

Aby rozpocząć proces wzbogacania, wybierz **Uruchom** na pasku poleceń. Można również zezwolić, aby system automatycznie uruchamiał wzbogacenie w ramach [zaplanowanego odświeżenia](system.md#schedule-tab). Czas przetwarzania będzie zależał od rozmiaru danych klienta i czasów odpowiedzi API firmy HERE Technologies.

Po zakończeniu procesu wzbogacania można przejrzeć dane nowo wzbogacone profile klientów w **Moje wzbogacenia**. Ponadto znajdziesz tam czas ostatniej aktualizacji i liczbę wzbogaconych profilów.

Aby uzyskać dostęp do szczegółowego widoku poszczególnych wzbogaconych profilów, należy zaznaczyć **Wyświetl wzbogacone dane**.

## <a name="next-steps"></a>Następne kroki

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi HERE Technologies można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że HERE Technologies spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć wzbogacanie, aby przestać używać tej funkcji.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
