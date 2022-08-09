---
title: Twórz złożone segmenty za pomocą narzędzia do tworzenia segmentów
description: Użyj narzędzia do tworzenia segmentów, aby tworzyć złożone segmenty klientów, grupując je na podstawie różnych atrybutów.
ms.date: 03/25/2022
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
ms.openlocfilehash: cde373cd65e296675e1b3c92f3024e1093853842
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170648"
---
# <a name="create-complex-segments-with-segment-builder"></a>Twórz złożone segmenty za pomocą narzędzia do tworzenia segmentów

Zdefiniować złożone filtry dla ujednoliconej encji klienta i jej encji pokrewnych. Każdy segment, po przetworzeniu, tworzy zestaw rekordów klientów, który można eksportować i na którym można podejmować akcje.

> [!TIP]
> Segmenty oparte na **poszczególnych klientach** automatycznie zawierają dostępne informacje kontaktowe dla elementów członkowskich segmentu. W środowiskach **kont biznesowych** segmenty są oparte na kontach (firmach lub filiach). Aby uwzględnić informacje kontaktowe w segmencie, użyj funkcji **Atrybuty projektu** w konstruktorze segmentów. Upewnij się, że źródła danych kontaktów są [semantycznie mapowane do encji ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).

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

1. Wybierz **Edytuj szczegóły** obok segmentu bez tytułu. Podaj nazwę swojego segmentu i zaktualizuj sugerowaną **nazwę encji wyjściowej** dla tego segmentu. Opcjonalnie dodaj opis i [etykiety](work-with-tags-columns.md#manage-tags) do segmentu.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Okno dialogowe Edytuj szczegóły.":::

1. W sekcji **Reguła 1** wybierz atrybut obiektu, według którego chcesz filtrować klientów. Istnieją dwa sposoby wybierania atrybutów:
   - Przejrzyj listę dostępnych obiektów i atrybutów w okienku **Dodaj do reguły** i wybierz ikonę **+** obok atrybutu, który chcesz dodać. Określ, czy atrybut ma zostać dodany do istniejącej reguły, czy podczas tworzenia nowej reguły.
   - Aby wyświetlić pasujące sugestie, wpisz nazwę atrybutu w sekcji reguły.

1. Wybierz operatory, aby określić odpowiadające wartości warunku. Atrybut może mieć jeden z czterech typów danych: wartość numeryczna, ciąg, data lub wartość logiczna. W zależności od typu danych atrybutu do określania warunku są dostępne różne operatory. W przypadku segmentów z kontami biznesowymi są dostępne dwa specjalne operatory do dołączania potencjalnych hierarchii między pozyskanymi kontami. Użyj operatorów *element podrzędny* i *element nadrzędny* do dołączania pokrewnych klientów.

1. Wybierz opcję **Dodaj warunek**, aby dodać więcej warunków do reguły. Aby utworzyć regułę na podstawie bieżącej reguły, wybierz opcję **Dodaj regułę podrzędną**.

1. Jeśli reguła używa innych encji niż encja *Klient*, wybierz **Ustaw ścieżkę relacji**, aby zmapować wybraną encję do ujednoliconej encji klienta. Jeśli jest dostępna tylko jedna ścieżka relacji, system wybierze ją automatycznie. Różne [ścieżki relacji](relationships.md#relationship-paths) mogą dostarczyć różnych wyników. Każda reguła może mieć własną ścieżkę relacji.

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

1. Domyślnie encja wyjściowa będzie automatycznie zawierała wszystkie atrybuty profili klientów, które pasują do zdefiniowanych filtrów. Jeśli segment jest oparty na encjach innych niż *Klient*, wybierz **Atrybuty projektu**, aby dodać więcej atrybutów z tych encji do encji wyjściowej.

   > [!IMPORTANT]
   > W przypadku segmentów opartych na kontach biznesowych szczegółowe informacje dotyczące jednego lub większej liczby kontaktów każdego klienta z encji *ContactProfile* muszą zostać uwzględnione w tym segmencie, aby umożliwić uaktywnienie lub wyeksportowanie tego segmentu do miejsc, w których są wymagane informacje kontaktowe. Aby uzyskać więcej informacji o encji *ContactProfile*, zobacz [mapowanie semantyczne](semantic-mappings.md).
   > Przykładowe dane wyjściowe dla segmentu oparte na kontach biznesowych z projektowanych atrybutów kontaktów mogą wyglądać tak:
   >
   > |ID  |Nazwa klienta  |Przychód  |Nazwa kontaktu  | Rola kontaktu|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100 tys. | [Abbie Moss, Ruth Soto]  | [Dyrektor generalny, kierownik zaopatrzenia]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Przykład projektowanych atrybutów wybranych w okienku bocznym, które mają zostać dodane do encji wyjściowej.":::
  
   Na przykład segment jest oparty na encji zawierającej dane dotyczące zakupu, która jest powiązana z encją *Klient*. Segment wyszukuje wszystkich klientów z Hiszpanii, którzy nabywali towary w bieżącym roku. Można dodać atrybuty, takie jak cena towarów lub data zakupu, do wszystkich pasujących rekordów klientów w encji wyjściowej. Te informacje mogą być przydatne do przeanalizowania skojarzeń z łącznymi wydatkami.

   > [!NOTE]
   > - **Atrybuty projektu** działają tylko w przypadku encji, które mają relację jeden do wielu z encją klienta. Na przykład jeden klient może mieć wiele subskrypcji.
   > - Jeśli atrybut, który ma być projektowany, jest więcej niż jeden przeskok od encji *Klient*, zgodnie z definicją relacji, powinien być używany we wszystkich regułach definiowanego zapytania segmentu.
   > - Jeśli atrybut, który ma być projektowany, jest tylko jeden przeskok od encji *Klient*, nie musi być obecny we wszystkich regułach definiowanego zapytania segmentu.
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
