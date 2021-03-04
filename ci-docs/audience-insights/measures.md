---
title: Tworzenie miar i zarządzanie nimi
description: Zdefiniuj miary do analizy i odzwierciedlenia wyników Twojej firmy.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269941"
---
# <a name="define-and-manage-measures"></a>Definiowanie miar i zarządzanie nimi

Miary pomagają lepiej zrozumieć zachowania klientów i wyniki biznesowe poprzez pobieranie odpowiednich wartości z [ujednoliconych profili](data-unification.md). Na przykład firma chce zobaczyć *łączne wydatki na klienta*, aby poznać historię zakupów poszczególnych klientów. Lub zmierz *całkowitą sprzedaż firmy*, aby poznać łączne przychody z całej firmy.  

Miary są tworzone za pomocą konstruktora miar, platformy zapytań o dane z różnymi operatorami i prostymi opcjami mapowania. Umożliwia filtrowanie danych, grupowanie wyników, wykrywanie [ścieżek relacji między encjami](relationships.md) i wyświetlanie podglądu danych wyjściowych.

Użyj konstruktora miar, aby zaplanować działania biznesowe, wykonując zapytania dotyczące danych klientów i wyodrębniając szczegółowe informacje. Na przykład utworzenie miary *całkowitych wydatków na klienta* i *całkowitego zwrotu na klienta* pomaga zidentyfikować grupę klientów z wysokimi wydatkami, ale z wysokim zwrotem. Możesz utworzyć [segment](segments.md), aby stworzyć najlepsze akcje. 

## <a name="create-a-measure"></a>Utwórz miarę

W tej sekcji otworzymy nową miarę od podstaw. Możesz zbudować miarę z atrybutami danych z jednostek danych, które mają skonfigurowaną relację do łączenia się z encją Klient. 

1. W analizach odbiorców przejdź do **Miary**.

1. Wybierz **Nowy**.

1. Wybierz opcję **Edytuj** nazwę i podaj **Nazwa** miary. 
   > [!NOTE]
   > Jeśli nowa konfiguracja miary ma tylko dwa pola, na przykład IDklienta i jedno obliczenie, dane wyjściowe zostaną dodane jako nowa kolumna do jednostki wygenerowanej przez system o nazwie Customer_Measure. Będziesz mógł zobaczyć wartość miary w ujednoliconym profilu klienta. Inne miary będą generować własne encje.

1. W obszarze konfiguracji wybierz funkcję agregowania z menu rozwijanego **Wybierz funkcję**. Funkcje agregowania obejmują: 
   - **Sum**
   - **Średnia**
   - **Licznik**
   - **Liczba unikatowych**
   - **Maksimum**
   - **Min**
   - **Pierwszy**: pobiera pierwszą wartość rekordu danych
   - **Ostatnia**: pobiera ostatnią wartość dodaną do rekordu danych

   :::image type="content" source="media/measure-operators.png" alt-text="Operatory do oceny obliczeń.":::

1. Wybierz **Dodaj atrybut**, aby wybrać dane potrzebne do utworzenia tej miary.
   
   1. Wybrane kartę **Atrybuty**. 
   1. Encja danych: wybierz encję zawierającą atrybut, który chcesz zmierzyć. 
   1. Atrybut danych: wybierz atrybut, którego chcesz użyć w funkcji agregowania, aby obliczyć miarę. Możesz wybrać tylko jeden atrybut naraz.
   1. Atrybut danych można także wybrać z istniejącej miary, wybierając kartę **Miary**. Można także wyszukać nazwę encji lub miary. 
   1. Wybierz opcję **Dodaj**, aby dodać do miary wybrany atrybut.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Wybierz atrybut, który ma być używany w obliczeniach.":::

1. Aby zbudować bardziej złożone miary, możesz dodać więcej atrybutów lub użyć operatorów matematycznych w funkcji miary.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Utwórz złożoną miarę za pomocą operatorów matematycznych.":::

1. Aby dodać filtry, wybierz **Filtr** w obszarze konfiguracji. 
  
   1. W sekcji **Dodawanie atrybutu** w okienku **Filtry** wybierz atrybut, którego chcesz użyć do tworzenia filtrów.
   1. Ustaw operatory filtru, aby zdefiniować filtr dla każdego wybranego atrybutu.
   1. Wybierz opcję **Zastosuj**, aby dodać do miary wybrany filtr.

1. Aby dodać wymiary, wybierz **Wymiar** w obszarze konfiguracji. Wymiary będą wyświetlane jako kolumny w encji wyjściowej miary.
   1. Wybierz opcję **Edytuj rozmiary**, aby dodać atrybuty danych, według których chcesz grupować wartości miary. Na przykład miasto lub płeć. Domyślnie wymiar *CustomerID* jest wybrany do tworzenia *miar na poziomie klienta*. Do utworzenia *miar na poziomie firmy* można usunąć rozmiar domyślny.
   1. Wybierz opcję **Gotowe**, aby dodać do miary wybrany wymiar.

1. Jeśli istnieje wiele ścieżek między zmapowaną jednostką danych a jednostką Klient, musisz wybrać jedną ze zidentyfikowanych [ścieżek relacji między encjam](relationships.md). Wyniki mogą się różnić w zależności od wybranej ścieżki.
   1. Wybierz **preferencje dotyczące danych** i wybierz ścieżkę encji, która powinna być używana do identyfikacji miary.
   1. Wybierz opcję **Gotowe**, aby zastosować wybór. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Wybierz ścieżkę jednostki dla miary.":::

1. Aby dodać więcej obliczeń dla miary, wybierz opcję **Nowe obliczenia**. Do nowych obliczeń można używać tylko elementów znajdujących się na tej samej ścieżce encji. Więcej obliczeń zostanie wyświetlonych jako nowe kolumny w jednostce wyniku pomiaru.

1. Wybierz opcję **...** w obliczeniach jako **Duplikat**, **Zmień nazwę** lub **Usuń** obliczenia z miary.

1. W obszarze **Podgląd** jest wyświetlony schemat danych encji wyjściowej miary wraz z filtrami i rozmiarami. Podgląd jest dynamicznie reaktywny na zmiany w konfiguracji.

1. Wybierz opcję **Uruchom**, aby obliczyć wyniki dla skonfigurowanej miary. Wybierz opcję **Zapisz i zamknij**, jeśli chcesz zachować bieżącą konfigurację i uruchomić miarę później.

1. Wybierz **Miary**, aby zobaczyć nowo utworzoną miarę na liście.

## <a name="manage-your-measures"></a>Zarządzanie miarami

Po [utworzeniu jednej miary](#create-a-measure) zostanie wyświetlona lista miar na stronie **Miary**.

Znajdziesz informacje o rodzaju miary, twórcy, dacie utworzenia, stanie i stanie. Po wybraniu miary z listy można wyświetlić podgląd wyniku i pobrać plik .CSV.

Aby odświeżyć wszystkie miary w tym samym czasie, wybierz **Odśwież wszystko** bez wybierania określonej miary.

> [!div class="mx-imgBorder"]
> ![Akcje służące do zarządzania pojedynczymi miarami](media/measure-actions.png "Akcje służące do zarządzania pojedynczymi miarami")

Wybierz z listy miarę dla następujących opcji:

- Wybierz nazwę miary, aby wyświetlić jej szczegóły.
- **Edytuj** konfigurację miary.
- **Odśwież** miarę na podstawie najnowszych danych.
- **Zmień nazwę** miary.
- **Usuń** miarę.
- **Aktywuj** lub **Dezaktywuj**. Nieaktywne miary nie będą odświeżane podczas [zaplanowanego odświeżania](system.md#schedule-tab).

> [!TIP]
> Istnieje [sześć typów stanu](system.md#status-types) zadań/procesów. Ponadto większość procesów [zależy od innych procesów podrzędnych](system.md#refresh-policies). Istnieje możliwość wybrania stanu procesu w celu wyświetlenia szczegółowych informacji o postępie w całym zadaniu. Po wybraniu opcji **Zobacz szczegółowe informacje** dla jednego z zadań zadania, można znaleźć więcej informacji: czas przetwarzania, Data ostatniego przetwarzania oraz wszystkie błędy i ostrzeżenia skojarzone z zadaniem.

## <a name="next-step"></a>Następny krok

Zastosowanie istniejących miar umożliwia utworzenie [segmentu klienta](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]