---
title: Eksportuj segmenty do Criteo (podgląd)
description: Dowiedz się, jak skonfigurować połączenie i eksport do Criteo.
ms.date: 05/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ace9056d200a3179e442132004324a01f0d247b6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081545"
---
# <a name="export-segments-to-criteo-preview"></a>Eksportuj segmenty do Criteo (podgląd)

Eksportuj segmenty ujednoliconych profili klientów w celu generowania kampanii, dostarczania e-mail marketingu i korzystania z określonych grup klientów za pomocą Criteo.

## <a name="prerequisites-for-connection"></a>Wymagania wstępne dla połączenia

-   Masz [konto Criteo Dynamics Retargeting](https://www.criteo.com/login/) i odpowiednie poświadczenia administratora.
-   Posiadasz [skonfigurowane segmenty](segments.md).
-   Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- Do 1 miliona profili klientów na eksport do Criteo.
- Eksport do Criteo jest ograniczony do segmentów.
- Eksportowanie segmentów z łącznie 1 mln profilów klientów może zająć do 30 minut. 
- Liczba profili klientów, które możesz wyeksportować do Criteo, jest zależna i ograniczona od Twojej umowy z Criteo.

## <a name="set-up-connection-to-criteo"></a>Skonfiguruj połączenie z usługą Criteo

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz **Dodaj połączenie** i wybierz **Criteo**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wybierz **Zgadzam się**, aby potwierdzić **Prywatność i zgodność danych** i wybierz **Połącz**, aby zainicjować połączenie z Criteo.

1. Wybierz **Uwierzytelnij za pomocą Criteo** i podaj swoją nazwę użytkownika administratora oraz dane uwierzytelniające dla Criteo. 

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.

1. W polu **Połączenie do eksportu** wybierz połączenie z sekcji Criteo. Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika. 

1. W sekcji **Dopasowywanie danych** w polu **E-mail** wybierz pole reprezentujące adres e-mail klienta. 

1. Opcjonalnie możesz wyeksportować **identyfikator reklamodawcy** i **Nazwa**

1. Wybierz segmenty, które chcesz wyeksportować. 

1. Wybierz pozycję **Zapisz**.

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab). Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu Dynamics 365 Customer Insights do przesyłania danych do Criteo, zezwalasz na transfer danych poza granicami zgodności dla Dynamics 365 Customer Insights, w tym potencjalnie poufnych danych, takich jak Dane osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale Ty jesteś odpowiedzialny za zapewnienie, że Criteo spełnia wszelkie Twoje zobowiązania dotyczące prywatności lub bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.


[!INCLUDE[footer-include](includes/footer-banner.md)]
