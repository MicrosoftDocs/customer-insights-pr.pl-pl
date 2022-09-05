---
title: Wzbogać profile klientów dzięki danych demograficznych z Experian (wersja zapoznawcza)
description: Ogólne informacje o wzbogaceniach od zewnętrznej firmy Experian.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: fccb37cde3f05a70009c18b6c52db01a5ede094d
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/08/2022
ms.locfileid: "9238009"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Wzbogać profile klientów dzięki danych demograficznych z Experian (wersja zapoznawcza)

Firma Experian jest światowym liderem w dziedzinie sprawozdawczości kredytowej dla konsumentów i przedsiębiorstw oraz usług marketingowych. Dzięki usługom wzbogacania danych firmy Experian możesz lepiej poznać swoich klientów, wzbogacając ich profile o dane demograficzne, takie jak wielkość gospodarstwa domowego, dochody i inne.

## <a name="supported-countriesregions"></a>Obsługiwane kraje/regiony

Obecnie profily klientów są wzbogacane wyłącznie w Stanach Zjednoczonych.

## <a name="prerequisites"></a>Wymagania wstępne

- Pobierz aktywne subskrypcje Experian. Aby uzyskać subskrypcję, skontaktuj się z [Experian](https://www.experian.com/marketing-services/contact). [Dowiedz się więcej o wzbogacaniu danych Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- [Połączenie](connections.md) Experian jest [konfigurowane](#configure-the-connection-for-experian) przez administratora.

- Identyfikator użytkownika Experian, identyfikator strony i numer modelu dla utworzonego dla konta Secure Transport z SSH (ST), które Experian utworzył dla użytkownika.

## <a name="configure-the-connection-for-experian"></a>Konfigurowanie ról połączeń w Experian

Użytkownik musi być [administratorem](permissions.md#admin) Customer Insights i mieć aktywny identyfikator klienta Experian, identyfikator strony i numer modelu.

1. Wybierz opcję **Dodaj połączenie** podczas konfigurowania wzbogacania lub wybierz pozycję **Administracja** > **Połączenia** i wybierz opcję **Skonfiguruj** na kafelku Experian.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Menu konfiguracji łączności Experian.":::

1. Wprowadź nazwę połączenia i prawidłowy identyfikator użytkownika, identyfikator strony i numer modelu dla bezpiecznego konta transportowego Experian.

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Wybierz **Weryfikuj**, aby sprawdzić poprawność konfiguracji, a następnie wybierz opcję **Zapisz**.

## <a name="configure-the-enrichment"></a>Konfiguracja wzbogacania

1. Przejdź do **Dane** > **Wzbogacenie** i wybierz kartę **Odkrywanie**.

1. Wybierz opcję **Wzbogać moje dane** na kafelku Experian z **Dane demograficzne**.

   :::image type="content" source="media/experian-tile.png" alt-text="Kafelek Experian na stronie przeglądu wzbogacania. ":::

1. Przejrzyj omówienie, a następnie wybierz **Dalej**.

1. Wybierz połączenie. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wybierz **Dalej**.

1. Wybierz **Zestaw danych klienta** i wybierz profil i segment, który chcesz wzbogacić o dane demograficzne z Experian. Można wybrać encję *Klient*, aby wzbogacić wszystkie profile klientów, lub wybierz jednostkę segmentu, aby wzbogacić tylko profile klientów zawarte w tym segmencie.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Zrzut ekranu podczas wybierania zestawu danych klienta.":::

1. Określ, jakiego typu pola z twoich profili zunifikowanych powinny być używane do wyszukiwania demograficznych z Experian. Wymagane jest co najmniej jedno z pól **Nazwa i adres**, **Telefon** lub **Wiadomość e-mail**. Aby uzyskać większą dokładność dopasowania, należy dodać inne pola. Wybierz **Dalej**.

1. Zamapuj pola na dane demograficzne z Experian.

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