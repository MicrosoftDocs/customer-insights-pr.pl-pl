---
title: Wzbogacanie danych tożsamościowych LiveRamp
description: Wzbogać profile klientów o dane LiveRamp.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0727818f6df565d9a031966a68d521ae7167e484
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646713"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Wzbogacanie profilów klientów przy użyciu danych tożsamości z LiveRamp (wersja zapoznawcza) 

LiveRamp zapewnia deterministyczne rozwiązywanie problemów z tożsamością w trybie offline i konsolidację danych klientów. Możesz mapować osobiste identyfikatory w swoich danych klientów do grafu tożsamości AbiliTec i otrzymywać identyfikatory AbiliTec. Możesz wtedy wykorzystać te identyfikatory do lepszego ujednolicenia danych klientów. 

## <a name="prerequisites"></a>Wymagania wstępne 

Aby skonfigurować wzbogacenie, muszą być spełnione następujące warunki wstępne: 

- Masz aktywną subskrypcję LiveRamp. Aby uzyskać subskrypcję, skontaktuj się ze swoim zespołem ds. konta LiveRamp lub z [dynamics@liveramp.com](mailto:dynamics@liveramp.com), aby uzyskać więcej informacji.   

- Aktywna subskrypcja AbiliTec z identyfikatorem klienta i sekretem umożliwiającym dostęp do API. Aby uzyskać więcej informacji, zobacz [Centrum dla deweloperów AbiliTec API](https://developers.liveramp.com/abilitec-api/). 

## <a name="supported-countriesregions"></a>Obsługiwane kraje/regiony 

Obecnie wspieramy wzbogacanie profili klientów o dane LiveRamp tylko w Stanach Zjednoczonych. 

## <a name="configure-the-enrichment"></a>Konfiguracja wzbogacania 

1. Przejdź do **Dane** > **Wzbogacenie** i wybierz kartę **Odkrywanie**. 

1. Wybierz opcję **Wzbogać moje dane** na kafelku **Tożsamość**. 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Kafelek Tożsamość na stronie przeglądu wzbogacania. ":::

1. Wybierz [połączenie](connections.md) z listy rozwijanej. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie. Jeśli jesteś administratorem, możesz utworzyć połączenie, wybierając **Dodaj połączenie**. Z rozwijanej listy wybierz **LiveRamp**. 

1. Wybierz **Następny** i wybierz **Zestaw danych klienta**, który chcesz wzbogacić o dane dotyczące tożsamości z LiveRamp. Można wybrać encję *Klient*, aby wzbogacić wszystkie profile klientów, lub wybierz jednostkę *segmentu*, aby wzbogacić tylko profile klientów zawarte w tym segmencie. 

1. Wybierz **Następny** i określ, jakiego typu pola z twoich profili zunifikowanych powinny być używane do wyszukiwania pasujących danych tożsamości w LiveRamp. Przynajmniej jedno z pól **Imię/nazwisko i adres**, **Telefon** lub **E-mail** jest wymagane. 

   > [!TIP]
   > Im więcej kluczowych identyfikatorów i pól mapuje się, tym wyższe jest prawdopodobieństwo dopasowania 

1. Zmapuj pola z twojej zunifikowanej encji *Klient*, które będą używane do dopasowania do grafu ID AbiliTec LiveRamp. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Opcje mapowania danych dla wzbogacenia LiveRamp.":::

1. Wybierz **Dalej**, by zakończyć mapowanie pól. 

1. Podaj **Nazwę** dla wzbogacenia oraz **Obiekt wyjściowy**. 

1. Wybierz opcję **Zapisz wzbogacenie** po przejrzeniu wybranych opcji. 

## <a name="configure-the-connection-for-liveramp"></a>Skonfiguruj połączenie dla LiveRamp 

Aby [skonfigurować połączenia](connections.md), użytkownik musi być administratorem. Wybierz **Dodaj połączenie** podczas konfigurowania wzbogacenia lub przejdź do **Admin** > **Połączenia** i wybierz **Ustaw** na kafelku **LiveRamp**. 

:::image type="content" source="media/liveramp-connection.png" alt-text="Panel Konfiguracja służy do skonfigurowania połączenia z usługą LiveRamp AbiliTec. ":::

1. W polu **Nazwa wyświetlacza** wpisz nazwę połączenia. 

1. Podaj prawidłowy identyfikator klienta LiveRamp oraz klucz tajny. 

1. Sprawdź poprawność i wyraź zgodę na **Prywatność danych i zgodność z przepisami** zaznaczając pole wyboru **Zgadzam się**. 

1. Wybierz opcję **Weryfikuj**, aby sprawdzić poprawność konfiguracji. 

1. Wybierz pozycję **Zapisz**, aby zakończyć połączenie. 

## <a name="enrichment-results"></a>Wyniki wzbogacenia 

Aby rozpocząć proces wzbogacania, wybierz Uruchom na pasku poleceń. Można również zezwolić, aby system automatycznie uruchamiał wzbogacenie w ramach  [zaplanowanego odświeżenia](system.md#schedule-tab). Czas przetwarzania zależy od rozmiaru danych klienta. 

Po zakończeniu procesu wzbogacania możesz przejrzeć nowo wzbogacone dane profilu klienta w zakładce  **Moje wzbogacenia**. Ponadto znajdziesz tam czas ostatniej aktualizacji i liczbę wzbogaconych profilów. 

Aby uzyskać dostęp do szczegółowego widoku poszczególnych wzbogaconych profilów, należy zaznaczyć  **Wyświetl wzbogacone** dane. 

## <a name="next-steps"></a>Następne kroki

Kompiluj na wierzchu wzbogaconych danych klientów. Użyj identyfikatorów AbiliTec, aby skonsolidować profile klientów w widoku opartym na osobach. 
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami 

Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi LiveRamp można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft przekaże takie dane na twoje polecenie, ale to ty jesteś odpowiedzialny za zapewnienie, że LiveRamp spełnia wszelkie zobowiązania dotyczące prywatności i bezpieczeństwa, jakie możesz mieć. Aby uzyskać więcej informacji, zapoznaj się z [Oświadczeniem o ochronie prywatności firmy Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć wzbogacanie, aby przestać używać tej funkcji. 


[!INCLUDE [footer-include](includes/footer-banner.md)]
