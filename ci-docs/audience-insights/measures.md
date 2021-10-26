---
title: Tworzenie miar i zarządzanie nimi
description: Zdefiniuj miary do analizy i odzwierciedlenia wyników Twojej firmy.
ms.date: 09/30/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 39acca78c022bc15ebc15dc80f21fe175da04d4d
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/11/2021
ms.locfileid: "7622983"
---
# <a name="define-and-manage-measures"></a>Definiowanie miar i zarządzanie nimi

Miary pomagają lepiej poznać zachowania klientów i wydajność biznesową. Analizują one odpowiednie wartości z [ujednoliconych profilów](data-unification.md). Na przykład, firma chce zobaczyć *całkowite wydatki na klienta*, aby zrozumieć historię zakupów poszczególnych klientów lub zmierzyć *całkowitą sprzedaż firmy*, aby zrozumieć zagregowany poziom przychodów w całej firmie.  

Miary są tworzone za pomocą konstruktora miar, platformy zapytań o dane z różnymi operatorami i prostymi opcjami mapowania. Umożliwia filtrowanie danych, grupowanie wyników, wykrywanie [ścieżek relacji między encjami](relationships.md) i wyświetlanie podglądu danych wyjściowych.

Użyj konstruktora miar, aby zaplanować działania biznesowe, wykonując zapytania dotyczące danych klientów i wyodrębniając szczegółowe informacje. Na przykład utworzenie miary *całkowitych wydatków na klienta* i *całkowitego zwrotu na klienta* pomaga zidentyfikować grupę klientów z wysokimi wydatkami, ale z wysokim zwrotem. Możesz utworzyć [segment](segments.md), aby stworzyć najlepsze akcje. 

## <a name="build-your-own-measure-from-scratch"></a>Utwórz własną miarę od podstaw

W tej sekcji otworzymy nową miarę od podstaw. Można utworzyć miarę z atrybutami danych z encji danych, które mają relację ustawioną w celu połączenia z encją ujednoliconego profilu klienta.

# <a name="individual-customers-b2c"></a>[Klienci indywidualni (B2C)](#tab/b2c)

1. W analizach odbiorców przejdź do **Miary**.

1. Wybierz opcję **Nowa** i wybierz pozycję **Utwórz własną**.

1. Wybierz opcję **Edytuj** nazwę i podaj **Nazwa** miary. 

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
   1. Atrybut danych można także wybrać z istniejącej miary, wybierając kartę **Miary** lub można także wyszukać nazwę encji lub miary. 
   1. Wybierz opcję **Dodaj**, aby dodać do miary wybrany atrybut.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Wybierz atrybut, który ma być używany w obliczeniach.":::

1. Aby zbudować bardziej złożone miary, możesz dodać więcej atrybutów lub użyć operatorów matematycznych w funkcji miary.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Utwórz złożoną miarę za pomocą operatorów matematycznych.":::

1. Aby dodać filtry, wybierz **Filtr** w obszarze konfiguracji. 
  
   1. W sekcji **Dodawanie atrybutu** okienka **Filtry** wybierz atrybut, którego chcesz użyć do tworzenia filtrów.
   1. Ustaw operatory filtru, aby zdefiniować filtr dla każdego wybranego atrybutu.
   1. Wybierz opcję **Zastosuj**, aby dodać do miary wybrany filtr.

1. Aby dodać wymiary, wybierz **Wymiar** w obszarze konfiguracji. Wymiary będą wyświetlane jako kolumny w encji wyjściowej miary.
 
   1. Wybierz opcję **Edytuj rozmiary**, aby dodać atrybuty danych, według których chcesz grupować wartości miary. Na przykład miasto lub płeć. Domyślnie wymiar *CustomerID* jest wybrany do tworzenia *miar na poziomie klienta*. Do utworzenia *miar na poziomie firmy* można usunąć rozmiar domyślny.
   1. Wybierz opcję **Gotowe**, aby dodać do miary wybrany wymiar.

1. Jeśli w danych znajdują się wartości, które trzeba zastąpić liczbą całkowitą, wybierz opcję **Regułę**. Skonfiguruj regułę i upewnij się, że jako zamienniki wybierane są tylko liczby całkowite. Na przykład zastąp wartość *null* wartością *0*.

1. Jeśli istnieje wiele ścieżek między mapowaną encją danych a encją *Klient*, musisz wybrać jedną ze zidentyfikowanych [ścieżek relacji między encjami](relationships.md). Wyniki mogą się różnić w zależności od wybranej ścieżki. 
   
   1. Wybierz **ścieżkę relacji** i wybierz ścieżkę encji, która powinna być używana do identyfikacji miary. Jeśli do encji *Klient* jest dostępna tylko jedna ścieżka, ta kontrolka nie będzie wyświetlana.
   1. Wybierz opcję **Gotowe**, aby zastosować wybór. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Wybierz ścieżkę jednostki dla miary.":::

1. Aby dodać więcej obliczeń dla miary, wybierz opcję **Nowe obliczenia**. Do nowych obliczeń można używać tylko elementów znajdujących się na tej samej ścieżce encji. Więcej obliczeń zostanie wyświetlonych jako nowe kolumny w jednostce wyniku pomiaru.

1. Wybierz opcję **...** w obliczeniach jako **Duplikat**, **Zmień nazwę** lub **Usuń** obliczenia z miary.

1. W obszarze **Podgląd** jest wyświetlony schemat danych encji wyjściowej miary wraz z filtrami i rozmiarami. Podgląd jest dynamicznie reaktywny na zmiany w konfiguracji.

1. Wybierz opcję **Uruchom**, aby obliczyć wyniki dla skonfigurowanej miary. Wybierz opcję **Zapisz i zamknij**, jeśli chcesz zachować bieżącą konfigurację i uruchomić miarę później.

1. Wybierz **Miary**, aby zobaczyć nowo utworzoną miarę na liście.

# <a name="business-accounts-b2b"></a>[Klienci biznesowi (B2B)](#tab/b2b)

1. W analizach odbiorców przejdź do **Miary**.

1. Wybierz opcję **Nowa** i wybierz pozycję **Utwórz własną**.

1. Wybierz opcję **Edytuj** nazwę i podaj **Nazwa** miary. 

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
   1. Atrybut danych można także wybrać z istniejącej miary, wybierając kartę **Miary** lub można także wyszukać nazwę encji lub miary. 
   1. Wybierz opcję **Dodaj**, aby dodać do miary wybrany atrybut.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Wybierz atrybut, który ma być używany w obliczeniach.":::

1. Aby zbudować bardziej złożone miary, możesz dodać więcej atrybutów lub użyć operatorów matematycznych w funkcji miary.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Utwórz złożoną miarę za pomocą operatorów matematycznych.":::

1. Aby dodać filtry, wybierz **Filtr** w obszarze konfiguracji. 
  
   1. W sekcji **Dodawanie atrybutu** okienka **Filtry** wybierz atrybut, którego chcesz użyć do tworzenia filtrów.
   1. Ustaw operatory filtru, aby zdefiniować filtr dla każdego wybranego atrybutu.
   1. Wybierz opcję **Zastosuj**, aby dodać do miary wybrany filtr.

1. Aby dodać wymiary, wybierz **Wymiar** w obszarze konfiguracji. Wymiary będą wyświetlane jako kolumny w encji wyjściowej miary.
 
   1. Wybierz opcję **Edytuj rozmiary**, aby dodać atrybuty danych, według których chcesz grupować wartości miary. Na przykład miasto lub płeć. Domyślnie wymiar *CustomerID* jest wybrany do tworzenia *miar na poziomie klienta*. Do utworzenia *miar na poziomie firmy* można usunąć rozmiar domyślny.
   1. Wybierz opcję **Gotowe**, aby dodać do miary wybrany wymiar.

1. Jeśli w danych znajdują się wartości, które trzeba zastąpić liczbą całkowitą, wybierz opcję **Regułę**. Skonfiguruj regułę i upewnij się, że jako zamienniki wybierane są tylko liczby całkowite. Na przykład zastąp wartość *null* wartością *0*.

1. Można używać przełącznika **Zwiń wszystkich klientów podrzędnych**, jeśli [używasz klientów z hierarchiami](relationships.md#set-up-account-hierarchies).
   - Jeśli ustawiono wartość **Wył.**, miara jest obliczana dla każdego klienta. Każdy klient ma własny wynik.
   - Jeśli ustawiono wartość **Wł.**, wybierz opcję **Edytuj**, aby wybrać hierarchię klientów według pozyskanych hierarchii. Miara daje tylko jeden wynik, ponieważ jest agregowana przy użyciu klientów podrzędnych.

1. Jeśli istnieje wiele ścieżek między mapowaną encją danych a encją *Klient*, musisz wybrać jedną ze zidentyfikowanych [ścieżek relacji między encjami](relationships.md). Wyniki mogą się różnić w zależności od wybranej ścieżki. 
   
   1. Wybierz **ścieżkę relacji** i wybierz ścieżkę encji, która powinna być używana do identyfikacji miary. Jeśli do encji *Klient* jest dostępna tylko jedna ścieżka, ta kontrolka nie będzie wyświetlana.
   1. Wybierz opcję **Gotowe**, aby zastosować wybór. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Wybierz ścieżkę jednostki dla miary.":::

1. Wybierz opcję **...** w obliczeniach jako **Duplikat**, **Zmień nazwę** lub **Usuń** obliczenia z miary.

1. W obszarze **Podgląd** jest wyświetlony schemat danych encji wyjściowej miary wraz z filtrami i rozmiarami. Podgląd jest dynamicznie reaktywny na zmiany w konfiguracji.

1. Wybierz opcję **Uruchom**, aby obliczyć wyniki dla skonfigurowanej miary. Wybierz opcję **Zapisz i zamknij**, jeśli chcesz zachować bieżącą konfigurację i uruchomić miarę później.

1. Wybierz **Miary**, aby zobaczyć nowo utworzoną miarę na liście.

---

## <a name="use-a-template-to-build-a-measure"></a>Tworzenie miary za pomocą szablonu

Do ich utworzenia miar można użyć wstępnie zdefiniowanych szablonów najczęściej stosowanych miar. Szczegółowe opisy szablonów i działanie z przewodnikiem mogą ułatwić efektywne tworzenie miar. Szablony są budowane na podstawie zamapowanych danych z encji *Ujednolicone działanie*. Należy więc upewnić się, że skonfigurowano [działania klientów](activities.md) przed utworzeniem miary na podstawie szablonu.

# <a name="individual-customers-b2c"></a>[Klienci indywidualni (B2C)](#tab/b2c)

Do ich utworzenia miar można użyć wstępnie zdefiniowanych szablonów najczęściej stosowanych miar. Szczegółowe opisy szablonów i działanie z przewodnikiem mogą ułatwić efektywne tworzenie miar. Szablony są budowane na podstawie zamapowanych danych z encji *Ujednolicone działanie*. Należy więc upewnić się, że skonfigurowano [działania klientów](activities.md) przed utworzeniem miary na podstawie szablonu.

Dostępne szablony miar: 
- Średnia wartość transakcji (ATV)
- Łączna wartość transakcji
- Średni przychód dzienny
- Średni przychód roczny
- Liczba transakcji
- Zdobyte punkty lojalnościowe
- Zrealizowane punkty lojalnościowe
- Saldo punktów lojalnościowych
- Okres istnienia aktywnego klienta
- Czas trwania uczestnictwa w programie lojalnościowym
- Czas od ostatniego zakupu

W poniższej procedurze przedstawiono w zarysie kroki tworzenia nowej miary za pomocą szablonu.

1. W analizach odbiorców przejdź do **Miary**.

1. Wybierz **Nowy** i wybierz **Wybierz szablon**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Zrzut ekranu menu rozwijanego podczas tworzenia nowej miary z wyróżnieniem szablonu.":::

1. Znajdź szablon odpowiedni do potrzeb i wybierz opcję **Wybierz szablon**.

1. Przejrzyj wymagane dane i wybierz pozycję **Rozpocznij**, jeśli masz już wszystkie dane.

1. W okienku **Edycja nazwy** ustaw nazwę miary i encji wyjściowej. 

1. Wybierz pozycję **Gotowe**.

1. W sekcji **Ustawianie okresu czasu** zdefiniuj horyzont czasowy danych, które mają być użyte. Określ, czy nowa miara ma obejmować cały zestaw danych, wybierając opcję **Ogółem** lub jeśli chcesz skupić się na **określonym okresie**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Zrzut ekranu przedstawiający sekcję okresu podczas konfigurowania miary z szablonu.":::

1. W następnej sekcji wybierz pozycję **Dodaj dane**, aby wybrać działania i zmapować odpowiednie dane z encji *Ujednolicone działanie*.

    1. Krok 1 z 2: w obszarze **Typ działania** wybierz typ encji, której chcesz użyć. W przypadku **Działań** wybierz encje, które chcesz zamapować.
    1. Krok 2 z 2: wybierz atrybut z encji *Ujednolicone działanie* dla składnika wymaganego przez formułę. Na przykład w przypadku Średniej wartości transakcji jest to atrybut reprezentujący wartość Transakcji. W przypadku **Znacznika czasu działania** wybierz atrybut z encji Ujednolicone działanie reprezentujący datę i godzinę działania.
   
1. Po pomyślnym mapowaniu danych można zobaczyć stan jako **Zakończone** oraz nazwę zamapowanych działań i atrybutów.

   :::image type="content" source="media/measure-template-configured.png" alt-text="Zrzut ekranu przedstawiający zakończoną konfigurację szablonu miary.":::

1. Teraz można wybrać opcję **Uruchom**, aby obliczyć wyniki miary. Aby uściślić go później, wybierz opcję **Zapisz kopię roboczą**.

# <a name="business-accounts-b2b"></a>[Klienci biznesowi (B2B)](#tab/b2b)

Ta funkcja jest dostępna tylko dla działań utworzonych w środowiskach, w których klienci indywidualni są podstawowymi odbiorcami docelowymi.

---

## <a name="manage-your-measures"></a>Zarządzanie miarami

Listę miar można znaleźć na stronie **Miary**.

Znajdziesz informacje o rodzaju miary, twórcy, dacie utworzenia, stanie i stanie. Po wybraniu miary z listy można wyświetlić podgląd danych wyjściowych i pobrać plik CSV.

Aby odświeżyć wszystkie miary w tym samym czasie, wybierz **Odśwież wszystko** bez wybierania określonej miary.

> [!div class="mx-imgBorder"]
> ![Akcje służące do zarządzania pojedynczymi miarami.](media/measure-actions.png "Akcje służące do zarządzania pojedynczymi miarami.")

Wybierz z listy miarę dla następujących opcji:

- Wybierz nazwę miary, aby wyświetlić jej szczegóły.
- **Edytuj** konfigurację miary.
- **Odśwież** miarę na podstawie najnowszych danych.
- **Zmień nazwę** miary.
- **Usuń** miarę.
- **Aktywuj** lub **Dezaktywuj**. Nieaktywne miary nie będą odświeżane podczas [zaplanowanego odświeżania](system.md#schedule-tab).

> [!TIP]
> Istnieje [sześć typów stanu](system.md#status-types) zadań/procesów. Ponadto większość procesów [zależy od innych procesów podrzędnych](system.md#refresh-policies). Istnieje możliwość wybrania stanu procesu w celu wyświetlenia szczegółowych informacji o postępie w całym zadaniu. Po wybraniu opcji **Zobacz szczegóły** dla jednego z zadań, zobaczysz dodatkowe informacje: czas przetwarzania, data ostatniego przetwarzania i wszystkie błędy i ostrzeżenia związane z zadaniem.

## <a name="next-step"></a>Następny krok

Istniejące miary można wykorzystać do utworzenia [segmentu klienta](segments.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
