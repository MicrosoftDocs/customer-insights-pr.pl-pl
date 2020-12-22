---
title: Wzbogacanie profili firm o zewnętrzne wzbogacenie Leadspace
description: Ogólne informacje o wzbogacaniu strony trzeciej Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668736"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Wzbogacanie profili firm z Leadspace (wersja zapoznawcza)

Leadspace jest firmą badawczą, która dostarcza platformę danych klientów typu B2B. Dzięki niej klienci z ujednoliconymi profilami klientów dla firm mogą wzbogacać swoje dane. Wzbogacenia obejmują dodatkowe atrybuty, takie jak wielkość firmy, lokalizacja, branża i inne.

## <a name="prerequisites"></a>Wymagania wstępne

Aby skonfigurować Leadspce muszą być spełnione następujące wymagania wstępne:

- Posiadasz aktywną licencję Leadspace i „wieczysty klucz” (określany jako **token Leadspace**). Skontaktuj się bezpośrednio z [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/), aby uzyskać szczegółowe informacje na temat ich produktu.
- Masz uprawnienia [Administratora](permissions.md#administrator).
- Istnieją [ujednolicone profile klientów](customer-profiles.md) dla firm.

## <a name="configuration"></a>Konfiguracja

1. W analizach odbiorców przejdź do **Dane** > **Wzbogacenie**.

1. Wybierz **Wzbogać moje dane** na kafelku Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Zrzut ekranu kafelka Leadspace.":::

1. Wybierz pozycję **Rozpocznij**, a następnie wprowadź aktywny **token Leadspace** (klucz wieczysty). Sprawdź poprawność i wyraź zgodę na **Prywatność danych i zgodność z przepisami** zaznaczając pole wyboru **Zgadzam się**. Potwierdzenie obydwu składników są wprowadzane po wybraniu opcji **Połącz z Leadspace**.

1. Wybierz opcję **Mapowanie danych** i zdefiniuj pola w ujednoliconych profilach, aby wyszukać pasujące dane firmy pochodzące z Leadspace. Pole **Nazwa firmy** jest wymagane. Aby zwiększyć dokładność dopasowania, można dodać maksymalnie dwa inne pola, **Witrynę sieci Web firmy** i **Lokalizację firmy**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Okienko mapowania pola Leadspace.":::
   
1. Wybierz opcję **Zastosuj**, aby zakończyć mapowanie pola.

1. Wybierz **Uruchom**, aby wzbogacić profile firm. Czas trwania wzbogacenia zależy od liczby ujednoliconych profilów klientów.

## <a name="enrichment-results"></a>Wyniki wzbogacenia

Po odświeżeniu wzbogacenia można zapoznać się z nowo wzbogaconymi danymi firmowymi w ramach [Moje wzbogacenia](enrichment-hub.md). Możesz sprawdzić czas ostatniej aktualizacji oraz liczbę wzbogaconych profilów.

Aby uzyskać dostęp do szczegółowego widoku poszczególnych wzbogaconych profilów, należy zaznaczyć **Wyświetl wzbogacone dane**.

Aby uzyskać więcej informacji, zobacz [Interfejsy API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Następne kroki

Kompiluj na wierzchu wzbogaconych danych klientów. Utwórz [segmenty](segments.md), [miary](measures.md), a nawet [eksportuj dane](export-destinations.md), aby zapewnić klientom spersonalizowane rozwiązania.

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Leadspace można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że Leadspace spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć wzbogacanie, aby przestać używać tej funkcji.