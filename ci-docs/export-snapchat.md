---
title: Eksportowanie segmentów do usługi Snapchat (wersja zapoznawcza)
description: Dowiedz się, jak skonfigurować połączenie i eksport do programu Snapchat.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 85443dcb54ebd58182997fbb56a738901f2a051f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195395"
---
# <a name="export-segments-to-snapchat-preview"></a>Eksportowanie segmentów do usługi Snapchat (wersja zapoznawcza)

Wyeksportuj segmenty ujednoliconych profilów klientów do usługi Snapchat i użyj ich w celach reklamowych.

## <a name="prerequisites"></a>Wymagania wstępne

- Konto [konto biznesowe Snapchat](https://business.snapchat.com/), [konto reklamowe Snapchat](https://ads.snapchat.com/) i odpowiednie dane logowania administratora. Musisz być co najmniej członkiem Konta organizacji i Menedżerem danych określonego konta reklamowego.
- Masz przynajmniej odbiocrów w Manedżerze odbiorców Snapchat typu SAM (Snap Audience Match).
- Wprowadź [Segment/identyfikator odbiorców Snapchat](https://businesshelp.snapchat.com/s/article/custom-audiences). Identyfikator odbiorcy znajduje się w adresie URL po wybraniu opcji odbiorcy w Menedżerze odbiorcy Snapchat.
- [Skonfigurowane segmenty](segments.md) w Customer Insights.
- Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- Do 1 miliona profili klientów, co może zająć do 15 minut.
- Tylko segmenty.

## <a name="set-up-connection-to-snapchat"></a>Skonfiguruj połączenie z usługą Snapchat

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Snapchat**.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Domyślnie – tylko administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Wybierz opcję **Połącz**, aby zainicjować połączenie.

1. Wybierz opcję **Uwierzytelnij za pomocą usługi Snapchat** i podaj swoje poświadczenia administratora dla usługi Snapchat.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz opcję **Dodaj eksport**.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Snapchat. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wpisz nazwę eksportu.

1. Wprowadź **Segment/identyfikator odbiorców Snapchat**.

1. W sekcji **Dopasowywanie danych** w polu **E-mail** wybierz pole reprezentujące adres e-mail klienta.

1. Wybierz segmenty, które chcesz wyeksportować.

1. Wybierz pozycję **Zapisz**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
