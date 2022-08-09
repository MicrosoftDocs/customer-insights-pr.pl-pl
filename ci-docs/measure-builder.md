---
title: Tworzenie miar przy użyciu konstruktora miar
description: Tworzenie miar od podstaw w celu przeanalizowania kluczowych metryk dotyczących działalności.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: fac00b8a1b4ca6e09dd29abe46dfe240adcc029e
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170875"
---
# <a name="create-measures-with-measure-builder"></a>Tworzenie miar przy użyciu konstruktora miar

Konstruktor miar umożliwia definiowanie obliczeń przy użyciu operatorów, funkcji agregacji i filtrów. Zdefiniuj miary za pomocą atrybutów z jednostek, które są powiązane z ujednoliconą jednostką *Klient*.

Tworzenie miar w środowiskach B2C i B2B działa tak samo. Jeśli jednak w środowisku B2B są [używane konta z hierarchiami](relationships.md#set-up-account-hierarchies), można agregować miarę dla powiązanych kont podległych.

# <a name="individual-consumers-b-to-c"></a>[Klienci indywidualni (B2C)](#tab/b2c)

Miary można tworzyć na poziomie poszczególnych klientów (atrybut klienta, miara klienta) lub na poziomie jednostki biznesowej/organizacji (miara biznesowa). Atrybut klienta i miara klienta umożliwiają śledzenie wydajności na klienta. Może to być na przykład łączna kwota wydawana przez każdego klienta. Miary biznesowe śledzą wydajność na firmę. Na przykład łączny przychód według firmy.

- Atrybut klienta: generuje dane wyjściowe jako nowy atrybut, który jest zapisywany jako nowa kolumna w encji wygenerowanej przez system o nazwie *Customer_Measure*. Podczas odświeżania atrybutu klienta wszystkie inne atrybuty klienta w encji *Customer_Measure* także są równocześnie odświeżane. Ponadto atrybuty klienta są wyświetlane na karcie profilu klienta. Po uruchomieniu lub zapisaniu nie można zmienić atrybutu klienta na miarę klienta.

- Miara klienta: generuje dane wyjściowe jako własną encję i nie można zmienić jej na atrybut klienta po jej uruchomieniu lub zapisaniu. Miary klienta nie są wyświetlane w karcie profilu klienta.

- Miara biznesowa: generuje dane wyjściowe jako własną encję i wyświetla na stronie głównej środowiska Customer Insights.

1. Przejdź do **Miar**.

1. Wybierz opcję **Nowy** > **Utwórz własne**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Pusty ekran konfiguracji dla miary B2C. " lightbox="media/measure-b2c.png":::

1. Wybierz **Edytuj szczegóły** obok działania bez tytułu. Podaj nazwę miary. Opcjonalnie dodaj [etykiety](work-with-tags-columns.md#manage-tags) do miary.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Okno dialogowe Edytuj szczegóły.":::

1. Wybierz pozycję **Gotowe**.

1. Aby śledzić wyniki na poziomie biznesowym, przełącz **Typ pomiaru** na **Poziom biznesowy**. Domyślnie wybrany jest **Poziom klienta**. Poziom **Klient** automatycznie dodaje atrybut *CustomerId* do wymiarów, a **poziom firmowy** automatycznie go usuwa.

1. W obszarze konfiguracji wybierz funkcję agregowania z menu rozwijanego **Wybierz funkcję**. Funkcje agregowania obejmują:
   - **Sum**
   - **Średnia**
   - **Licznik**
   - **Liczba unikatowych**
   - **Maksimum**
   - **Min**
   - **Pierwszy**: pobiera pierwszą wartość rekordu danych
   - **Ostatnia**: pobiera ostatnią wartość dodaną do rekordu danych
   - **ArgMax**: znajduje rekord danych podając maksymalną wartość z funkcji docelowej
   - **ArgMin**: znajduje rekord danych podając minimalną wartość z funkcji docelowej

1. Wybierz **Dodaj atrybut**, aby wybrać dane potrzebne do utworzenia tej miary.

   1. Wybrane kartę **Atrybuty**.
   1. Encja danych: wybierz encję zawierającą atrybut, który chcesz zmierzyć.
   1. Atrybut danych: wybierz atrybut, którego chcesz użyć w funkcji agregowania, aby obliczyć miarę. Możesz wybrać tylko jeden atrybut naraz.
   1. Atrybut danych można także wybrać z istniejącej miary, wybierając kartę **Miary** lub można także wyszukać nazwę encji lub miary.
   1. Wybierz **Dodaj**.

1. Aby zbudować bardziej złożone miary, możesz dodać więcej atrybutów lub użyć operatorów matematycznych w funkcji miary.

1. Aby dodać filtry, wybierz **Filtr** w obszarze konfiguracji. Stosowanie filtrów będzie używać tylko rekordów, które pasują do filtrów w celu obliczania miary.
  
   1. W sekcji **Dodawanie atrybutu** okienka **Filtry** wybierz atrybut, którego chcesz użyć do tworzenia filtrów.
   1. Ustaw operatory filtru, aby zdefiniować filtr dla każdego wybranego atrybutu.
   1. Wybierz **Zastosuj**.

1. Wybierz opcję **Rozmiar**, aby wybrać więcej pól, które zostaną dodane jako kolumny do encji wyjściowej miary.

   1. Wybierz opcję **Edytuj rozmiary**, aby dodać atrybuty danych, według których chcesz grupować wartości miary. Na przykład miasto lub płeć.
      > [!TIP]
      > Jeśli jako **typ miary** wybrano **Poziom klienta**, atrybut *CustomerId* jest już dodany. Jeśli usuniesz ten atrybut, **Typ miary** zmieni się na **Poziom biznesowy**.
   1. Wybierz pozycję **Gotowe**.

1. Jeśli w danych znajdują się wartości, które trzeba zastąpić liczbą całkowitą, wybierz opcję **Regułę**. Skonfiguruj regułę i upewnij się, że jako zamienniki wybierane są tylko liczby całkowite. Na przykład zastąp wartość *null* wartością *0*.

1. Jeśli istnieje wiele ścieżek między mapowaną encją danych a encją *Klient*, musisz wybrać jedną ze zidentyfikowanych [ścieżek relacji między encjami](relationships.md). Wyniki mogą się różnić w zależności od wybranej ścieżki.

   1. Wybierz **ścieżkę relacji** i wybierz ścieżkę encji, która powinna być używana do identyfikacji miary. Jeśli do encji *Klient* jest dostępna tylko jedna ścieżka, ta kontrolka nie będzie wyświetlana.
   1. Wybierz pozycję **Gotowe**.

1. Aby dodać więcej obliczeń dla miary, wybierz opcję **Nowe obliczenia**. Do nowych obliczeń można używać tylko elementów znajdujących się na tej samej ścieżce encji. Więcej obliczeń zostanie wyświetlonych jako nowe kolumny w jednostce wyniku pomiaru. Opcjonalnie wybierz opcję **Edytuj nazwę**, aby utworzyć nazwę obliczania.

1. Wybierz wielokropek pionowy (&vellip;) w obliczeniach jako **Duplikat** lub **Usuń** obliczenia z miary.

1. W obszarze **Podgląd** jest wyświetlony schemat danych encji wyjściowej miary wraz z filtrami i rozmiarami. Podgląd jest dynamicznie reaktywny na zmiany w konfiguracji.

1. Wybierz opcję **Uruchom**, aby obliczyć wyniki dla skonfigurowanej miary. Wybierz opcję **Zapisz i zamknij**, jeśli chcesz zachować bieżącą konfigurację i uruchomić miarę później. Wyświetla się strona **Miary**.

# <a name="business-accounts-b-to-b"></a>[Klienci biznesowi (B2B)](#tab/b2b)

Miary można tworzyć na poziomie poszczególnych kont (atrybut klienta, miara klienta) lub na poziomie wszystkich kont (miara biznesowa).

- Miara klienta: generuje dane wyjściowe jako własną encję. Miary klienta nie są wyświetlane w karcie profilu klienta.

- Miara biznesowa: generuje dane wyjściowe jako własną encję i wyświetla na stronie głównej środowiska Customer Insights.

1. Przejdź do **Miar**.

1. Wybierz **Nowy**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Pusty ekran konfiguracji dla miary B2B. ":::

1. Wybierz **Edytuj szczegóły** obok działania bez tytułu. Podaj nazwę miary. Opcjonalnie dodaj [etykiety](work-with-tags-columns.md#manage-tags) do miary. 
   :::image type="content" source="media/measures_edit_details.png" alt-text="Okno dialogowe Edytuj szczegóły.":::

1. Wybierz pozycję **Gotowe**.

1. W obszarze konfiguracji wybierz funkcję agregowania z menu rozwijanego **Wybierz funkcję**. Funkcje agregowania obejmują:
   - **Sum**
   - **Średnia**
   - **Licznik**
   - **Liczba unikatowych**
   - **Maksimum**
   - **Min**
   - **Pierwszy**: pobiera pierwszą wartość rekordu danych
   - **Ostatnia**: pobiera ostatnią wartość dodaną do rekordu danych

1. Wybierz **Dodaj atrybut**, aby wybrać dane potrzebne do utworzenia tej miary.

   1. Wybrane kartę **Atrybuty**.
   1. Encja danych: wybierz encję zawierającą atrybut, który chcesz zmierzyć.
   1. Atrybut danych: wybierz atrybut, którego chcesz użyć w funkcji agregowania, aby obliczyć miarę. Możesz wybrać tylko jeden atrybut naraz.
   1. Atrybut danych można także wybrać z istniejącej miary, wybierając kartę **Miary** lub można także wyszukać nazwę encji lub miary.
   1. Wybierz opcję **Dodaj**, aby dodać do miary wybrany atrybut.

1. Aby zbudować bardziej złożone miary, możesz dodać więcej atrybutów lub użyć operatorów matematycznych w funkcji miary.

1. Aby dodać filtry, wybierz **Filtr** w obszarze konfiguracji. Stosowanie filtrów będzie używać tylko rekordów, które pasują do filtrów w celu obliczania miary.
  
   1. W sekcji **Dodawanie atrybutu** okienka **Filtry** wybierz atrybut, którego chcesz użyć do tworzenia filtrów.
   1. Ustaw operatory filtru, aby zdefiniować filtr dla każdego wybranego atrybutu.
   1. Wybierz opcję **Zastosuj**, aby dodać do miary wybrany filtr.

1. Wybierz opcję **Rozmiar**, aby wybrać więcej pól, które zostaną dodane jako kolumny do encji wyjściowej miary.

   1. Wybierz opcję **Edytuj rozmiary**, aby dodać atrybuty danych, według których chcesz grupować wartości miary. Na przykład miasto lub płeć.
      > [!TIP]
      > Atrybut *CustomerId* został już dodany, wskazując, że jest to typ miary na poziomie klienta. Jeśli usuniesz atrybut, typ miary zmieni się na poziom biznesowy.
   1. Wybierz opcję **Gotowe**, aby dodać do miary wybrany wymiar.

1. Jeśli w danych znajdują się wartości, które trzeba zastąpić liczbą całkowitą, wybierz opcję **Regułę**. Skonfiguruj regułę i upewnij się, że jako zamienniki wybierane są tylko liczby całkowite. Na przykład zastąp wartość *null* wartością *0*.

1. Jeśli [używasz kont z hierarchiami](relationships.md#set-up-account-hierarchies), przejrzyj **Zwiń subkonta**.
   - Jeśli ustawiono wartość **Wył.**, miara jest obliczana dla każdego klienta. Każdy klient ma własny wynik.
   - Jeśli ustawiono wartość **Wł.**, wybierz opcję **Edytuj**, aby wybrać hierarchię klientów według pozyskanych hierarchii. Miara daje tylko jeden wynik, ponieważ jest agregowana przy użyciu klientów podrzędnych.

1. Jeśli istnieje wiele ścieżek między mapowaną encją danych a encją *Klient*, musisz wybrać jedną ze zidentyfikowanych [ścieżek relacji między encjami](relationships.md). Wyniki mogą się różnić w zależności od wybranej ścieżki.

   1. Wybierz **ścieżkę relacji** i wybierz ścieżkę encji, która powinna być używana do identyfikacji miary. Jeśli do encji *Klient* jest dostępna tylko jedna ścieżka, ta kontrolka nie będzie wyświetlana.
   1. Wybierz opcję **Gotowe**, aby zastosować wybór.

1. Wybierz wielokropek pionowy (&vellip;) w obliczeniach jako **Duplikat** lub **Usuń** obliczenia z miary.

1. W obszarze **Podgląd** jest wyświetlony schemat danych encji wyjściowej miary wraz z filtrami i rozmiarami. Podgląd jest dynamicznie reaktywny na zmiany w konfiguracji.

1. Wybierz opcję **Uruchom**, aby obliczyć wyniki dla skonfigurowanej miary. Wybierz opcję **Zapisz i zamknij**, jeśli chcesz zachować bieżącą konfigurację i uruchomić miarę później. Wyświetla się strona **Miary**.

---

## <a name="next-step"></a>Następny krok

Istniejące miary można wykorzystać do utworzenia [segmentu klienta](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
