---
title: Eksportowanie danych Customer Insights do usługi Menedżer reklam Facebook
description: Dowiedz się, jak skonfigurować połączenie i eksport do Menedżera reklam na portalu Facebook.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 37d25aa038ea32b98f2d1850d7b42b701292438d
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976055"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Eksportowanie listy segmentów do Menedżera reklam na portalu Facebook (wersja zapoznawcza)

Eksportuj segmenty zunifikowanych profilów klientów do Menedżera Facebook Ads, aby tworzyć kampanie Facebook i Instagram.

## <a name="prerequisites-for-connection"></a>Wymagania wstępne dla połączenia

- Musisz mieć [**konto reklamowe na portalu Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) zawierające [**konto firmowe na portalu Facebook**](https://business.facebook.com/).
- Musisz być Administratorem [**konta reklam Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Znane ograniczenia

- Do 10 milionów profili klientów na eksport do Menedżera reklam na portalu Facebook.
- Eksport do Menedżera reklam na portalu Facebook jest ograniczony do segmentów.
- Tworzenie lub aktualizowanie niestandardowych odbiorców na portalu Facebook tylko typu *lista klientów*.
- Eksportowanie segmentów zawierających łącznie 10 milionów profili może zająć do 90 minut.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Konfiguruj połączenie z Menedżerem reklam na portalu Facebook

Przed utworzeniem eksportu administrator musi skonfigurować połączenie z usługą i umożliwić współautorom korzystanie z połączenia.

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Menedżer reklam na portalu Facebook**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Jeśli nie podejmiesz działania, ustawieniem domyślnym będą **Administratorzy**. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Uwierzytelnianie przy użyciu reklam na portalu Facebook: 

   1. Wybierz **Kontynuuj z Facebook**, aby zalogować się do swojego konta Facebook Ad.

   1. Zezwalaj na uprawnienie **ads_management** po uwierzytelnieniu za pomocą Facebook.

   1. Wybierz **Konto Facebook Ads**, z którym chcesz pracować.

   1. Wybierz **Istniejącego odbiorcę niestandardowego** z listy rozwijanej lub utwórz **Nowego odbiorcę niestandardowego**. Aby uzyskać więcej informacji, zobacz temat [**Odbiorcy w Menedżerze Facebook Ads**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > Za pomocą tego eksportu można tylko tworzyć lub aktualizować odbiorców na portalu Facebook typu *lista klientów*. W niektórych przypadkach na liście rozwijanej można zobaczyć niestandardowych odbiorców różnych typów. Wybranie innego typu danych niż *lista klientów* spowoduje niepowodzenie eksportu. 

1. Przejrzyj zasady **Prywatność danych i zgodność z przepisami** i wybierz opcję **Wyrażam zgodę**.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport. 

1. W opcji **Połączenia dla eksportu** wybierz połączenie z sekcji Menedżer reklam na portalu **Facebook**. Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.

1. W polu **Wybierz identyfikator klucza** wybierz **E-mail**, **Nazwisko i adres** lub **Telefon**, aby przesłać do Menedżera Facebook Ads. 

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.

1. Mapowanie odpowiednich atrybutów ze swojej zunifikowanej encji klienta dla wybranego identyfikatora klucza.
   > [WSKAZÓWKA] Największa szansa dopasowania pojawia się w przypadku wybrania opcji **E-mail** jako identyfikatora klucza. Dodanie dodatkowych identyfikatorów może poprawić dopasowanie.

1. Wybierz **Dodaj atrybut**, aby zamapować więcej atrybutów do Menedżera reklam na portalu Facebook. Atrybuty Menedżera Facebook Ads Ads są mapowane na poniższe przyjazne nazwy użytkowników: **FN** = **Imię**, **LN** = **Nazwisko**, **FI** = **Pierwszy inicjał**, **PHONE** = **Telefon**, **GEN** = **Płeć**, **DOB** = **Data urodzenia**, **ST** = **Stan**, **CT** = **Miasto**, **ZIP** = **Kod pocztowy**, **COUNTRY** = **Kraj / Region**

1. Wybierz segmenty, które chcesz wyeksportować.

1. Wybierz pozycję **Zapisz**.

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab). Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Włączając Dynamics 365 Customer Insights przesyłanie danych do menedżera reklam Facebook, zezwalasz na przesyłanie danych poza granice zgodności dla Dynamics 365 Customer Insights, w tym potencjalnie wrażliwych danych, takich jak Dane Osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że reklamy Facebook spełniają wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
