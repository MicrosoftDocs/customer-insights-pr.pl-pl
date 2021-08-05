---
title: Wzbogacanie za pomocą strony trzeciej – Experian
description: Ogólne informacje o wzbogaceniach od zewnętrznej firmy Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: abe9ee447745081e3c462d44e5901b6dac919adf
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555366"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Wzbogać profile klientów dzięki danych demograficznych z Experian (wersja zapoznawcza)

Firma Experian jest światowym liderem w dziedzinie sprawozdawczości kredytowej dla konsumentów i przedsiębiorstw oraz usług marketingowych. Dzięki usługom wzbogacania danych firmy Experian możesz lepiej poznać swoich klientów, wzbogacając ich profile o dane demograficzne, takie jak wielkość gospodarstwa domowego, dochody i inne.

## <a name="prerequisites"></a>Wymagania wstępne

Aby można było skonfigurować wpisy do usługi Experian, muszą być spełnione następujące wymagania wstępne:

- Użytkownik musi mieć aktywną subskrypcję Experian. Aby uzyskać subskrypcję, skontaktuj się z [Experian](https://www.experian.com/marketing-services/contact). [Dowiedz się więcej o wzbogacaniu danych Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Połączenie Experian z usługą SFTP jest już skonfigurowane przez administratora *lub* użytkownik ma uprawnienia [administratora](permissions.md#administrator). Potrzebujesz także identyfikatora użytkownika, identyfikatora strony i numeru modelu konta Secure Transport (ST) z obsługą SSH, które zostało utworzone przez Experian.

## <a name="supported-countriesregions"></a>Obsługiwane kraje/regiony

Obecnie profily klientów są wzbogacane wyłącznie w Stanach Zjednoczonych.

## <a name="configure-the-enrichment"></a>Konfiguracja wzbogacania

1. Przejdź do **Dane** > **Wzbogacenie** i wybierz kartę **Odkrywanie**.

1. Wybierz opcję **Wzbogać dane** na kafelku Experian.

   > [!div class="mx-imgBorder"]
   > ![Kafelek Experian.](media/experian-tile.png "Experian tile")
   > 

1. Wybierz [połączenie](connections.md) z listy rozwijanej. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie. Jeśli jesteś administratorem, możesz utworzyć połączenie, wybierając **Dodaj połączenie** i wybierając Experian z listy rozwijanej. 

1. Wybierz opcję **Połącz z Experian**, aby potwierdzić wybór połączenia.

1.  Wybierz opcję **Dalej** i wybierz **zestaw danych klienta**, który chcesz wzbogacić danymi demograficznymi z Experian. Można wybrać encję **Klient**, aby wzbogacić wszystkie profile klientów, lub wybierz jednostkę segmentu, aby wzbogacić tylko profile klientów zawarte w tym segmencie.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Zrzut ekranu podczas wybierania zestawu danych klienta.":::

1. Wybierz opcję **Dalej** i zdefiniuj, jakiego typu pola z ujednoliconych profilów powinny być używane do wyszukiwania pasujących danych demograficznych w Experian. Wymagane jest co najmniej jedno z pól **Nazwa i adres**, **Telefon** lub **Wiadomość e-mail**. Aby dokładność dopasowania było lepsza, można dodać maksymalnie dwa inne pola. Ten wybór będzie miał wpływ na pola mapowania, do których użytkownik będzie miał dostęp w następnym kroku.

    > [!TIP]
    > Więcej wysłanych atrybutów kluczowych identyfikatorów do Experian daje większy odsetek dopasowania.

1. Wybierz **Dalej**, by rozpocząć mapowanie.

1. Zdefiniuj, jakiego typu pola z ujednoliconych profilów powinny być używane do wyszukiwania pasujących danych demograficznych w Experian. Zaznaczone pola są wymagane.

1. Podaj nazwę dla wzbogacania oraz nazwę encji wyjściowej.

1. Wybierz opcję **Zapisz wzbogacenie** po przejrzeniu wybranych opcji.

## <a name="configure-the-connection-for-experian"></a>Konfigurowanie ról połączeń w Experian 

Aby skonfigurować połączenia, użytkownik musi być administratorem. Wybierz opcję **Dodaj połączenie** podczas konfigurowania wzbogacania *lub* wybierz pozycję **Administracja** > **Połączenia** i wybierz opcję **Skonfiguruj** na kafelku Experian.

1. Wybierz **Rozpocznij**.

1. Wprowadź nazwę połączenia w polu **Wyświetlana nazwa**.

1. Wprowadź prawidłowy identyfikator użytkownika, identyfikator strony i numer modelu dla swojego konta Experian Secure Transport.

1. Przejrzyj i wyraź zgodę na **Zasady ochrony prywatności danych**, wybierając przycisk **I agree (Wyrażam zgodę)**.

1. Wybierz opcję **Weryfikuj**, aby sprawdzić poprawność konfiguracji.

1. Po zakończeniu weryfikacji wybierz opcję **Zapisz**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Menu konfiguracji łączności Experian.":::

## <a name="enrichment-results"></a>Wyniki wzbogacenia

Aby rozpocząć proces wzbogacania, wybierz **Uruchom** na pasku poleceń. Można również zezwolić, aby system automatycznie uruchamiał wzbogacenie w ramach [zaplanowanego odświeżenia](system.md#schedule-tab). Czas przetwarzania będzie zależał od wielkości danych klienta i procesów wzbogacania ustawionych dla konta przez Experian.

Po zakończeniu procesu wzbogacania można przejrzeć dane nowo wzbogacone profile klientów w **Moje wzbogacenia**. Ponadto znajdziesz tam czas ostatniej aktualizacji i liczbę wzbogaconych profilów.

Aby uzyskać dostęp do szczegółowego widoku poszczególnych wzbogaconych profilów, należy zaznaczyć **Wyświetl wzbogacone dane**.

## <a name="next-steps"></a>Następne kroki

Kompiluj na wierzchu wzbogaconych danych klientów. Twórz [segmenty](segments.md) i [miary](measures.md) oraz [eksportuj dane](export-destinations.md) w celu świadczenia klientom spersonalizowanych usług.

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Włączenie w Dynamics 365 Customer Insights opcji przekazywania danych do usługi Experian umożliwia przesyłanie danych poza granice obszaru zgodności dla Dynamics 365 Customer Insights, w tym potencjalnie poufne dane, takie jak dane osobiste. Microsoft będzie przekazywać takie dane zgodnie z Twoimi instrukcjami, ale to Ty jesteś odpowiedzialny za zapewnienie, że Experian spełnia wszelkie zobowiązania dotyczące prywatności i bezpieczeństwa, jakie możesz mieć. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć wzbogacanie, aby przestać używać tej funkcji.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
