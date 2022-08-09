---
title: Wzbogacanie profilów klientów za pomocą HERE Technologies (wersja zapoznawcza)
description: Ogólne informacje o wzbogacaniu strony trzeciej HERE Technologies.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 26de9fce863c9832b70adf3ce39cb2ae0ce43d0e
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196269"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Wzbogacanie profilów klientów za pomocą HERE Technologies (wersja zapoznawcza)

HERE Technologies to firma oferująca platformę lokalizacyjną, która dostarcza dane i usługi zorientowane na lokalizację. Usługi wzbogacenia danych firmy HERE Technologies poprawiają dokładność informacji o lokalizacjach klientów. Zapewnia on normalizację adresów, szerokość i długość geograficzną wyodrębniania itp.

## <a name="prerequisites"></a>Wymagania wstępne

- Aktywna subskrypcja HERE Technologies. Aby uzyskać subskrypcję, [zarejestruj się tutaj](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) lub [skontaktuj się bezpośrednio z działem HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Dowiedz się więcej o wzbogacaniu lokalizacji HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- [Połączenie](connections.md) HERE jest [konfigurowane](#configure-the-connection-for-here-technologies) przez administratora.

## <a name="configure-the-connection-for-here-technologies"></a>Konfigurowanie połączenia dla HERE Technologies

Musisz mieć rolę [administratora](permissions.md#admin) funkcji Customer Insights i mieć aktywny klucz interfejsu API HERE Technologies.

1. Wybierz opcję **Dodaj połączenie** podczas konfigurowania wzbogacania lub wybierz pozycję **Admin** > **Połączenia** i wybierz opcję **Konfiguruj** na kafelku HERE Technologies.

1. Wprowadź nazwę połączenia i prawidłowy klucz interfejsu API HERE Technologies.

1. Przejrzyj i wyraź zgodę na [Zasady ochrony prywatności danych](#data-privacy-and-compliance), wybierając przycisk **I agree (Wyrażam zgodę)**.

1. Wybierz **Weryfikuj**, aby sprawdzić poprawność konfiguracji, a następnie wybierz opcję **Zapisz**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Strona konfiguracji połączenia HERE Technologies.":::

### <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi HERE Technologies można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że HERE Technologies spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć wzbogacanie, aby przestać używać tej funkcji.

## <a name="configure-the-enrichment"></a>Konfiguracja wzbogacania

1. Przejdź do **Dane** > **Wzbogacenie** i wybierz kartę **Odkrywanie**.

1. Wybierz opcję **Wzbogać moje dane** na kafelku HERE Technologies **Lokalizacja**.

   :::image type="content" source="media/HERE-tile.png" alt-text="Kafelek HERE Technologies.":::

1. Przejrzyj omówienie, a następnie wybierz **Dalej**.

1. Wybierz połączenie. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wybierz **Dalej**.

1. Wybierz **Zestaw danych klienta** i wybierz profil i segment, który chcesz wzbogacić o dane dotyczące tożsamości z HERE Technologies. Można wybrać encję *Klient*, aby wzbogacić wszystkie profile klientów, lub wybierz jednostkę segmentu, aby wzbogacić tylko profile klientów zawarte w tym segmencie.

1. Zdefiniuj typy pól z ujednoliconych profilów, które mają być dopasowane: adres podstawowy i/lub dodatkowy. Można oddzielnie określić mapowanie pól dla obu adresów i wzbogacić profile dla obu adresów. Na przykład: adres domowy i adres służbowy. Wybierz **Dalej**.

1. Zamapuj pola na dane identyfikujące z HERE Technologies. Pola **Ulica 1** i **Kod pocztowy** są wymagane dla wybranego adresu głównego i / lub dodatkowego. Aby uzyskać większą dokładność dopasowania, należy dodać więcej pól.

1. Wybierz **Dalej**, by zakończyć mapowanie pól.

1. Podaj **Nazwę** dla wzbogacenia oraz **Nazwa encji wyjściowej**.

1. Wybierz opcję **Zapisz wzbogacenie** po przejrzeniu wybranych opcji.

1. Wybierz przycisk **Uruchom**, aby rozpocząć proces wzbogacenia lub zamknąć, aby powrócić do strony **Wzbogacanie**.

## <a name="view-enrichment-results"></a>Wyświetlanie wyników wzbogacenia

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Liczba klientów wzbogaconych według pola** zapewnia szczegółowe informacje na temat pokrycia każdego wzbogaconego pola.

## <a name="next-steps"></a>Następne kroki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
