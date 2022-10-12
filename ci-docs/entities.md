---
title: Encje w Customer Insights
description: Wyświetlanie danych na stronie Encji.
ms.date: 08/04/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: e365945b27e7c985ca5371c6b72619610b6f3af1
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610111"
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

[!INCLUDE [footer-include](includes/footer-banner.md)]
