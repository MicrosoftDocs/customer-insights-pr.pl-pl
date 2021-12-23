---
title: Encje i zestawy danych
description: Wyświetlanie danych na stronie Encji.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 00c5ee50fb9f0906622c91699852ffba0acb5c15
ms.sourcegitcommit: 11b343f6622665251ab84ae39ebcd91fa1c928ca
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2021
ms.locfileid: "7900440"
---
# <a name="entities-in-audience-insights"></a>Encje w analizach odbiorców

Po [skonfigurowaniu źródeł danych](data-sources.md) przejdź na stronę **Encje**, aby oceniać jakość pobranych danych. Encje są traktowane jako zestawy danych. Wokół tych encji jest zbudowanych wiele funkcji Dynamics 365 Customer Insights. Ich ścisłe przejrzenie może pomóc w sprawdzeniu poprawności danych wyjściowych możliwości.

Strona **Encje** zawiera listę podmiotów i zawiera te kolumny:

- **Nazwa**: Nazwa encji danych. Jeśli obok nazwy encji zostanie wyświetlony symbol ostrzeżenia, oznacza to, że dane dotyczące tej encji nie zostały pomyślnie załadowane.
- **Źródło**: Typ źródła danych, z którego pochodzi encja.
- **Zaktualizowano**: Czas ostatniej aktualizacji jednostki.
- **Stan**: szczegółowe informacje o ostatniej aktualizacji encji.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>Eksploruj dane określonej encji

1. W analizach odbiorców przejdź do **Dane** > **Encje**.
1. Na stronie **Encji** wybierz podmiot, aby otworzyć stronę ze szczegółami.  
1. Zbadaj różne pola i rekordy zawarte w tej jednostce.

- Karta **Atrybuty** jest domyślnie wybrana i pokazuje tabelę przeglądania szczegółów wybranej encji, takich jak nazwy pól, typy danych i typy. W kolumnie **Typ** są wyświetlane typy skojarzone z Common Data Model, które są automatycznie identyfikowane przez system lub [ręcznie mapowane](map-entities.md) przez użytkowników. Te typy są typami semantycznymi, które mogą się różnić od typów danych atrybutów. Na przykład pole *Poczta e-mail* poniżej ma typ danych *Tekst*, ale jego (semantyczny) typ Common Data Model może być *Pocztą e-mail* lub *Adresem e-mail*.

> [!div class="mx-imgBorder"]
> ![Tabela pól.](media/data-manager-entities-fields.PNG "Tabela pól")

> [!NOTE]
> Ta strona pokazuje tylko próbkę danych Twojej jednostki. Aby wyświetlić pełny zestaw danych, przejdź na stronę **Źródła danych**, wybierz encję, wybierz pozycję **Edytuj**, a następnie wyświetl dane tej encji przy użyciu edytora Power Query, jak wyjaśniono w [Źródła danych](data-sources.md).

Aby dowiedzieć się więcej o danych pobranych w encji, kolumna **Podsumowanie** dostarcza znaczących cech danych, takich jak wartości zerowe, brakujące wartości, unikatowe wartości, zliczenia i rozkłady, które mają zastosowanie do danych. Aby wyświetlić podsumowanie danych, należy wybrać ikonę wykresu.

> [!div class="mx-imgBorder"]
> ![Symbol podsumowania.](media/data-manager-entities-summary.png "Tabela podsumowania danych")

- Na karcie **Dane** jest pokazana tabela ze szczegółami poszczególnych rekordów obiektu. Wymienione szczegóły zależą od typu danych encji.

> [!div class="mx-imgBorder"]
> ![Wybierz encję.](media/data-manager-entities-data.png "Wybierz encję")

- Zakładka **Raporty** (dostępna dla niektórych encji) umożliwia Ci wizualizację Twoich danych poprzez stworzenie raportu i zawiera te kolumny:

  - **Nazwa raportu**: Nazwa raportu.
  - **Autor**: Imię i nazwisko osoby, która utworzyła encję.
  - **Utworzono**: Data i godzina utworzenia encji.
  - **Autor edycji**: Imię i nazwisko osoby, która zmodyfikowała encję.
  - **Data edycji**: Data i godzina zmodyfikowania encji. 

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
