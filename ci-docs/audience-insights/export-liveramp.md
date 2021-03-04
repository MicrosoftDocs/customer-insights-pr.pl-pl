---
title: Łącznik LiveRamp
description: Dowiedz się, jak eksportować dane do LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 64d781f52e8124fc3e83a7b84f468830c5249cfd
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270171"
---
# <a name="liverampreg-connector-preview"></a>LiveRamp &reg;łącznik (wersja zapoznawcza)

Aktywuj swoje dane w LiveRamp, aby łączyć się z ponad 500 platformami obejmującymi ekosystemy cyfrowe, społecznościowe i telewizyjne. Pracuj z danymi w LiveRamp, aby kierować, pomijać i personalizować kampanie reklamowe.

## <a name="prerequisites"></a>Wymagania wstępne

- Aby korzystać z tego łącznika, należy dysponować subskrypcją LiveRamp.
- Aby uzyskać subskrypcję, [skontaktuj się z LiveRamp](https://liveramp.com/contact/) bezpośrednio. [Dowiedz się więcej na temat dołączania do LiveRamp](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>Połącz z LiveRamp

1. W analizach odbiorców przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.

1. Na kafelku **LiveRamp** wybierz **Konfiguracja**.

1. W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej rozpoznawalną nazwę.

1. Wprowadź **Nazwę użytkownika** i **Hasło** dla swojego konta LiveRamp Secure FTP (SFTP).
Poświadczenia te mogą być inne niż poświadczenia LiveRamp Onboarding.

1. Wybierz **Weryfikuj**, aby przetestować połączenie z LiveRamp.

1. Po pomyślnym sprawdzeniu zapewnij zgodę na **Prywatność danych i zgodność z przepisami** zaznaczając pole wyboru **Zgadzam się**.

1. Wybierz **Dalej**, aby skonfigurować łącznik LiveRamp.

## <a name="configure-the-connector"></a>Skonfiguruj łącznik

1. W polu **Wybierz identyfikator klucza** wybierz **Email**, **Nazwisko i adres** lub **Telefon**, aby wysłać do LiveRamp w celu rozpoznania tożsamości.

1. Mapowanie odpowiednich atrybutów ze swojej zunifikowanej encji klienta dla wybranego identyfikatora klucza.

1. Wybierz **Dodaj atrybut**, aby zamapować dodatkowe atrybuty do wysyłania do LiveRamp.

   > [!TIP]
   > Wysłanie większej liczby atrybutów z identyfikatorami kluczy do LiveRamp może pomóc uzyskać więcej dopasowań.

1. Zaznacz segmenty, które chcesz eksportować do LiveRamp.

1. Wybierz pozycję **Zapisz**.

> [!div class="mx-imgBorder"]
> ![Łącznik LiveRamp z mapowaniem atrybutu](media/export-liveramp-segments.png "Łącznik LiveRamp z mapowaniem atrybutu")

## <a name="export-the-data"></a>Eksportowanie danych

Eksport zostanie rozpoczęty krótko po zakończeniu wszystkich wymagań wstępnych dotyczących eksportu. Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab).
Po pomyślnym zakończeniu eksportu możesz zalogować się w LiveRamp Onboarding, aby aktywować i rozesłać dane.

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Liveramp można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że Liveramp spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.

[!INCLUDE[footer-include](../includes/footer-banner.md)]