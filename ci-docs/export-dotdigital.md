---
title: Eksportowanie segmentów do usługi DotDigital (wersja zapoznawcza)
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi DotDigital.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cabaea84e31f8fe97bc558a8dca8d93bc40f43b7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196085"
---
# <a name="export-segments-to-dotdigital-preview"></a>Eksportowanie segmentów do usługi DotDigital (wersja zapoznawcza)

Eksportuj segmenty ujednoliconych profili klientów do książek adresowych DotDigital i wykorzystuj je do prowadzenia kampanii, marketingu e-mailowego i budowania segmentów klientów za pomocą DotDigital.

## <a name="prerequisites"></a>Wymagania wstępne

- Masz [konto DotDigital](https://dotdigital.com/) i [użytkownika interfejsu API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- Identyfikator DotDigital z [nowej](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) lub istniejącej książki adresowej w pliku DotDigital. Identyfikator można znaleźć w adresie URL podczas wybierania i otwierania książki adresowej.
- [Skonfigurowane segmenty](segments.md) w Customer Insights.
- Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- Do 1 miliona profili klientów na eksport do DotDigital, co może zająć do trzech godzin ze względu na ograniczenia po stronie dostawcy. Liczba profilów klientów, które można eksportować do usługi DotDigital, zależy od kontraktu z usługą DotDigital i jest ograniczona.
- Tylko segmenty.

## <a name="set-up-connection-to-dotdigital"></a>Konfiguruj połączenie z usługą DotDigital

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **DotDigital**.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Domyślnie – tylko administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wprowadź **nazwę użytkownika i hasło usługi DotDigital**.

1. Wprowadź **Identyfikator książki adresowej DotDigital**.

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Wybierz opcję **Połącz**, aby zainicjować połączenie.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz opcję **Dodaj eksport**.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi DotDigital. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wpisz nazwę eksportu.

1. W sekcji **Dopasowywanie danych** w polu **E-mail** wybierz pole reprezentujące adres e-mail klienta.

1. Opcjonalnie można wyeksportować **Imię**, **Nazwisko**, **Imię i nazwisko**, **Dane** i **Kod pocztowy**.

1. Wybierz segmenty, które chcesz wyeksportować.

1. Wybierz pozycję **Zapisz**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

W DotDigital można znaleźć segmenty w [książkach adresowych DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

[!INCLUDE [footer-include](includes/footer-banner.md)]
