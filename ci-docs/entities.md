---
title: Encje w Customer Insights
description: Wyświetlanie danych na stronie Encji.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: 0beaa46d47545ac195ced876b509dfc57821bfaf
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183585"
---
# <a name="entities-in-customer-insights"></a>Encje w Customer Insights

Po [skonfigurowaniu źródeł danych](data-sources.md) przejdź na stronę **Encje**, aby oceniać jakość pobranych danych. Encje są traktowane jako zestawy danych. Wokół tych encji jest zbudowanych wiele funkcji Dynamics 365 Customer Insights. Ich ścisłe przejrzenie może pomóc w sprawdzeniu poprawności danych wyjściowych możliwości.

Podczas pracy w aplikacji Customer Insights wzbogacając dane lub tworząc segmenty, miary i działania, encje utworzone na podstawie tych akcji są wyświetlane na stronie **Encje**.

## <a name="view-a-list-of-entities"></a>Wyświetlanie listy encji

Przejdź do **Dane** > **Encje**, aby wyświetlić listę encji. Dla każdej encji wyświetlane są następujące informacje.

- **Nazwa**: Nazwa encji danych. Jeśli obok nazwy encji zostanie wyświetlony symbol ostrzeżenia, oznacza to, że dane dotyczące tej encji nie zostały pomyślnie załadowane.
- **Źródło**: Typ źródła danych, z którego pochodzi encja.
- **Zaktualizowano**: Czas ostatniej aktualizacji jednostki.
- **Stan**: szczegółowe informacje o ostatniej aktualizacji encji.

## <a name="explore-a-specific-entitys-data"></a>Eksploruj dane określonej encji

1. Przejdź do **Dane** > **Encje**.
1. Wybierz encję, aby otworzyć stronę szczegółów.  
1. Zbadaj różne pola i rekordy zawarte w tej jednostce.

- Karta **Atrybuty** jest domyślnie wybrana i przegląd szczegółów wybranej encji, takich jak nazwy pól, typy danych i typy. W kolumnie **Typ** są wyświetlane typy skojarzone z Common Data Model, które są automatycznie identyfikowane przez system lub [ręcznie mapowane](map-entities.md) przez użytkowników. Te typy są typami semantycznymi, które mogą się różnić od typów danych atrybutów. Na przykład pole *Poczta e-mail* poniżej ma typ danych *Ciąg*, ale jego (semantyczny) typ Common Data Model może być *Email*, *EmailAddress* lub *Identity.Service.Email*.

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Tabela pól.":::

   > [!NOTE]
   > Ta strona pokazuje tylko próbkę danych Twojej jednostki. Aby wyświetlić pełny zestaw danych, przejdź na stronę **Źródła danych**, wybierz encję, wybierz pozycję **Edytuj**, a następnie wyświetl dane tej encji przy użyciu edytora Power Query, jak wyjaśniono w [Źródła danych](data-sources.md).

   Aby dowiedzieć się więcej o danych pobranych w encji, kolumna **Podsumowanie** zawiera kilka ważnych cech danych, takich jak wartości null, braki danych, unikatowe wartości, liczebności i rozkłady, niezależnie od tego, co ma zastosowanie do Twoich danych. Aby wyświetlić podsumowanie danych, należy wybrać ikonę wykresu.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Tabela podsumowania danych.":::

- Karta **Dane** zawiera szczegółowe informacje o poszczególnych rekordach podmiotu. Wymienione szczegóły zależą od typu danych encji.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Wybierz encję.":::

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

Przejdź do **Dane** > **Jednostki** i poszukaj uszkodzonych jednostek w sekcji **System**. Schemat nazewnictwa uszkodzonych jednostek: „DataSourceName_EntityName_corrupt”. Wybierz uszkodzoną encję, aby zidentyfikować wszystkie uszkodzone pola i przyczynę na poziomie indywidualnego rekordu.

   :::image type="content" source="media/corruption-reason.png" alt-text="Przyczyna uszkodzenia.":::

Customer Insights nadal przetwarza uszkodzone rekordy. Jednak mogą one powodować problemy podczas pracy z ujednoliconymi danymi.

Następujące kontrole są uruchamiane na pozyskanych danych w celu ujawnienia uszkodzonych rekordów:

- Wartość pola nie jest zgodna z typem danych jego kolumny.
- Pola zawierają znaki, które powodują, że kolumny nie są zgodne z oczekiwanym schematem. Na przykład: niepoprawnie sformatowane cudzysłowy, niezamknięte cudzysłowy lub znaki nowego wiersza.
- Jeśli istnieją kolumny datetime/date/datetimeoffset, ich format musi być określony w modelu, jeśli nie jest zgodny ze standardowym formatem ISO.

[!INCLUDE [footer-include](includes/footer-banner.md)]
