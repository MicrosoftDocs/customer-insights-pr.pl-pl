---
title: Tworzenie segmentów i zarządzanie nimi
description: W celu pogrupowania klientów na podstawie różnych atrybutów można utworzyć ich segmenty.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064950"
---
# <a name="create-and-manage-segments"></a>Tworzenie segmentów i zarządzanie nimi

Zdefiniować złożone filtry dla ujednoliconej encji klienta i jej encji pokrewnych. Każdy segment, po przetworzeniu, tworzy zestaw rekordów klientów, który można eksportować i na którym można podejmować akcje. Segmenty są zarządzane na stronie **Segmenty**. 

Poniższy przykład ilustruje możliwości segmentacji. Zdefiniowano segment dla klientów, którzy zamówili towary za przynajmniej 500 USD w ciągu ostatnich 90 dni *i* którzy uczestniczyli w rozmowie telefonicznej z obsługą klienta, która eskalowała.

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Zrzut ekranu interfejsu użytkownika segmentu konstruktora z dwiema grupami określającymi segment klientów.":::

## <a name="create-a-new-segment"></a>Utwórz nowy segment

Istnieje wiele sposobów utworzenia nowego segmentu. W tej sekcji opisano sposób tworzenia *pustego segmentu* od podstaw. Można również utworzyć *krótki segment* na podstawie istniejących obiektów lub skorzystać z uczenia maszynowego, aby uzyskać *sugerowane segmenty*. Więcej informacji: [Omówienie segmentów](segments.md).

Podczas tworzenia segmentu można zapisać jego wersje robocze. Zostanie on zapisany jako nieaktywny segment i nie można go aktywować w ramach prawidłowej konfiguracji.

1. Przejdź do strony **Segmenty**.

1. Wybierz **Nowy** > **Pusty segment**.

1. W okienku **Nowy segment** wybierz typ segmentu:

   - **Dynamiczne segmenty** są [odświeżane](segments.md#refresh-segments) w harmonogramie cyklicznym.
   - **Segmenty statyczne** są uruchamiane jeden raz podczas ich tworzenia.

1. Podaj **nazwę encji wyjściowej** dla segmentu. Opcjonalnie można podać wyświetlaną nazwę i opis ułatwiający identyfikację segmentu.

1. Wybierz **Dalej**, aby połączyć się ze stroną **Konstruktor segmentu**, na której jest definiowana grupa. Grupa jest zbiorem klientów.

1. Wybierz encję zawierającą atrybut, według którego chcesz segmentować.

1. Wybierz atrybut, według którego ma zostać przeprowadzona segmentacja. Ten atrybut może mieć jeden z czterech typów wartości: numeryczny, ciąg, data lub wartość logiczna.

1. Wybierz operatora i wartość dla zaznaczonego atrybutu.

   > [!div class="mx-imgBorder"]
   > ![Niestandardowy filtr grup](media/customer-group-numbers.png "Filtr grupy klienta")

   |Liczba |Definicja  |
   |---------|---------|
   |1     |Entity          |
   |2     |Atrybut          |
   |3    |Operator         |
   |4    |Wartość         |

   1. Aby dodać do grupy więcej warunków, można użyć dwóch operatorów logicznych:

      - **AND** operator: oba warunki muszą być spełnione w procesie segmentacji. Ta opcja jest najbardziej przydatna podczas definiowania warunków między różnymi encjami.

      - **OR** operator: jeden z warunków musi zostać osiągnięty jako część procesu segmentacji. Ta opcja jest najbardziej przydatna podczas definiowania wielu warunków dla tej samej encji.

      > [!div class="mx-imgBorder"]
      > ![OR operator, w którym oba warunki muszą zostać spełnione](media/segmentation-either-condition.png "OR operator, w którym oba warunki muszą zostać spełnione")

      Obecnie istnieje możliwość zawinięcia operatora **OR** pod operatorem **AND**, ale nie na odwrót.

   1. Każda grupa odpowiada grupie klientów. Można łączyć grupy w celu uwzględnienia klientów wymaganych dla danego przypadku biznesowego.    
   Wybierz **Dodaj grupę**.

      > [!div class="mx-imgBorder"]
      > ![Grupa klientów, Dodawanie grupy](media/customer-group-add-group.png "Grupa klientów, Dodawanie grupy")

   1. Wybierz jeden z operatorów: **Związek**, **Część wspólna** lub **Z wyjątkiem**.

   > [!div class="mx-imgBorder"]
   > ![Grupa klientów, Dodawanie związku](media/customer-group-union.png "Grupa klientów, Dodawanie związku")

   - **Związek** łączy dwie grupy.

   - **Część wspólna** pokrywa się z dwiema grupami. Tylko dane, które *są wspólne* dla obu grup, są zachowywane w ujednoliconej grupie.

   - **Z wyjątkiem** łączy dwie grupy. Tylko dane w grupie A, które *nie są wspólne* dla grupy B, są zachowywane w ujednoliconej grupie.

1. Jeśli encja jest połączona z zunifikowaną encją klient za pośrednictwem [relacji](relationships.md), należy zdefiniować ścieżkę relacji, aby utworzyć prawidłowy segment. Dodaj encje ze ścieżki relacji, aż będzie można wybrać encję **Klient : CustomerInsights** z listy rozwijanej. Następnie dla każdego kroku wybierz opcję **Wszystkie rekordy**.

   > [!div class="mx-imgBorder"]
   > ![Ścieżka relacji podczas tworzenia segmentu](media/segments-multiple-relationships.png "Ścieżka relacji podczas tworzenia segmentu")

1. Domyślnie segmenty generują encję wyjściową zawierającą wszystkie atrybuty profilów klientów zgodne ze zdefiniowanymi filtrami. Jeśli segment jest oparty na encjach innych niż encja *Klient*, do encji wyjściowej można dodać więcej atrybutów z tych encji. Wybierz pozycję **Atrybuty projektu**, aby wybrać atrybuty, które będą dołączane do encji wyjściowej.  
  
   Przykład: segment jest oparty na encji zawierającej dane działań klienta powiązane z encją *Klient*. Segment wyszukuje wszystkich klientów, którzy w ciągu ostatnich 60 dni dzwonili do działu pomocy technicznej. Można dodać czas trwania rozmowy oraz liczbę rozmów telefonicznych do wszystkich pasujących rekordów klientów w encji wyjściowej. Te informacje mogą być przydatne podczas wysyłania wiadomości e-mail z pomocnymi linków do artykułów pomocy online i często zadawanych pytań do klientów, którzy często dzwonili do działu pomocy.

   > [!NOTE]
   > - Atrybuty projektu działają tylko w przypadku encji, które mają relację jeden do wielu z encją klienta. Na przykład jeden klient może mieć wiele subskrypcji.
   > - Możesz rzutować tylko te atrybuty z encji, które są używane w każdej grupie segmentów, które budujesz.
   > - Atrybuty rzutowane są uwzględniane podczas używania operatorów zestawów.

1. Wybierz **Zapisz**, aby zapisać segment. Segment zostanie zapisany i przetworzony po sprawdzeniu poprawności wszystkich wymagań. W przeciwnym razie zostanie zapisany jako wersja robocza.

1. Wybierz **Wróć do segmentów**, aby wrócić do strony **Segmenty**.



## <a name="quick-segments"></a>Szybkie segmenty

Szybkie segmenty umożliwiają tworzenie prostych segmentów z jednym operatorem w celu szybszego wglądu w dane.

1. Na stronie **Segmentów** wybierz opcję **Nowy** > **Utwórz za pomocą**.

   - Wybierz opcję **profile**, aby zbudować segment utworzony na podstawie *ujednoliconej encji klienta*.
   - Wybierz opcję **Miary**, aby utworzyć segment na podstawie miar utworzonych wcześniej.
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

## <a name="next-steps"></a>Następne kroki

[Wyeksportuj segment](export-destinations.md) i zapoznaj się z [kartą klienta](customer-card-add-in.md) i [łącznikami](export-power-bi.md), aby zdobyć informacje na poziomie klienta.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
