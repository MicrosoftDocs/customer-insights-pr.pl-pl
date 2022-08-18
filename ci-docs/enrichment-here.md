---
title: Wzbogacanie profilów klientów za pomocą HERE Technologies (wersja zapoznawcza)
description: Ogólne informacje o wzbogacaniu strony trzeciej HERE Technologies.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 86a070342193dd7afda38823d90f4bd28c8b862e
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237871"
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

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Wybierz **Weryfikuj**, aby sprawdzić poprawność konfiguracji, a następnie wybierz opcję **Zapisz**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Strona konfiguracji połączenia HERE Technologies.":::

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
