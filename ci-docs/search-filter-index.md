---
title: Zarządzaj indeksem wyszukiwania i filtrowania dla profili klientów
description: Szybki dostęp do informacji o ujednoliconych profilach klientów i filtrach dla określonych atrybutów.
ms.date: 07/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: dfbfcbff3ffb3e4483252377e591229631d38556
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/22/2022
ms.locfileid: "9187922"
---
# <a name="manage-the-search--filter-index-for-customer-profiles"></a>Zarządzaj indeksem wyszukiwania i filtrowania dla profili klientów

Ujednolicenie danych klienta jest encją *klienta*, która umożliwia zunifikowany widok całej podstawowej bazy klientów. Aby szybko [znaleźć informacje o określonym kliencie lub grupie klientów](customer-profiles.md), administrator musi skonfigurować funkcje **Wyszukiwania** i **Filtrowania** na stronie **Klienci**.

   :::image type="content" source="media/search-filter.png" alt-text="Filtr wyszukiwania":::

## <a name="define-searchable-attributes-and-indexed-fields"></a>Definiowanie atrybutów z kryteriami wyszukiwania i pól indeksowanych

Jeśli za pierwszym razem definiuje się jako Administrator atrybuty jako atrybuty, które można wyszukiwać, należy najpierw zdefiniować pola indeksowane. Sugerujemy wybranie wszystkich atrybutów, dzięki którym użytkownicy mogą wyszukiwać i filtrować klientów na stronie **klienci**. Można określić tylko atrybuty istniejące w jednostce *Klient* utworzonej podczas procesu ujednolicania danych.

1. Otwórz **Klienci** i wybierz **Wyszukiwanie i indeks filtrów**.

1. Wybierz **+ Dodaj**.

1. Wybierz atrybuty z listy, które chcesz dodać jako pola indeksowane i kliknij **Zastosuj**.

1. Aby dodać więcej atrybutów, wybierz **Dodaj**. Aby usunąć wybrany atrybut, wybierz atrybut, a następnie **Usuń**.

   :::image type="content" source="media/search-filter-index.png" alt-text="Strona indeksu wyszukiwania i filtrowania.":::

1. Wybierz opcję **Uruchom** po przygotowaniu się do zastosowania ustawień wyszukiwania i filtrowania. Po przetworzeniu zmian można je znaleźć na [kartach klientów na stronie Klient](customer-profiles.md).

## <a name="define-filtering-options-for-a-given-attribute"></a>Zdefiniuj opcje filtrowania dla danego atrybutu

Skonfiguruj pola, których można używać do filtrowania klientów na stronie **Klienci**.

1. Otwórz **Klienci** i wybierz **Wyszukiwanie i indeks filtrów**.

1. Wybierz atrybut i **Dodaj filtr**. Określ liczbę wyników i kolejność, w jakiej będą one zorganizowane. W zależności od typu danych atrybutu jest wyświetlane jedeno z następujących okienek.

   - Atrybuty będące ciągiem: Określ liczbę oczekiwanych wyników w okienku **Filtruj ciągi** oraz zasadę kolejności, zgodnie z którą będą one zorganizowane.

   - Atrybuty typu liczbowego: Określ interwały w okienku **Filtruj liczby** oraz zasadę kolejności, zgodnie z którą będą one zorganizowane.

   - Atrybuty typu dane: Określ interwały w okienku **Filtruj dane** oraz zasadę kolejności, zgodnie z którą będą one zorganizowane.

1. Zaznacz **OK**. Powtórz dla wszystkich atrybutów, według których chcesz filtrować.

1. Wybierz opcję **Uruchom** po przygotowaniu się do zastosowania ustawień wyszukiwania i filtrowania. Po przetworzeniu zmian można je znaleźć na [kartach klientów na stronie Klient](customer-profiles.md).

## <a name="view-indexed-customer-fields"></a>Wyświetl zindeksowane pola klientów

Strona **Indeks wyszukiwania i filtrowania** zawiera następujące informacje:

- **Nazwa**: reprezentuje nazwę atrybutu, która jest wyświetlana w encji *klienta*.
- **Typ danych**: określa, czy typem danych jest ciąg, liczba lub data.
- **Uwzględnione w wyszukiwaniu**: określa, czy można korzystać z tego atrybutu do wyszukiwania klientów na stronie **klienci** w polu **Wyszukaj**.
- **Dodaj filtr**: formant służący do definiowania sposobu korzystania z tego atrybutu w celu filtrowania na stronie **Klienci**.

## <a name="next-steps"></a>Następne kroki

Przejrzyj [stronę ujednoliconych profilów](customer-profiles.md), aby wyszukać profile lub użyj pól indeksowanych, aby wyświetlić podzbiór wszystkich ujednoliconych profilów.

[!INCLUDE [footer-include](includes/footer-banner.md)]
