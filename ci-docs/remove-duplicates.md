---
title: Usuwanie duplikatów przed rozsyłaniem danych
description: Drugim krokiem w procesie ujednolicania jest wybór rekordu, który należy zachować w przypadku znalezienia duplikatów.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: a838fbdabdb3bfffc6d3835a3f0e97306a43964a
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139442"
---
# <a name="remove-duplicates-before-unifying-data"></a>Usuwanie duplikatów przed rozsyłaniem danych

Ten krok w ujednolicenia opcjonalnie umożliwia ustawienie reguł obsługi zduplikowanych rekordów w obrębie encji. *Deduplikacja* identyfikuje duplikaty rekordów i łączy je w jeden rekord. Rekordy źródłowe są łączone ze scalanym rekordem z innymi identyfikatorami. Jeśli reguły nie są skonfigurowane, stosowane są reguły zdefiniowane przez system.

## <a name="include-enriched-entities-preview"></a>Uwzględnij wzbogacone encje (wersja zapoznawcza)

Jeśli wzbogaciłeś encje na poziomie źródła danych, aby poprawić wyniki ujednolicenia, zaznacz je. Aby uzyskać więcej informacji, zobacz [Wzbogacanie dla źródeł danych](data-sources-enrichment.md).

1. Na stronie **Duplikacja rekordów** wybierz **Użyj wzbogaconych encji** na górze strony.

1. W okienku **Użyj wzbogaconych encji** wybierz jedną lub więcej wzbogaconych encji.

1. Wybierz pozycję **Gotowe**.

## <a name="define-deduplication-rules"></a>Zdefiniuj reguły deduplikacji

1. Na stronie **Duplikacja rekordów** zaznacz encję i wybierz **Dodaj regułę**, aby zdefiniować reguły deduplikacji.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Zrzut ekranu strony z duplikatami rekordów z zaznaczoną opcją Pokaż więcej":::

   1. W okienku **Dodaj regułę** wprowadź następujące informacje:
      - **Wybierz pole**: Wybierz z listy dostępne pola encji, które chcesz sprawdzić pod kątem duplikatów. Wybierz pola, które będą unikatowe dla każdego pojedynczego klienta. Może to być na przykład adres e-mail lub kombinacja imienia i nazwiska, miasta oraz numeru telefonu.
      - **Normalizuj**: wybierz opcję spośród następujących opcji normalizowania wybranych atrybutów.
        - **Cyfry**: konwertuje cyfry z innych systemów numerycznych, takie jak cyfry rzymskie, na cyfry arabskie. Ciąg *VIII* staje się ciągiem *8*.
        - **Symbole**: usuwa wszystkie symbole i znaki specjalne. Ciąg *Head&Shoulder* staje się ciągiem *HeadShoulder*.
        - **Tekst na małe litery: konwertuje wszystkie znaki na małe litery**. Ciąg *ALL CAPS and Title Case* staje się ciągiem *all caps and title case*.
        - **Typ (telefon, nazwa, adres, organizacja)**: standaryzuje nazwy, tytuły, numery telefonów, adresy itp.
        - **Unicode na ASCII**: konwertuje znaki notacje unicode na znaki ASCII. Ciąg */u00B2* staje się ciągiem *2*.
        - **Biały znak**: usuwa wszystkie spacje. Ciąg *Hello   World* staje się ciągiem *HelloWorld*.
      - **Dokładność**: ustaw poziom dokładności, która ma być ustawiona dla tego warunku.
        - **Podstawowa:** wybierz opcję *Niska (30%)*, *Średnia (60%)*, *Wysoka (80%)* i *Dokładnie (100%)*. Wybierz opcję **Dokładnie**, aby dopasować tylko rekordy zgodne w 100 procentach.
        - **Niestandardowa**: ustaw procent, do którego należy dopasować rekordy. System będzie dopasowywać tylko rekordy przekraczające ten próg.
      - **Nazwa**: Nazwa reguły.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Zrzut ekranu okienka dodawania reguł do usuwania duplikatów.":::

   1. Opcjonalnie wybierz **Dodaj** > **Dodaj warunek**, aby dodać więcej warunków do reguły. Warunki są połączone z operatorem logicznym AND i dlatego są wykonywane tylko wtedy, gdy zostaną spełnione wszystkie warunki.

   1. Opcjonalnie, **Dodaj** > **Dodaj wyjątek**, aby [dodać wyjątki do reguły](match-entities.md#add-exceptions-to-a-rule). Wyjątki są stosowane w rzadkich przypadkach fałszywych pozytywów i fałszywych negatywów.

   1. Wybierz opcję **Gotowe**, aby utworzyć regułę.

1. Opcjonalnie [dodaj więcej reguł](#define-deduplication-rules).

1. Wybierz encję, a następnie **Edytuj preferencje scalania**.

1. W panelu **Preferencje łączenia**:
   1. Wybierz jedną z trzech opcji, aby określić, który rekord ma zostać zachowany, jeśli zostanie znaleziony duplikat:
      - **Najbardziej wypełnione**: identyfikuje rekord z największą liczbą wypełnionych pól atrybutów jako rekord zwycięzcy. Jest to opcja domyślna scalania.
      - **Najnowsze**: Identyfikuje rekord zwycięzcy na podstawie aktualności. Wymaga daty lub pola liczbowego do zdefiniowania aktualności.
      - **Najstarsze**: Identyfikuje rekord zwycięzcy na podstawie najmniejszej aktualności. Wymaga daty lub pola liczbowego do zdefiniowania aktualności.
      
      W przypadku remisu wygrywa rekord, który ma MAX(PK) lub większą wartość klucza głównego.
      
   1. Opcjonalnie, aby określić preferencje scalania dla poszczególnych atrybutów encji, wybierz **Zaawansowane** na dole panelu. Można na przykład zachować najnowszą wiadomość e-mail ORAZ najbardziej pełny adres z różnych rekordów. Rozwiń encję, aby wyświetlić wszystkie jej atrybuty i zdefiniuj opcję używaną dla poszczególnych atrybutów. Jeśli wybierzesz opcję opartą na niedawności, musisz również określić pole daty/czasu definiujące niedawność.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Panel zaawansowanych preferencji scalania pokazujący ostatni e-mail i pełny adres":::

   1. Wybierz **Gotowe**, aby zastosować swoje preferencje scalania.

1. Po określeniu reguł deduplikacji i preferencji scalania wybierz **Dalej**.
  
> [!div class="nextstepaction"]
> [Następny krok dla pojedynczej encji: Ujednolicenie pól](merge-entities.md)

> [!div class="nextstepaction"]
> [Następny krok dla wielu encji: Dopasowanie warunków](match-entities.md)

## <a name="deduplication-output-as-an-entity"></a>Deduplikacja wyjściowa jako encja

Proces deduplikacji tworzy nową deduplikowaną encję dla każdej z encji źródłowych. Te encje można znaleźć razem z elementem **ConftronicMatchPpias:CustomerInsights** w sekcji **System** na stronie **Encje** z nazwą **Deduplication_DataSource_Entity**.

Obiekt wyjściowy deduplikacji zawiera następujące informacje:

- Identyfikatory/klucze
  - Pola klucza głównego i alternatywnego identyfikatora. Pole Alternatywny ID zawiera wszystkie identyfikatory alternatywne zidentyfikowane dla danego rekordu.
  - Pole Deduplication_GroupId przedstawia grupę lub klaster zidentyfikowaną w ramach jednostki, która grupuje wszystkie podobne rekordy na podstawie określonych pól deduplikacji. Jest ono używane do przetwarzania w systemie. Jeśli nie określono reguł ręcznej deduplikacji i mają zastosowanie reguły deduplikacji zdefiniowane przez system, to pole może nie być dostępne w jednostce wyjściowej deduplikacji.
  - Deduplication_WinnerId: To pole zawiera identyfikator zwycięzcy ze zidentyfikowanych grup lub klastrów. Jeśli Deduplication_WinnerId jest taki sam jak wartość klucza podstawowego dla rekordu, oznacza to, że rekord jest rekordem zwycięzcy.
- Pola używane do definiowania reguł deduplikacji.
- Pola Reguła i Wynik określające, które z reguł deduplikacji zostały zastosowane, oraz wynik zwracany przez algorytm dopasowujący.

[!INCLUDE[footer-include](includes/footer-banner.md)]
