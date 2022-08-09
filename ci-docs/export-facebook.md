---
title: Eksportowanie segmentów do Menedżera reklam serwisu Facebook (wersja zapoznawcza) (zawiera film wideo)
description: Dowiedz się, jak skonfigurować połączenie i eksport do Menedżera reklam na portalu Facebook.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01be1a075db0da05dc5536aea8a33093f9a2ea13
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195027"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Eksportowanie segmentów do Menedżera reklam serwisu Facebook (wersja zapoznawcza)

Eksportuj segmenty zunifikowanych profilów klientów do Menedżera Facebook Ads, aby tworzyć kampanie Facebook i Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>Wymagania wstępne

- Musisz mieć [konto reklamowe Facebook Ads](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) zawierające [konto firmowe Facebook Business](https://business.facebook.com/).
- Administrator do uprawnienia [Konto Facebook Ads](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Znane ograniczenia

- Do 10 miliona profili klientów na eksport do Facebook Ads Manager, co może zająć do 90 minut.
- Tylko segmenty.
- Typ *listy klientów* Facebook tylko dla [odbiorców niestandardowych](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
  > [!NOTE]
  > W niektórych przypadkach na liście rozwijanej mogą być widoczne niestandardowe grupy odbiorców różnych typów. W przypadku wybrania innego typu niż *lista klientów*, eksport nie powiedzie się.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Konfiguruj połączenie z Menedżerem reklam na portalu Facebook

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Facebook Ads Manager**.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. [Zezwalaj współautorom na używanie połączenia do eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Uwierzytelnianie przy użyciu reklam na portalu Facebook:

   1. Wybierz opcję **Kontynuuj za pomocą Facebook**, aby zalogować się na konto reklamowe Facebook.

   1. Zezwalaj na uprawnienie **ads_management** po uwierzytelnieniu za pomocą Facebook.

   1. Wybierz **Konto Facebook Ads**, z którym chcesz pracować.

   1. Wybierz **Istniejącą grupę odbiorców** z listy rozwijanej lub utwórz **Nową grupę odbiorców**.

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz opcję **Dodaj eksport**.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Facebook Ads Manager. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wpisz nazwę eksportu.

1. W polu **Połącz dane** wybierz **E-mail**, **Nazwisko i adres** lub **Telefon**, aby przesłać do Menedżera Facebook Ads.

1. Mapowanie odpowiednich atrybutów ze swojej zunifikowanej encji klienta dla wybranego identyfikatora klucza.
   > [!TIP]
   > Największa szansa dopasowania pojawia się w przypadku wybrania opcji **E-mail** jako identyfikatora głównego. Dodanie dodatkowych identyfikatorów może poprawić dopasowanie.

1. Wybierz **Dodaj atrybut**, aby zamapować więcej atrybutów do Menedżera reklam na portalu Facebook. Atrybuty Menedżera Facebook Ads Ads są mapowane na poniższe przyjazne nazwy użytkowników: **FN** = **Imię**, **LN** = **Nazwisko**, **FI** = **Pierwszy inicjał**, **PHONE** = **Telefon**, **GEN** = **Płeć**, **DOB** = **Data urodzenia**, **ST** = **Stan**, **CT** = **Miasto**, **ZIP** = **Kod pocztowy**, **COUNTRY** = **Kraj / Region**

1. Wybierz segmenty, które chcesz wyeksportować.

1. Wybierz pozycję **Zapisz**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
