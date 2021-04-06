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
ms.openlocfilehash: 383523bad5105e08e57758838e90a49e805b5f9b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596420"
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

## <a name="exploring-a-specific-entitys-data"></a>Eksplorowanie danych określonej encji

Wybierz encję, aby poznać różne pola i rekordy zawarte w tej encji.

> [!div class="mx-imgBorder"]
> ![Wybierz encję](media/data-manager-entities-data.png "Wybierz encję")

- Karta **Dane** jest domyślnie zaznaczona i zawiera tabelę zawierającą szczegółowe informacje na temat poszczególnych rekordów encji.

> [!div class="mx-imgBorder"]
> ![Tabela pól](media/data-manager-entities-fields.PNG "Tabela pól")

- Na karcie **Pola** jest wyświetlona tabela służąca do przejrzenia szczegółowych informacji o wybranej encji, takich jak nazwy pól, typy danych i typy. W kolumnie **Typ** są wyświetlane typy skojarzone z Common Data Model, które są automatycznie identyfikowane przez system lub [ręcznie mapowane](map-entities.md) przez użytkowników. Są to typy semantyczne, które mogą różnić się w zależności od typów danych atrybutów — na przykład pole *Poczta e-mail* poniżej zawiera typ danych *Tekst*, ale jego (semantycznym) typem Common Data Model może być *Email* lub *EmailAddress*.

> [!NOTE]
> W obu tabelach przedstawiono tylko próbkę danych encji. Aby wyświetlić pełny zestaw danych, przejdź na stronę **Źródła danych**, wybierz encję, wybierz pozycję **Edytuj**, a następnie wyświetl dane tej encji przy użyciu edytora Power Query, jak wyjaśniono w [Źródła danych](data-sources.md).

Aby dowiedzieć się więcej o danych pobranych w encji, kolumna **Podsumowanie** dostarcza znaczących cech danych, takich jak wartości zerowe, brakujące wartości, unikatowe wartości, zliczenia i rozkłady, które mają zastosowanie do danych.

Aby wyświetlić podsumowanie danych, należy wybrać ikonę wykresu.

> [!div class="mx-imgBorder"]
> ![Symbol podsumowania](media/data-manager-entities-summary.png "Tabela podsumowania danych")

### <a name="next-step"></a>Następny krok

Zobacz temat [Ujednolicanie](data-unification.md), aby dowiedzieć się jak *mapować*, *dopasowywać* i *scalić* pobrane dane.


[!INCLUDE[footer-include](../includes/footer-banner.md)]