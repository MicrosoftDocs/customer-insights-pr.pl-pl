---
title: Łącznik LiveRamp
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi LiveRamp.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4c0f58083e8486d2042d8efcc8b3690020efb1c3
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226365"
---
# <a name="export-segments-to-liverampreg-preview"></a>Eksportowanie segmentów do usługi LiveRamp&reg; (wersja zapoznawcza)

Aktywuj dane w u usłudze LiveRamp, aby połączyć się z ponad 500 platformami za pośrednictwem mediów cyfrowych, społecznościowych i telewizji. Pracuj z danymi w LiveRamp, aby kierować, pomijać i personalizować kampanie reklamowe.

## <a name="prerequisites-for-a-connection"></a>Wymagania wstępne dla połączenia

- Aby korzystać z tego łącznika, należy dysponować subskrypcją LiveRamp.
- Aby uzyskać subskrypcję, [skontaktuj się z LiveRamp](https://liveramp.com/contact/) bezpośrednio. [Dowiedz się więcej na temat dołączania do LiveRamp](https://liveramp.com/our-platform/data-onboarding/).

## <a name="set-up-connection-to-liveramp"></a>Skonfiguruj połączenie z usługą LiveRamp

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **LiveRamp**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wprowadź **Nazwę użytkownika** i **Hasło** dla swojego konta LiveRamp Secure FTP (SFTP).
Poświadczenia te mogą być inne niż poświadczenia LiveRamp Onboarding.

1. Wybierz **Weryfikuj**, aby przetestować połączenie z LiveRamp.

1. Po pomyślnym sprawdzeniu zapewnij zgodę na **Prywatność danych i zgodność z przepisami** zaznaczając pole wyboru **Zgadzam się**.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi LiveRamp. Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.

1. W polu **Wybierz identyfikator klucza** wybierz **Email**, **Nazwisko i adres** lub **Telefon**, aby wysłać do LiveRamp w celu rozpoznania tożsamości.
   > [!div class="mx-imgBorder"]
   > ![Łącznik LiveRamp z mapowaniem atrybutu.](media/export-liveramp-segments.png "Łącznik LiveRamp z mapowaniem atrybutu")

1. Mapuj odpowiednie atrybuty obiektu z encji *Klient* na wybrany identyfikator klucza.

1. Wybierz **Dodaj atrybut**, aby zamapować więcej atrybutów do usługi LiveRamp.

   > [!TIP]
   > Wysłanie większej liczby atrybutów z identyfikatorami kluczy do LiveRamp może pomóc uzyskać więcej dopasowań.

1. Zaznacz segmenty, które chcesz eksportować do LiveRamp.

1. Wybierz pozycję **Zapisz**.

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab). Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Liveramp można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że Liveramp spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
