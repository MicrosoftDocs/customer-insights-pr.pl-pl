---
title: Wzbogacanie danych za pomocą Experian innych firm
description: Ogólne informacje o wzbogacaniu strony trzeciej Experian.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668825"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Wzbogacanie profilów klientów za pomocą danych demograficznych z Experian (wersja zapoznawcza)

Experian jest globalnym liderem w zakresie sprawozdawczości kredytowej dla konsumentów i firm oraz usług marketingowych. Dzięki usługom wzbogacania Experian można lepiej zrozumieć klientów, wzmacniając profile klientów danymi demograficznymi, takimi jak rozmiar gospodarstwa domowego, przychód itp.

## <a name="prerequisites"></a>Wymagania wstępne

Aby skonfigurować Experian, należy spełnić następujące wymagania wstępne:

- Użytkownik ma aktywną subskrypcję Experian. Aby uzyskać subskrypcję, [skontaktuj się z Experian](https://www.experian.com/marketing-services/contact) bezpośrednio. [Dowiedz się więcej na temat Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).
- Użytkownik posiada Identyfikator użytkownika, Identyfikator jednostki i numer modelu dla konta usługi Secure Transport (ST) SSH, które Experian utworzył dla użytkownika.
- Posiadasz uprawnienia [Administratora](permissions.md#administrator) w analizach odbiorców.

## <a name="configuration"></a>Konfiguracja

1. Przejdź do **Dane** > **Wzbogacenie** i wybierz kartę **Odkrywanie**.

1. Wybierz **Wzbogać moje dane** na kafelku Experian.

   > [!div class="mx-imgBorder"]
   > ![Kafelek Experian](media/experian-tile.png "Kafelek Experian")

1. Wybierz **Rozpocznij** i wprowadź identyfikator użytkownika, identyfikator jednostki i numer modelu dla Twojego konta Experian Secure Transport. Sprawdź poprawność i wyraź zgodę na **Prywatność danych i zgodność z przepisami** zaznaczając pole wyboru **Zgadzam się**. Aby potwierdzić wszystkie dane, należy wybrać opcję **Zastosuj**.

## <a name="map-your-fields"></a>Zamapuj swoje pola

1. Wybierz opcję **Dodaj dane** i wybierz identyfikatory kluczy z **Nazwa i adres**, **E-mail** lub **Telefon**, aby wysłać do Experian w celu rozpoznania tożsamości.

   > [!TIP]
   > Więcej atrybutów identyfikatorów kluczy wysłanych do Experian prawdopodobnie zapewni wyższy współczynnik zgodności.

1. Wybierz **Dalej** i zamapuj odpowiednie atrybuty z encji Unified Customer dla wybranych pól identyfikatorów kluczy.

1. Wybierz **Dodaj atrybut**, aby zamapować wszelkie dodatkowe atrybuty, które chcesz wysłać do Experian.

1.  Wybierz **Zapisz**, aby zakończyć mapowanie pola.

   > [!div class="mx-imgBorder"]
   > ![Mapowanie pól Experian](media/experian-field-mapping.png "Mapowanie pól Experian")

## <a name="enrichment-results"></a>Wyniki wzbogacenia

Aby rozpocząć proces wzbogacania, wybierz **Uruchom** na pasku poleceń. Można również zezwolić, aby system automatycznie uruchamiał wzbogacenie w ramach [zaplanowanego odświeżenia](system.md#schedule-tab). Czas przetwarzania będzie uzależniony od wielkości danych klienta i procesów wzbogacania ustanowionych dla konta przez Experian.

Po zakończeniu procesu wzbogacania można przejrzeć dane nowo wzbogacone profile klientów w **Moje wzbogacenia**. Ponadto znajdziesz tam czas ostatniej aktualizacji i liczbę wzbogaconych profilów.

Aby uzyskać dostęp do szczegółowego widoku poszczególnych wzbogaconych profilów, należy zaznaczyć **Wyświetl wzbogacone dane**.

## <a name="next-steps"></a>Następne kroki

Kompiluj na wierzchu wzbogaconych danych klientów. Utwórz [segmenty](segments.md), [miary](measures.md), a nawet [eksportuj dane](export-destinations.md), aby zapewnić klientom spersonalizowane rozwiązania.

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Experian można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że Experian spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć wzbogacanie, aby przestać używać tej funkcji.