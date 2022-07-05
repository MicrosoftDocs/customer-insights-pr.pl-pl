---
title: Eksportowanie segmentów do Sendinblue (wersja zapoznawcza)
description: Dowiedz się, jak skonfigurować połączenie i wyeksportować je do usługi Sendinblue.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f6550b5c57866702631b4c294bb059279461bd6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081685"
---
# <a name="export-segments-to-sendinblue-preview"></a>Eksportowanie segmentów do Sendinblue (wersja zapoznawcza)

Eksportuj segmenty ujednoliconych profili klientów, aby generować kampanie, prowadzić email marketing i korzystać z określonych grup klientów z Sendinblue.

## <a name="prerequisites-for-connection"></a>Wymagania wstępne dla połączenia

-   Użytkownik ma konto [Sendinblue](https://www.sendinblue.com/) i odpowiednie uprawnienia administratora.
-   Istnieją listy w Sendinblue i odpowiadające im identyfikatory.
-   Posiadasz [skonfigurowane segmenty](segments.md).
-   Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- Do 1 mln profilów klientów na eksport do usługi Sendinblue.
- Eksport do Sendinblue jest ograniczony do segmentów.
- Eksportowanie segmentów z łącznie 1 mln profilów klientów może zająć do 90 minut. 
- Liczba profilów klientów, które można eksportować do usługi Sendinblue, zależy od kontraktu z usługą Sendinblue i jest ograniczona.

## <a name="set-up-connection-to-sendinblue"></a>Konfiguruj połączenie z Sendinblue

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Sendinblue**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Domyślnie to tylko administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wprowadź **[klucz interfejsu API Sendinblue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.

1. Zaznacz opcję **Wyrażam zgodę** na **Zapisy zasad ochrony prywatności i zgodności** i wybierz opcję **Połącz**, aby inicjować połączenie z Sendinblue.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.

1. W polu **Połączenie do eksportu** wybierz połączenie z sekcji Sendinblue. Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.

1. Wprowadź **Identyfikator listy usługi** 

1. W sekcji **Dopasowywanie danych** w polu **E-mail** wybierz pole reprezentujące adres e-mail klienta. 

1. Opcjonalnie możesz wyeksportować **Imię**, **Nazwisko** i **Telefon**, aby stworzyć bardziej spersonalizowane wiadomości e-mail. Wybierz opcję **Dodaj atrybut**, aby zamapować te pola.

1. Wybierz segmenty, które chcesz wyeksportować. 

1. Wybierz pozycję **Zapisz**.

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab). Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Włączenie Dynamics 365 Customer Insights w celu przekazywania danych do usługi Sendinblue umożliwia przesyłanie danych poza granice obszaru zgodności dla Dynamics 365 Customer Insights, w tym potencjalnie poufne dane, takie jak dane osobiste. Microsoft będzie przekazywać takie dane zgodnie z Twoimi instrukcjami, ale to Ty jesteś odpowiedzialny za zapewnienie, że Sendinblue spełnia wszelkie zobowiązania dotyczące prywatności i bezpieczeństwa, jakie możesz mieć. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.


[!INCLUDE [footer-include](includes/footer-banner.md)]
