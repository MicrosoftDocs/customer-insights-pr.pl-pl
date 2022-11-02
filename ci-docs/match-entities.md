---
title: Warunki dopasowania dla ujednolicenia danych
description: Dopasowanie encji w celu utworzenia ujednoliconych profili klientów.
recommendations: false
ms.date: 10/07/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: bbd2c5f441b85460250c11f02358ea67260278d6
ms.sourcegitcommit: 52ea58c872b10f1e6f9d120be93df93cca1a12dd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/26/2022
ms.locfileid: "9721534"
---
# <a name="match-conditions-for-data-unification"></a>Warunki dopasowania dla ujednolicenia danych

Ten krok w ujednolicenia określa kolejność dopasowania i zasady dopasowania między encjami. Ten krok wymaga co najmniej dwóch podmiotów.

> [!NOTE]
> Po utworzeniu warunków dopasowania i wybraniu **Dalej** nie możesz usunąć wybranej encji lub atrybutu. W razie potrzeby wybierz **Wstecz**, aby przejrzeć wybrane encje i atrybuty przed kontynuowaniem.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="include-enriched-entities-preview"></a>Uwzględnij wzbogacone encje (wersja zapoznawcza)

Jeśli wzbogaciłeś encje na poziomie źródła danych, aby poprawić wyniki ujednolicenia, zaznacz je. Aby uzyskać więcej informacji, zobacz [Wzbogacanie dla źródeł danych](data-sources-enrichment.md). Jeśli wybrałeś encje wzbogacone na stronie **Duplikaty rekordów**, nie musisz wybierać ich ponownie.

1. Na stronie **Warunki dopasowania** wybierz **Użyj wzbogaconych encji** na górze strony.

1. W okienku **Użyj wzbogaconych encji** wybierz jedną lub więcej wzbogaconych encji.

1. Wybierz pozycję **Gotowe**.

## <a name="specify-the-match-order"></a>Określ kolejność dopasowywania.

Każde dopasowanie ujednolica co najmniej dwie encje w postaci jednej skonsolidowanej encji. Jednocześnie są w nim zachowywane unikatowe rekordy klientów. Kolejność dopasowania wskazuje kolejność, w jakiej system próbuje dopasować rekordy.

> [!IMPORTANT]
> Pierwsza jednostka nazywana jest jednostką podstawową, która służy jako podstawa dla twoich zunifikowanych profili. Dodatkowe jednostki, które zostaną wybrane, zostaną dodane do tej jednostki.
>
> Ważne uwagi:
>
> - Jako jednostkę główną wybierz jednostkę posiadającą najbardziej kompletne i wiarygodne dane profilowe o swoich klientach.
> - Wybierz encję, która kilka atrybutów wspólnych z innymi encjami (np. imię i nazwisko, numer telefonu lub adres e-mail), jako encję podstawową.

1. Na stronie **Warunków dopasowania** użyj strzałek w górę i w dół, aby przenieść encje w wybranej kolejności, lub przeciągnij je i upuść. Na przykład wybierz element **eCommerceCustomers** jako encję podstawową i element **loyCustomers** jako drugą encję.

1. Aby każdy rekord w encji był unikalnym klientem, niezależnie od tego, czy zostanie znalezione dopasowanie, wybierz **Uwzględnij wszystkie rekordy**. Wszystkie rekordy w tej encji, które nie pasują do rekordów w innych encjach, są uwzględniane w profilu ujednoliconym. Rekordy, które nie mają dopasowania, nazywane są pojedynczymi.
  
Podstawowa encja *Contacts:eCommerce* jest dopasowana do następnej encji *CustomerLoyalty:Loyalty*. Zestaw danych będący wynikiem pierwszego kroku dopasowania jest dopasowany do następującej encji, jeśli użytkownik ma ponad dwie encje.

:::image type="content" source="media/m3_match.png" alt-text="Zrzut ekranu przedstawiający wybraną kolejność dopasowania dla jednostek." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Definiowanie reguł dla par dopasowania

Reguły dopasowania określają logikę, według której będzie dopasowywana określona para encji. Reguła składa się z jednego lub więcej warunków.

Ostrzeżenie obok nazwy encji oznacza, że dla danej pary dopasowań nie została zdefiniowana żadna reguła dopasowania.

1. Wybierz **Dodaj regułę** dla pary encji, aby zdefiniować reguły dopasowania.

1. W okienku **Dodaj regułę** skonfiguruj warunki dla reguły.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Zrzut ekranu okienka Dodaj regułę.":::

   - **Wybierz podmiot/pole (pierwszy wiersz)**: Wybierz powiązaną encję i atrybut, która prawdopodobnie jest unikalna dla klienta. Może to być na przykład numer telefonu lub adres e-mail. Unikaj dopasowywania według atrybutów typu działania. Na przykład identyfikator zakupu prawdopodobnie nie będzie mieć dopasowania w innych typach rekordów.

   - **Wybierz podmiot/pole (drugi rząd)**: Wybierz atrybut, który odnosi się do atrybutu encji określonej w pierwszym rzędzie.

   - **Normalizuj**: wybierz opcję spośród następujących opcji normalizowania wybranych atrybutów.
     - **Cyfry**: konwertuje cyfry z innych systemów numerycznych, takie jak cyfry rzymskie, na cyfry arabskie. Ciąg *VIII* staje się ciągiem *8*.
     - **Symbole**: usuwa wszystkie symbole i znaki specjalne. Ciąg *Head&Shoulder* staje się ciągiem *HeadShoulder*.
     - **Tekst na małe litery**: konwertuje wszystkie znaki na małe litery. Ciąg *ALL CAPS and Title Case* staje się ciągiem *all caps and title case*.
     - **Typ (telefon, nazwa, adres, organizacja)**: standaryzuje imiona, tytuły, numery telefonów, adresy i organizacje.
     - **Unicode na ASCII**: konwertuje znaki notacje unicode na znaki ASCII. Ciąg */u00B2* staje się ciągiem *2*.
     - **Biały znak**: usuwa wszystkie spacje. Ciąg *Hello   World* staje się ciągiem *HelloWorld*.

   - **Dokładność**: ustaw poziom dokładności, która ma być ustawiona dla tego warunku.
     - **Podstawowa:** wybierz opcję *Niska (30%)*, *Średnia (60%)*, *Wysoka (80%)* i *Dokładnie (100%)*. Wybierz opcję **Dokładnie**, aby dopasować tylko rekordy zgodne w 100 procentach.
     - **Niestandardowa**: ustaw procent, do którego należy dopasować rekordy. System będzie dopasowywać tylko rekordy przekraczające ten próg.

   - **Nazwa**: Nazwa reguły.

1. Aby dopasować encje tylko wtedy, gdy atrybuty spełniają wiele warunków, wybierz **Dodaj** > **Dodaj warunek**, aby dodać więcej warunków do reguły dopasowania. Warunki są połączone z operatorem logicznym AND i dlatego są wykonywane tylko wtedy, gdy zostaną spełnione wszystkie warunki.

1. Opcjonalnie rozważ zaawansowane opcje, takie jak [wyjątki](#add-exceptions-to-a-rule) lub [niestandardowe warunki dopasowania](#specify-custom-match-conditions).

1. Wybierz opcję **Gotowe**, aby zakończyć tworzenie reguły.

1. Opcjonalnie [dodaj więcej reguł](#add-rules-to-a-match-pair).

1. Kliknij przycisk **Dalej**.

> [!div class="nextstepaction"]
> [Następny krok: Ujednolicenie pól](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Dodawanie reguł do pary dopasowania

Reguły dopasowania reprezentują zestawy warunków. Aby dopasować encje według warunków na podstawie wielu atrybutów, dodaj więcej reguł.

1. Wybierz **Dodaj regułę** w encji, do której chcesz dodać reguły.

1. Wykonaj kroki opisane w części [Definiowanie reguł dla par dopasowania](#define-rules-for-match-pairs).

> [!NOTE]
> Kolejność reguł ma znaczenie. Algorytm dopasowujący próbuje dopasować rekord klienta na podstawie twojej pierwszej reguły i przechodzi do drugiej reguły tylko wtedy, gdy nie zidentyfikowano dopasowań na podstawie pierwszej reguły.

## <a name="advanced-options"></a>Opcje zaawansowane

### <a name="add-exceptions-to-a-rule"></a>Dodawanie wyjątków do reguły

W większości przypadków encja dopasowania potencjalnych klientów do unikatowych profilów klientów ze skonsolidowanych danymi. Aby rozwiązać rzadkie przypadki wyników fałszywie dodatnich i fałszywie ujemnych, można zdefiniować wyjątki dla reguły dopasowania. Wyjątki są stosowanie po przetworzeniu reguł dopasowania w celu uniknięcia dopasowania wszystkich rekordów, które spełniają kryteria wyjątków.

Jeśli na przykład reguła dopasowania zawiera nazwisko, miejscowość i datę urodzenia, system będzie identyfikować bliźniacze wpisy z tym samym nazwiskiem, zamieszkałe w tej samej miejscowości, jako ten sam profil. Można określić wyjątek, który nie pasuje do profilów, jeśli imiona w encji, które są łączone, nie są takie same.

1. W okienku **Edytuj regułę** wybierz opcję **Dodaj** > **Dodaj wyjątek**.

1. Określ kryteria wyjątków.

1. Wybierz **Gotowe**, aby zapisać zasadę.

### <a name="specify-custom-match-conditions"></a>Określanie niestandardowych warunków dopasowania

Określ warunki zastępowania domyślnej logiki dopasowania. Dostępne są cztery opcje:

|Opcja  |opis |Przykład  |
|---------|---------|---------|
|Zawsze pasują     | Określa wartości dla kluczy podstawowych, które są zawsze dopasowane.         |  Zawsze należy dopasować wiersz z kluczem podstawowym *12345* do wiersza z kluczem podstawowym *54321*.       |
|Nigdy nie pasują     | Określa wartości dla kluczy podstawowych, które nigdy nie są dopasowane.        | Nigdy nie dopasowuj wiersz z kluczem podstawowym *12345* do wiersza z kluczem podstawowym *54321*.        |
|Obejdź            | Określa wartości, które system powinien zawsze ignorować na etapie dopasowania. |  Podczas dopasowania ignoruj wartości *11111* i *Nieznane*.        |
|Mapowanie aliasu    | Zdefiniowanie wartości, które system powinien rozważyć jako tę samą wartość.         | Załóż, że *Joe* jest równe *Joseph*.        |

1. Wybierz **Niestandardowy**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Przycisk Niestandardowy":::

1. Wybierz **typ niestandardowy** i zaznacz **pobierz szablon**. Zmień nazwę szablonu bez użycia spacji. Dla każdej opcji dopasowania użyj osobnego szablonu.

1. Otwórz pobrany plik szablonu i wypełnij szczegóły. Szablon zawiera pola umożliwiające określenie encji i wartości kluczy podstawowych encji, które mają być używane w dopasowaniu niestandardowym. W nazwach encji jest rozróżniana wielkość liter. Na przykład aby klucz podstawowy *12345* z encji *Sprzedaż* zawsze był dopasowany do klucza podstawowego *34567* z encji *Kontakt*, wypełnij szablon:
   - Entity1: Sprzedaż
   - Entity1Key: 12345
   - Encja2: Kontakt
   - Entity2Key: 34567

   Ten sam plik szablonu może zawierać rekordy dopasowania niestandardowego pochodzące z wielu encji.

   > [!NOTE]
   > Jeśli chcesz określić niestandardowe dopasowanie do deduplikacji w encji, podaj tę samą jednostkę, co Entity1 i Entity2, i ustaw różne wartości klucza podstawowego. Do użycia niestandardowego dopasowania należy zdefiniować co najmniej jedną regułę deduplikacji dla encji.

1. Po dodaniu wszystkich zastąpień zapisz plik szablonu.

1. Wybierz **Dane** > **Źródła danych** i pobierz pliki szablonów jako nowe encje.

1. Po załadowaniu plików ponownie wybierz opcję **Niestandardowe**. Z menu rozwijanego wybierz wymagane encje i wybierz polecenie **Wykonane**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Zrzut ekranu z oknem dialogowym umożliwiającym wybranie opcji zastępowania scenariusza dopasowania niestandardowego.":::

1. Zastosowanie dopasowania niestandardowego zależy od opcji dopasowania, której chcesz użyć.

   - W przypadku opcji **Zawsze dopasuj** lub **Nigdy nie dopasuj** przejdź do następnego kroku.
   - W przypadku **Pominięcie** lub **Mapowania aliasu** wybierz **Edytuj** w istniejącej regule dopasowania lub utwórz nową regułę. W liście rozwijanej Normalizacje wybierz opcję **Pominięcie niestandardowe** lub **Mapowanie aliasu** i wybierz **Wykonano**.

1. Wybierz **Gotowe** w panelu **Niestandardowe**, aby zastosować niestandardową konfigurację dopasowania.

   Każdy przejmowany plik szablonu jest swoim własnym źródłem danych. Jeśli zostaną wykryte rekordy, które wymagają specjalnego dopasowania, należy zaktualizować odpowiednie źródło danych. Aktualizacja będzie używana podczas następnego procesu unifikacji. Na przykład identyfikujesz bliźnięta o prawie tym samym imieniu mieszkające pod tym samym adresem, które zostały połączone jako jedna osoba. Zaktualizuj źródło danych, aby zidentyfikować jednostki jako oddzielne, unikatowe rekordy.

> [!div class="nextstepaction"]
> [Następny krok: Ujednolicenie pól](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
