---
title: Przewidywanie odpływu transakcji (Wideo)
description: Przewiduj, czy klient jest zagrożony, jeśli przestanie kupować Twoje produkty lub usługi.
ms.date: 10/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: ad87e0fd848168d1a18f28f2ac5c507bb01e1f28
ms.sourcegitcommit: 12910882ca990ec0e890ed4deaf3dac7e01621e5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/10/2021
ms.locfileid: "7904085"
---
# <a name="transaction-churn-prediction-preview"></a>Przewidywanie rezygnacji z transakcji (wersja zapoznawcza)

Prognozowanie rezygnacji z transakcji pomaga przewidzieć, czy klient nie będzie już kupować Twoich produktów lub usług w danym oknie czasowym. Nowe przewidywania mogą być tworzone w **Analizy** > **Przewidywania**. Wybierz **Moje przewidywania**, aby wyświetlić inne utworzone przewidywania. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

W środowiskach opartych na kontach biznesowych można przewidywać rezygnację z transakcji klienta oraz kombinację konta i innego poziomu informacji, takich jak kategoria produktu. Dodanie wymiarów może pomóc w określeniu, na ile prawdopodobne jest, że klient „Contoso” przestanie kupować kategorię produktów „materiały biurowe”. W przypadku kont biznesowych możemy również użyć AI do wygenerowania listy potencjalnych przyczyn, dla których konto jest zagrożone dla kategorii informacji na poziomie pomocniczym.

> [!TIP]
> Wypróbuj samouczek dotyczący przewidywania rezygnacji z transakcji używający przykładowych danych: [Przykład przewidywania rezygnacji z transakcji (wersja zapoznawcza) — przewodnik](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Wymagania wstępne

# <a name="individual-consumers-b-to-c"></a>[Klienci indywidualni (B2C)](#tab/b2c)

- Co najmniej [Uprawnienia współautora](permissions.md) w Customer Insights.
- Wiedza biznesowa, pozwalająca zrozumieć co rezygnacja oznacza dla Twojej działalności. Obsługujemy definicje rezygnacji na podstawie czasu, co oznacza, że klient odszedł po okresie braku zakupów.
- Dane o transakcjach/zakupach oraz ich historii:
    - Identyfikatory transakcji w celu rozróżnienia zakupionych/transakcji.
    - Identyfikatory klientów, aby odpowiadały transakcjom klientów.
    - Daty zdarzeń transakcji, które określają daty, w których doszło do transakcji.
    - Schemat danych semantycznych dla operacji zakupu/transakcji wymaga następujących informacji:
        - **Identyfikator transakcji**: unikatowy identyfikator zakupu lub transakcji.
        - **Data transakcji**: data zakupu lub transakcji.
        - **Wartość transakcji**: kwota waluty/wartości liczbowej transakcji/pozycji.
        - (Opcjonalnie) **Unikatowy identyfikator produktu**: identyfikator zakupionego produktu lub usługi, jeśli dane są na poziomie pozycji wiersza.
        - (Opcjonalnie) **Czy ta transakcja była zwrotem**: pole typu prawda/fałsz, które określa, czy transakcja była zwrotna, czy nie. Jeśli **Wartość transakcji** jest ujemna, Microsoft będzie również używać tych informacji do wywnioskowania, że nastąpił zwrot.
- (Opcjonalnie) Dane o działaniach klientów:
    - Identyfikatory działań w celu wyróżnienia działań tego samego typu.
    - Identyfikatory klientów, umożliwiające mapowanie działań do klientów.
    - Informacje o działaniu zawierające nazwę i datę działania.
    - Schemat danych semantycznych dla działań klientów zawiera:
        - **Klucz podstawowy:** Unikatowy identyfikator działania. Na przykład wizyta w witrynie internetowej lub zapis użytkowania pokazujący, że klient wypróbował próbkę Twojego produktu.
        - **Sygnatura czasowa:** Data i godzina zdarzenia identyfikowanego przez klucz podstawowy.
        - **Zdarzenie:** Określ nazwę zdarzenia, które chcesz użyć. Na przykład pole o nazwie „UserAction” w sklepie spożywczym może być kuponem używanym przez klienta.
        - **Szczegóły:** Szczegółowe informacje o zdarzeniu. Na przykład pole o nazwie „CouponValue” w sklepie spożywczym może zawierać walutę kuponu.

# <a name="business-accounts-b-to-b"></a>[Klienci biznesowi (B2B)](#tab/b2b)

- Co najmniej [Uprawnienia współautora](permissions.md) w Customer Insights.
- Wiedza biznesowa, pozwalająca zrozumieć co rezygnacja oznacza dla Twojej działalności. Obsługujemy definicje rezygnacji na podstawie czasu, co oznacza, że klient odszedł po okresie braku zakupów.
- Dane o transakcjach/zakupach oraz ich historii:
    - Identyfikatory transakcji w celu rozróżnienia zakupionych/transakcji.
    - Identyfikatory klientów, aby odpowiadały transakcjom klientów.
    - Daty zdarzeń transakcji, które określają daty, w których doszło do transakcji.
    - Schemat danych semantycznych dla operacji zakupu/transakcji wymaga następujących informacji:
        - **Identyfikator transakcji**: unikatowy identyfikator zakupu lub transakcji.
        - **Data transakcji**: data zakupu lub transakcji.
        - **Wartość transakcji**: kwota waluty/wartości liczbowej transakcji/pozycji.
        - (Opcjonalnie) **Unikatowy identyfikator produktu**: identyfikator zakupionego produktu lub usługi, jeśli dane są na poziomie pozycji wiersza.
        - (Opcjonalnie) **Czy ta transakcja była zwrotem**: pole typu prawda/fałsz, które określa, czy transakcja była zwrotna, czy nie. Jeśli **Wartość transakcji** jest ujemna, Microsoft będzie również używać tych informacji do wywnioskowania, że nastąpił zwrot.
- (Opcjonalnie) Dane o działaniach klientów:
    - Identyfikatory działań w celu wyróżnienia działań tego samego typu.
    - Identyfikatory klientów, umożliwiające mapowanie działań do klientów.
    - Informacje o działaniu zawierające nazwę i datę działania.
    - Schemat danych semantycznych dla działań klientów zawiera:
        - **Klucz podstawowy:** Unikatowy identyfikator działania. Na przykład wizyta w witrynie internetowej lub zapis użytkowania pokazujący, że klient wypróbował próbkę Twojego produktu.
        - **Sygnatura czasowa:** Data i godzina zdarzenia identyfikowanego przez klucz podstawowy.
        - **Zdarzenie:** Określ nazwę zdarzenia, które chcesz użyć. Na przykład pole o nazwie „UserAction” w sklepie spożywczym może być kuponem używanym przez klienta.
        - **Szczegóły:** Szczegółowe informacje o zdarzeniu. Na przykład pole o nazwie „CouponValue” w sklepie spożywczym może zawierać walutę kuponu.
- (Opcjonalnie) Dane o klientach:
    - Te dane powinny być zgodne z bardziej statycznymi atrybutami, aby zapewnić najlepsze wyniki w modelu.
    - Schemat danych semantycznych dla danych klienta obejmuje:
        - **Identyfikator klienta:** unikatowy identyfikator klienta.
        - **Data utworzenia:** data początkowego dodania klienta.
        - **Województwo:** lokalizacja województwa klienta.
        - **Kraj:** kraj klienta.
        - **Branża:** typ branży klienta. Na przykład pole o nazwie „Branża” dla ekspresu do kawy może wskazywać, czy był to klient sprzedaży detalicznej.
        - **Klasyfikacja:** kategoryzowanie klienta na potrzeby firmy. Na przykład pole o nazwie „ValueSegment” w ekspresie do kawy może być warstwą klienta w zależności od wielkości klienta.

---

- Sugerowana charakterystyka danych:
    - Wystarczające dane historyczne: dane transakcji dla co najmniej podwójnego wybranego okna czasowego. Najlepiej, dwa do trzech lat historii transakcji. 
    - Wiele zakupów na klienta: idealnie przynajmniej dwie transakcje na klienta.
    - Liczba klientów: co najmniej 10 profilów klientów, najlepiej ponad 1000 unikalnych klientów. Model zakończy z niepowodzeniem, jeśli będzie mniej niż 10 klientów oraz niewystarczające dane historycznych.
    - Pełność danych: mniej niż 20% brakujących wartości w polu danych dostarczonej encji.

> [!NOTE]
> W przypadku działalności o wysokiej częstotliwości zakupów u klientów (co kilka tygodni) zaleca się wybranie krótszego okna przewidywania i definicji rezygnacji. W przypadku niskiej częstotliwości zakupu (co kilka miesięcy lub raz do roku), wybierz dłuższy przewidywania i definicji rezygnacji.

## <a name="create-a-transaction-churn-prediction"></a>Tworzenie przewidywania rezygnacji z transakcji

1. W Customer Insights przejdź do **Analizy** > **Przewidywania**.

1. Wybierz kafelek **Model rezygnacji klientów (wersja zapoznawcza)** i wybierz opcję **Użyj tego modelu**.

1. W okienku **Model rezygnacji klienta** wybierz opcję **Transakcja** i wybierz opcję **Rozpocznij**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Zrzut ekranu z wybraną opcją transakcji w okienku modelu rezygnacji klienta.":::

### <a name="name-model"></a>Nadaj nazwę modelowi

1. Podaj nazwę modelu odróżniającą go od innych modeli.

1. Podaj nazwę encji wyjściowej używając wyłącznie liter i cyfr, bez żadnych spacji. To jest nazwa, której będzie używać encja modelowa. 

1. Wybierz **Dalej**.

### <a name="define-customer-churn"></a>Definiuj rezygnację klienta

1. Ustaw przedział dni na prognozowanie rezygnacji w polu **Zidentyfikuj klientów, którzy mogą odejść w następnym**. Na przykład prognozuj ryzyko odejścia klientów w ciągu najbliższych 90 dni, aby dostosować się do działań marketingowych dotyczących utrzymania klientów. Przewidywanie ryzyka odejścia na dłuższy lub krótszy okres może utrudnić uwzględnienie czynników w profilu ryzyka odejścia, ale zależy to od konkretnych wymagań biznesowych.
   >[!TIP]
   > W dowolnym momencie możesz wybrać **Zapisz i zamknij**, aby zapisać przewidywanie jako wersję roboczą. Aby kontynuować, należy znaleźć przewidywanie w wersji roboczej na karcie **Moje przewidywania**.

1. Wprowadź liczbę dni do zdefiniowania rezygnacji w polu **Klient odszedł, jeśli nie dokonał zakupów w:**. Na przykład, jeśli klient nie dokonał zakupów w ciągu ostatnich 30 dni, może zostać uznany za klienta, który zrezygnował, w przypadku Twojej firmy. 

1. Wybierz **Dalej**, aby kontynuować.

### <a name="add-required-data"></a>Dodaj wymagane dane

1. Wybierz opcję **Dodaj dane** i wybierz typ działania w okienku bocznym zawierającym wymagane informacje o historii transakcji lub zakupów.

1. W obszarze **Wybierz działania** wybierz określone działania z wybranego działania, na których chcesz skupić się podczas obliczania.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Okienko boczne po stronie przedstawiające wybranie określone działania w ramach typu semantycznego.":::

1. Jeśli działanie nie zostało jeszcze zamapowane na typ semantyczny, wybierz opcję **Edytuj**, aby to zrobić. Zostanie otwarte środowisko nadzorowane służące do mapowania działań semantycznych. Zamapuj swoje dane na odpowiednie pola w wybranym typie działania.

   :::image type="content" source="media/product-recommendation-set-activity-type.PNG" alt-text="Typ działania ustawienia strony.":::

1. Po zamapowaniu działania na odpowiedni typ semantyczny, wybierz opcję **Dalej**, aby kontynuować

1. Zamapuj atrybuty semantyczne na pola wymagane do uruchomienia modelu. Jeśli poniższe pola nie są wypełnione, skonfiguruj relację z encji historii zakupu do encji *Klient*.

1. Wybierz **Dalej**.

# <a name="individual-consumers-b-to-c"></a>[Klienci indywidualni (B2C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Dodawanie dodatkowych danych (opcjonalnie)

Skonfiguruj relację z encji działania klienta z encją *Klient*.

1. Wybierz pole, które identyfikuje klienta w tabeli aktywności klientów. Może być bezpośrednio powiązany z głównym identyfikatorem *Klienta* encji klienta.

1. Wybierz encję, która jest podstawową encją *Klient*.

1. Wprowadź nazwę, która opisuje relację.

#### <a name="customer-activities"></a>Działania klienta

1. Możesz też wybrać pozycję **Dodaj dane** do **Działań klienta**.

1. Wybierz typ działania semantycznego, który zawiera dane, których chcesz użyć, a następnie zaznacz jedno lub więcej działań w sekcji **Działania**.

1. Wybierz typ działania odpowiadający typowi działania klienta, które konfigurujesz. Wybierz opcję **Utwórz nowy** i wybierz dostępny typ działania lub utwórz nowy typ.

1. Wybierz opcję **Dalej**, a następnie **Zapisz**.

1. Jeśli istnieją inne działania dotyczące klientów, które mają zostać uwzględnione, powtórz te kroki.

# <a name="business-accounts-b-to-b"></a>[Klienci biznesowi (B2B)](#tab/b2b)

### <a name="select-prediction-level"></a>Wybieranie poziomu przewidywania

Większość przewidywań jest tworzona na poziomie klienta. W niektórych przypadkach może to nie być na tyle szczegółowe, aby zaspokoić potrzeby firmy. Tej funkcji można użyć na przykład do przewidywania dla gałęzi klienta, a nie dla klienta jako całości.

1. Aby utworzyć przewidywanie na poziomie bardziej szczegółowym niż klient, wybierz pozycję **Wybierz encję dla poziomu pomocniczego**. Jeśli ta opcja nie jest dostępna, upewnij się, że poprzednia sekcja została zakończona.

1. Rozwiń encje, z których chcesz wybrać poziom pomocniczy, lub użyj pola filtru wyszukiwania w celu odfiltrowania wybranych opcji.

1. Wybierz atrybut, który ma być używany jako poziom pomocniczy, a następnie wybierz opcję **Dodaj**.

1. Wybierz **Dalej**.

> [!NOTE]
> Encje dostępne w tej sekcji są wyświetlane, ponieważ mają relację z encją wybraną w poprzedniej sekcji. Jeśli nie widzisz encji, którą chcesz dodać, upewnij się, że jest w niej prawidłowa relacja w obszarze **Relacje**. W przypadku tej konfiguracji można obowiązuje tylko relacja jeden-do-jednego i wiele-do-jednego.

### <a name="add-additional-data-optional"></a>Dodawanie dodatkowych danych (opcjonalnie)

Skonfiguruj relację z encji działania klienta z encją *Klient*.

1. Wybierz pole, które identyfikuje klienta w tabeli aktywności klientów. Może być bezpośrednio powiązany z głównym identyfikatorem *Klienta* encji klienta.

1. Wybierz encję, która jest podstawową encją *Klient*.

1. Wprowadź nazwę, która opisuje relację.

#### <a name="customer-activities"></a>Działania klienta

1. Możesz też wybrać pozycję **Dodaj dane** do **Działań klienta**.

1. Wybierz typ działania semantycznego, który zawiera dane, których chcesz użyć, a następnie zaznacz jedno lub więcej działań w sekcji **Działania**.

1. Wybierz typ działania odpowiadający typowi działania klienta, które konfigurujesz. Wybierz opcję **Utwórz nowy** i wybierz dostępny typ działania lub utwórz nowy typ.

1. Wybierz opcję **Dalej**, a następnie **Zapisz**.

1. Jeśli istnieją inne działania dotyczące klientów, które mają zostać uwzględnione, powtórz te kroki.

#### <a name="customers-data"></a>Dane klientów

1. Opcjonalnie wybierz opcję **Dodaj dane** dla obszaru **Dane klientów**.

1. Mapuj atrybuty semantyczne na pola własnych danych zidentyfikowanych klientów. Dane w używanych polach nie powinny często się zmieniać, aby zapewnić najlepsze wyniki w modelu. Na przykład wybranie pola „Klasyfikacja”, które zmienia się co miesiąc, będzie zawierać tylko ostatnią wartość używaną w przewidywaniu, nawet jeśli w przeszłości ta sama wartość nie była stosowana dla klienta podczas tworzenia wzorców przewidywania.

1. Wybierz **Dalej**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Podaj opcjonalną listę kont porównawczych

Dodaj listę klientów biznesowych i kont, których chcesz użyć jako testów porównawczych. Zobaczysz [szczegółowe informacje dotyczące tych kont porównawczych](#review-a-prediction-status-and-results), w tym wynik dotyczący rezygnacji i większość funkcji, które wpływały na przewidywanie ich rezygnacji.

1. Wybierz **+ Dodaj klientów**.

1. Wybierz klientów, którzy pełnią rolę testu porównawczego.

1. Wybierz **Dalej**, aby kontynuować.

---

### <a name="set-schedule-and-review-configuration"></a>Konfigurowanie harmonogramu i przeglądu konfiguracji

1. Ustaw częstotliwość ponownego uczenia modelu. To ustawienie jest ważne, aby zaktualizować dokładność prognoz w miarę pozyskiwania nowych danych. Większość firm może przeprowadzać ponowne szkolenia raz w miesiącu i uzyskać dobrą dokładność przewidywań.

1. Wybierz **Dalej**.

1. Przejrzyj konfigurację prognozy. Aby wrócić do poprzednich kroków, można wybrać opcję **Edycji** pod pokazaną wartością. Można też wybrać krok konfiguracji ze wskaźnika postępu.

1. Jeśli wszystkie wartości są poprawnie skonfigurowane, wybierz **Zapisz i uruchom**, aby rozpocząć proces przewidywania. Na karcie **Moje przewidywania** można sprawdzić stan przewidywań. Przeprowadzanie procesu może potrwać kilka godzin, w zależności od ilości danych użytych w przewidywaniu.

## <a name="review-a-prediction-status-and-results"></a>Przejrzyj stan przewidywania i wyniki

1. Wybierz **Analizy** > **Przewidywania** i wybierz kartę **Moje przewidywania**.

1. Wybierz przewidywania do przeglądu.
   - **Nazwa przewidywania**: Nazwa przewidywania podana podczas jej tworzenia.
   - **Typ przewidywania**: typ modelu używanego przez przewidywanie
   - **Encja wyjściowa**: Nazwa encji, w której mają być przechowywane wyniki przewidywania. Encję o tej nazwie można znaleźć w **Dane** > **Encje**.
     W encji wyjściowej *ChurnScore* jest prawdopodobieństwem rezygnacji, a *IsChurn* jest binarnym poziomem na podstawie wyniku *ChurnScore* z progiem 0,5. Domyślny próg może nie działać w tym scenariuszu. [Utwórz nowy segment](segments.md#create-a-new-segment) z wybranym progiem.
     Nie wszyscy klienci muszą być aktywnymi klientami. Niektórzy z nich mogą nie mieć żadnego działania przez dłuższy czas i są już traktowane jako rezygnacja na podstawie definicji rezygnacji. Przewidywanie ryzyka rezygnacji dla klientów, którzy już zrezygnowali, nie jest przydatne, ponieważ ci odbiorcy nie są dla Ciebie interesujący.
   - **Przewidywane pole**: to pole jest wypełniane tylko w przypadku niektórych typów przewidywań i nie jest używane w przewidywaniu rezygnacji.
   - **Stan**: Stan przebiegu przewidywania.
        - **W kolejce**: przewidywanie oczekuje na uruchomienie innych procesów.
        - **Odświeżanie**: przewidywanie jest obecnie uruchomione w celu wyprodukowania wyników, które będą przepływać na encję wyjściową.
        - **Niepowodzenie**: uruchomienie przewidywanie zakończyło się niepowodzeniem. Aby uzyskać więcej informacji, [przejrzyj dzienniki](manage-predictions.md#troubleshoot-a-failed-prediction).
        - **Zakończono pomyślnie**: przewidywanie zakończyło się sukcesem. Wybierz **Widok** pod pionowymi wielokropkami, aby przejrzeć przewidywanie
   - **Edytowano**: Data konfiguracji dla przewidywania została zmieniona.
   - **Ostatnie odświeżenie**: Data odświeżonych wyników przewidywania w encji wyjściowej.

1. Zaznacz pionowy wielokropek obok przewidywania, dla którego chcesz przejrzeć wyniki, i wybierz **Widok**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Wyświetl kontrolkę, aby zobaczyć wyniki prognozy.":::

# <a name="individual-consumers-b-to-c"></a>[Klienci indywidualni (B2C)](#tab/b2c)

1. Na stronie wyników wyszukiwania znajdują się trzy podstawowe sekcje danych:
   - **Wydajność modelu szkoleniowego**: A, B i C są możliwymi wynikami. Ten wynik wskazuje wydajność przewidywania i może pomóc w podjęciu decyzji w zakresie korzystania z wyników przechowywanych w encji wyjściowej. Wyniki są określane na podstawie następujących reguł: 
        - **A** kiedy model dokładnie przewidział co najmniej 50% wszystkich prognoz, a odsetek trafnych prognoz dla klientów, którzy zrezygnowali, jest większy od wskaźnika bazowego o co najmniej 10%.
            
        - **B** kiedy model dokładnie przewidział co najmniej 50% wszystkich prognoz, a odsetek trafnych prognoz dla klientów, którzy zrezygnowali, jest do 10% większy niż poziom bazowy.
            
        - **C** kiedy model dokładnie przewidział mniej niż 50% wszystkich prognoz lub odsetek trafnych prognoz dla klientów, którzy zrezygnowali, jest do 10% mniejszsy niż poziom bazowy.
               
        - **Linia bazowa** przyjmuje dane wejściowe w oknie czasowym przewidywania dla modelu (na przykład jeden rok), a model tworzy różne ułamki czasu, dzieląc je przez 2, aż osiągnie jeden miesiąc lub mniej. Wykorzystuje te ułamki do stworzenia reguły biznesowej dla klientów, którzy nie dokonali zakupów w tym przedziale czasowym. Tych klientów uważa się za utraconych. Jako model bazowy wybrano regułę biznesową opartą na czasie z największą zdolnością przewidywania, kto prawdopodobnie odejdzie.
            
    - **Prawdopodobieństwo rezygnacji (liczba klientów)**: grupy klientów na podstawie ich przewidywanego ryzyka rezygnacji. Te dane mogą pomóc później, jeśli chcesz utworzyć segment klientów z dużym ryzykiem rezygnacji. Takie segmenty ułatwiają zrozumienie tego, w którym miejscu powinien się znaleźć próg dla członkostwa w segmencie.
       
    - **Czynniki mające największy wpływ**: istnieje wiele czynników branych pod uwagę podczas tworzenia przewidywania. Każdy z czynników ma swoją wagę obliczoną dla zagregowanych prognoz tworzonych przez model. Tych czynników można użyć w celu zweryfikowania wyników przewidywania lub można później użyć tych informacji do [utworzenia segmentów](segments.md), które mogą mieć wpływ na ryzyko rezygnacji klientów.


# <a name="business-accounts-b-to-b"></a>[Klienci biznesowi (B2B)](#tab/b2b)

1. Na stronie wyników wyszukiwania znajdują się trzy podstawowe sekcje danych:
   - **Wydajność modelu szkoleniowego**: A, B i C są możliwymi wynikami. Ten wynik wskazuje wydajność przewidywania i może pomóc w podjęciu decyzji w zakresie korzystania z wyników przechowywanych w encji wyjściowej. Wyniki są określane na podstawie następujących reguł: 
        - **A** kiedy model dokładnie przewidział co najmniej 50% wszystkich prognoz, a odsetek trafnych prognoz dla klientów, którzy zrezygnowali, jest większy od wskaźnika bazowego o co najmniej 10%.
            
        - **B** kiedy model dokładnie przewidział co najmniej 50% wszystkich prognoz, a odsetek trafnych prognoz dla klientów, którzy zrezygnowali, jest do 10% większy niż poziom bazowy.
            
        - **C** kiedy model dokładnie przewidział mniej niż 50% wszystkich prognoz lub odsetek trafnych prognoz dla klientów, którzy zrezygnowali, jest do 10% mniejszsy niż poziom bazowy.
               
        - **Linia bazowa** przyjmuje dane wejściowe w oknie czasowym przewidywania dla modelu (na przykład jeden rok), a model tworzy różne ułamki czasu, dzieląc je przez 2, aż osiągnie jeden miesiąc lub mniej. Wykorzystuje te ułamki do stworzenia reguły biznesowej dla klientów, którzy nie dokonali zakupów w tym przedziale czasowym. Tych klientów uważa się za utraconych. Jako model bazowy wybrano regułę biznesową opartą na czasie z największą zdolnością przewidywania, kto prawdopodobnie odejdzie.
            
    - **Prawdopodobieństwo rezygnacji (liczba klientów)**: grupy klientów na podstawie ich przewidywanego ryzyka rezygnacji. Te dane mogą pomóc później, jeśli chcesz utworzyć segment klientów z dużym ryzykiem rezygnacji. Takie segmenty ułatwiają zrozumienie tego, w którym miejscu powinien się znaleźć próg dla członkostwa w segmencie.
       
    - **Czynniki mające największy wpływ**: istnieje wiele czynników branych pod uwagę podczas tworzenia przewidywania. Każdy z czynników ma swoją wagę obliczoną dla zagregowanych prognoz tworzonych przez model. Tych czynników można użyć w celu zweryfikowania wyników przewidywania lub można później użyć tych informacji do [utworzenia segmentów](segments.md), które mogą mieć wpływ na ryzyko rezygnacji klientów.


1. W przypadku kont biznesowych skorzystaj ze strona informacyjnej **Analiza czynników wpływających**. Zawiera ona cztery sekcje danych:

    - Zawartość na tej stronie jest określana przez element wybrany w prawym okienku. Wybierz pozycję z listy **Najlepsi klienci** lub **Klienci używani w testach porównawczych**. Obie listy są uporządkowane według zmniejszającej się wartości wyniku dla rezygnacji, niezależnie od tego, czy wynik jest tylko dla klienta, czy też łączny wynik klienta i poziomu pomocniczego, takiego jak kategoria produktu.
        
        - **Najlepsi klienci**: lista 10 klientów, których istnieje największe ryzyko rezygnacji i najniższe ryzyko rezygnacji określone na podstawie ich wyników dotyczących rezygnacji. 
        - **Klienci używani w testach porównawczych**: lista maksymalnie 10 klientów wybranych podczas konfigurowania modelu.
 
    - **Wynik rezygnacji:** pokazuje wynik rezygnacji dla elementu wybranego w prawym okienku.
    
    - **Rozkład wyników rezygnacji:** pokazuje rozkład wyników rezygnacji między klientami i percentyl, w którym znajduje się wybrany klient. 
    
    - **Najważniejsze funkcje zwiększające i zmniejszające ryzyko rezygnacji:** dla elementu wybranego w prawym okienku pięć najważniejszych funkcji, które zwiększały i zmniejszały ryzyko rezygnacji. Dla każdej funkcji wywierającej wpływ można znaleźć wartość funkcji dla tego elementu i jej wpływ na wynik rezygnacji. Jest również wyświetlana średnia wartość każdej funkcji w segmentach klientów z niskim, średnim i wysokim ryzykiem rezygnacji. Pomaga to w lepszym określaniu kontekstu wartości najważniejszych funkcji wywierających wpływ dla wybranego elementu i porównywaniu ich z segmentami klientów o niskim, średnim i wysokim ryzyku rezygnacji.

       - Niskie: klienci lub kombinacje klientów i poziom pomocniczy z wynikiem rezygnacji od 0 do 0,33
       - Średnie: klienci lub kombinacje klientów i poziomy pomocnicze z wynikiem rezygnacji od 0,33 do 0,66
       - Wysokie: klienci lub kombinacje klientów i poziomy pomocnicze z wynikiem rezygnacji większym niż 0,66
    
       Podczas przewidywania ryzyka na poziomie klienta wszyscy klienci są uwzględniani jako wartości średnie funkcji dla segmentów rezygnacji. W przypadku przewidywania rezygnacji na poziomie pomocniczym dla każdego klienta dane pochodzące z segmentów rezygnacji zależą od poziomu pomocniczego elementu wybranego w okienku bocznym. Na przykład, jeśli element ma poziom pomocniczy w kategorii produktu = materiały biurowe, podczas pobierania średnich wartości funkcji dla segmentów ryzyka są uwzględniane jedynie elementy z materiałami biurowymi. Ta logika jest stosowana w celu zapewnienia uczciwego porównywania wartości funkcji elementu z wartościami średnimi w segmentach o niskim, średnim i wysokim ryzyku.

       W niektórych przypadkach wartość średnia segmentów o niskim, średnim lub wysokim ryzyku jest pusta lub niedostępna, ponieważ nie ma elementów należących do odpowiednich segmentów ryzyka na podstawie powyższej definicji.
       
       > [!NOTE]
       > Interpretacja wartości poniżej ogólnie niskich, średnich i wysokich kolumn są inne w przypadku funkcji kategorycznych, takich jak kraj lub sektor. Ponieważ funkcja „średnie” nie ma zastosowania do funkcji kategorycznych, wartości w tych kolumnach to odsetek klientów w segmentach niskie, średnie lub wysokie, które mają tę samą wartość w przypadku funkcji kategorycznych w porównaniu z elementem wybranym w panelu bocznym.

---

## <a name="manage-predictions"></a>Zarządzaj przewidywaniami

Można optymalizować, rozwiązywać problemy, odświeżać lub usuwać przewidywania. Zapoznaj się z raportem użyteczności danych wejściowych, aby dowiedzieć się, jak przyspieszyć przewidywanie i zwiększyć jego wiarygodność. Aby uzyskać więcej informacji, przejdź do strony [Zarządzanie przewidywaniami](manage-predictions.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
