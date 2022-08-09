---
title: Eksportowanie segmentów do usługi Constant Contact (wersja zapoznawcza)
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi Constant Contact.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4d2ec29c194dc481ee40048b8ecbed813291b4d2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196499"
---
# <a name="export-segments-to-constant-contact-preview"></a>Eksportowanie segmentów do usługi Constant Contact (wersja zapoznawcza)

Wyeksportuj segmenty ujednoliconych profilów klientów do usługi Constant Contact i użyj ich w działaniach marketingowych.

## <a name="prerequisites"></a>Wymagania wstępne

- Konto [Kontakt administracyjny usługi Constant Contact](https://www.constantcontact.com/account-home) i odpowiednie dane logowania administratora.
- [Identyfikator listy usługi Constant Contact](https://app.constantcontact.com/pages/contacts/ui#lists). Otwórz listę w usłudze Constant Contact, aby znaleźć identyfikator listy w adresie URL.
- [Skonfigurowane segmenty](segments.md) w Customer Insights.
- Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- Do 1 miliona profili klientów na eksport do Constant Contact, co może zająć nawet godzinę. Liczba profilów klientów, które można eksportować do usługi Constant Contact, zależy od kontraktu z usługą Constant Contactl.
- Tylko segmenty.

## <a name="set-up-connection-to-constant-contact"></a>Konfiguracja połączenia z usługą Constant Contact

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Constant Contact**.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Domyślnie – tylko administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Wybierz opcję **Połącz**, aby zainicjować połączenie.

1. Wybierz pozycję **Uwierzytelnij przy stałym kontakcie** i podaj poświadczenia administratora dla stałego kontaktu.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz opcję **Dodaj eksport**.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Constant Contact. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wpisz nazwę eksportu.

1. Wprowadź swój **Identyfikator listy usługi Constant Contact**.

1. W sekcji **Dopasowywanie danych** w polu **E-mail** wybierz pole reprezentujące adres e-mail klienta.

1. Można też eksportować **imię** i **Nazwisko** jako dodatkowe pola, aby utworzyć bardziej spersonalizowane wiadomości e-mail. Wybierz opcję **Dodaj atrybut**, aby zamapować te pola.

1. Wybierz segmenty, które chcesz wyeksportować.

1. Wybierz pozycję **Zapisz**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
