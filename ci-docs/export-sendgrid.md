---
title: Eksportowanie segmentów do programu SendGrid (wersja zapoznawcza)
description: Dowiedz się, jak skonfigurować połączenie i eksport do programu SendGrid.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f2990ad410dda0cbf952f82f3fc30b3a53a7bcd4
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197005"
---
# <a name="export-segments-to-sendgrid-preview"></a>Eksportowanie segmentów do programu SendGrid (wersja zapoznawcza)

Eksportuj segmenty ujednoliconych profili klientów do list kontaktów SendGrid i używaj ich do kampanii i marketingu e-mailowego w SendGrid.

## <a name="prerequisites"></a>Wymagania wstępne

- [Konto usługi SendGrid](https://sendgrid.com/) i odpowiadające mu poświadczenia administratora.
- [Istniejące listy kontaktów w SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) i odpowiadające im identyfikatory.
- [Klucz interfejsu API usługi SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).
- [Skonfigurowane segmenty](segments.md) w Customer Insights.
- Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- Łącznie do 100 000 profili klientów w SendGrid, co może zająć nawet kilka godzin. Liczba profilów klientów, które można eksportować do usługi SendGrid, zależy od kontraktu z usługą SendGrid.
- Tylko segmenty.

## <a name="set-up-connection-to-sendgrid"></a>Skonfiguruj połączenie z usługą SendGrid

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **SendGrid**.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Domyślnie – tylko administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wprowadź **klucz interfejsu API SendGrid**.

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Wybierz opcję **Połącz**, aby zainicjować połączenie.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz opcję **Dodaj eksport**.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi SendGrid. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wpisz nazwę eksportu.

1. Wprowadź **Identyfikator listy SendGrid**.

1. W sekcji **Dopasowywanie danych** w polu **E-mail** wybierz pole reprezentujące adres e-mail klienta.

1. Opcjonalnie wybierz pola, takie jak **Imię**, **Nazwisko**, **Kraj/Region**, **Stan**, **Miasto** i **Kod pocztowy**.

1. Wybierz segmenty, które chcesz wyeksportować zgodnie ze znanymi ograniczeniami.

1. Wybierz pozycję **Zapisz**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
