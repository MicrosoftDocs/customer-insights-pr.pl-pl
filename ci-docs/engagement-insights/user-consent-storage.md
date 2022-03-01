---
title: Zarządzanie plikami cookie i zgodą użytkownika na przechowywanie danych
description: Opis sposobu, w jaki pliki cookie i zgody użytkowników są używane w celu identyfikowania osób odwiedzających witrynę.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7b3195a92c969ab36e5b43f4c2e4221ff477a0a8958838e1256528f58fe13dce
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036751"
---
# <a name="manage-cookies-and-user-consent"></a>Zarządzanie plikami cookie i zgodą użytkownika

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Funkcja obsługi analizy interakcji w Dynamics 365 Customer Insights używa plików cookie i lokalnego magazynu (`localStorage`) w celu identyfikowania osób odwiedzających witrynę.

Pliki cookie to małe pliki przechowujące elementy informacji dotyczących interakcji użytkownika z witryną sieci Web. Są one zapisywane w przeglądarkach sieci Web. Kiedy użytkownicy odwiedzają stronę internetową, na której zapisano pliki cookie, przeglądarka wysyła te informacje do serwera, który zwraca informacje unikalne dla danego użytkownika. Jest to technologia, która pozwala np. wykorzystać koszyk na zakupy online i zachować w nim wybrane pozycje, nawet jeśli użytkownik opuści stronę.

## <a name="user-consent"></a>Zgoda użytkownika

[Ogólne rozporządzenie o ochronie danych (RODO)](/dynamics365/get-started/gdpr/) to przepisy UE, które określają sposób, w jaki organizacje powinny obsługiwać prywatność i bezpieczeństwo użytkowników. W plikach cookie są często zapisywane lub zbierane dane osobowe, takie jak identyfikator online, które podlegają RODO. Jeśli Twoja firma zatrudnia i/lub sprzedaje dane osobom z UE, GDPR ma to na Ciebie wpływ. [Dowiedz się więcej o tym, w jaki sposób firma Microsoft może w ten sposób ułatwić użytkownikom zgodność z RODO](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Aby zezwolić na przechowywanie plików cookie lub innych poufnych informacji przez SDK funkcji analizy interakcji, należy określić, czy użytkownicy wyrazili na to zgodę. Taka sytuacja ma miejsce podczas inicjowania pracy zestawu SDK.

W przypadku wskazania, że nie ma zgody użytkownika, zestaw SDK nie będzie przechowywać żadnych danych ani nie wysyłać zdarzeń śledzenia zachowania użytkownika. Wszelkie zapisane wcześniej dane zostaną usunięte z przeglądarki.

Jeśli nie zostanie podana żadna wartość zgody użytkownika, zestaw SDK przyjmie założenie, że użytkownik wyraził zgodę. Oznacza to, że jeśli Użytkownik (jako nasz klient) nie określi wartości zgody użytkownika w zestawie SDK, będą zbierane dane. Jeśli jednak użytkownik określi, że wartość zgody użytkownika musi być ustawiona na „true”, dane nie zostaną zebrane, jeśli użytkownik odrzuci lub nie udostępni jawnej zgody.

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Przechowywanie danych użytkowników w funkcjach funkcji obsługi funkcji analizy interakcji

### <a name="cookies"></a>Wypieki

- _msei
    - Przechowuje anonimowy identyfikator użytkownika. Plik cookie jest ustawiany w domenie klienta i wygaśnie w ciągu 365 dni.

### <a name="local-storage"></a>Magazyn lokalny

Funkcja wglądu w dane typu zaangażowanie umożliwia także korzystanie z lokalnego magazynu (`localStorage`) w celu śledzenia danych o niskiej wadze. Te dane są w pełni przechowywane w samej przeglądarce i nie są wysyłane żadne dane do ani z serwerów użytkownika.

- *EISession.Id* 
    - Przechowuje informacje o bieżącej sesji użytkownika, takie jak identyfikator sesji, data rozpoczęcia i wygaśnięcia.
- *EISession.Previous*
    - Przechowuje adres URL uprzednio odwiedzanej strony w bieżącej sesji.
    
Klucze w magazynie lokalnym nie wygasają automatycznie. Będą resetowane podczas następnej sesji przez zestaw SDK.

## <a name="deleting-cookies"></a>Usuwanie plików cookie

Klienci mogą ręcznie usunąć pliki cookie i klucze lokalnego magazynu w dowolnym momencie, za pomocą ustawień przeglądarki.


[!INCLUDE[footer-include](../includes/footer-banner.md)]