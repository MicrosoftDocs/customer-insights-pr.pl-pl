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
ms.openlocfilehash: 4403c6f535f5dc60919be3717073d52640bbe61a
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/08/2021
ms.locfileid: "7619224"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Eksportowanie listy segmentów do Menedżera reklam na portalu Facebook (wersja zapoznawcza)

Eksportuj segmenty zunifikowanych profilów klientów do Menedżera Facebook Ads, aby tworzyć kampanie Facebook i Instagram.

## <a name="prerequisites-for-connection"></a>Wymagania wstępne dla połączenia

- Musisz mieć [**konto reklamowe Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) zawierające [**konto firmowe Facebook**](https://business.facebook.com/).
- Musisz mieć uprawnienia administratora [**konta reklamowego Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Znane ograniczenia

- Do 10 milionów profili klientów na eksport do Menedżera reklam Facebook.
- Eksport do Menedżera reklam na portalu Facebook jest ograniczony do segmentów.
- Tworzenie lub aktualizowanie niestandardowych odbiorców na portalu Facebook tylko typu *lista klientów*.
- Eksportowanie segmentów z łącznie 10 mln profilów klientów może zająć do 90 minut.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Konfiguruj połączenie z Menedżerem reklam na portalu Facebook

Przed utworzeniem eksportu administrator musi skonfigurować połączenie z usługą i umożliwić współautorom korzystanie z połączenia.

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Menedżer reklam na portalu Facebook**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Uwierzytelnianie przy użyciu reklam na portalu Facebook: 

   1. Wybierz opcję **Kontynuuj za pomocą Facebook**, aby zalogować się na konto reklamowe Facebook.

   1. Zezwalaj na uprawnienie **ads_management** po uwierzytelnieniu za pomocą Facebook.

   1. Wybierz **Konto Facebook Ads**, z którym chcesz pracować.

   1. Wybierz **Istniejącą grupę odbiorców** z listy rozwijanej lub utwórz **Nową grupę odbiorców**. Aby uzyskać więcej informacji, zobacz temat [**Odbiorcy w Menedżerze Facebook Ads**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > Za pomocą tego eksportu można tylko tworzyć lub aktualizować odbiorców na portalu Facebook typu *lista klientów*. W niektórych przypadkach na liście rozwijanej widoczne są niestandardowe grupy odbiorców różnych typów. Wybranie innego typu danych niż *lista klientów* spowoduje niepowodzenie eksportu. 

1. Przejrzyj zasady **Prywatność danych i zgodność z przepisami** i wybierz opcję **Wyrażam zgodę**.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport. 

1. W opcji **Połączenia dla eksportu** wybierz połączenie z sekcji Menedżer reklam na portalu **Facebook**. Jeśli nie widzisz tej nazwy sekcji, to znaczy, że nie masz dostępu do żadnych połączeń tego typu.

1. W polu **Wybierz identyfikator klucza** wybierz **E-mail**, **Nazwisko i adres** lub **Telefon**, aby przesłać do Menedżera Facebook Ads. 

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.

1. Mapowanie odpowiednich atrybutów ze swojej zunifikowanej encji klienta dla wybranego identyfikatora klucza.
   > [!TIP]
   > Największa szansa dopasowania pojawia się w przypadku wybrania opcji **E-mail** jako identyfikatora głównego. Dodanie dodatkowych identyfikatorów może poprawić dopasowanie.

1. Wybierz **Dodaj atrybut**, aby zamapować więcej atrybutów do Menedżera reklam na portalu Facebook. Atrybuty Menedżera Facebook Ads Ads są mapowane na poniższe przyjazne nazwy użytkowników: **FN** = **Imię**, **LN** = **Nazwisko**, **FI** = **Pierwszy inicjał**, **PHONE** = **Telefon**, **GEN** = **Płeć**, **DOB** = **Data urodzenia**, **ST** = **Stan**, **CT** = **Miasto**, **ZIP** = **Kod pocztowy**, **COUNTRY** = **Kraj / Region**

1. Wybierz segmenty, które chcesz wyeksportować.

1. Wybierz pozycję **Zapisz**.

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab). 

Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Włączając Dynamics 365 Customer Insights przesyłanie danych do menedżera reklam Facebook, zezwalasz na przesyłanie danych poza granice zgodności dla Dynamics 365 Customer Insights, w tym potencjalnie wrażliwych danych, takich jak Dane Osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że reklamy Facebook spełniają wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
