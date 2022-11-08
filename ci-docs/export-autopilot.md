---
title: Eksportowanie segmentów do programu Autopilot (wersja zapoznawcza)
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi Autopilot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b4b14ba9de2c7e20175fac664a705f2212a411fd
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724770"
---
# <a name="export-segments-to-autopilot-preview"></a>Eksportowanie segmentów do programu Autopilot (wersja zapoznawcza)

Eksportuj segmenty ujednoliconych profili klientów do Autopilota i używaj ich do marketingu e-mailowego w Autopilocie.

## <a name="prerequisites-for-a-connection"></a>Wymagania wstępne dla połączenia

- [Konto usługi Autopilot](https://www.autopilothq.com/) i odpowiadające mu poświadczenia administratora.
- [Klucz interfejsu API usługi Autopilot](https://autopilot.docs.apiary.io/#)
- [Skonfigurowane segmenty](segments.md) w Customer Insights.
- Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- Link prywatny w połączeniu z opcją BYOS (Bring your owne storage) nie jest obsługiwany.
- Do 100 000 profili klientów na eksport do Autopilota, co może potrwać nawet kilka godzin. Liczba profilów klientów, które można eksportować do usługi Autopilot, zależy od kontraktu z usługą Autopilot i jest ograniczona.
- Tylko segmenty.

## <a name="set-up-connection-to-autopilot"></a>Skonfiguruj połączenie z usługą Autopilot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Autopilot**.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Domyślnie – tylko administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wprowadź klucz interfejsu API Autopilot.

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Wybierz opcję **Połącz**, aby zainicjować połączenie.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz opcję **Dodaj eksport**.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Autopilot. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wpisz nazwę eksportu.

1. W sekcji **Dopasowywanie danych** w polu **E-mail** wybierz pole reprezentujące adres e-mail klienta.

1. Opcjonalnie można wyeksportować inne pola, **Imię** lub **Nazwisko**.

1. Wybierz segmenty, które chcesz wyeksportować zgodnie ze znanymi ograniczeniami.

1. Wybierz pozycję **Zapisz**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
