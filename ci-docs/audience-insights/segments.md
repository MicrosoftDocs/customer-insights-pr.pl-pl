---
title: Tworzenie segmentów i zarządzanie nimi
description: W celu pogrupowania klientów na podstawie różnych atrybutów można utworzyć ich segmenty.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: a1308f07ac3ba7d4b09931bab3d19b6dfaf479ee
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270369"
---
# <a name="create-and-manage-segments"></a>Tworzenie segmentów i zarządzanie nimi

Segmenty umożliwiają grupowanie klientów na podstawie atrybutów demograficznych, transakcyjnych i behawioralnych. W celu realizacji celów biznesowych można korzystać z segmentów w celu ukierunkowania kampanii promocyjnych, działań sprzedaży i akcji obsługi klienta.

Istnieje możliwość zdefiniowania złożonych filtrów wokół encji profil klienta i encji pokrewnych. Każdy segment, po przetworzeniu, tworzy zestaw rekordów klientów, który można eksportować i na którym można podejmować akcje. Niektóre [ograniczenia dotyczące usług](service-limits.md) mają zastosowanie.

O ile nie zaznaczono inaczej, wszystkie segmenty są **Segmentami dynamicznymi**, które są odświeżane w harmonogramie cyklicznym.

Poniższy przykład ilustruje możliwości segmentacji. Zdefiniowano segment dla klientów, którzy zamówili towary za przynajmniej 500 USD w ciągu ostatnich 90 dni *i* którzy uczestniczyli w rozmowie telefonicznej z obsługą klienta, która eskalowała.

> [!div class="mx-imgBorder"]
> ![Wiele grup](media/segmentation-group1-2.png "Wiele grup")

## <a name="create-a-new-segment"></a>Utwórz nowy segment

Segmenty są zarządzane na stronie **Segmenty**.

1. W analizach odbiorców przejdź do strony **Segmenty**.

2. Wybierz **Nowy** > **Pusty segment**.

3. W okienku **nowy segment** wybierz typ segmentu i podaj jego **nazwę**.

   Opcjonalnie można podać wyświetlaną nazwę i opis ułatwiający identyfikację segmentu.

4. Wybierz **Dalej**, aby połączyć się ze stroną **Konstruktor segmentu**, na której jest definiowana grupa. Grupa jest zbiorem klientów.

5. Wybierz encję zawierającą atrybut, według którego chcesz segmentować.

6. Wybierz atrybut, według którego ma zostać przeprowadzona segmentacja. Ten atrybut może mieć jeden z czterech typów wartości: numeryczny, ciąg, data lub wartość logiczna.

7. Wybierz operatora i wartość dla zaznaczonego atrybutu.

   > [!div class="mx-imgBorder"]
   > ![Niestandardowy filtr grup](media/customer-group-numbers.png "Filtr grupy klienta")

   |Numer |Definicja  |
   |---------|---------|
   |1     |Entity          |
   |2     |Atrybut          |
   |3    |Operator         |
   |100    |Wartość         |

8. Jeśli encja jest połączona z zunifikowaną encją klient za pośrednictwem [relacji](relationships.md), należy zdefiniować ścieżkę relacji, aby utworzyć prawidłowy segment. Dodaj encje ze ścieżki relacji, aż będzie można wybrać encję **Klient : CustomerInsights** z listy rozwijanej. Następnie wybierz **Wszystkie rekordy** dla każdego warunku.

   > [!div class="mx-imgBorder"]
   > ![Ścieżka relacji podczas tworzenia segmentu](media/segments-multiple-relationships.png "Ścieżka relacji podczas tworzenia segmentu")

9. Wybierz **Zapisz**, aby zapisać segment. Segment zostanie zapisany i przetworzony po sprawdzeniu poprawności wszystkich wymagań. W przeciwnym razie zostanie zapisany jako wersja robocza.

10. Wybierz **Wróć do segmentów**, aby wrócić do strony **Segmenty**.

## <a name="manage-existing-segments"></a>Zarządzanie istniejącymi segmentami

Na stronie **Segmenty** można wyświetlić wszystkie zapamiętane segmenty i zarządzać nimi.

Każdy segment jest reprezentowany przez wiersz zawierający dodatkowe informacje o segmencie.

Aby posortować segmenty w kolumnie, należy wybrać nagłówek kolumny.

Użyj pola **Wyszukaj**, które znajduje się w prawym górnym rogu, aby filtrować segmenty.

> [!div class="mx-imgBorder"]
> ![Opcje zarządzania istniejącym segmentem](media/segments-selected-segment.png "Opcje zarządzania istniejącym segmentem")

Po wybraniu segmentu są dostępne następujące akcje:

- **Wyświetlanie** szczegółowych informacji o segmencie, w tym trendu liczby członków podgląd składników segmentu.
- **Edytuj** segment, aby zmienić jego właściwości.
- **Odśwież** segment, aby uwzględnić najnowsze dane.
- **Aktywuj** lub **Dezaktywuj** segment. Segmenty mogą być w dwóch stanach — aktywnym lub nieaktywnym. Te stany są przydatne przy edytowaniu segmentu. W przypadku nieaktywnych segmentów definicja segmentu istnieje, ale nie zawiera jeszcze żadnych klientów. W przypadku aktywowania segmentu jego stan zmieni się z "nieaktywny" na "aktywny" i rozpocznie wyszukiwanie klientów zgodnych z definicją segmentu. Jeśli skonfigurowano [zaplanowane odświeżanie](system.md#schedule-tab), segment nieaktywne mają **Stan** wyświetlany jako **Pominięty**, co oznacza, że nie wystąpiła jeszcze próba odświeżenia. W przypadku aktywowania nieaktywnego segmentu zostanie on odświeżony i będzie uwzględniony w zaplanowanych odświeżeniach.
  Alternatywnie można użyć funkcji **Zaplanuj później** na liście rozwijanej **Aktywuj/Zdezaktywuj**, aby określić przyszłą datę i godzinę aktywacji i dezaktywacji konkretnego segmentu.
- **Zmień nazwę** segmentu.
- **Pobierz** listę członków jako plik .CSV.
- Opcja **Dodaj do** wysyła listę identyfikatorów klientów w segmencie w celu ich przetworzenia w innej aplikacji.
- **Usuń** segment.

## <a name="refresh-segments"></a>Odśwież segmenty

Można odświeżyć wszystkie segmenty naraz, wybierając **Odśwież wszystko** na stronie **Segmenty** lub odświeżyć jeden lub wiele segmentów po ich zaznaczeniu i wybraniu **Odśwież** z opcji. Alternatywnie można skonfigurować cykliczne odświeżanie w **Administracja** > **System** > **Harmonogram**.

> [!TIP]
> Istnieje [sześć typów stanu](system.md#status-types) zadań/procesów. Ponadto większość procesów [zależy od innych procesów podrzędnych](system.md#refresh-policies). Istnieje możliwość wybrania stanu procesu w celu wyświetlenia szczegółowych informacji o postępie w całym zadaniu. Po wybraniu opcji **Zobacz szczegółowe informacje** dla jednego z zadań zadania, można znaleźć więcej informacji: czas przetwarzania, Data ostatniego przetwarzania oraz wszystkie błędy i ostrzeżenia skojarzone z zadaniem.

## <a name="download-and-export-segments"></a>Pobieranie i eksportowanie segmentów

Segmenty można pobrać do pliku CSV lub wyeksportować je do Dynamics 365 Sales.

### <a name="download-segments-to-a-csv-file"></a>Pobierz segmenty do pliku CSV

1. W analizach odbiorców przejdź do strony **Segmenty**.

2. Wybierz wielokropek na kafelku konkretnego segmentu.

3. Z listy rozwijanej akcje wybierz polecenie **Pobierz jako CSV**.

### <a name="export-segments-to-dynamics-365-sales"></a>Eksportuj segmenty do Dynamics 365 Sales

Przed wyeksportowaniem segmentów do Dynamics 365 Sales, administrator musi [utworzyć miejsce docelowe eksportu](export-destinations.md) dla Dynamics 365 Sales.

1. W analizach odbiorców przejdź do strony **Segmenty**.

2. Wybierz wielokropek na kafelku konkretnego segmentu.

3. Z listy rozwijanej akcji wybierz **Dodaj do** i wybierz miejsce docelowe eksportu, do którego chcesz wysłać dane.

## <a name="draft-mode-for-segments"></a>Tryb roboczy dla segmentów

Jeśli nie wszystkie wymagania dotyczące przetwarzania segmentu są spełnione, można zapisać dany segment jako wersję roboczą i uzyskać do niego dostęp z poziomu strony **Segmenty**.

Zostanie on zapisany w nieaktywnym segmencie i nie będzie można go aktywować, dopóki nie będzie prawidłowy.

## <a name="add-more-conditions-to-a-group"></a>Dodawanie warunków do grupy

Aby dodać do grupy więcej warunków, można użyć dwóch operatorów logicznych:

- **AND** operator: oba warunki muszą być spełnione w procesie segmentacji. Ta opcja jest najbardziej przydatna podczas definiowania warunków między różnymi encjami.

- **OR** operator: jeden z warunków musi zostać osiągnięty jako część procesu segmentacji. Ta opcja jest najbardziej przydatna podczas definiowania wielu warunków dla tej samej encji.

   > [!div class="mx-imgBorder"]
   > ![OR operator, w którym oba warunki muszą zostać spełnione](media/segmentation-either-condition.png "OR operator, w którym oba warunki muszą zostać spełnione")

Obecnie istnieje możliwość zawinięcia operatora **OR** pod operatorem **AND**, ale nie na odwrót.

## <a name="combine-multiple-groups"></a>Łączenie wielu grup

Każda grupa dostarcza określony zbiór klientów. Te grupy można połączyć w celu dołączenia klientów niezbędnych do pracy z sprawą biznesową.

1. W analizach odbiorców przejdź na stronę **Segmenty** i wybierz segment.

2. Wybierz **Dodaj grupę**.

   > [!div class="mx-imgBorder"]
   > ![Grupa klientów, Dodawanie grupy](media/customer-group-add-group.png "Grupa klientów, Dodawanie grupy")

3. Wybierz jeden z następujących operatorów zestawu: **Związek**, **Część wspólna** lub **Z wyjątkiem**.

   > [!div class="mx-imgBorder"]
   > ![Grupa klientów, Dodawanie związku](media/customer-group-union.png "Grupa klientów, Dodawanie związku")

   Wybierz operator zestawu, aby zdefiniować nową grupę. Zapisz różne grupy, aby określić, jakie dane mają zostać zachowane:

   - **Związek** łączy dwie grupy.

   - **Część wspólna** pokrywa się z dwiema grupami. Tylko dane, które *są wspólne* dla obu grup, są zachowywane w ujednoliconej grupie.

   - **Z wyjątkiem** łączy dwie grupy. Tylko dane w grupie A, które *nie są wspólne* dla grupy B, są zachowywane w ujednoliconej grupie.

## <a name="view-processing-history-and-segment-members"></a>Wyświetlanie historii przetwarzania i członków segmentu

Istnieje możliwość wyświetlenia skonsolidowanych danych o segmencie dzięki przejrzeniu jego szczegółów.

Na stronie **Segmenty** zaznacz segment, który chcesz przejrzeć.

W górnej części strony znajduje się wykres trendów zawierający wizualizacje zmian w licznikach członków. Umieść wskaźnik myszy nad punktami danych, aby wyświetlić liczbę członków w określonym dniu.

Użytkownik może aktualizować horyzont czasowy wizualizacji.

> [!div class="mx-imgBorder"]
> ![Zakres czasu segmentu](media/segment-time-range.png "Zakres czasu segmentu")

W dolnej części znajduje się lista członków segmentu.

> [!NOTE]
> Pola wyświetlane na tej liście są oparte na atrybutach encji segmentu.
>
>Lista jest podglądem pasujących składników segmentu i zawiera pierwsze 100 rekordów segmentu, dzięki czemu można szybko oceniać i przejrzeć w razie potrzeby jego definicje. Aby wyświetlić wszystkie pasujące rekordy, należy [wyeksportować segment](export-destinations.md).

## <a name="quick-segments"></a>Szybkie segmenty

Poza konstruktorem segmentu istnieje też inna ścieżka do tworzenia segmentów. Szybkie segmenty umożliwiają tworzenie prostych segmentów z jednym operatorem szybko i z natychmiastowymi wynikami analiz.

1. Na stronie **Segmenty** wybierz **Nowe** > **Szybko utwórz z**.

   - Wybierz opcję **profile**, aby zbudować segment utworzony na podstawie ujednoliconej encji klienta.
   - Wybierz opcję **miary**, aby zbudować segment dla każdego typu atrybutu klienta, który został uprzednio utworzony na stronie **miary**.
   - Wybierz opcję **Analizy**, aby utworzyć segment wokół jednej z encji wyjściowych wygenerowanych przy użyciu funkcji **Przewidywania** lub **Modele niestandardowe**.

2. W oknie dialogowym **Nowy szybki segment** wybierz atrybut z listy rozwijanej **Pole**.

3. W ramach systemu będzie dostępne kilka dodatkowych informacji ułatwiających stworzenie lepszych segmentów klientów.
   - W przypadku pól kategorii pokażemy 10 największych klientów. Wybierz **Wartość** i wybierz **Przejrzyj**.

   - W przypadku atrybutu numerycznego system pokaże, jaka wartość atrybutu mieści się w percentylu każdego klienta Wybierz **Operator** i **Wartość**, a następnie wybierz pozycję **Przeglądaj**.

4. System zaproponuje opcje **Szacowany rozmiar segmentu**. Użytkownik może wybrać, czy ma zostać wyświetlona definicja segmentu, czy też najpierw ją ponownie przejrzeć w celu uzyskania innego rozmiaru segmentu.

    > [!div class="mx-imgBorder"]
    > ![Nazwa i oszacowanie szybkiego segmentu](media/quick-segment-name.png "Nazwa i oszacowanie szybkiego segmentu")

5. Podaj **Nazwę** segmentu. Opcjonalnie, podaj **Nazwę wyświetlaną**.

6. Wybierz opcję **Zapisz**, aby utworzyć segment.

7. Po zakończeniu przetwarzania segmentu można go wyświetlić tak samo, jak każdy inny segment utworzony przez użytkownika.

W poniższych scenariuszach zaleca się użycie konstruktora segment zamiast możliwości zalecanego segmentu:

- Tworzenie segmentów z filtrami na polach jakościowych, w których operator jest inny niż operator **Is**.
- Tworzenie segmentów z filtrami na polach numerycznych, w których operator jest inny niż operatory **Między**, **Większe niż** i **Mniejsze niż**.
- Tworzenie segmentów z filtrami w polach typu Data

## <a name="next-steps"></a>Następne kroki

[Wyeksportuj segment](export-destinations.md) i zapoznaj się z [kartą klienta](customer-card-add-in.md) i [łącznikami](export-power-bi.md), aby zdobyć informacje na poziomie klienta.


[!INCLUDE[footer-include](../includes/footer-banner.md)]