---
title: Wzbogacanie za pomocą strony trzeciej – Experian
description: Ogólne informacje o wzbogaceniach od zewnętrznej firmy Experian.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 735da18e584b0d9db76b557f4d16dbdf1757f33c
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954100"
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

1. Przejrzyj i wyraź zgodę na [Zasady ochrony prywatności danych](#data-privacy-and-compliance), wybierając przycisk **I agree (Wyrażam zgodę)**.

1. Wybierz **Weryfikuj**, aby sprawdzić poprawność konfiguracji, a następnie wybierz opcję **Zapisz**.

### <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Włączenie w Dynamics 365 Customer Insights opcji przekazywania danych do usługi Experian umożliwia przesyłanie danych poza granice obszaru zgodności dla Dynamics 365 Customer Insights, w tym potencjalnie poufne dane, takie jak dane osobiste. Microsoft będzie przekazywać takie dane zgodnie z Twoimi instrukcjami, ale to Ty jesteś odpowiedzialny za zapewnienie, że Experian spełnia wszelkie zobowiązania dotyczące prywatności i bezpieczeństwa, jakie możesz mieć. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732). Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć wzbogacanie, aby przestać używać tej funkcji.

## <a name="configure-the-enrichment"></a>Konfiguracja wzbogacania

1. Przejdź do **Dane** > **Wzbogacenie** i wybierz kartę **Odkrywanie**.

1. Wybierz opcję **Wzbogać moje dane** na kafelku Experian z **Dane demograficzne**.

   :::image type="content" source="media/experian-tile.png" alt-text="Kafelek Experian na stronie przeglądu wzbogacania. ":::

1. Przejrzyj omówienie, a następnie wybierz **Dalej**.

1. Wybierz połączenie. Skontaktuj się z administratorem, jeśli nie jest dostępne.

1. Wybierz **Dalej**.

1. Wybierz **Zestaw danych klienta** i wybierz profil i segment, który chcesz wzbogacić o dane demograficzne z Experian. Można wybrać encję *Klient*, aby wzbogacić wszystkie profile klientów, lub wybierz jednostkę segmentu, aby wzbogacić tylko profile klientów zawarte w tym segmencie.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Zrzut ekranu podczas wybierania zestawu danych klienta.":::

1. Określ, jakiego typu pola z twoich profili zunifikowanych powinny być używane do wyszukiwania demograficznych z Experian. Wymagane jest co najmniej jedno z pól **Nazwa i adres**, **Telefon** lub **Wiadomość e-mail**. Aby uzyskać większą dokładność dopasowania, należy dodać inne pola. Wybierz **Dalej**.

1. Zamapuj pola na dane demograficzne z Experian.

1. Wybierz **Dalej**, by zakończyć mapowanie pól.

1. Podaj **Nazwę** dla wzbogacenia oraz **Nazwa encji wyjściowej**.

1. Wybierz opcję **Zapisz wzbogacenie** po przejrzeniu wybranych opcji.

1. Wybierz przycisk **Uruchom**, aby rozpocząć proces wzbogacenia lub zamknąć, aby powrócić do strony **Wzbogacanie**.

## <a name="enrichment-results"></a>Wyniki wzbogacenia

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Liczba klientów wzbogaconych według pola** zapewnia szczegółowe informacje na temat pokrycia każdego wzbogaconego pola.

## <a name="next-steps"></a>Następne kroki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
