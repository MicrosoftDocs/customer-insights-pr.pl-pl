---
title: 'Profile klientów: Wyszukiwanie i indeks filtrów'
description: Szybki dostęp do informacji o ujednoliconych profilach klientów i filtrach dla określonych atrybutów.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: fc076e341f744ac2922dcacdf5f20ae8ecbdbaa0
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9050822"
---
# <a name="customer-profiles-search--filter-index"></a>Profile klientów: Wyszukiwanie i indeks filtrów

Ujednolicenie danych klienta jest encją profilu klienta, która umożliwia zunifikowany widok całej podstawowej bazy klientów. Aby szybko [znaleźć informacje o określonym kliencie lub grupie klientów](customer-profiles.md), można skonfigurować funkcje **Wyszukiwania** i **Filtrowania** na stronie **Klienci**. W tym artykule opisano, jak Administratorzy mogą edytować atrybuty na stronie **Wyszukiwanie i indeks filtrów**, które są dostępne dla użytkowników w wyszukiwaniu i filtrowaniu.

   :::image type="content" source="media/search-filter.png" alt-text="Filtr wyszukiwania":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="add-fields-and-specify-attributes"></a>Dodawanie pól i określanie atrybutów

Jeśli za pierwszym razem definiuje się jako Administrator atrybuty jako atrybuty, które można wyszukiwać, należy najpierw zdefiniować pola indeksowane. Sugerujemy wybranie wszystkich atrybutów, dzięki którym użytkownicy mogą wyszukiwać i filtrować klientów na stronie **klienci**. Użytkownik może podać tylko te atrybuty, które istnieją w encji profil klienta, która została utworzona podczas procesu zjednoczenia danych.

1. Otwórz stronę **Klienci** i wybierz **Wyszukiwanie i indeks filtrów**.

2. Wybierz **+ Dodaj**, aby określić indeksowane pola.

3. Wybierz atrybuty z listy, które chcesz dodać jako pola indeksowane. Zawsze możesz dodać więcej atrybutów wybierając **Dodaj**. Można również usunąć dowolne wybrane atrybuty, wybierając symbol **Usuń**.

## <a name="explore-the-indexed-customer-fields-table"></a>Poznawanie tabeli pól indeksowanych klientów

Poniższe informacje przedstawiono w tabeli.

- **Nazwa**: reprezentuje nazwę atrybutu, która jest wyświetlana w encji profil klienta.
- **Typ danych**: określa, czy typem danych jest ciąg, liczba lub data.
- **Uwzględnione w wyszukiwaniu**: określa, czy można korzystać z tego atrybutu do wyszukiwania klientów na stronie **klienci** w polu **Wyszukaj**.
- **Dodaj filtr**: formant służący do definiowania sposobu korzystania z tego atrybutu w celu filtrowania na stronie **Klienci**.

## <a name="editing-filtering-options-for-a-given-attribute"></a>Edytowanie opcji filtrowania dla danego atrybutu

Menu **Filtruj** na stronie **Klienci** może zawierać różną liczbę poziomów atrybutów (na przykład różne grupy wiekowe do filtrowania klientów).

1. Wybierz **Dodaj filtr** dla danego atrybutu na stronie **Wyszukiwanie i indeks filtrów**. Można zdefiniować liczbę wyników i kolejność ich zorganizowania. W zależności od typu danych atrybutu jest wyświetlane jedeno z następujących okienek.

- Atrybuty będące ciągiem: Określ liczbę oczekiwanych wyników w okienku **Opcje filtru ciągów** oraz zasadę kolejności, zgodnie z którą będą one zorganizowane.

- Atrybuty typu liczbowego: Określ interwały w okienku **Opcje filtru liczb** oraz zasadę kolejności, zgodnie z którą będą one zorganizowane.

- Atrybuty typu dane:  Określ interwały w okienku **Opcje filtru danych** oraz zasadę kolejności, zgodnie z którą będą one zorganizowane.

2. Wybierz pozycję **Zapisz**, aby zastosować zmiany.

3. Wybierz opcję **Uruchom** po przygotowaniu się do zastosowania ustawień. Po przetworzeniu zmian można je znaleźć na [kartach klientów na stronie Klient](customer-profiles.md). 

## <a name="next-steps"></a>Następne kroki

Przejrzyj [stronę ujednoliconych profilów](customer-profiles.md), aby wyszukać profile lub użyj pól indeksowanych, aby wyświetlić podzbiór wszystkich ujednoliconych profilów.


[!INCLUDE [footer-include](includes/footer-banner.md)]
