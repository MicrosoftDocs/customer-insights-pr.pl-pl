---
title: Wzbogacanie danych za pomocą HERE Technologies innych firm
description: Ogólne informacje o wzbogacaniu strony trzeciej HERE Technologies.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 8e8d6bfea4e0df54682501f60759c24c893444af
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597754"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Wzbogacenie profili klientów za pomocą HERE Technologies (wersja zapoznawcza)

HERE Technologies to firma oferująca platformę lokalizacyjną, która dostarcza dane i usługi zorientowane na lokalizację. Dzięki usługom wzbogacania danych HERE Technologies możesz dokładniej zrozumieć lokalizację swoich klientów dzięki normalizacji adresu, ekstrakcji szerokości i długości geograficznej i nie tylko.

## <a name="prerequisites"></a>Wymagania wstępne

Aby skonfigurować wzbogacenia HERE Technologies, muszą zostać spełnione następujące wymagania wstępne:

- Masz aktywną subskrypcję HERE Technologies. Aby uzyskać subskrypcję, możesz zasubskrybować [tutaj](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) lub [skontaktować się bezpośrednio z HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Dowiedz się więcej o wzbogacaniu lokalizacji HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Masz klucz API HERE Technologies.

- Masz uprawnienia [Administratora](permissions.md#administrator).

## <a name="configuration"></a>Konfiguracja

1. Przejdź do **Dane** > **Wzbogacanie**.

1. Na kafelku importu niestandardowego HERE wybierz pozycję **Wzbogacanie danych**.

   > [!div class="mx-imgBorder"]
   > ![Kafelek HERE Technologies](media/HERE-tile.png "Kafelek HERE Technologies")

1. Wprowadź aktywny **klucz interfejsu API HERE Technologies**. Sprawdź poprawność i wyraź zgodę na **Prywatność danych i zgodność z przepisami** zaznaczając pole wyboru **Zgadzam się**. 

1. Potwierdzenie obydwu składników są wprowadzane po wybraniu opcji **Połącz z HERE**.

1.  Wybierz opcję **Dodaj dane** i wybierz **Zestaw danych klienta**, który chcesz wzbogacić o dane lokalizacyjne z firmy HERE Technologies. Można wybrać encję **Klient**, aby wzbogacić wszystkie profile klientów, lub wybierz jednostkę segmentu, aby wzbogacić tylko profile klientów zawarte w tym segmencie.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Zrzut ekranu podczas wybierania zestawu danych klienta.":::

1. Wybierz, jeśli chcesz zmapować pola na adres podstawowy i/lub pomocniczy. Możesz określić mapowanie pól dla obu adresów (na przykład adresu domowego i adresu firmy) i wzbogacić profile dla obu adresów osobno. Wybierz **Dalej**.

1. Zdefiniuj, które pola z ujednoliconych profili mają być używane do wyszukiwania pasujących danych o lokalizacji z HERE Technologies. Pola **Ulica 1** i **Kod pocztowy** są wymagane dla wybranego adresu głównego i / lub dodatkowego. Aby zwiększyć dokładność dopasowania, można dodać więcej pól.

   > [!div class="mx-imgBorder"]
   > ![Strona konfiguracji wzbogacenia HERE Technologies](media/enrichment-HERE-configuration.png "Strona konfiguracji wzbogacenia HERE Technologies")

1. Wybierz opcję **Zastosuj**, aby zakończyć mapowanie pola.

## <a name="enrichment-results"></a>Wyniki wzbogacenia

Aby rozpocząć proces wzbogacania, wybierz **Uruchom** na pasku poleceń. Można również zezwolić, aby system automatycznie uruchamiał wzbogacenie w ramach [zaplanowanego odświeżenia](system.md#schedule-tab). Czas przetwarzania będzie zależał od rozmiaru danych klienta i czasów odpowiedzi API firmy HERE Technologies.

Po zakończeniu procesu wzbogacania można przejrzeć dane nowo wzbogacone profile klientów w **Moje wzbogacenia**. Ponadto znajdziesz tam czas ostatniej aktualizacji i liczbę wzbogaconych profilów.

Aby uzyskać dostęp do szczegółowego widoku poszczególnych wzbogaconych profilów, należy zaznaczyć **Wyświetl wzbogacone dane**.

## <a name="next-steps"></a>Następne kroki

Kompiluj na wierzchu wzbogaconych danych klientów. Utwórz [segmenty](segments.md), [miary](measures.md), a nawet [eksportuj dane](export-destinations.md), aby zapewnić klientom spersonalizowane rozwiązania.

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi HERE Technologies można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że HERE Technologies spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć wzbogacanie, aby przestać używać tej funkcji.


[!INCLUDE[footer-include](../includes/footer-banner.md)]