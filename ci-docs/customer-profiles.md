---
title: Wyświetlaj profile klientów
description: Wyświetlanie ujednoliconych danych klientów, w tym używanie funkcji wyszukiwania i filtrowania
ms.date: 06/08/2022
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
ms.openlocfilehash: 6cdf47e6997f230811dcb0f2cf5542f3a6db2367
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188106"
---
# <a name="view-customer-profiles"></a>Wyświetlaj profile klientów

Profile klientów są dostępne po utworzeniu [ujednoliconej encji *klienta*](data-unification.md). Połączony widok Twoich ujednoliconych profili klientów jest wyświetlany na stronie **Klienci**. Klientami mogą być pojedyncze osoby lub organizacje.

Przejdź na stronę **Klienci**, aby wyświetlić swoich klientów i ich profile. Każdy profil klienta jest reprezentowany przez kafelek. Aby uzyskać więcej rekordów, użyj kontrolek stronicowania. Na karcie są wyświetlane pola encji *Klient* zgodnie z **Indeksem wyszukiwania i filtrowania**. Kolejność pól na każdej karcie jest wybierana przez system.

> [!NOTE]
> Jeśli kafelki nie są widoczne po wybraniu opcji **Klienci**, administrator musi [zdefiniować co najmniej jeden atrybut, który można wyszukać](search-filter-index.md) w **indeksie wyszukiwania i filtrowania**.

:::image type="content" source="media/customers-page-result-tiles-B2C.png" alt-text="Strona Klienci z kafelkami wyników.":::

Wybierz dowolne z następujących działań:
- [Zobacz dane klienta](#view-customer-details)
- [Zarządzanie indeksem wyszukiwania i filtrów](search-filter-index.md) (tylko administratorzy)
- [Filtrowanie klientów](#filter-customers)
- **Rozwiń karty** lub **Zwiń karty**, aby rozwinąć lub zwinąć informacje wyświetlane na kafelku klienta
- **Sortowanie według** konkretnego atrybutu
- [Wyszukaj klientów](#search-for-customers)

  > [!NOTE]
  > Aby korzystać z wyszukiwania i filtrowania, administrator musi skonfigurować atrybuty wyszukiwania i zdefiniować pola, które można filtrować, korzystając z indeksu wyszukiwania i filtrowania.

## <a name="search-for-customers"></a>Wyszukaj klientów

Wyszukaj klientów, wprowadzając nazwę lub inny atrybut w **Wyszukaj klientów**. Atrybuty, które można wyszukiwać, są definiowane przez administratora i pochodzą z encji ujednoliconej *Klient*.

> [!NOTE]
> **Ciąg** tekstowy to jedyny typ danych uwzględniany w wyszukiwaniu. Użyj jej w polu **Wyszukaj klientów** na stronie Klienci, aby wyszukać klientów.

## <a name="filter-customers"></a>Filtrowanie klientów

Klientów można filtrować według pól encji *Klient*. Pola filtrowane są definiowane przez administratora.

1. Na stronie **Klienci** wybierz opcję **Pokaż filtry**. Zostanie wyświetlone okienko Filtr.

1. Zaznacz pola wyboru obok atrybutów, według których chcesz filtrować klientów.

1. Usuń wszystkie filtry, wybierając **Wyczyść filtry** lub wyczyść pole wyboru obok wybranego atrybutu.

1. Wybierz **Ukryj filtry**, aby zamknąć okienko filtrów.

1. Aby zapisać wyniki filtru jako [segment](segments.md), wybierz opcję **Zapisz filtry jako segment**.
   1. Wpisz nazwę segmentu.
   1. Wybierz **Zapisz**, aby zapisać segment.
   1. Możesz teraz wybrać opcję **Uaktywnij** lub uruchom segment, wybierając opcję **Później**.

## <a name="view-customer-details"></a>Zobacz dane klienta

Na stronie **Klienci** wybierz kafelek klienta, aby wyświetlić szczegóły wybranego klienta.

:::image type="content" source="media/customers-details-B2C.png" alt-text="Strona Szczegóły klienta.":::

Szczegóły klienta zawierają:

**Kafelek profilu klienta** przedstawia różne wartości w ujednoliconej encji *Klient*. Jeśli pole nie ma wartości dla wybranego profilu klienta, nie będzie ono wyświetlane poza polem adresu. Kafelek jest uporządkowany na sekcje:

- W pierwszej sekcji przedstawiono wstępnie zdefiniowany zestaw pól, a po nich wszystkie pola w indeksie wyszukiwania i filtrowania. Wszystkie pola związane z adresami są połączone w jeden wiersz, który jest wyświetlany nawet, jeśli profil nie zawiera informacji o adresie.
- **Kontakty dotyczące tego klienta** są wyświetlane w środowiskach dla kont biznesowych. Każdy kontakt jest wyświetlany z ich polami. Puste pola są ukryte.
- **Pola dodatkowe** pokazuje pozostałe pola wybranego klienta z wyjątkiem identyfikatorów.
- **Identyfikatory** zawiera listę wszystkich identyfikatorów pod ich nazwą encji. Pola są identyfikowane jako identyfikatory na podstawie ich semantyki.

**Oś czasu działania** pokazuje dane, jeśli skonfigurowano [działania](activities.md). Widok osi czasu zawiera chronologiczne działania wybranego klienta, zaczynając od najnowszego działania.

**Szczegółowe informacje**:

- **Miary** pokaż, czy masz skonfigurowane [miary atrybutów klienta](measures.md). Obejmują one obliczone KPI wokół Twoich klientów na poziomie klienta indywidualnego.

- **Potencjalne zainteresowania, potencjalne marki** wskazuje, czy [skonfigurowano wzbogacenie marki lub zainteresowania](enrichment-microsoft.md). Reprezentuje potencjalne interesy i możliwości dla miar na podstawie innych klientów, których profil jest podobny do wybranego profilu klienta.

Aby wrócić do strony **Klienci**, wybierz **Powrót do klientów**.

## <a name="next-steps"></a>Następne kroki

[Dodaj więcej źródeł danych](data-sources.md), [wzbogać ujednolicone profile](enrichment-hub.md) lub [utwórz segmenty](segments.md), aby pracować z ujednoliconym profilami klientów w innych aplikacjach.

[!INCLUDE [footer-include](includes/footer-banner.md)]
