---
title: Tworzenie i edytowanie miar
description: Zdefiniowanie miar związanych z klientami w celu przeanalizowania i odzwierciedlenia wydajności pewnych obszarów biznesowych.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406591"
---
# <a name="define-and-manage-measures"></a>Definiowanie miar i zarządzanie nimi

**Miary** reprezentują kluczowe wskaźniki wydajności (KPI), które odzwierciedlają wydajność i kondycję poszczególnych obszarów biznesowych. Analiza odbiorców zapewnia intuicyjne środowisko tworzenia różnych typów miar za pomocą konstruktora zapytań, który nie wymaga ręcznego kodowania ani sprawdzania poprawności miar. Miary biznesowe można śledzić na **stronie głównej**, zobaczyć miary dotyczące określonych klientów w **Karcie klienta**, a następnie użyć miar w celu zdefiniowania segmentów klientów na stronie **Segmenty**.

## <a name="create-a-measure"></a>Utwórz miarę

Niniejsza sekcja zawiera instrukcje dotyczące tworzenia miary od podstaw. Miarą można zbudować na podstawie danych z wielu źródeł danych połączonych za pośrednictwem encji klienta. Niektóre [ograniczenia dotyczące usług](service-limits.md) mają zastosowanie.

1. W analizach odbiorców przejdź do **Miary**.

2. Wybierz opcję **Nowa miara**.

3. Wybierz **typ** miary:

   - **Atrybut klienta**: jedno pole na klienta, które odzwierciedla wyniki, wartość lub stan dla klienta. Atrybuty klienta są tworzone jako atrybuty w nowym obiekcie wygenerowanym przez system o nazwie **Customer_Measure**.

   - **Miara klienta**: wgląd w informacje dotyczące zachowania klienta z podziałem według wybranych wymiarów. Dla każdej miary zostanie wygenerowana nowa encja, prawdopodobnie z wieloma rekordami na klienta.

   - **Miary biznesowe**: pozwala śledzić wyniki działalności i kondycję prowadzonej działalności. Miary biznesowe mogą mieć dwie różne wyjścia: liczbowe wyniki, które są wyświetlane na **stronie głównej** lub w nowej encji, która znajduje się na stronie **Encje** .

4. Wpisz **nazwę** i opcjonalnie **wyświetlaną nazwę**, a następnie wybierz **Dalej**.

5. W sekcji **Encje** wybierz pierwszą encję z listy rozwijanej. W tym momencie należy określić, czy w ramach definicji miary są potrzebne dodatkowe encje.

   > [!div class="mx-imgBorder"]
   > ![Definicja miary](media/measure-definition.png "Definicja miary")

   Aby dodać więcej encji, wybierz pozycję **Dodaj encję** i wybierz encje, które mają być używane dla miary.

   > [!NOTE]
   > Możesz wybrać tylko encje, które mają powiązania z encją początkową. Aby uzyskać więcej informacji dotyczących definiowania relacji, zobacz [Relacje](relationships.md).

6. Opcjonalnie można skonfigurować zmienne. W sekcji **Zmienne** wybierz pozycję **Nowa zmienna**.

   Zmienne są obliczeniami dokonywanymi w poszczególnych zaznaczonych rekordach. Na przykład: sumowanie punktów sprzedaży (POS) i sprzedaży online w przypadku poszczególnych rekordów klientów.

7. W polu **Nazwa** podaj nazwę zmiennej.

8. W obszarze **Wyrażenia** wybierz pole, od którego chcesz rozpocząć obliczenia.

9. Umożliwia wpisanie wyrażenia w obszarze **Wyrażenia** podczas wybierania większej liczby pól, które mają zostać uwzględnione w obliczeniu.

   > [!NOTE]
   > Obecnie obsługiwane są tylko wyrażenia arytmetyczne. Ponadto, obliczanie zmiennych nie jest obsługiwane w przypadku encjipochodzących z różnych [ścieżek encji](relationships.md).

10. Wybierz **Gotowe**.

11. W sekcji **Definicja miary** zdefiniujesz, jak wybrane encje i obliczane zmienne są agregowane w nowych encjach lub atrybutach miary.

12. Wybierz **Nowy wymiar**. Wymiar może być postrzegany jako funkcja *Grupuj według*. Dane wyjściowe encji lub atrybutu miary zostaną pogrupowane według wszystkich zdefiniowanych wymiarów.

    > [!div class="mx-imgBorder"]
    > ![Wybieranie cyklu agregacji](media/measures-businessreport-measure-definition2.png "Wybieranie cyklu agregacji")

    Wybierz lub wprowadź następujące informacje jako część definicji danego wymiaru:

    - **Encja**: po zdefiniowaniu miary encji powinna ona zawierać co najmniej jeden atrybut. W przypadku zdefiniowania atrybutu miary będzie w nim domyślnie uwzględniony tylko jeden atrybut. Ta opcja służy do wybierania encji zawierającej dany atrybut.
    - **Pole**: wybierz konkretny atrybut, który ma zostać uwzględniony w encji lub atrybucie miary.
    - **Zasobnik**: należy wybrać, czy dane mają być agregowane codzienne, comiesięczne czy roczne. Jest to wymagane tylko w przypadku wybrania atrybutu typu Data.
    - **Jako**: definiuje nazwę nowego pola.
    - **Wyświetlana nazwa**: definiuje wyświetlaną nazwę pola.

    > [!NOTE]
    > Miara biznesowa zostanie zapisana jako encja z jednym numerem i będzie widoczna na **stronie głównej**, chyba że dodasz więcej wymiarów do miary. Po dodaniu dodatkowych wymiarów miara *nie* zostanie wyświetlona na **stronie głównej**.

13. Opcjonalnie dodaj funkcje agregowania. Każda utworzona wartość zagregowana powoduje utworzenie nowej wartości w encji lub atrybucie miary. Obsługiwane są następujące funkcje agregujące: **Min.**, **Max.**, **Średnia**, **Mediana**, **Suma**, **Liczba unikatowych**, **Pierwsze** (pobiera pierwszy rekord wartości wymiaru) i **ostatnia** (pobiera ostatni rekord dodany do wartości wymiaru).

14. Wybierz pozycję **Zapisz**, aby zapisać zmiany wprowadzone w miarze.

## <a name="manage-your-measures"></a>Zarządzanie miarami

Po utworzeniu co najmniej jednej miary zostanie wyświetlona lista miar na stronie **Miary**.

Znajdują się na niej informacje o typie miary, autorze, dacie i godzinie utworzenia, daty i godziny ostatniej edycji, stanie (bez względu na to, czy miara jest aktywna, nieaktywna lub błędna) oraz data i godzina ostatniego odświeżenia. Po wybraniu miary z listy można wyświetlić podgląd jej wyników.

Aby odświeżyć wszystkie miary w tym samym czasie, wybierz **Odśwież wszystko** bez wybierania określonej miary.

> [!div class="mx-imgBorder"]
> ![Akcje służące do zarządzania pojedynczymi miarami](media/measure-actions.png "Akcje służące do zarządzania pojedynczymi miarami")

Można też wybrać miarę z listy, a następnie wykonać jedną z następujących czynności:

- Wybierz nazwę miary, aby wyświetlić jej szczegóły.
- **Edytuj** konfigurację miary.
- **Zmień nazwę** miary.
- **Usuń** miarę.
- Wybierz wielokropek (...), a następnie **Odśwież**, aby rozpocząć proces odświeżania miary.
- Wybierz wielokropek (...), a następnie **Pobierz**, aby uzyskać plik .CSV miary.

> [!TIP]
> Istnieje [sześć typów stanu](system.md#status-types) zadań/procesów. Ponadto większość procesów [zależy od innych procesów podrzędnych](system.md#refresh-policies). Istnieje możliwość wybrania stanu procesu w celu wyświetlenia szczegółowych informacji o postępie w całym zadaniu. Po wybraniu opcji **Zobacz szczegółowe informacje** dla jednego z zadań zadania, można znaleźć więcej informacji: czas przetwarzania, Data ostatniego przetwarzania oraz wszystkie błędy i ostrzeżenia skojarzone z zadaniem.

## <a name="next-step"></a>Następny krok

W tym celu należy skorzystać z istniejących miar w celu utworzenia pierwszego segmentu klienta na stronie **Segmenty**. Aby uzyskać więcej informacji, zobacz [Segmenty](segments.md).
