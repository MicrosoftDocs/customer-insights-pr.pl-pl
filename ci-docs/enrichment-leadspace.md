---
title: Wzbogacenie profilów firmy z Leadspace (wersja zapoznawcza)
description: Ogólne informacje o wzbogacaniu strony trzeciej Leadspace.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f45fabc036775e11fc439f69513678d0607729d0
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237963"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>Wzbogacenie profilów firmy z Leadspace (wersja zapoznawcza)

Leadspace to firma zajmującą się nauką o danych, która oferuje platformę danych dla klienta typu B2B. Umożliwia ona środowiskom, które mają ujednolicone profile klientów oparte na klientach, wzbogacanie swoich danych. Wzbogać *profile klientów* o atrybuty, takie jak wielkość firmy, lokalizacja lub sektor. Wzbogać *profile kontaktów* o atrybuty, takie jak tytuł, osoba lub weryfikacja wiadomości e-mail.

## <a name="prerequisites"></a>Wymagania wstępne

- Aktywna licencja Leadspace.
- [Ujednolicone profile klientów](customer-profiles.md) na podstawie klientów.
- [Połączenie](connections.md) Leadspace jest [konfigurowane](#configure-the-connection-for-leadspace) przez administratora. Aby uzyskać szczegółowe informacje na temat produktu, należy bezpośrednio skontaktować się z [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/).

## <a name="configure-the-connection-for-leadspace"></a>Konfigurowanie połączenia dla Leadspace

Użytkownik musi mieć rolę [administratora](permissions.md#admin) w Customer Insights i mieć "klucz bezterminowy" (nazywany **tokenem Leadspace**).

1. Wybierz opcję **Dodaj połączenie** podczas konfigurowania wzbogacania lub wybierz pozycję **Admin** > **Połączenia** i wybierz opcję **Konfiguruj** na kafelku Leadspace.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Strona konfiguracji połączenia Leadspace.":::

1. Wprowadź nazwę połączenia i prawidłowy token Leadspace.

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Wybierz **Weryfikuj**, aby sprawdzić poprawność konfiguracji, a następnie wybierz opcję **Zapisz**.

## <a name="configure-the-enrichment"></a>Konfiguracja wzbogacania

1. Przejdź do **Dane** > **Wzbogacenie** i wybierz kartę **Odkrywanie**.

1. Wybierz opcję **Wzbogać moje dane** na kafelku Leadspace **Dane firmy**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Zrzut ekranu kafelka Leadspace.":::

1. Przejrzyj omówienie, a następnie wybierz **Dalej**.

1. Wybierz połączenie. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wybierz **Dalej**.

1. Wybierz **Zestaw danych klienta** i wybierz profil i segment, który chcesz wzbogacić o dane firmy z Leadspace. Można wybrać encję *Klient*, aby wzbogacić wszystkie profile klientów, lub wybierz jednostkę segmentu, aby wzbogacić tylko profile klientów zawarte w tym segmencie.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Zrzut ekranu podczas wybierania zestawu danych klienta.":::

1. Zdefiniuj typy pól z ujednoliconych profilów, które mają być dopasowane: adres podstawowy i/lub dodatkowy. Można oddzielnie określić mapowanie pól dla obu adresów i wzbogacić profile dla obu adresów. Na przykład: adres domowy i adres służbowy. Wybierz **Dalej**.

1. Zamapuj pola na dane firmy z Leadspace. Pole **Nazwa firmy** jest wymagane. Aby zwiększyć dokładność dopasowania, można dodać maksymalnie dwa inne pola, **Witrynę sieci Web firmy** i **Lokalizację firmy**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Okienko mapowania pola Leadspace.":::

1. Wybierz **Dalej**, by zakończyć mapowanie pól.

1. Zaznacz pole wyboru, jeśli masz *profile kontaktów*, które chcesz wzbogacić. Customer Insights będzie automatycznie mapować wymagane pola.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Wzbogacanie rekordów kontaktów Leadspace.":::

1. Wybierz **Dalej**.

1. Podaj **Nazwę** dla wzbogacenia oraz **Nazwa encji wyjściowej**.

1. Wybierz opcję **Zapisz wzbogacenie** po przejrzeniu wybranych opcji.

1. Wybierz przycisk **Uruchom**, aby rozpocząć proces wzbogacenia lub zamknąć, aby powrócić do strony **Wzbogacanie**.

## <a name="view-enrichment-results"></a>Wyświetlanie wyników wzbogacenia

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Aby uzyskać więcej informacji, zobacz [Interfejsy API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Następne kroki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]