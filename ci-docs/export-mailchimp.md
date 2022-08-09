---
title: Eksportowanie segmentów do usługi Mailchimp (wersja zapoznawcza)
description: Dowiedz się, jak skonfigurować połączenie i eksport do programu Mailchimp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 54aec10e24b6356e2e4317cf33e740a1a086a2dd
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196867"
---
# <a name="export-segments-to-mailchimp-preview"></a>Eksportowanie segmentów do usługi Mailchimp (wersja zapoznawcza)

Wyeksportowane segmenty zunifikowanych profilów klientów umożliwiają MailChimp tworzenie biuletynów i kampanii za pośrednictwem poczty e-mail.

## <a name="prerequisites"></a>Wymagania wstępne

- [Konto usługi Mailchimp](https://mailchimp.com/) i odpowiadające mu poświadczenia administratora.
- [Istniejący odbiorcy w Mailchimp](https://mailchimp.com/help/create-audience/) i odpowiadające im [identyfikatory odbiorców](https://mailchimp.com/help/find-audience-id/).
- [Skonfigurowane segmenty](segments.md).
- Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- Do 1 miliona profili klientów na eksport do Mailchimp, co może zająć do 3 godzin. Liczba profilów klientów, które można eksportować do usługi Mailchimp, zależy od kontraktu z usługą Mailchimp.
- Tylko segmenty.

## <a name="set-up-connection-to-mailchimp"></a>Skonfiguruj połączenie z usługą Mailchimp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Mailchimp**.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Domyślnie – tylko administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Wybierz opcję **Połącz**, aby zainicjować połączenie.

1. Wybierz **Uwierzytelnianie za pomocą usługi Mailchimp** i przekaż swoje poświadczenia w usłudze Mailchimp.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz opcję **Dodaj eksport**.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Mailchimp. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wpisz nazwę eksportu.

1. Wpisz swój **Identyfikator odbiorcy usługi Mailchimp**.

1. W sekcji **Dopasowywanie danych** w polu **E-mail** wybierz pole reprezentujące adres e-mail klienta.

1. Opcjonalnie możesz wyeksportować **Imię** i **Nazwisko**, aby utworzyć bardziej spersonalizowane wiadomości e-mail. Wybierz opcję **Dodaj atrybut**, aby zamapować te pola.

1. Wybierz segmenty, które chcesz wyeksportować.

1. Wybierz pozycję **Zapisz**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
