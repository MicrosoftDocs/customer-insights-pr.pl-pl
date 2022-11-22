---
title: Zarządzaj nieznanymi profilami dzięki funkcji Customer Insights
description: Pracuj z profilami nieznanych klientów, które są tworzone i zarządzane w Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: 0e12f64a22b93d117009fb8aee76d02a7583e699
ms.sourcegitcommit: 24627d53dcdf607baaab1cc3c299a3584c386173
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2022
ms.locfileid: "9776834"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Zarządzaj nieznanymi profilami dzięki funkcji Customer Insights

Użytkownicy Internetu są często niezidentyfikowani lub anonimowi w sieci. Nawet najbardziej lojalność klientów może się wydawać „nieznana”, jeśli nie są zalogowani na różnych urządzeniach. Dla wielu marek znani lub uwierzytelnieni użytkownicy stanowią mniejszość, pomimo rosnących oczekiwań klientów dotyczących personalizacji. Biorąc pod uwagę przyszłość plików cookie stron trzecich, zarządzanie preferencjami użytkowników w oparciu o dane własne ma kluczowe znaczenie dla osiągnięcia spersonalizowanych doświadczeń.

Personalizacja konwersji zależy od tego, jak dobrze znasz klienta i jego dane dzięki aplikacji Customer Insights, dzięki śledzeniu wszystkich klientów.  Nie musisz ograniczać ani zaprzestawać wykorzystywania danych zebranych na początku podróży klienta. Customer Insights umożliwia wprowadzenie własnych danych w celu stworzenia profilu klienta dla nieznanych użytkowników. Następnie możesz wykorzystać ten profil do dalszych działań, mimo brakujących informacji kontaktowych. Importuj do Customer Insights dane pochodzące ze źródeł takich jak strony internetowe, urządzenia mobilne czy systemy CRM, aby stale wzbogacać profile klientów. W miarę ujednolicania kolejnych interakcji [zamień *nieznanego* klienta w *znanego* klienta](unknown-to-known.md).

## <a name="sample-scenario"></a>Przykładowy scenariusz

Załóżmy, że użytkownik korzysta z urządzenia mobilnego do przeglądania Twojej witryny e-commerce. Strona przypisuje odwiedzającemu "mobile_guest123" jako unikalny identyfikator, a Ty zaczynasz zbierać dane behawioralne na podstawie jego aktywności online. Na przykład, jakie strony odwiedzili, ile czasu spędzili na tych stronach lub jakie linki kliknęli. Nie znasz ich imienia ani adresu e-mail, ale te dane mogą dostarczyć marce istotnych informacji o tym konkretnym użytkowniku. Z kolei te spostrzeżenia możesz wykorzystać przy następnej wizycie użytkownika na stronie. Zapytajcie Customer Insights o "mobile_guest123", aby uzyskać listę segmentów użytkownika, takich jak "organiczni", "mobilni klienci zamawiający w przedsprzedaży", "klienci o wysokiej wartości" itp. lub pobrać profil, aby stworzyć spersonalizowane doświadczenia internetowe. Możesz również wyeksportować dane do dowolnego systemu aktywacji, aby zrobić to samo.

## <a name="prerequisites"></a>Wymagania wstępne

- Wprowadzanie danych z pierwszej ręki do Customer Insights
- Każda encja ma unikalne ID, które jest ustawione jako klucz główny
- Każda jednostka z kluczem głównym do personalizacji jest zunifikowana
- System zarządzania treścią twojej strony internetowej jest zdolny do korzystania z API (do personalizacji strony internetowej opartej na bezpośredniej komunikacji z Customer Insights)

W poniższej tabeli przedstawiono uproszczony przykład przechwytywania zdarzeń internetowych o wysokiej wartości.

|EventID|EventTimeStamp|UserID|PrimaryKey|EventName|
|--|--|--|--|--|
|1|09-15-2022 9:00:00|abc123|CookieID1|Widok produktu|
|2|09-18-2022 10:05:00|abc123|CookieID1|Widok produktu|
|3|09-18-2022 10:10:00|abc123|CookieID1|Dodaj do koszyka|
|100|09-21-2022 09:05:00|abc123|CookieID1|Widok produktu|

## <a name="data-ingestion"></a>Pozyskiwanie danych

Aby uzyskać więcej informacji o dostępnych opcjach pozyskiwania danych, zobacz [Przegląd źródeł danych](data-sources.md).

## <a name="data-unification"></a>Ujednolicenie danych

Więcej informacji na temat ujednolicenia profili klientów, zobacz [Omówienie ujednolicania danych](data-unification.md).

## <a name="get-insights"></a>Pobierz wyniki analiz

[Wzbogać](enrichment-hub.md) dane, utwórz [miary](measures.md) i utwórz [segmenty](segments.md) w celu dalszej aktywacji.

Na przykład możesz stworzyć segmenty nieznanych użytkowników, którzy przeglądali te same strony z produktami, ale nigdy nie dokończyli zakupów.

## <a name="activation"></a>Aktywacja

Mając dane w Customer Insights i gotowe do pracy spostrzeżenia, możesz wykorzystać Customer Insights do personalizacji:

1. Użyj [OData API](apis.md), aby pobrać członkostwo w segmencie lub profil klienta Więcej przykładów znajdziesz w [Przykłady zapytań OData dla interfejsów API Customer Insights](odata-examples.md).

1. [Eksportuj](export-destinations.md) swoje dane do systemów aktywacji.

Przykład: Nieznany użytkownik wielokrotnie odwiedza stronę internetową i odwiedza strony z produktami dotyczącymi różnych modeli skórzanych butów. Mając te dane dostępne w Customer Insights, możesz włączyć nieznanego użytkownika do segmentu osób zainteresowanych skórzanymi butami. Wykorzystaj ten segment, aby spersonalizować budowę witryny dla powracających użytkowników. Przy kolejnej wizycie strona rozpoznaje nieznanego użytkownika i może zaoferować mu kupon zniżki 10% na buty skórzane.

[!INCLUDE [footer-include](includes/footer-banner.md)]
