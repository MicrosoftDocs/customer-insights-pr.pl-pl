---
title: Wyświetlaj profile klientów
description: Umożliwia uzyskanie połączonego widoku ujednoliconych danych klienta.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-customer-card
- ci-activities
- ci-activities-wizard
- customerInsights
ms.openlocfilehash: 074d84eff65d52b083fff6c161282d4fafa1af85
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2022
ms.locfileid: "8523745"
---
# <a name="customer-profiles"></a>Profile klientów

Na stronie **Klienci** jest wyświetlany połączony widok ujednoliconych profilów klientów. Profile klientów są dostępne po [utworzeniu ujednoliconej encji Klient](data-unification.md). Strona umożliwia wyszukiwanie klientów i definiowanie indeksu służącego do tego wyszukiwania.

Klientami mogą być pojedyncze osoby lub organizacje. Każdy profil klienta jest reprezentowany przez kafelek. Aby uzyskać więcej rekordów, użyj kontrolek stronicowania. Na karcie są wyświetlane pola encji *Klient* zgodnie z **Indeksem wyszukiwania i filtrowania**. Kolejność pól na każdej karcie jest wybierana przez system.

Wybierz kafelek, aby zobaczyć dane wybranego klienta na dedykowanej stronie o nazwie [Strona szczegółów klienta](customer-profiles.md#customer-details-page).

> [!div class="mx-imgBorder"] 
> ![Strona Klienci z kafelkami wyników](media/customers-page-result-tiles-B2C.png "Strona Klienci z kafelkami wyników")

> [!NOTE]
> Jeśli kafelki nie są widoczne po wybraniu opcji **Klienci** w nawigacji, administrator musi [zdefiniować co najmniej jeden atrybut, który można wyszukać](search-filter-index.md) w **indeksie wyszukiwania i filtrowania**.

## <a name="search-for-customers"></a>Wyszukaj klientów

Wyszukaj klientów, wprowadzając nazwę lub inny atrybut w polu wyszukiwania. Wyszukiwanie działa tylko w encji _Klient_ utworzonej podczas procesu ujednolicania danych.

Administrator może skonfigurować atrybuty, które można przeszukiwać, korzystając ze strony **Wyszukiwanie i indeks filtrów**. Aby uzyskać więcej informacji, przejdź do tematu [Zarządzanie indeksem wyszukiwania i filtrowania](search-filter-index.md).

## <a name="filter-customers"></a>Filtrowanie klientów

Klientów można filtrować według pól encji _Klient_. Podobnie jak w przypadku funkcji wyszukiwania administrator będzie musiał zdefiniować pola jako filtrowane przy użyciu strony **Wyszukiwanie i indeks filtrów**.

1. Wybierz opcję **Pokaż filtry** na stronie **Klienci**.

1. Zaznacz pola wyboru obok atrybutów, według których chcesz filtrować klientów.

1. Aby usunąć filtry, wybierz pozycję **Wyczyść filtry** na stronie **Klienci**.

## <a name="customer-details-page"></a>Strona Szczegóły klienta

Wybierz dowolną tabliczkę z klientami, aby otworzyć **Stronę szczegółów klienta**. Ten widok zawiera zunifikowane informacje dotyczące wybranego klienta. Szczegóły klienta zawierają następujące informacje:

**Kafelek profilu klienta**: ten kafelek przedstawia różne wartości w ujednoliconej encji _Klient_. Jeśli pole nie ma wartości dla wybranego profilu klienta, nie będzie ono wyświetlane. Kafelek jest uporządkowany na sekcje:  
  - W pierwszej sekcji przedstawiono wstępnie zdefiniowany zestaw pól, a po nich wszystkie pola w indeksie wyszukiwania i filtrowania. Wszystkie pola związane z adresami są połączone w jeden wiersz, jeśli profil zawiera takie pola. 
  - **Kontakty tego klienta**: w środowiskach dotyczących kont biznesowych w drugiej sekcji będą widoczne wszystkie kontakty pokrewne dotyczące tego klienta. Każdy kontakt jest wyświetlany z ich polami. Puste pola są ukryte.
  - **Pola dodatkowe**: pokazuje pozostałe pola wybranego klienta z wyjątkiem identyfikatorów. 
  - **Identyfikatory**: zawiera listę wszystkich identyfikatorów pod ich nazwą encji. Pola są identyfikowane jako identyfikatory według semantyki kategoryzującej je w odpowiedni sposób.

**Oś czasu działania**: pokazuje dane, jeśli skonfigurowano działania. Widok osi czasu zawiera chronologiczne działania wybranego klienta, zaczynając od najnowszego działania. Aby uzyskać więcej informacji, przejdź do tematu [Działania klienta](activities.md).

**Szczegółowe informacje**:  
  - **Miary**: wskazuje, czy skonfigurowano jedną lub więcej miar atrybutów klienta. Obejmują one obliczone KPI wokół Twoich klientów na poziomie klienta indywidualnego. Aby uzyskać więcej informacji, przejdź do tematu [Definiowanie miar i zarządzanie nimi](measures.md).

  - **Potencjalne zainteresowania, potencjalne marki**: wskazuje, czy skonfigurowano wzbogacenie marki lub zainteresowania. Reprezentuje potencjalne interesy i możliwości dla miar na podstawie innych klientów, których profil jest podobny do wybranego profilu klienta. Aby uzyskać więcej informacji, przejdź do strony [Wzbogacanie profilów klientów o sympatie do marki i zainteresowań](enrichment-microsoft.md).

Aby powrócić do strony wyszukiwania klientów, wybierz opcję **Wróć do klientów**.

## <a name="next-steps"></a>Następne kroki

[Dodaj więcej źródeł danych](data-sources.md), [wzbogać ujednolicone profile](enrichment-hub.md) lub [utwórz segmenty](segments.md), aby pracować z ujednoliconym profilami klientów w innych aplikacjach.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
