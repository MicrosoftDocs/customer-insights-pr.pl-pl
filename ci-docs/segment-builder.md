---
title: Twórz złożone segmenty za pomocą narzędzia do tworzenia segmentów
description: Użyj narzędzia do tworzenia segmentów, aby tworzyć złożone segmenty klientów, grupując je na podstawie różnych atrybutów.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 7f691fd0b2ea76a2960d5adf766a4b166f02ebb4
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304762"
---
# <a name="create-complex-segments-with-segment-builder"></a>Twórz złożone segmenty za pomocą narzędzia do tworzenia segmentów

Zdefiniuj złożone filtry wokół ujednoliconego klienta lub ujednoliconego kontaktu i powiązanych z nim encji. Każdy segment, po przetworzeniu, tworzy zestaw rekordów klientów lub kontaktów, które można wyeksportować i podjąć działania.

> [!TIP]
> Segmenty oparte na **poszczególnych klientach** automatycznie zawierają dostępne informacje kontaktowe dla elementów członkowskich segmentu. W **przypadku kont** biznesowych po [unifikacji](data-unification.md) kont i kontaktów wybierz, czy segment jest oparty na kontach, czy na kontaktach biznesowych. Aby wyeksportować do miejsca docelowego spodziewane informacje kontaktowe, użyj segmentu kontaktów. Aby wyeksportować do miejsca docelowego spodziewane informacje kontaktowe, użyj segmentu kontaktów.

## <a name="segment-builder"></a>Konstruktor segmentów

Na poniższym obrazie przedstawiono różne aspekty konstruktora segmentów. Wskazuje segment, którego wynikiem jest grupa klientów. Klienci zamówili towary w określonym horyzoncie czasowym i zdobyli punkty nagród lub wydali określoną kwotę pieniężną.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elementy konstruktora segmentów." lightbox="media/segment-builder-overview.png":::

1. Organizuj segmenty za pomocą reguł i reguł podrzędnych. Każda reguła lub reguła podrzędna składa się z warunków. Łączenie warunków z operatorami logicznymi.

1. Wybierz [ścieżkę relacji](relationships.md) między jednostkami, która dotyczy reguły. Ścieżka relacji określa, które atrybuty mogą być używane w warunku.

1. Zarządzaj regułami i regułami podrzędnymi. Zmień pozycję reguły lub ją usuń.

1. Dodaj warunki i skonstruuj odpowiedni poziom zagnieżdżania przy użyciu reguł podrzędnych.

1. Zastosuj operacje zestawów do połączonych reguł.

1. Użyj okienka atrybutów do dodania dostępnych atrybutów encji lub utworzenia warunków na podstawie atrybutów. W okienku jest wyświetlona lista encji i atrybutów na podstawie wybranej ścieżki reguły, która jest dostępna dla wybranej reguły.

1. Dodaj warunki na podstawie atrybutów do istniejących reguł i reguł podrzędnych lub dodaj je do nowej reguły.

1. Cofnij i ponownie zastosuj zmiany podczas konstruowania segmentu.

W tym przykładzie przedstawiono możliwości w zakresie segmentacji. Definiujemy segment dla klientów, którzy kupili towary online za co najmniej 500 USD *i* są zainteresowani opracowaniem oprogramowania.

## <a name="create-a-new-segment-with-segment-builder"></a>Utwórz nowy segment za pomocą narzędzia do tworzenia segmentów

1. Przejdź do **Segmenty**.

1. Wybierz opcję **Nowy** > **Utwórz własne**. Na stronie konstruktora segmentów można definiować lub definiować reguły. Reguła składa się z jednego lub większej liczby warunków definiującej zbiór klientów.

   > [!NOTE]
   > W przypadku środowisk opartych na kontach firmowych wybierz **Nowy** > **Segment kont** lub **Segment kontaktów (wersja zapoznawcza)** w zależności od typu segmentu, który chcesz utworzyć. Jeśli hierarchia [kont została](relationships.md#set-up-account-hierarchies) zdefiniowana i chcesz utworzyć reguły filtrowania danych na podstawie relacji podrzędnej i nadrzędnej, wybierz opcję **Użyj hierarchii? (podgląd),** wybierz hierarchię, a następnie **zastosuj**.
   >
   > :::image type="content" source="media/segment_acct_hierarchy.png" alt-text="Segment wybierz panel hierarchii kont.":::

1. Wybierz **Edytuj szczegóły** obok segmentu bez tytułu. Podaj nazwę swojego segmentu i zaktualizuj sugerowaną **nazwę encji wyjściowej** dla tego segmentu. Opcjonalnie dodaj opis i [etykiety](work-with-tags-columns.md#manage-tags) do segmentu.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Okno dialogowe Edytuj szczegóły.":::

1. W sekcji **Reguła 1** wybierz atrybut obiektu, według którego chcesz filtrować klientów. Istnieją dwa sposoby wybierania atrybutów:
   - Przejrzyj listę dostępnych obiektów i atrybutów w okienku **Dodaj do reguły** i wybierz ikonę **+** obok atrybutu, który chcesz dodać. Określ, czy atrybut ma zostać dodany do istniejącej reguły, czy podczas tworzenia nowej reguły.
   - Aby wyświetlić pasujące sugestie, wpisz nazwę atrybutu w sekcji reguły.

1. Wybierz operatory, aby określić odpowiadające wartości warunku. Atrybut może mieć jeden z czterech typów danych: wartość numeryczna, ciąg, data lub wartość logiczna. W zależności od typu danych atrybutu do określania warunku są dostępne różne operatory.

1. Wybierz opcję **Dodaj warunek**, aby dodać więcej warunków do reguły. Aby utworzyć regułę na podstawie bieżącej reguły, wybierz opcję **Dodaj regułę podrzędną**.

1. Jeśli w encji *B-to-B* reguła używa innych encji niż encja Klient (*lub encja ContactProfile*), **wybierz ścieżkę relacji Ustaw**, aby zamapować wybraną encję na ujednoliconą encję klienta. Jeśli jest dostępna tylko jedna ścieżka relacji, system wybierze ją automatycznie. Różne [ścieżki relacji](relationships.md#relationship-paths) mogą dostarczyć różnych wyników. Każda reguła może mieć własną ścieżkę relacji.

   :::image type="content" source="media/relationship-path.png" alt-text="Potencjalna ścieżka relacji podczas tworzenia reguły opartej na encji zamapowanej na encję ujednoliconego klienta.":::

1. Jeśli w regule istnieje kilka warunków, można wybrać operator logiczny, który je łączy.  
   - Operator **I**: aby uwzględnić rekord w segmencie, muszą zostać spełnione wszystkie warunki. Użyj tej opcji, gdy definiujesz warunki w różnych encjach.
   - Operator **LUB**: aby uwzględnić rekord w segmencie, musi zostać spełniony jeden z warunków. Użyj tej opcji, gdy definiujesz wiele warunków dla tej samej encji.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Reguła z dwoma warunkami I.":::

   Podczas używania operatora LUB wszystkie warunki muszą być oparte na encji w ścieżki relacji.

1. Aby utworzyć różne zestawy rekordów klientów, utwórz wiele reguł. Aby uwzględnić klientów wymaganych dla Twojego uzasadnienia biznesowego, połącz grupy. W szczególności, jeśli nie możesz uwzględnić jednostki w regule z powodu określonej ścieżki relacji, utwórz nową regułę, aby wybrać z niej atrybuty.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Dodaj nową regułę do segmentu i wybierz operator zestawu.":::

   1. Wybierz **Dodaj regułę**.
   1. Wybierz jeden z operatorów: **Związek**, **Część wspólna** lub **Z wyjątkiem**.

      - **Związek** łączy dwie grupy.
      - **Część wspólna** pokrywa się z dwiema grupami. W ujednoliconej grupie pozostają tylko dane *wspólne* dla obu grup.
      - **Z wyjątkiem** łączy dwie grupy. W grupie A przechowywane są tylko te dane, które *nie są wspólne* z grupą B.

1. Domyślnie encja wyjściowa będzie automatycznie zawierała wszystkie atrybuty profili klientów, które pasują do zdefiniowanych filtrów. W programie B-to-B podczas używania obiektu *ContactProfile* identyfikator konta jest automatycznie dołączona. Jeśli segment jest oparty na innych encjach niż encja *Klient* lub aby uwzględnić więcej atrybutów z pliku *ContactProfile*, należy wybrać **atrybuty projektu**, aby dodać więcej atrybutów z tych obiektów do obiektu wyjściowego.
 
   Na przykład segment jest oparty na encji zawierającej dane dotyczące zakupu, która jest powiązana z encją *Klient*. Segment wyszukuje wszystkich klientów z Hiszpanii, którzy nabywali towary w bieżącym roku. Można dodać atrybuty, takie jak cena towarów lub data zakupu, do wszystkich pasujących rekordów klientów w encji wyjściowej. Te informacje mogą być przydatne do przeanalizowania skojarzeń z łącznymi wydatkami.

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Przykład projektowanych atrybutów wybranych w okienku bocznym, które mają zostać dodane do encji wyjściowej.":::
 
   Przykładowe dane wyjściowe dla segmentu oparte na kontach biznesowych z projektowanych atrybutów kontaktów mogą wyglądać tak:

   |ID  |Nazwa klienta  |Przychód  |Nazwa kontaktu  | Rola kontaktu|
   |---------|---------|---------|---------|---|
   |10021     | Contoso | 100 tys. | [Abbie Moss, Ruth Soto]  | [Dyrektor generalny, kierownik zaopatrzenia]

   > [!NOTE]
   > - **Atrybuty projektu** działają tylko w przypadku encji, które mają relację jeden-do-wielu z encją *Customer* lub *ContactProfile*. Na przykład jeden klient może mieć wiele subskrypcji.
   > - Jeśli atrybut, który ma być projektowany, jest więcej niż jeden przeskok od encji *Customer* lub *ContactProfile*, zgodnie z definicją relacji, powinien być używany we wszystkich regułach definiowanego zapytania segmentu.
   > - Jeśli atrybut, który ma być projektowany, jest tylko jeden przeskok od encji *Customer* lub *ContactProfile*, nie musi być obecny we wszystkich regułach definiowanego zapytania segmentu.
   > - **Atrybuty rzutowane** są uwzględniane podczas używania operatorów zestawów.

1. Wybierz opcję **Uruchom**, aby utworzyć segment. Wybierz opcję **Zapisz**, jeśli chcesz zachować bieżącą konfigurację i uruchomić segment później. Zostanie wyświetlona strona **Segmenty**.

### <a name="segment-builder-tips"></a>Wskazówki dotyczące tworzenia segmentów

Tworząc segment przy użyciu konstruktora segmentów, należy pamiętać o następujących wskazówkach:

- Konstruktor segmentów nie zasugeruje prawidłowych wartości z encji podczas ustawiania operatorów na określonych warunkach. Można przejść do obszaru **Dane** > **Encje** i pobrać dane encji, aby sprawdzić, które wartości są dostępne.
- Warunki oparte na datach umożliwiają przełączanie się między stałymi datami a zmiennoprzecinkowym zakresem dat.
- Jeśli dla swojego segmentu masz kilka reguł, reguła, która jest edytowana, ma obok siebie pionowy niebieski wiersz.
- Reguły i warunki można przenieść do innych miejsc definicji segmentu. Wybierz wielokropek pionowy (&vellip;) obok reguły lub warunku i wybierz sposób i miejsce jego przeniesienia.
- Kontrolki **Cofnij** i **Ponów** na pasku poleceń umożliwiają cofnięcie zmian.
- Po utworzeniu segmentu niektóre segmenty [umożliwiają śledzenie wykorzystania tego segmentu](segments.md#track-usage-of-a-segment).

## <a name="next-steps"></a>Następne kroki

[Wyeksportuj segment](export-destinations.md) i zapoznaj się z [integracją karty klienta](customer-card-add-in.md), aby używać segmentów w innych aplikacjach.

[!INCLUDE [footer-include](includes/footer-banner.md)]
