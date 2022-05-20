---
title: Wzbogacanie profilów klientów na podstawie danych lokalizacji z usługi Azure Maps
description: Ogólne informacje o wzbogaceniach od naszej firmy w usłudze Azure Maps.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 6d43dc2ca82c034fbd396d92637e7aea8179df77
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755367"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Wzbogacanie profilów klientów za pomocą usługi Azure Maps (wersja zapoznawcza)

Usługa Azure Maps zapewnia dane i usługi oparte na lokalizacjach, dzięki którym można dostarczać dane geoprzestrzenne na podstawie danych geograficznych przy użyciu wbudowanej funkcji analizy lokalizacji. Usługi wzbogacenia danych za pomocą usługi Azure Maps poprawiają dokładność informacji o lokalizacjach klientów. Dodają one funkcje, takie jak normalizacja adresu i wyodrębnianie szerokości i długości geograficznej, do aplikacji Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Wymagania wstępne

Aby skonfigurować wzbogacenie danych za pomocą usługi Azure Maps, należy spełnić następujące wymagania wstępne:

- Użytkownik musi mieć aktywną subskrypcję usługi Azure Maps. Aby uzyskać subskrypcję, możesz się [zarejestrować lub uzyskać bezpłatną wersję próbną](https://azure.microsoft.com/services/azure-maps/).

- [Połączenie](connections.md) usług Azure Maps jest dostępne *lub* masz uprawnienia [administratora](permissions.md#admin) i aktywny klucz interfejsu API usługi Azure Maps.

## <a name="configure-the-enrichment"></a>Konfiguracja wzbogacania

1. Przejdź do **Dane** > **Wzbogacanie**. 

1. Na kafelku **Lokalizacja** wybierz pozycję **Wzbogać moje dane**.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Kafelek usługi Azure Maps.":::

1. Wybierz [połączenie](connections.md) z listy rozwijanej. Skontaktuj się z administratorem, jeśli nie jest dostępne połączenie z usługą Azure Maps. Jeśli jesteś administratorem, możesz [skonfigurować połączenie dla usługi Azure Maps](#configure-the-connection-for-azure-maps). 

1. Wybierz opcję **Dalej**, aby potwierdzić wybór.

1. Wybierz **zestaw danych klienta**, który chcesz wzbogacić przy użyciu danych lokalizacji z usługi Azure Maps. Można wybrać encję **Klient**, aby wzbogacić wszystkie ujednolicone profile klientów, lub wybrać encję segmentu, aby wzbogacić tylko profile klientów zawarte w tym segmencie.

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="Zrzut ekranu podczas wybierania zestawu danych klienta.":::

1. Wybierz, czy pola mają być mapowane na adres podstawowy i/lub pomocniczy. Można określić mapowanie pól dla obu adresów i wzbogacić profile dla obu adresów oddzielnie &mdash; na przykład dla adresu głównego i adresu służbowego. Wybierz **Dalej**.

1. Zdefiniuj, jakiego typu pola z ujednoliconych profilów mają być używane do wyszukiwania danych lokalizacji z usługi Azure Maps. Dla wybranego adresu podstawowego lub pomocniczego wymagane są pola **Ulica 1** i **Kod pocztowy**. Aby dokładność dopasowania było większa, można dodać więcej pól.

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Strona konfiguracji wzbogacenia w usłudze Azure Maps.":::

1. Wybierz **Dalej**, by zakończyć mapowanie pól.

1. Oceń, czy chcesz zmodyfikować **ustawienia zaawansowane**. Ustawienia te zostały wprowadzone, by zapewnić maksymalną elastyczność w obsłudze zaawansowanych przypadków użycia, ale wartości domyślne będą wystarczające w większości przypadków:
   - **Typ adresów**: domyślnym zachowaniem jest to, że wzbogacenie zwraca najlepsze dopasowanie adresu, nawet jeśli jest niekompletne. Aby otrzymać tylko pełne adresy &mdash; na przykład adresy z numerem telefonu &mdash; wyczyść wszystkie pola wyboru poza polem **Adresy punktów**. 
   - **Język**: domyślnie adresy są zwracane w języku regionu, do którego został określony adres. Aby zastosować ustandaryzowany język adresu, wybierz język z menu rozwijanego. Na przykład wybranie opcji **Angielski** zwróci wartość **Copenhagen, Denmark**, zamiast **København, Danmark**.

1. Podaj nazwę wzbogacenia.

1. Przejrzyj wybrane wartości, a następnie kliknij przycisk **Zapisz wzbogacenie**.

## <a name="configure-the-connection-for-azure-maps"></a>Konfigurowanie połączenia dla usługi Azure Maps

Aby konfigurować połączenia, musisz być administratorem w aplikacji Customer Insights. Wybierz opcję **Dodaj połączenie** podczas konfigurowania wzbogacenia lub wybierz pozycję **Administracja** > **Połączenia** i wybierz opcję **Skonfiguruj** na kafelku usługi Azure Maps.

1. W polu **Nazwa wyświetlana** wprowadź nazwę połączenia.

1. Podaj prawidłowy klucz interfejsu API usługi Azure Maps.

1. Sprawdź poprawność i wyraź zgodę na **Prywatność danych i zgodność z przepisami** zaznaczając pole wyboru **Zgadzam się**

1. Wybierz opcję **Weryfikuj**, aby sprawdzić poprawność konfiguracji.

1. Po zakończeniu weryfikacji wybierz opcję **Zapisz**.

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Strona konfiguracji połączenia w usłudze Azure Maps.":::

## <a name="enrichment-results"></a>Wyniki wzbogacenia

Aby rozpocząć proces wzbogacania, wybierz **Uruchom** na pasku poleceń. Można również zezwolić, aby system automatycznie uruchamiał wzbogacenie w ramach [zaplanowanego odświeżenia](system.md#schedule-tab). Czas przetwarzania zależy od rozmiaru danych klienta i czasu odpowiedzi interfejsu API.

Po zakończeniu procesu wzbogacania można w obszarze **Moje wzbogacenia** przejrzeć nowo wzbogacone dane profilów klientów. Ponadto znajdziesz tam czas ostatniej aktualizacji i liczbę wzbogaconych profilów.

Aby uzyskać dostęp do szczegółowego widoku poszczególnych wzbogaconych profilów, należy zaznaczyć **Wyświetl wzbogacone dane**.

## <a name="next-steps"></a>Następne kroki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Włączenie funkcji przekazywania danych do usługi Azure Maps w aplikacji Dynamics 365 Customer Insights umożliwia przesyłanie danych poza granice obszaru zgodności dla aplikacji Dynamics 365 Customer Insights, w tym potencjalnie poufnych danych, takich jak dane osobiste. Microsoft przekaże takie dane na twoje polecenie, ale to ty jesteś odpowiedzialny za zapewnienie, że spotkanie Azure Maps spełnia wszelkie zobowiązania dotyczące prywatności i bezpieczeństwa, jakie możesz mieć. Więcej informacji można znaleźć w [Oświadczeniu o ochronie prywatności Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć wzbogacanie, aby przestać używać tej funkcji.

[!INCLUDE [footer-include](includes/footer-banner.md)]
