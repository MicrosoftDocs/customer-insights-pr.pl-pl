---
title: Wzbogacanie profilów klientów przy użyciu danych tożsamości z LiveRamp (wersja zapoznawcza)
description: Wzbogać profile klientów o dane LiveRamp.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0aa6dc144602741b87843a5373779855ee3e334c
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237826"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Wzbogacanie profilów klientów przy użyciu danych tożsamości z LiveRamp (wersja zapoznawcza)

LiveRamp zapewnia deterministyczne rozwiązywanie problemów z tożsamością w trybie offline i konsolidację danych klientów. Możesz mapować osobiste identyfikatory w swoich danych klientów do grafu tożsamości AbiliTec i otrzymywać identyfikatory AbiliTec. Możesz wtedy wykorzystać te identyfikatory do lepszego ujednolicenia danych klientów.

## <a name="supported-countriesregions"></a>Obsługiwane kraje/regiony

Obecnie wspieramy wzbogacanie profili klientów o dane LiveRamp tylko w Stanach Zjednoczonych.

## <a name="prerequisites"></a>Wymagania wstępne

- Aktywna subskrypcja LiveRamp. Aby uzyskać subskrypcję, skontaktuj się ze swoim zespołem ds. konta LiveRamp lub z [dynamics@liveramp.com](mailto:dynamics@liveramp.com), aby uzyskać więcej informacji.

- Aktywna subskrypcja AbiliTec z identyfikatorem klienta i sekretem umożliwiającym dostęp do API. Aby uzyskać więcej informacji, zobacz [Centrum dla deweloperów AbiliTec API](https://developers.liveramp.com/abilitec-api/).

- [Połączenie](connections.md) LiveRamp jest [konfigurowane](#configure-the-connection-for-liveramp) przez administratora.

## <a name="configure-the-connection-for-liveramp"></a>Skonfiguruj połączenie dla LiveRamp

Użytkownik musi być [administratorem](permissions.md#admin) Customer Insights i mieć aktywny identyfikator klienta LiveRamp oraz wpis tajny.

1. Wybierz **Dodaj połączenie** podczas konfigurowania wzbogacenia lub przejdź do **Admin** > **Połączenia** i wybierz **Ustaw** na kafelku LiveRamp.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Panel Konfiguracja służy do skonfigurowania połączenia z usługą LiveRamp AbiliTec. ":::

1. Wprowadź nazwę połączenia i prawidłowy identyfikator klienta usługi LiveRamp oraz wpis tajny.

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Wybierz **Weryfikuj**, aby sprawdzić poprawność konfiguracji, a następnie wybierz opcję **Zapisz**.

## <a name="configure-the-enrichment"></a>Konfiguracja wzbogacania

1. Przejdź do **Dane** > **Wzbogacenie** i wybierz kartę **Odkrywanie**.

1. Wybierz opcję **Wzbogać moje dane** na kafelku LiveRamp **Tożsamość**.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Kafelek Tożsamość na stronie przeglądu wzbogacania. ":::

1. Przejrzyj omówienie, a następnie wybierz **Dalej**.

1. Wybierz połączenie. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wybierz **Dalej**.

1. Wybierz **Zestaw danych klienta** i wybierz profil i segment, który chcesz wzbogacić o dane dotyczące tożsamości z LiveRamp. Można wybrać encję *Klient*, aby wzbogacić wszystkie profile klientów, lub wybierz jednostkę segmentu, aby wzbogacić tylko profile klientów zawarte w tym segmencie.

1. Określ, jakiego typu pola z twoich profili zunifikowanych powinny być używane do wyszukiwania pasujących danych tożsamości w LiveRamp. Przynajmniej jedno z pól **Imię/nazwisko i adres**, **E-mail** lub **Telefon** jest wymagane. Aby uzyskać większą dokładność dopasowania, należy dodać inne pola. Wybierz **Dalej**.

1. Zamapuj pola na dane identyfikujące z witryny LiveRamp.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Opcje mapowania danych dla wzbogacenia LiveRamp.":::

1. Wybierz **Dalej**, by zakończyć mapowanie pól.

1. Podaj **Nazwę** dla wzbogacenia oraz **Nazwa encji wyjściowej**.

1. Wybierz opcję **Zapisz wzbogacenie** po przejrzeniu wybranych opcji.

1. Wybierz przycisk **Uruchom**, aby rozpocząć proces wzbogacenia lub zamknąć, aby powrócić do strony **Wzbogacanie**.

## <a name="view-enrichment-results"></a>Wyświetlanie wyników wzbogacenia

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Liczba klientów wzbogaconych według pola** zapewnia szczegółowe informacje na temat pokrycia każdego wzbogaconego pola.

## <a name="next-steps"></a>Następne kroki

Kompiluj na wierzchu wzbogaconych danych klientów. Użyj identyfikatorów AbiliTec, aby skonsolidować profile klientów w widoku opartym na osobach.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]