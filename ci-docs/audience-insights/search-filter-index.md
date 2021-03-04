---
title: Wyszukiwanie i filtrowanie profilów klientów
description: Szybki dostęp do informacji o ujednoliconych profilach klientów i filtrach dla określonych atrybutów.
ms.date: 01/19/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d675738c43cbdb5f9b478d53d6124db38ba3004d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270079"
---
# <a name="customer-profiles-search--filter-index"></a>Profile klientów: Wyszukiwanie i indeks filtrów

Ujednolicenie danych klienta jest encją profilu klienta, która umożliwia zunifikowany widok całej podstawowej bazy klientów. Aby szybko [znaleźć informacje o określonym kliencie lub grupie klientów](customer-profiles.md), można skonfigurować funkcje **Wyszukiwania** i **Filtrowania** na stronie **Klienci**. W tym artykule opisano, jak Administratorzy mogą edytować atrybuty na stronie **Wyszukiwanie i indeks filtrów**, które są dostępne dla użytkowników w wyszukiwaniu i filtrowaniu.

> [!div class="mx-imgBorder"]
> ![Filtr wyszukiwania](media/search-filter.png "Filtr wyszukiwania")

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

3. Wybierz opcję **Uruchom** po przygotowaniu się do zastosowania ustawień.

## <a name="next-steps"></a>Następne kroki

Przejdź na stronę **Klienci**, aby wyszukać profile klientów lub użyj pól indeksowanych, aby wyświetlić podzbiór wszystkich profilów klientów.


[!INCLUDE[footer-include](../includes/footer-banner.md)]