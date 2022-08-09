---
title: Eksportowanie segmentów do usługi LinkedIn Ads (wersja zapoznawcza)
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi LinkedIn Ads.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d1a9ae985043398f4bc38163be26ecf0c3c8e2ba
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196821"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Eksportowanie segmentów do usługi LinkedIn Ads (wersja zapoznawcza)

Eksportuj segmenty ujednoliconych profili klientów do LinkedIn Ads, aby tworzyć dopasowane grupy Matched Audiences. Wykorzystaj dopasowane grupy Matched Audiences do targetowania firm i kontaktów.

## <a name="prerequisites"></a>Wymagania wstępne

- [Konto LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) i odpowiednie poświadczenia administratora.
- [Identyfikator konta LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).
- [Skonfigurowane segmenty](segments.md) w Customer Insights.
- Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- Do 100 000 profili klientów na eksport do LinkedIn Ads, co może zająć do 10 minut.
- Tylko segmenty. Segment musi zawierać co najmniej 300 unikalnych profili.

## <a name="set-up-connection-to-linkedin-ads"></a>Skonfiguruj połączenie z usługą LinkedIn Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **LinkedIn Ads**.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Domyślnie – tylko administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Należy podać Identyfikator konta LinkedIn Campaign Manager.

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Wybierz opcję **Połącz**, aby zainicjować połączenie.

1. Wybierz opcję **Uwierzytelnij za pomocą usługi LinkedIn** i podaj swoje poświadczenia administratora dla usługi LinkedIn Campaign Manager.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz opcję **Dodaj eksport**.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi LinkedIn Ads. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wpisz nazwę eksportu.

1. Możesz określić, czy chcesz eksportować dane, aby [ukierunkowywać kontakty](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting), czy [ukierunkowywać przedsiębiorstwa](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) w usłudze LinkedIn.

1. W sekcji **Dopasowywanie danych**, aby ukierunkowywać kontakty, wybierz co najmniej jedno pole reprezentujące adres e-mail klienta, identyfikator Apple Ad ID, identyfikator Google Ad ID, identyfikator użytkownika Google lub imię i nazwisko. Jeśli wybierzesz kierowanie do firm, wybierz co najmniej jedno pole reprezentujące nazwę firmy, domenę poczty e-mail, adres URL strony LinkedIn, symbol giełdowy lub witrynę internetową.

1. Opcjonalnie dodaj pola, aby dokładniej zdefiniować eksport. Wybierz opcję **Dodaj atrybut**, aby zamapować te pola.

1. Wybierz segmenty, które chcesz wyeksportować. Matched Audiences w LinkedIn Campaign Manager zostaną automatycznie utworzone z nazwą segmentów, które wybrałeś do eksportu. W przypadku każdego z segmentów będzie to oddzielne dopasowanie odbiorcy.

1. Wybierz pozycję **Zapisz**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
