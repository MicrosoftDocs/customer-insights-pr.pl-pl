---
title: Eksportowanie segmentów do programu Microsoft Advertising (wersja zapoznawcza)
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi Microsoft Advertising.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196545"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Eksportowanie segmentów do programu Microsoft Advertising (wersja zapoznawcza)

Eksport segmentów Customer Insights do Microsoft Advertising w celu stworzenia grup odbiorców Customer Match. Grupy odbiorców mogą być wykorzystania w kampaniach reklamowych.

## <a name="prerequisites"></a>Wymagania wstępne

- [Konto Microsoft Advertising](https://ads.microsoft.com/) i odpowiednie dane logowania administratora.
- Identyfikator klienta i konta Microsoft Advertising. Możesz znaleźć ID klienta (`cid`) i ID konta (`aid`) w parametrach adresu URL po zalogowaniu w Microsoft Advertising.
- Warunki korzystania z Customer Match są akceptowane.
- [Skonfigurowane segmenty](segments.md) w Customer Insights.
- Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- Do 500 000 profili klientów na eksport do Microsoft Advertising, co może zająć do 10 minut.
- Tylko segmenty.

## <a name="set-up-connection-to-microsoft-advertising"></a>Skonfiguruj połączenie z usługą Microsoft Advertising

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Microsoft Advertising**.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Wartość domyślna to administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wprowadź **Identyfikator klienta w usłudze Microsoft Advertising**.

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Wybierz opcję **Połącz**, aby zainicjować połączenie.

1. Wybierz opcję **Uwierzytelnij z usługą Microsoft Advertising** i podaj swoje poświadczenia administratora dla usługi Microsoft Advertising.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz opcję **Dodaj eksport**.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Microsoft Advertising. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wpisz nazwę eksportu.

1. Wybierz segmenty do eksportu. Odbiorcy Customer Match w Microsoft Advertising są automatycznie tworzeni z nazwą segmentów wybranych do eksportu. W przypadku każdego z segmentów będzie to Customer Match odbiorcy.

1. Wprowadź swój **Identyfikator klienta i konta Microsoft Advertising**.

1. W sekcji **Dopasowywanie danych** w polu **E-mail** wybierz pole z adresem e-mail klienta.

1. Wybierz pozycję **Zapisz**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
