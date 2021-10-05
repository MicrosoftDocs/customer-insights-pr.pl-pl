---
title: Zarządzanie plikami cookie i zgodą użytkownika na przechowywanie danych użytkownika w aplikacji Dynamics 365 Customer Insights
description: Opis sposobu, w jaki pliki cookie i zgody użytkowników są używane w celu identyfikowania osób odwiedzających witrynę.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: c824e50b723fe7f3b421048bb6ab96b7a9efc31f
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558884"
---
# <a name="manage-cookies-and-user-consent"></a>Zarządzanie plikami cookie i zgodą użytkownika

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Funkcja wyników analiz interakcji w aplikacji Dynamics 365 Customer Insights używa plików cookie i kluczy (`localStorage`) do identyfikowania osób odwiedzających witrynę internetową.

Pliki cookie to małe pliki przechowujące elementy informacji dotyczących interakcji użytkownika z witryną sieci Web. Są one zapisywane w przeglądarkach sieci Web. Kiedy użytkownicy odwiedzają stronę internetową, na której zapisano pliki cookie, przeglądarka wysyła te informacje do serwera, który zwraca informacje unikalne dla danego użytkownika. Jest to technologia, która pozwala np. wykorzystać koszyk na zakupy online i zachować w nim wybrane pozycje, nawet jeśli użytkownik opuści stronę.

## <a name="user-consent"></a>Zgoda użytkownika

[Ogólne rozporządzenie o ochronie danych (RODO)](/dynamics365/get-started/gdpr/) to przepisy UE, które określają sposób, w jaki organizacje powinny obsługiwać prywatność i bezpieczeństwo użytkowników. W plikach cookie są często zapisywane lub zbierane dane osobowe, takie jak identyfikator online, które podlegają RODO. Jeśli Twoja firma zatrudnia i/lub sprzedaje dane osobom z UE, GDPR ma to na Ciebie wpływ. [Dowiedz się więcej o tym, w jaki sposób firma Microsoft może w ten sposób ułatwić użytkownikom zgodność z RODO](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Aby zezwolić na przechowywanie plików cookie lub innych poufnych informacji przez SDK funkcji analizy interakcji, należy określić, czy użytkownicy wyrazili na to zgodę. Taka sytuacja ma miejsce podczas inicjowania zestawu SDK przez ustawienie pola `userConsent` w konfiguracji.

W przypadku wskazania, że nie ma zgody użytkownika, zestaw SDK nie będzie przechowywać żadnych danych ani nie wysyłać zdarzeń śledzenia zachowania użytkownika. Wszelkie zapisane wcześniej dane zostaną usunięte z przeglądarki.

Jeśli nie zostanie podana żadna wartość zgody użytkownika, zestaw SDK przyjmie założenie, że użytkownik wyraził zgodę. Oznacza to, że jeśli Użytkownik (jako nasz klient) nie określi wartości zgody użytkownika w zestawie SDK, będą zbierane dane. Jeśli jednak użytkownik określi, że wartość zgody użytkownika musi być ustawiona na „true”, dane nie zostaną zebrane, jeśli użytkownik odrzuci lub nie udostępni jawnej zgody.

Poniżej znajduje się wstawka kodu do inicjowania internetowego zestawu SDK za pomocą zgody użytkownika:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Przechowywanie danych użytkowników w funkcjach funkcji obsługi funkcji analizy interakcji

### <a name="cookies"></a>Wypieki

- _msei
    - Przechowuje anonimowy identyfikator użytkownika. Plik cookie jest ustawiany w domenie klienta i wygaśnie w ciągu 365 dni.

### <a name="local-storage"></a>Magazyn lokalny

Funkcja wyników analiz interakcji używa także kluczy (`localStorage`) do śledzenia danych innych niż poufne. Te dane są w pełni przechowywane w samej przeglądarce i nie są wysyłane żadne dane do ani z serwerów użytkownika.

- *EISession.Id*
    - Przechowuje informacje o bieżącej sesji użytkownika, takie jak identyfikator sesji, data rozpoczęcia i wygaśnięcia.
- *EISession.Previous*
    - Przechowuje adres URL uprzednio odwiedzanej strony w bieżącej sesji.

Klucze w magazynie lokalnym nie wygasają automatycznie i zostaną zresetowane podczas następnej sesji zestawu SDK.

## <a name="deleting-cookies"></a>Usuwanie plików cookie

Klienci mogą ręcznie usunąć pliki cookie i klucze lokalnego magazynu w dowolnym momencie, za pomocą ustawień przeglądarki.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
