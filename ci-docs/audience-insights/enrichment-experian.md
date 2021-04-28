---
title: Wzbogacanie danych za pomocą Experian innych firm
description: Ogólne informacje o wzbogacaniu strony trzeciej Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896386"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Wzbogacanie profilów klientów za pomocą danych demograficznych z Experian (wersja zapoznawcza)

Experian jest globalnym liderem w zakresie sprawozdawczości kredytowej dla konsumentów i firm oraz usług marketingowych. Dzięki usługom wzbogacania Experian można lepiej zrozumieć klientów, wzmacniając profile klientów danymi demograficznymi, takimi jak rozmiar gospodarstwa domowego, przychód itp.

## <a name="prerequisites"></a>Wymagania wstępne

Aby skonfigurować Experian, należy spełnić następujące wymagania wstępne:

- Użytkownik ma aktywną subskrypcję Experian. Aby uzyskać subskrypcję, [skontaktuj się z Experian](https://www.experian.com/marketing-services/contact) bezpośrednio. [Dowiedz się więcej na temat Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Połączenie z programem Experian jest już skonfigurowane przez administratora *lub* użytkownik ma uprawnienia [administratora](permissions.md#administrator). Potrzebny jest także identyfikator użytkownika, identyfikator strony i numer modelu dla konta bezpiecznego transportu (ST) z włączoną usługą SSH, które utworzył dla użytkownika program Experian.

## <a name="configure-the-enrichment"></a>Konfiguracja wzbogacania

1. Przejdź do **Dane** > **Wzbogacenie** i wybierz kartę **Odkrywanie**.

1. Wybierz **Wzbogać moje dane** na kafelku Experian.

   > [!div class="mx-imgBorder"]
   > ![Kafelek Experian](media/experian-tile.png "Kafelek Experian")
   > 

1. Wybierz [połączenie](connections.md) z listy rozwijanej. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie. Jeśli użytkownik jest administratorem, może on utworzyć połączenie, wybierając opcję **Dodaj połączenie** i wybierając pozycję Experian z listy rozwijanej. 

1. Wybierz opcję **Połącz z programem Experian**, aby potwierdzić wybrane połączenie.

1.  Wybierz opcję **Dalej** i wybierz **Zestaw danych klienta**, który chcesz wzbogacić danymi demograficznymi z programu Experian. Można wybrać encję **Klient**, aby wzbogacić wszystkie profile klientów, lub wybierz jednostkę segmentu, aby wzbogacić tylko profile klientów zawarte w tym segmencie.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Zrzut ekranu podczas wybierania zestawu danych klienta.":::

1. Wybierz opcję **Dalej** i zdefiniuj, jakiego typu pola z ujednoliconych profilów powinny być używane do wyszukiwania pasujących danych demograficznych z programu Experian. Wymagane jest co najmniej jedno z pól **Nazwa i adres**, **Telefon** lub **Wiadomość e-mail**. Aby dokładność dopasowania było lepsza, można dodać maksymalnie dwa inne pola. Ten wybór będzie miał wpływ na pola mapowania, do których użytkownik będzie miał dostęp w następnym kroku.

    > [!TIP]
    > Więcej atrybutów identyfikatorów kluczy wysłanych do Experian prawdopodobnie zapewni wyższy współczynnik zgodności.

1. Wybierz **Dalej**, by rozpocząć mapowanie.

1. Zdefiniuj, jakie pola z ujednoliconych profilów powinny być używane do wyszukiwania pasujących danych demograficznych z programu Experian. Zaznaczone pola są wymagane.

1. Podaj nazwę dla wzbogacania oraz nazwę encji wyjściowej.

1. Wybierz opcję **Zapisz wzbogacenie** po przejrzeniu wybranych opcji.

## <a name="configure-the-connection-for-experian"></a>Konfigurowanie połączenia dla programu Experian 

Aby skonfigurować połączenia, użytkownik musi być administratorem. Wybierz opcję **Dodaj połączenie** podczas konfigurowania wzbogacania *lub* wybierz pozycję **Admin** > **Połączenia** i wybierz opcję **Konfiguruj** na kafelku Experian.

1. Wybierz **Rozpocznij**.

1. Wprowadź nazwę połączenia w polu **Wyświetlana nazwa**.

1. Wprowadź prawidłowy identyfikator użytkownika, identyfikator strony i numer modelu dla swojego konta bezpiecznego transportu Experian.

1. Sprawdź poprawność i wyraź zgodę na **Prywatność danych i zgodność z przepisami** zaznaczając pole wyboru **Zgadzam się**

1. Wybierz opcję **Weryfikuj**, aby sprawdzić poprawność konfiguracji.

1. Po zakończeniu weryfikacji wybierz opcję **Zapisz**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Okienko konfiguracji połączenia programu Experian.":::

## <a name="enrichment-results"></a>Wyniki wzbogacenia

Aby rozpocząć proces wzbogacania, wybierz **Uruchom** na pasku poleceń. Można również zezwolić, aby system automatycznie uruchamiał wzbogacenie w ramach [zaplanowanego odświeżenia](system.md#schedule-tab). Czas przetwarzania będzie uzależniony od wielkości danych klienta i procesów wzbogacania ustanowionych dla konta przez Experian.

Po zakończeniu procesu wzbogacania można przejrzeć dane nowo wzbogacone profile klientów w **Moje wzbogacenia**. Ponadto znajdziesz tam czas ostatniej aktualizacji i liczbę wzbogaconych profilów.

Aby uzyskać dostęp do szczegółowego widoku poszczególnych wzbogaconych profilów, należy zaznaczyć **Wyświetl wzbogacone dane**.

## <a name="next-steps"></a>Następne kroki

Kompiluj na wierzchu wzbogaconych danych klientów. Utwórz [segmenty](segments.md), [miary](measures.md), a nawet [eksportuj dane](export-destinations.md), aby zapewnić klientom spersonalizowane rozwiązania.

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Experian można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że Experian spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć wzbogacanie, aby przestać używać tej funkcji.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
