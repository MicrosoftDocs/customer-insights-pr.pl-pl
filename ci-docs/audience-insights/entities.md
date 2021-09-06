---
title: Encje i zestawy danych
description: Wyświetlanie danych na stronie Encji.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 137de726b243b501491fcbe7866820aaee26097fcf379270c423c277374ae9a4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033828"
---
# <a name="entities-in-audience-insights"></a>Encje w analizach odbiorców

Po [skonfigurowaniu źródeł danych](data-sources.md) przejdź na stronę **Encje**, aby oceniać jakość pobranych danych. Encje są traktowane jako zestawy danych. Wokół tych encji jest zbudowanych wiele funkcji Dynamics 365 Customer Insights. Ich ścisłe przejrzenie może pomóc w sprawdzeniu poprawności danych wyjściowych możliwości.

Na stronie **Encje** znajduje się lista encji i zawiera kilka kolumn:

- **Nazwa**: Nazwa encji danych. Jeśli obok nazwy encji zostanie wyświetlony symbol ostrzeżenia, oznacza to, że dane dotyczące tej encji nie zostały pomyślnie załadowane.
- **Źródło**: Typ źródła danych, które pobrało encję
- **Autor**: Imię i nazwisko osoby, która utworzyła encję
- **Utworzono**: Data i godzina utworzenia encji
- **Zaktualizowane przez**: Imię i nazwisko osoby, która zaktualizowała encję
- **Ostatnia aktualizacja**: Data i godzina ostatniej aktualizacji encji
- **Ostatnie odświeżenie**: Data i godzina ostatniego odświeżenia danych

## <a name="explore-a-specific-entitys-data"></a>Eksploruj dane określonej encji

Wybierz encję, aby poznać różne pola i rekordy zawarte w tej encji.

> [!div class="mx-imgBorder"]
> ![Wybierz encję.](media/data-manager-entities-data.png "Wybierz encję")

- Na karcie **Dane** jest pokazana tabela ze szczegółami poszczególnych rekordów obiektu.

> [!div class="mx-imgBorder"]
> ![Tabela pól.](media/data-manager-entities-fields.PNG "Tabela pól")

- Karta **Atrybuty** jest domyślnie wybrana i pokazuje tabelę przeglądania szczegółów wybranej encji, takich jak nazwy pól, typy danych i typy. W kolumnie **Typ** są wyświetlane typy skojarzone z Common Data Model, które są automatycznie identyfikowane przez system lub [ręcznie mapowane](map-entities.md) przez użytkowników. Te typy są typami semantycznymi, które mogą się różnić od typów danych atrybutów. Na przykład pole *Poczta e-mail* poniżej ma typ danych *Tekst*, ale jego (semantyczny) typ Common Data Model może być *Pocztą e-mail* lub *Adresem e-mail*.

> [!NOTE]
> W obu tabelach przedstawiono tylko próbkę danych encji. Aby wyświetlić pełny zestaw danych, przejdź na stronę **Źródła danych**, wybierz encję, wybierz pozycję **Edytuj**, a następnie wyświetl dane tej encji przy użyciu edytora Power Query, jak wyjaśniono w [Źródła danych](data-sources.md).

Aby dowiedzieć się więcej o danych pobranych w encji, kolumna **Podsumowanie** dostarcza znaczących cech danych, takich jak wartości zerowe, brakujące wartości, unikatowe wartości, zliczenia i rozkłady, które mają zastosowanie do danych.

Aby wyświetlić podsumowanie danych, należy wybrać ikonę wykresu.

> [!div class="mx-imgBorder"]
> ![Symbol podsumowania.](media/data-manager-entities-summary.png "Tabela podsumowania danych")

## <a name="entity-specific-information"></a>Informacje na temat określonej encji

Poniższa sekcja zawiera informacje o niektórych encjach utworzonych przez system.

### <a name="corrupted-data-sources"></a>Uszkodzone źródła danych

Pola z przeanalizowanego źródła danych mogą zawierać uszkodzone dane. Rekordy z uszkodzonymi polami są udostępniane w encjach utworzonych przez system. Znajomość uszkodzonych rekordów pomaga zidentyfikować dane, które mają być przeglądane i aktualizowane w systemie źródłowym. Po następnym odświeżeniu źródła danych poprawione rekordy są pozyskiwane do usługi Customer Insights i przekazywane do procesów podrzędnych. 

Na przykład kolumna „urodziny” ma typ danych ustawiony jako „data”. Rekord klienta ma jego urodziny wprowadzone jako „01/01/19777”. System oznaczy ten rekord jako uszkodzony. Ktoś może teraz zmienić urodziny w systemie źródłowym na „1977”. Po automatycznym odświeżeniu źródeł danych pole ma teraz prawidłowy format, a rekord zostanie usunięty z uszkodzonej jednostki. 

Przejdź do **Dane** > **Jednostki** i poszukaj uszkodzonych jednostek w sekcji **System**. Schemat nazewnictwa uszkodzonych jednostek: „DataSourceName_EntityName_corrupt”.

Customer Insights nadal przetwarza uszkodzone rekordy. Jednak mogą one powodować problemy podczas pracy z ujednoliconymi danymi.

Następujące kontrole są uruchamiane na pozyskanych danych w celu ujawnienia uszkodzonych rekordów: 

- Wartość pola nie jest zgodna z typem danych jego kolumny.
- Pola zawierają znaki, które powodują, że kolumny nie są zgodne z oczekiwanym schematem. Na przykład: niepoprawnie sformatowane cudzysłowy, niezamknięte cudzysłowy lub znaki nowego wiersza.
- Jeśli istnieją kolumny datetime/date/datetimeoffset, ich format musi być określony w modelu, jeśli nie jest zgodny ze standardowym formatem ISO.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
