---
title: Dopasuj encji do ujednolicenia danych
description: Dopasowanie encji w celu utworzenia ujednoliconych profili klientów.
ms.date: 02/07/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: 44f030f69b84a00438e92aa5fddca832f4e54c41
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646898"
---
# <a name="match-entities"></a>Dopasowywanie encji

Faza dopasowania określa sposób łączenia zestawów danych w ujednolicony zestaw danych profilu klienta. Po zakończeniu [kroku mapowania](map-entities.md) w procesie ujednolicania danych można dopasować je do swoich encji. Faza dopasowania wymaga co najmniej dwóch zamapowanych encji.

Strona dopasowania składa się z trzech sekcji: 
- Kluczowe metryki podsumowujące liczbę dopasowanych rekordów
- Dopasowywanie kolejności i reguł w celu dopasowania między encjami
- Reguły deduplikacji encji dopasowania

## <a name="specify-the-match-order"></a>Określ kolejność dopasowywania.

Każde dopasowanie ujednolica co najmniej dwie encje w postaci jednej skonsolidowanej encji. Jednocześnie są w nim zachowywane unikatowe rekordy klientów. Kolejność dopasowania wskazuje kolejność, w jakiej system próbuje dopasować rekordy.

> [!IMPORTANT]
> Encja wybrana jako encja podstawowa będzie służyć jako podstawa dla ujednoliconego zestawu danych profilów. Do tej encji zostaną dodane dodatkowe encje wybrane podczas fazy dopasowania. Nie oznacza to, że encja ujednolicona będzie zawierać *wszystkie* dane zawarte w tej encji.
>
> Istnieją dwa kwestie, które mogą pomóc w wyborze hierarchii encji:
>
> - Jako encję podstawową należy wybrać encję o najbardziej kompletnych i wiarygodnych danych profilów dotyczących klientów.
> - Wybierz encję, która kilka atrybutów wspólnych z innymi encjami (np. imię i nazwisko, numer telefonu lub adres e-mail), jako encję podstawową.

1. Przejdź do opcji **Dane** > **Ujednolicanie** > **Dopasowywanie** i wybierz **Ustaw kolejność** , aby rozpocząć etap dopasowania.
1. Wybierz pozycję **Kolejność encji**. Na przykład wybierz element **eCommerce:eCommerceContacts** jako encję podstawową i element **LoyaltyScheme:loyCustomers** jako drugą encję. 
1. Aby uwzględnić każdy rekordy w encji jako unikatowego klienta oraz dopasowywać go do każdej kolejnej encji, wybierz pozycję **Uwzględnij wszystkie**.
1. Wybierz pozycję **Gotowe**. 

Po określeniu kolejności dopasowywania zdefiniowane pary dopasowań zostaną wyświetlone w obszarze **Szczegóły dopasowanych rekordów** w sekcji **Dane** > **Ujednolicanie** > **Dopasuj**. Kluczowe metryki są puste do momentu zakończenia procesu dopasowywania.

:::image type="content" source="media/match-page.png" alt-text="Zrzut ekranu przedstawiający stronę dopasowania w obszarze ujednolicania w procesie ujednolicania danych.":::
  
Encja podstawowa *eCommerce:eCommerceContacts* jest dopasowywana do następnej encji *LoyaltyScheme:loyCustomers*. Zestaw danych będący wynikiem pierwszego kroku dopasowania jest dopasowany do następującej encji, jeśli użytkownik ma ponad dwie encje.

## <a name="define-rules-for-match-pairs"></a>Definiowanie reguł dla par dopasowania

Reguły dopasowania określają logikę, według której będzie dopasowywana określona para encji.

Ostrzeżenie **Wymaga reguł** obok nazwy encji sugeruje, że dla pary dopasowania nie zdefiniowano reguły dopasowania. 

:::image type="content" source="media/match-rule-add.png" alt-text="Zrzut ekranu sekcji Szczegóły dopasowanych rekordów z wyróżnioną kontrolką służącą do dodawania reguł.":::

1. Wybierz pozycję **Dodaj regułę** dla encji w obszarze **Szczegóły dopasowanych rekordów**, aby zdefiniować reguły dopasowania.

1. W okienku **Tworzenie reguły** skonfiguruj warunki reguły.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Zrzut ekranu przedstawiający otwartą regułę dopasowania z dodanymi warunkami.":::

   - **Encja/pole (pierwszy wiersz)**: wybierz powiązaną encję i atrybut, aby określić właściwość rekordu, która najprawdopodobniej będzie unikatowa dla klienta. Może to być na przykład numer telefonu lub adres e-mail. Unikaj dopasowywania według atrybutów typu działania. Na przykład identyfikator zakupu prawdopodobnie nie będzie mieć dopasowania w innych typach rekordów.

   - **Encja/pole (drugi wiersz)**: wybierz atrybut powiązany z atrybutem encji określonym w pierwszym wierszu.

   - **Normalizuj**: wybierz opcję spośród następujących opcji normalizowania wybranych atrybutów. 
     - Cyfry: konwertuje cyfry z innych systemów numerycznych, takie jak cyfry rzymskie, na cyfry arabskie. Ciąg *VIII* staje się ciągiem *8*.
     - Symbole: usuwa wszystkie symbole i znaki specjalne. Ciąg *Head&Shoulder* staje się ciągiem *HeadShoulder*.
     - Tekst na małe litery: konwertuje wszystkie znaki na małe litery. Ciąg *ALL CAPS and Title Case* staje się ciągiem *all caps and title case*.
     - Typ (telefon, nazwa, adres, organizacja): standaryzuje nazwy, tytuły, numery telefonów, adresy itp. 
     - Unicode na ASCII: konwertuje znaki notacje unicode na znaki ASCII. Ciąg */u00B2* staje się ciągiem *2*.
     - Biały znak: usuwa wszystkie spacje. Ciąg *Hello   World* staje się ciągiem *HelloWorld*.

   - **Dokładność**: ustaw poziom dokładności, która ma być ustawiona dla tego warunku. 
     - **Podstawowa:** wybierz opcję *Niska*, *Średnia*, *Wysoka* i *Dokładnie*. Wybierz opcję **Dokładnie**, aby dopasować tylko rekordy zgodne w 100 procentach. Wybierz jeden z pozostałych poziomów w celu dopasowania do rekordów, które nie są w 100 procentach identyczne.
     - **Niestandardowa**: ustaw procent, do którego należy dopasować rekordy. System będzie dopasowywać tylko rekordy przekraczające ten próg.

1. W polu **Nazwa** podaj nazwę reguły.

1. [Dodaj więcej warunków](#add-conditions-to-a-rule) lub wybierz opcję **Gotowe** w celu sfinalizowania reguły.

1. Opcjonalnie [dodaj więcej reguł](#add-rules-to-a-match-pair).

1. Wybierz pozycję **Zapisz**, aby zastosować zmiany.

### <a name="add-conditions-to-a-rule"></a>Dodawanie warunków do reguły

Aby dopasować encje tylko wtedy, gdy atrybuty spełniają kilka warunków, dodaj więcej warunków do reguły dopasowania. Warunki są połączone z operatorem logicznym AND i dlatego są wykonywane tylko wtedy, gdy zostaną spełnione wszystkie warunki.

1. Przejdź do obszaru **Dane** > **Ujednolicanie** > **Dopasuj** i wybierz pozycję **Edytuj** w regule, do której chcesz dodać warunki.

1. W okienku **Edytuj regułę** wybierz pozycję **Dodaj warunek**.

1. Wybierz **Gotowe**, aby zapisać zasadę.

### <a name="add-rules-to-a-match-pair"></a>Dodawanie reguł do pary dopasowania

Reguły dopasowania reprezentują zestawy warunków. Aby dopasować encje według warunków na podstawie wielu atrybutów, dodaj więcej reguł.

1.  Przejdź do obszaru **Dane** > **Ujednolicanie** > **Dopasuj** i wybierz pozycję **Dodaj regułę** w encji, do której chcesz dodać reguły.

2. Wykonaj kroki opisane w części [Definiowanie reguł dla par dopasowania](#define-rules-for-match-pairs).

> [!NOTE]
> Kolejność reguł ma znaczenie. Algorytm dopasowywania próbuje dopasować na podstawie pierwszej reguły i kontynuuje pracę z drugą regułą tylko wtedy, gdy nie określono żadnych dopasowań dla pierwszej reguły.

### <a name="change-the-entity-order-in-match-rules"></a>Zmienianie kolejności encji w regułach dopasowania

Można zmienić kolejność encji dla reguł dopasowania, aby zmienić kolejność, w jakiej są przetwarzane. Reguły kolidujące ze zmienioną kolejnością zostaną usunięte. Trzeba ponownie utworzyć usunięte reguły przy użyciu zaktualizowanej konfiguracji.

1. Przejdź do **Dane** > **Unifikuj** > **Dopasuj** i wybierz opcję **Edytuj**.

1. W okienku **Edytuj regułę** wybierz **Przesuń w górę / w dół** i przenieś/upuść encje, aby zmienić kolejność.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="Opcje służące do zmiany kolejności, w której encje są przetwarzane na etapie dopasowania.":::

1. Wybierz **Gotowe**, aby zapisać zasadę.

## <a name="define-deduplication-on-a-match-entity"></a>Definiowanie deduplikacji dla encji dopasowania

Oprócz [reguł dopasowania między encjami](#define-rules-for-match-pairs) można również określić reguły deduplikacji. *Deduplikacja* to kolejny proces wykonywany podczas dopasowywania rekordów. Identyfikuje on zduplikowane rekordy i scala je w jeden rekord. Rekordy źródłowe są łączone ze scalanym rekordem z innymi identyfikatorami.

Rekordy po deduplikacji są używane w procesie dopasowywania między encjami. Deduplikacja odbywa zdarza się w przypadku poszczególnych encji i można ją skonfigurować dla każdej encji używanej w parach dopasowania.

Określenie reguł deduplikacji nie jest obowiązkowe. Jeśli żadne reguły nie są skonfigurowane, stosowane są reguły zdefiniowane w systemie. Łączą one wszystkie rekordy w jeden rekord przed przekazaniem danych encji do dopasowania między encjami w celu zwiększenia wydajności.

### <a name="add-deduplication-rules"></a>Dodaj reguły deduplikacji

1. Przejdź do sekcji **Dane** > **Ujednolicanie** > **Dopasuj**.

1. W sekcji **Szczegółowe informacje o deduplikowanych rekordach** zaznacz opcję **Ustawianie encji**. Jeśli reguły deduplikacji zostały już utworzone, wybierz opcję **Edytuj**.

1. W okienku **Preferencje scalania** wybierz encje, dla których chcesz uruchomić deduplikację.

   1. Określ sposób łączenia zduplikowanych rekordów i wybierz jedną z trzech opcji:
      - **Najbardziej wypełnione**: identyfikuje rekord z największą liczbą wypełnionych pól atrybutów jako rekord zwycięzcy. Jest to opcja domyślna scalania.
      - **Najnowsze**: Identyfikuje rekord zwycięzcy na podstawie aktualności. Wymaga daty lub pola liczbowego do zdefiniowania aktualności.
      - **Najstarsze**: Identyfikuje rekord zwycięzcy na podstawie najmniejszej aktualności. Wymaga daty lub pola liczbowego do zdefiniowania aktualności.

   1. Opcjonalnie, aby zdefiniować reguły deduplikacji dla poszczególnych atrybutów encji, wybierz opcję **Zaawansowane**. Można na przykład zachować najnowszą wiadomość e-mail ORAZ najbardziej pełny adres z różnych rekordów. Rozwiń encję, aby wyświetlić wszystkie jej atrybuty i zdefiniuj opcję używaną dla poszczególnych atrybutów. Jeśli wybierzesz opcję opartą na niedawności, musisz również określić pole daty/czasu definiujące niedawność. 
 
      > [!div class="mx-imgBorder"]
      > ![Reguły deduplikacji krok 1.](media/match-selfconflation.png "Reguły deduplikacji krok 1")

   1. Wybierz opcję **Wykonane**, aby zastosować preferencje dotyczące korespondencji seryjnej w celu powielania.
 
1. Po wybraniu encji i ustawieniu ich preferencji scalania wybierz opcję **Dodaj regułę** w celu zdefiniowania reguł deduplikacji na poziomie encji.
   - Opcja **Wybierz pole** powoduje wyświetlenie listy wszystkich dostępnych pól z tej encji. Wybierz pole, które ma być sprawdzane pod kątem duplikatów. Wybierz pola, które będą unikatowe dla każdego pojedynczego klienta. Może to być na przykład adres e-mail lub kombinacja imienia i nazwiska, miasta oraz numeru telefonu.
   - Określ ustawienia normalizacji i dokładności.
   - Zdefiniuj dalsze warunki, wybierając opcję **Dodaj warunek**.
 
   > [!div class="mx-imgBorder"]
   > ![Reguły deduplikacji krok 2.](media/match-selfconflation-rules.png "Reguły deduplikacji krok 2")

  Dla encji można utworzyć wiele reguł deduplikacji. 

1. Uruchomienie procesu dopasowywania powoduje teraz grupowanie rekordów na podstawie warunków zdefiniowanych w regułach deduplikacji. Po zgrupowaniu rekordów stosowane są zasady scalania, aby zidentyfikować rekord zwycięzcy.

1. Ten rekord zwycięzcy jest następnie przekazywany do dopasowania między obiektami, razem z rekordami zwycięzcy (na przykład alternatywnymi identyfikatorami), aby poprawić jakość dopasowania.

1. Wszystkie niestandardowe reguły dopasowania zdefiniowane w te sposób zastępują reguły deduplikacji. Jeśli reguła deduplikacji identyfikuje pasujące rekordy, a niestandardowa reguła dopasowania jest ustawiona tak, aby nigdy nie pasować do tych rekordów, te dwa rekordy nie zostaną dopasowane.

1. Po [zakończeniu procesu dopasowania](#run-the-match-process) statystyki deduplikacji są dostępne w kluczowych kafelkach metryk.

### <a name="deduplication-output-as-an-entity"></a>Deduplikacja wyjściowa jako encja

Proces deduplikacji powoduje utworzenie nowej encji dla każdej encji z par dopasowania w celu zidentyfikowania rekordów po deduplikacji. Te encje można znaleźć razem z elementem **ConftronicMatchPpias:CustomerInsights** w sekcji **System** na stronie **Encje** z nazwą **Deduplication_DataSource_Entity**.

Obiekt wyjściowy deduplikacji zawiera następujące informacje:
- Identyfikatory/klucze
  - Pole klucza podstawowego i jego inne pole identyfikatorów. Pole Alternatywne identyfikatory zawiera wszystkie alternatywne identyfikatory zidentyfikowane dla rekordu.
  - Pole Deduplication_GroupId przedstawia grupę lub klaster zidentyfikowaną w ramach jednostki, która grupuje wszystkie podobne rekordy na podstawie określonych pól deduplikacji. Jest ono używane do przetwarzania w systemie. Jeśli nie określono reguł ręcznej deduplikacji i mają zastosowanie reguły deduplikacji zdefiniowane przez system, to pole może nie być dostępne w jednostce wyjściowej deduplikacji.
  - Deduplication_WinnerId: To pole zawiera identyfikator zwycięzcy ze zidentyfikowanych grup lub klastrów. Jeśli Deduplication_WinnerId jest taki sam jak wartość klucza podstawowego dla rekordu, oznacza to, że rekord jest rekordem zwycięzcy.
- Pola używane do definiowania reguł deduplikacji.
- Pola Reguła i Wynik określające, które z reguł deduplikacji zostały zastosowane, oraz wynik zwracany przez algorytm dopasowujący.
 
## <a name="include-enriched-entities-preview"></a>Uwzględnij wzbogacone encje (wersja zapoznawcza)

Jeśli wzbogaciłeś encje na poziomie źródła danych, wybierz je przed uruchomieniem procesu dopasowania. Wzbogacone encje mogą poprawić twoje wyniki unifikacji. Aby uzyskać więcej informacji, zobacz [Wzbogacanie dla źródeł danych](data-sources-enrichment.md). 

Wzbogacona encja zawiera pola oryginalnego źródła danych oraz pola wzbogacone. Jeśli więc zdecydujesz się pracować z encją wzbogaconą, nie będzie to miało wpływu na istniejącą konfigurację. Może się jednak okazać, że będziesz musiał zaktualizować reguły dopasowania, aby zamiast nich używać pól wzbogaconych.

1. Przejdź do **Dane** > **Unifikacja** > **Dopasowanie** i wybierz **Użyj wzbogaconych encji** na górze strony.

1. W okienku **Użyj wzbogaconych encji** wybierz jedną lub więcej wzbogaconych encji.

1. Wybierz pozycję **Gotowe**. Wszędzie tam, gdzie używana jest encja źródłowa (np. kolejność dopasowania lub reguły), jest ona automatycznie zmieniana na encję wzbogaconą.
  
## <a name="run-the-match-process"></a>Uruchamianie procesu dopasowania

Po skonfigurowaniu reguł dopasowania, w tym reguł dopasowania między encjami i reguł deduplikacji, można uruchomić proces dopasowania. 

Przejdź do sekcji **Dane** > **Ujednolicanie** > **Dopasuj** i wybierz opcję **Uruchom**, aby rozpocząć proces. Wykonanie algorytmu dopasowywania potrwa pewien czas i nie można zmienić konfiguracji, dopóki nie zostanie on zakończony. Aby wprowadzić zmiany, można anulować uruchomienie. Wybierz stan zadania i wybierz opcję **Anuluj zadanie** w okienku **szczegółów postępu**.

Wynik pomyślnego uruchomienia, czyli ujednolicona encja profilu klienta, będzie widoczny na stronie **Encje**. Ujednolicona encja klienta nosi nazwę **Klienci** w sekcji **Profile**. Pierwsze udane uruchomienie dopasowania powoduje utworzenie ujednoliconej encji *Klient*. Wszystkie kolejne uruchomienia dopasowania rozszerzają tę encję.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="review-and-validate-your-matches"></a>Przejrzyj i zweryfikuj swoje dopasowania

Przejdź do obszaru **Dane** > **Ujednolicanie** > **Dopasuj**, aby ocenić jakość par dopasowania i w razie potrzeby ulepszyć je.

Kafelki u góry strony pokazują kluczowe metryki podsumowujące liczbę dopasowanych rekordów i duplikatów.

:::image type="content" source="media/match-KPIs.png" alt-text="Przycięty zrzut ekranu przedstawiający kluczowe metryki na stronie dopasowania z liczbami i szczegółami.":::

- **Unikatowe rekordy źródłowe** — liczba poszczególnych rekordów źródłowych przetworzonych w ostatnim uruchomieniu dopasowania.
- **Rekordy dopasowane i niedopasowane** — liczba wskazująca, ile unikatowych rekordów pozostaje po przetworzeniu reguł dopasowania.
- **Tylko rekordy dopasowane** — liczba dopasowań we wszystkich parach dopasowania.

Wyniki każdej pary dopasowania i jej reguł można oceniać w tabeli **Szczegóły dopasowanych rekordów**. Porównaj liczbę rekordów pochodzących z pary dopasowania z procentem pomyślnie dopasowanych rekordów.

Przejrzyj reguły pary dopasowania, aby sprawdzić procent pomyślnie dopasowanych rekordów na poziomie reguły. Wybierz wielokropek (...) a następnie wybierz opcję **Podgląd dopasowania**, aby wyświetlić wszystkie rekordy na poziomie reguły. Zaleca się, aby zweryfikować niektóre rekordy w celu sprawdzenia, czy zostały one dopasowane.

W celu znalezienia wartości optymalnej należy wypróbować różne progi dokładności.

  1. Wybierz wielokropek (...) dla reguły, z którą chcesz eksperymentować, i wybierz opcję **Edytuj**.

  2. Zmień wartości dokładności w warunkach, które chcesz poprawić.

  3. Wybierz opcję **Podgląd**, aby wyświetlić liczbę dopasowanych i niedopasowanych rekordów dla wybranego warunku.

## <a name="manage-match-rules"></a>Zarządzanie regułami dopasowania

Większość parametrów dopasowania można ponownie skonfigurować i odpowiednio dostosować.

:::image type="content" source="media/match-rules-management.png" alt-text="Zrzut ekranu menu rozwijanego z opcjami reguł dopasowania.":::

- **Zmień kolejność reguł** w przypadku zdefiniowania wielu reguł. Kolejność reguł dopasowania można zmienić, wybierając opcje **Przenieś w górę** i **Przenieś w dół** lub korzystając z metody przeciągania i upuszczania.

- **Zmień warunki reguły**, wybierając opcję **Edytuj**, i wybierz inne pola.

- **Zdezaktywuj regułę**, aby zachować regułę dopasowania, wykluczając ją z procesu dopasowania.

- **Duplikuj reguły**, jeśli zdefiniowano regułę dopasowania i chcesz utworzyć podobną regułę z modyfikacjami; wybierz pozycję **Duplikuj**.

- **Usuń regułę**, wybierając symbol **Usuń**.

## <a name="advanced-options"></a>Opcje zaawansowane

### <a name="add-exceptions-to-a-rule"></a>Dodawanie wyjątków do reguły

W większości przypadków encja dopasowania potencjalnych klientów do unikatowych profilów użytkowników ze skonsolidowanych danymi. Aby dynamicznie rozwiązać rzadkie przypadki wyników fałszywie dodatnich i fałszywie ujemnych, można zdefiniować wyjątki dla reguły dopasowania. Wyjątki są stosowanie po przetworzeniu reguł dopasowania w celu uniknięcia dopasowania wszystkich rekordów, które spełniają kryteria wyjątków.

Jeśli na przykład reguła dopasowania zawiera nazwisko, miejscowość i datę urodzenia, system będzie identyfikować bliźniacze wpisy z tym samym nazwiskiem, zamieszkałe w tej samej miejscowości, jako ten sam profil. Można określić wyjątek, który nie pasuje do profilów, jeśli imiona w encji, które są łączone, nie są takie same.

1. Przejdź do obszaru **Dane** > **Ujednolicanie** > **Dopasuj** i wybierz pozycję **Edytuj** w regule, do której chcesz dodać warunki.

1. W okienku **Edytuj regułę** wybierz opcję **Dodaj wyjątek**.

1. Określ kryteria wyjątków. 

1. Wybierz **Gotowe**, aby zapisać zasadę.

### <a name="specify-custom-match-conditions"></a>Określanie niestandardowych warunków dopasowania

Można określić warunki zastępowania domyślnej logiki dopasowania. Dostępne są cztery opcje: 

|Opcja  |Description |Przykład  |
|---------|---------|---------|
|Zawsze pasują     | Określa wartości, które są zawsze dopasowane.         |  Zawsze dopasowuje *Mike* i *MikeR*.       |
|Nigdy nie pasują     | Określa wartości, które nigdy nie są dopasowane.        | Nie dopasuje *John* i *Jonathan*.        |
|Obejście niestandardowe     | Określa wartości, które system powinien zawsze ignorować na etapie dopasowania. |  Podczas dopasowania ignoruj wartości *11111* i *Nieznane*.        |
|Mapowanie aliasu    | Zdefiniowanie wartości, które system powinien rozważyć jako tę samą wartość.         | Załóż, że *Joe* jest równe *Joseph*.        |

1. Przejdź do obszaru **Dane** > **Ujednolicanie** > **Dopasuj** i wybierz opcję **Dopasowanie niestandardowe w sekcji** w sekcji **Szczegóły dopasowanych rekordów**.

   :::image type="content" source="media/custom-match-create.png" alt-text="Zrzut ekranu sekcji reguł dopasowania z wyróżnioną kontrolką dopasowania niestandardowego.":::

1. W okienku **Niestandardowe** przejdź do karty **Rekordy**.

1. Z listy rozwijanej **Typ niestandardowy** wybierz opcję dopasowania niestandardowego i wybierz opcję **Pobierz szablon**. Dla każdej opcji dopasowania trzeba mieć osobny szablon.

1. Otwórz pobrany plik szablonu i wypełnij szczegóły. Szablon zawiera pola umożliwiające określenie encji i wartości kluczy podstawowych encji, które mają być używane w dopasowaniu niestandardowym. Na przykład aby klucz podstawowy *12345* z encji *Sprzedaż* zawsze był dopasowany do klucza podstawowego *34567* z encji *Kontakt*, wypełnij szablon:
    - Entity1: Sprzedaż
    - Entity1Key: 12345
    - Encja2: Kontakt
    - Entity2Key: 34567

   Ten sam plik szablonu może zawierać rekordy dopasowania niestandardowego pochodzące z wielu encji.
   
   Jeśli chcesz określić niestandardowe dopasowanie do deduplikacji w encji, podaj tę samą jednostkę, co Entity1 i Entity2, i ustaw różne wartości klucza podstawowego.

1. Po dodaniu wszystkich zastąpień zapisz plik szablonu.

1. Wybierz **Dane** > **Źródła danych** i pobierz pliki szablonów jako nowe encje.

1. Po przekazaniu plików, a kiedy encje są dostępne, należy ponownie wybrać opcję **Dopasowanie niestandardowe**. Zobaczysz opcje służące do określenia encji, które mają zostać uwzględnione. Z menu rozwijanego wybierz wymagane encje i wybierz polecenie **Wykonane**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Zrzut ekranu z oknem dialogowym umożliwiającym wybranie opcji zastępowania scenariusza dopasowania niestandardowego.":::

1. Zastosowanie dopasowania niestandardowego zależy od opcji dopasowania, której chcesz użyć. 

   - W przypadku opcji **Zawsze dopasuj** lub **Nigdy nie dopasuj** przejdź do następnego kroku.
   - W przypadku **Pominięcia niestandardowego** lub **Mapowania aliasu** wybierz **Edytuj** w istniejącej regule dopasowania lub utwórz nową regułę. W liście rozwijanej Normalizacje wybierz opcję **Pominięcie niestandardowe** lub **Mapowanie aliasu** i wybierz **Wykonano**.

1. Wybierz opcję **Zapisz** na stronie **Dopasowanie**, aby zastosować konfigurację dopasowania niestandardowego.

1. Wybierz opcję **Uruchom** na stronie **Dopasowanie**, aby rozpocząć proces dopasowywania. Inne określone reguły dopasowania zostaną zastąpione przez konfigurację dopasowania niestandardowego.

#### <a name="known-issues"></a>Znane problemy

- Samołączenie nie zawiera znormalizowanych danych w jednostkach deduplikacji. Stosuje jednak normalizację wewnętrznie podczas deduplikacji. Jest to normalne i prawidłowe dla wszystkich normalizacji. 
- Jeśli ustawienie typu semantycznego zostanie usunięte na etapie **Mapa** w przypadku, gdy reguła dopasowania używa mapowania aliasu lub niestandardowego pominięcia, normalizacja nie zostanie zastosowana. Dzieje się tak tylko w przypadku, gdy po skonfigurowaniu normalizacji w regule dopasowania zostanie wyczyszczony typ semantyczny, ponieważ będzie on nieznany.


## <a name="next-step"></a>Następny krok

Po zakończeniu procesu dopasowania dla co najmniej jednej pary dopasowania przejdź do kroku [**Scal**](merge-entities.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
