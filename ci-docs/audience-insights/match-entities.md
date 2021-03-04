---
title: Dopasuj encji do ujednolicenia danych
description: Dopasowanie encji w celu utworzenia ujednoliconych profili klientów.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 05afd17b7f1b34f7f24a8fa8cb2dc32c1649d40f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267491"
---
# <a name="match-entities"></a>Dopasowywanie encji

Po zakończeniu fazy mapowania można dopasować swoje encje do własnych potrzeb. Faza dopasowania określa sposób łączenia zestawów danych w ujednolicony zestaw danych profilu klienta. Faza dopasowania wymaga co najmniej [dwóch zamapowanych encji](map-entities.md).

## <a name="specify-the-match-order"></a>Określ kolejność dopasowywania.

Przejdź do opcji **Dane** > **Ujednolicanie** > **Dopasowywanie** i wybierz **Ustaw kolejność** , aby rozpocząć etap dopasowania.

Każde dopasowanie łączy dwie lub więcej encji w jedeną encję, zachowując każdy unikalny rekord klienta. W poniższym przykładzie wybrano trzy encje: **ContactCSV: TestData** jako encja **Podstawowa**, **WebAccountCSV: TestData** jako **Encja 2**, a **CallRecordSmall: TestData** jako **Encja 3**. Diagram nad wybranymi encjami ilustruje sposób wykonywania kolejności dopasowania.

> [!div class="mx-imgBorder"]
> ![Edytowanie kolejności dopasowania danych](media/configure-data-match-order-edit-page.png "Edytowanie kolejności dopasowania danych")
  
Encja **podstawowa** jest dopasowywana do **encji 2**. Zestaw danych występujący w wyniku pierwszego dopasowania jest zgodny z **encją 3**.
W tym przykładzie wybrano tylko dwa dopasowania, ale system może obsłużyć więcej.

> [!IMPORTANT]
> Encja wybrana jako encja **podstawowa** będzie służyć jako podstawa dla ujednoliconego głównego zestawu danych. Do tej encji zostaną dodane dodatkowe encje wybrane podczas fazy dopasowania. W tym samym czasie nie oznacza to, że ujednolicona encja będzie zawierać *wszystkie* dane zawarte w tej encji.
>
> Istnieją dwa kwestie, które mogą pomóc w wyborze hierarchii encji:
>
> - Jakie encje uznaje się za posiadające najpełniejsze i wiarygodne dane dotyczące klientów?
> - Czy zidentyfikowana encja ma atrybuty, które są również współużytkowane przez inne encje (np. imię, numer telefonu lub adres e-mail)? Jeśli nie, wybierz drugą w kolejności najbardziej niezawodną encję.

Wybierz **Gotowe**, aby zapisać pasującą kolejność.

## <a name="define-rules-for-your-first-match-pair"></a>Definiowanie reguł dla pierwszej pary dopasowania

Po określeniu kolejności dopasowania na stronie **Dopasowania** będą widoczne zdefiniowane dopasowania. Kafelki w górnej części ekranu będą puste, dopóki nie zostanie wykonane określenie kolejności dopasowania.

> [!div class="mx-imgBorder"]
> ![Definiuj reguły](media/configure-data-match-need-rules.png "Definiuj reguły")

Ostrzeżenie **Wymaga reguł** sugeruje, że reguła dopasowania nie jest zdefiniowana na parę dopasowania. Reguły dopasowania określają logikę, według której będzie dopasowywana określona para encji.

1. Aby zdefiniować pierwszą regułę, otwórz okienko **Definicji reguły**, wybierając odpowiedni wiersz dopasowania w tabeli dopasowania (1), a następnie wybierz pozycję **Utwórz nową regułę** (2).

   > [!div class="mx-imgBorder"]
   > ![Utwórz nową regułę](media/configure-data-match-new-rule2.png "Utwórz nową regułę")

2. W okienku **Edytuj regułę** skonfiguruj warunki tej reguły. Każdy warunek jest reprezentowany przez dwa wiersze, które zawierają obowiązkowe wybory.

   > [!div class="mx-imgBorder"]
   > ![Okienko nowej reguły](media/configure-data-match-new-rule-condition.png "Okienko nowej reguły")

   Encja/pole (pierwsze) — atrybut, który będzie używany do dopasowywania z encji pierwszego dopasowania. Przykłady mogą zawierać numery telefonów lub adresy e-mail. Wybierz atrybut, który może być unikatowy dla klienta.

   > [!TIP]
   > Należy unikać dopasowywania na podstawie atrybutów typu działania. Innymi słowy, jeśli atrybut wygląda na działanie, może to oznaczać, że kryteria są zbyt słabe, aby według nich dopasowywać.  

   Encja/pole (drugie) — atrybut, który będzie używany do dopasowywania z encji frugiego dopasowania.

   Normalizuj - **Metoda normalizacji**: dla wybranych atrybutów są dostępne różne opcje normalizacji. Na przykład usuwanie znaków interpunkcyjnych i usuwanie spacji

   W przypadku normalizacji nazwy organizacji (podgląd) można również wybrać **Typ (telefon, nazwa, organizacja)**.

   > [!div class="mx-imgBorder"]
   > ![Normalizacja — B2B](media/match-normalization-b2b.png "Normalizacja — B2B")

   Poziom dokładności — poziom dokładnooci, który będzie używany dla tego warunku. Ustawienie poziomu dokładności dla warunku dopasowywania może mieć dwa typy: **podstawowe** i **niestandardowe**.  
   - Podstawowe: umożliwia wybór następujących opcji: niski, średni, wysoki i dokładny. Wybierz **Dokładny**, aby dopasować tylko te rekordy, które odpowiadają wartościom w 100 procentach. Wybierz jeden z pozostałych poziomów w celu dopasowania do rekordów, które nie są w 100 procentach identyczne.
   - Niestandardowa: użyj suwaka do zdefiniowania niestandardowego procentu, który musi być zgodny z rekordem, lub wprowadź wartość w polu **Niestandardowe**. System będzie dopasowywać tylko te rekordy, które przekraczają próg jako połączone pary dopasowań. Wartości na suwaku są wartościami z zakresu od 0 do 1. Więc 0,64 reprezentuje 64 procent.

3. Wybierz **Gotowe**, aby zapisać zasadę.

### <a name="add-multiple-conditions"></a>Dodawanie wielu warunków

Aby dopasować encje tylko wtedy, gdy są spełnione różne warunki, należy dodać więcej warunków połączonych za pośrednictwem operatora AND.

1. W okienku **Edytuj regułę** wybierz pozycję **Dodaj warunek**. Warunki można również usunąć, wybierając przycisk Usuń znajdujący się obok istniejącego warunku.

2. Wybierz **Gotowe**, aby zapisać zasadę.

## <a name="add-multiple-rules"></a>Dodawanie wielu reguł

Każdy warunek ma zastosowanie do pojedynczej pary atrybutów, podczas gdy reguły reprezentują zbiory warunków. Aby obiekty odpowiadały różnym zestawom atrybutów, można dodać więcej reguł.

1. W analizach odbiorców przejdź do **Dane** > **Ujednolicanie** > **Dopasowywanie**.

2. Wybierz encję, którą chcesz aktualizować i wybierz **Dodaj reguły**.

3. Postępuj zgodnie z procedurą opisaną w sekcji [Definiowanie reguł dla pierwszej pary dopasowania](#define-rules-for-your-first-match-pair).

> [!NOTE]
> Kolejność reguł ma znaczenie. Algorytm dopasowywania usiłuje tworzyć dopasowania na podstawie pierwszej reguły i przechodzić do drugiej reguły tylko wtedy, gdy w ramach pierwszej reguły nie wskazano żadnych dopasowań.

## <a name="define-deduplication-on-a-match-entity"></a>Definiowanie deduplikacji dla encji dopasowania

Oprócz określania reguł dopasowywania między podmiotami, jak opisano w powyższych sekcjach, można również określić reguły deduplikacji. *Deduplikacja* jest procesem. Identyfikuje zduplikowane rekordy, łączy je w jeden rekord i łączy wszystkie rekordy źródłowe z tym scalonym rekordem z alternatywnymi identyfikatorami do scalonego rekordu.

Po zidentyfikowaniu zdeduplikowanego rekordu zostanie on użyty w procesie dopasowywania między encjami. Deduplikacja jest implementowana na poziomie jednostki i może być stosowana do każdej jednostki używanej w procesie dopasowywania.

### <a name="add-deduplication-rules"></a>Dodaj reguły deduplikacji

1. W analizach odbiorców przejdź do **Dane** > **Ujednolicanie** > **Dopasowywanie**.

1. W sekcji **Scal duplikaty** wybierz opcję **Ustaw encje**.

1. W sekcji **Preferencje scalania** wybierz encje, do których chcesz zastosować deduplikację.

1. Określ sposób scalania zduplikowanych rekordów i wybierz jedną z trzech opcji scalania:
   - *Najczęściej wypełnione*: Identyfikuje rekord z największą liczbą wypełnionych atrybutów jako rekord zwycięzcy. To jest opcja domyślna scalania.
   - *Najnowsze*: Identyfikuje rekord zwycięzcy na podstawie aktualności. Wymaga daty lub pola liczbowego do zdefiniowania aktualności.
   - *Najstarsze*: Identyfikuje rekord zwycięzcy na podstawie najmniejszej aktualności. Wymaga daty lub pola liczbowego do zdefiniowania aktualności.
 
   > [!div class="mx-imgBorder"]
   > ![Reguły deduplikacji krok 1](media/match-selfconflation.png "Reguły deduplikacji krok 1")
 
1. Po wybraniu encji i ich preferencjach scalania wybierz opcję **Utwórz nową regułę** w celu zdefiniowania reguł deduplikacji na poziomie encji.
   - **Zaznacz pole** powoduje wyświetlenie listy wszystkich dostępnych pól z tej encji, dla których chcesz usunąć duplikaty danych źródłowych.
   - Określ ustawienia normalizacji i precyzji we wskazany sposób zgodnie z dopasowaniem między encjami krzyżowymi.
   - Dodatkowe warunki można zdefiniować, zaznaczając opcję **Dodaj warunek**.
 
   > [!div class="mx-imgBorder"]
   > ![Reguły deduplikacji krok 2](media/match-selfconflation-rules.png "Reguły deduplikacji krok 2")

  Dla encji można utworzyć wiele reguł deduplikacji. 

1. Uruchomienie procesu dopasowywania powoduje teraz grupowanie rekordów na podstawie warunków zdefiniowanych w regułach deduplikacji. Po zgrupowaniu rekordów stosowane są zasady scalania, aby zidentyfikować rekord zwycięzcy.

1. Ten rekord zwycięzcy jest następnie przekazywany do dopasowania między obiektami, razem z rekordami zwycięzcy (na przykład alternatywnymi identyfikatorami), aby poprawić jakość dopasowania.

1. Dowolne niestandardowe reguły dopasowania, które zdefiniowano jako kryterium zgodności i nigdy nie odpowiadają regułom deduplikacji z regułami. Jeśli reguła deduplikacji identyfikuje pasujące rekordy, a niestandardowa reguła dopasowania jest ustawiona tak, aby nigdy nie pasować do tych rekordów, te dwa rekordy nie zostaną dopasowane.

1. Po uruchomieniu procesu dopasowywania zostanie wyświetlona statystyka deduplikacji.
   
> [!NOTE]
> Określenie reguł deduplikacji nie jest obowiązkowe. Jeśli żadne reguły nie są skonfigurowane, stosowane są reguły zdefiniowane w systemie. Zwijają wszystkie rekordy, które mają tę samą kombinację wartości (dopasowanie ścisłe) z klucza podstawowego i pól w regułach dopasowywania w jeden rekord przed przekazaniem danych encji do dopasowania między encjami w celu zwiększenia wydajności i sprawności systemu.

## <a name="run-your-match-order"></a>Uruchom kolejność dopasowania

Po zdefiniowaniu reguł dopasowania, w tym reguł dopasowania między encjami i reguł deduplikacji, można uruchomić kolejność dopasowania. Na stronie **Dopasowywanie** wybierz opcję **Uruchom**, aby rozpocząć proces. Wykonanie algorytmu dopasowywania może zająć dużo czasu. Nie można zmienić właściwości na stronie **Dopasowywanie** do czasu zakończenia procesu dopasowywania. Można znaleźćencję ujednoliconego profilu klienta, która została utworzona na stronie **encji**. Twoja ujednolicona encja klienta nosi nazwę **ConflationMatchPairs : CustomerInsights**.

Aby dokonać dodatkowych zmian i ponownie uruchomić krok, można anulować pasujący element w toku. Wybierz tekst **Odświeżanie...** i wybierz **Anuluj zadanie** u dołu wyświetlonego okienka bocznego.

Po zakończeniu procesu dopasowywania tekst **Odświeżanie...** zostanie zmieniony na **Sukces** i ponownie będzie można korzystać z wszystkich funkcji strony.

W pierwszym procesie dopasowywania powstaje ujednolicona encja główna. Każde następne uruchomienie powoduje rozszerzenie tej encji.

> [!TIP]
> Istnieje [sześć typów stanu](system.md#status-types) zadań/procesów. Ponadto większość procesów [zależy od innych procesów podrzędnych](system.md#refresh-policies). Istnieje możliwość wybrania stanu procesu w celu wyświetlenia szczegółowych informacji o postępie w całym zadaniu. Po wybraniu opcji **Zobacz szczegółowe informacje** dla jednego z zadań zadania, można znaleźć więcej informacji: czas przetwarzania, Data ostatniego przetwarzania oraz wszystkie błędy i ostrzeżenia skojarzone z zadaniem.

## <a name="deduplication-output-as-an-entity"></a>Deduplikacja wyjściowa jako encja
Oprócz ujednoliconej jednostki głównej utworzonej w ramach dopasowywania między obiektami, proces deduplikacji generuje również nową jednostkę dla każdej jednostki z kolejności dopasowania, aby zidentyfikować zdeduplikowane rekordy. Te encje można znaleźć razem z elementem **ConftronicMatchPpias:CustomerInsights** w sekcji **System** na stronie **Encje** i **Deduplication_Datasource_Entity**.

Obiekt wyjściowy deduplikacji zawiera następujące informacje:
- Identyfikatory/klucze
  - Pole klucza podstawowego i jego inne pole identyfikatorów. Pole Alternatywne identyfikatory zawiera wszystkie alternatywne identyfikatory zidentyfikowane dla rekordu.
  - Pole Deduplication_GroupId przedstawia grupę lub klaster zidentyfikowaną w ramach jednostki, która grupuje wszystkie podobne rekordy na podstawie określonych pól deduplikacji. Te dane są używane do przetwarzania w systemie. Jeśli nie określono reguł ręcznej deduplikacji i mają zastosowanie reguły deduplikacji zdefiniowane przez system, to pole może nie być dostępne w jednostce wyjściowej deduplikacji.
  - Deduplication_WinnerId: To pole zawiera identyfikator zwycięzcy ze zidentyfikowanych grup lub klastrów. Jeśli Deduplication_WinnerId jest taki sam jak wartość klucza podstawowego dla rekordu, oznacza to, że rekord jest rekordem zwycięzcy.
- Pola używane do definiowania reguł deduplikacji.
- Pola Reguła i Wynik określające, które z reguł deduplikacji zostały zastosowane, oraz wynik zwracany przez algorytm dopasowujący.

## <a name="review-and-validate-your-matches"></a>Przejrzyj i zweryfikuj swoje dopasowania

Oceń jakość swoich par dopasowania i udoskonal ją:

- Na stronie **Dopasowywanie** znajdują się dwa kafelki pokazujące początkowe informacje na temat danych.

  - **Unikatowi klienci**: pokazuje liczbę unikatowych profilów zidentyfikowanych przez system.
  - **Dopasowane rekordy**: pokazuje liczbę dopasowanych elementów we wszystkich parach dopasowania.

- W tabeli **Kolejność dopasowywania** można ocenić wyniki poszczególnych par dopasowań, porównując liczbę rekordów pochodzących z tej encji dopasowania z udziałem procentu dopasowanych rekordów.

- W sekcji **Reguły** encji w tabeli **Kolejność dopasowywania** można sprawdzić, czy na poziomie reguły procent pomyślnie dopasowanych rekordów na poziomie reguły. Zaznaczając symbol tabeli obok reguły, można wyświetlić wszystkie te rekordy na poziomie reguły. Zaleca się przejrzenie podzbioru rekordów w celu zweryfikowania, czy zostały poprawnie dopasowane.

- Eksperymentuj z różnymi progami dokładności, w celu zidentyfikowania optymalnej wartości.

  1. Wybierz wielokropek (...), dla reguły pary dopasowań, z którą chcesz poeksperymentować, a następnie wybierz pozycję **Edytuj**.

  2. Wybierz warunek, z którym chcesz eksperymentować. Każde kryterium jest reprezentowane jako jeden wiersz w okienku **Reguła dopasowywania**.

  3. Dane wyświetlone na stronie **Podgląd kryteriów** zależą od poziomu dokładności wybranego dla warunku. Znajdź liczbę dopasowanych i niedopasowanych rekordów dla wybranego warunku.

     Należy zapoznać się ze skutkami różnych poziomów progu. Można porównywać liczbę rekordów, które mają być dopasowane pod każdym poziomem progu, oraz wyświetlić rekordy w każdej opcji. Zaznacz poszczególne kafelki i przejrzyj dane w sekcji tabeli.

## <a name="optimize-your-matches"></a>Optymalizowanie dopasowania

Zwiększanie jakości dzięki ponownemu konfigurowaniu niektórych parametrów dopasowywania:

- Aby **zmienić kolejność dopasowywania**, wybierz pozycję **Edytuj** i zmień pola kolejności dopasowywania.

  > [!div class="mx-imgBorder"]
  > ![Edytowanie kolejności dopasowywania danych](media/configure-data-match-order-edit.png "Edytowanie kolejności dopasowywania danych")

- **Zmień kolejność reguł** w przypadku zdefiniowania wielu reguł. Aby zmienić kolejność reguł dopasowania, należy wybrać opcje **Przenieś w górę** i **Przenieś w dół** na siatce reguł dopasowywania.

  > [!div class="mx-imgBorder"]
  > ![Zmień kolejność reguł](media/configure-data-change-rule-order.png "Zmień kolejność reguł")

- **Skopiuj reguły**, jeśli zdefiniowałeś regułę dopasowania i chcesz utworzyć podobną regułę z modyfikacjami. W tym celu należy wybrać opcję **Duplikuj**.

  > [!div class="mx-imgBorder"]
  > ![Duplikuj regułę](media/configure-data-duplicate-rule.png "Duplikuj regułę")

- **Zdezaktywuj regułę**, aby zachować regułę dopasowania, wykluczając ją z procesu dopasowania.

  > [!div class="mx-imgBorder"]
  > ![Dezaktywuj regułę](media/configure-data-deactivate-rule.png "Dezaktywuj regułę")

- **Dokonaj edycji reguł**, wybierając symbol **Edytuj**. Można również zastosować następujące zmiany:

  - Zmiana atrybutów warunku: Wybierz nowe atrybuty w wierszu określonego warunku.
  - Zmiana progu warunku: Dopasuj suwak dokładności.
  - Zmiana metody normalizacji warunku: aktualizowanie metody normalizacji.

## <a name="specify-your-custom-match-records"></a>Określanie niestandardowych rekordów dopasowania

Możesz określić warunki, według których określone rekordy powinny zawsze pasować lub nigdy nie pasować. Te reguły można przesłać zbiorczo do procesu dopasowania.

1. Wybierz opcję **Dopasowanie niestandardowe** na ekranie **Kolejność dopasowywania**.

   > [!div class="mx-imgBorder"]
   > ![Tworzenie dopasowania niestandardowego](media/custom-match-create.png "Tworzenie dopasowania niestandardowego")

2. Jeśli nie ma żadnych przekazanych encji, zostanie wyświetlone nowe okno dialogowe **Dopasowania niestandardowego**, w którym należy podać niektóre informacje. Jeśli te informacje zostały podane wcześniej, przejdź do kroku 8.

   > [!div class="mx-imgBorder"]
   > ![Nowe okno dialogowe dopasowania niestandardowego](media/custom-match-new-dialog-box.png "Nowe okno dialogowe dopasowania niestandardowego")

3. Zaznacz **Wypełnij szablon**, aby uzyskać plik szablonu, który określa, które rekordy z których encji powinny zawsze pasować lub nigdy nie pasować. Konieczne będzie oddzielne wypełnienie rekordów „zawsze pasuje” i „nigdy nie pasuje” w dwóch różnych plikach.

4. Szablon zawiera pola umożliwiające określenie encji i wartości kluczy podstawowych encji, które mają być używane w dopasowaniu niestandardowym. Jeśli na przykład klucz podstawowy 12345 od encji sprzedaży będzie zawsze odpowiadał danemu kluczowi podstawowemu 34567 z encji kontaktu, należy określić to w następujący sposób:
    - Entity1: Sprzedaż
    - Entity1Key: 12345
    - Encja2: Kontakt
    - Entity2Key: 34567

   Ten sam plik szablonu może zawierać rekordy dopasowania niestandardowego pochodzące z wielu encji.
   
   Jeśli chcesz określić niestandardowe dopasowanie do deduplikacji w encji, podaj tę samą jednostkę, co Entity1 i Entity2, i ustaw różne wartości klucza podstawowego.

5. Po dodaniu wszystkich zastąpień, które chcesz zastosować, zapisz plik szablonu.

6. Wybierz **Dane** > **Źródła danych** i pobierz pliki szablonów jako nowe encje. Po pobraniu można za ich pomocą określić konfigurację dopasowania.

7. Po przekazaniu plików, a kiedy encje są dostępne, należy ponownie wybrać opcję **Dopasowanie niestandardowe**. Zobaczysz opcje służące do określenia encji, które mają zostać uwzględnione. Wybierz wymagane elementy z menu rozwijanego.

   > [!div class="mx-imgBorder"]
   > ![Zastąpienia dopasowania niestandardowego](media/custom-match-overrides.png "Zastąpienia dopasowania niestandardowego")

8. Wybierz encje, które mają być używane do **Zawsze pasują** i **Nigdy nie pasują**, wybierz **Gotowe**.

9. Wybierz opcję **Zapisz** na stronie **Dopasowywanie** dla konfiguracji niestandardowego dopasowania, która została właśnie skonfigurowana.

10. Wybierz polecenie **Uruchom** na stronie **Dopasowywanie**, aby rozpocząć proces dopasowywania, a konfiguracja dopasowania niestandardowego zostanie zastosowana. Wszystkie systemowe reguły dopasowania zostaną zastąpione przez zestaw konfiguracyjny.

11. Po zakończeniu dopasowywania można sprawdzić encję **ConflationMatchPair**, aby potwierdzić, że zastąpienia są stosowane w połączonych dopasowaniach.

## <a name="next-step"></a>Następny krok

Po zakończeniu procesu dopasowania dla co najmniej jednej pary dopasowań może dojść do rozstrzygnięcia możliwych zachodzących sprzeczności w danych za pośrednictwem tematu [**Scal**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]