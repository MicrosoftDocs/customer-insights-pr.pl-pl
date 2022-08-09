---
title: Eksportowanie segmentów do Sendinblue (wersja zapoznawcza)
description: Dowiedz się, jak skonfigurować połączenie i wyeksportować je do usługi Sendinblue.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 816a3b242fadaa5a75db878adf0a76baf638e41c
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196959"
---
# <a name="export-segments-to-sendinblue-preview"></a>Eksportowanie segmentów do Sendinblue (wersja zapoznawcza)

Eksportuj segmenty ujednoliconych profili klientów, aby generować kampanie, prowadzić email marketing i korzystać z określonych grup klientów z Sendinblue.

## <a name="prerequisites"></a>Wymagania wstępne

- Konto [Sendinblue](https://www.sendinblue.com/) i odpowiednie uprawnienia administratora.
- [Klucz interfejsu API usługi SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key).
- Istniejące listy w Sendinblue i odpowiadające im identyfikatory.
- [Skonfigurowane segmenty](segments.md).
- Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- Do 1 miliona profili klientów na eksport do Sendinblue, co może zająć do 90 minut. Liczba profilów klientów, które można eksportować do usługi Sendinblue, zależy od kontraktu z usługą Sendinblue.
- Tylko segmenty.

## <a name="set-up-connection-to-sendinblue"></a>Konfiguruj połączenie z Sendinblue

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Sendinblue**.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Domyślnie to tylko administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wprowadź **klucz interfejsu API SendinBlue**.

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Wybierz opcję **Połącz**, aby zainicjować połączenie.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz opcję **Dodaj eksport**.

1. W polu **Połączenie do eksportu** wybierz połączenie z sekcji Sendinblue. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wpisz nazwę eksportu.

1. Wprowadź **Identyfikator listy usługi**.

1. W sekcji **Dopasowywanie danych** w polu **E-mail** wybierz pole reprezentujące adres e-mail klienta.

1. Opcjonalnie możesz wyeksportować **Imię**, **Nazwisko** i **Telefon**, aby stworzyć bardziej spersonalizowane wiadomości e-mail. Wybierz opcję **Dodaj atrybut**, aby zamapować te pola.

1. Wybierz segmenty, które chcesz wyeksportować.

1. Wybierz pozycję **Zapisz**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
