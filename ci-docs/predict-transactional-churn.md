---
title: Przewidywanie odpływu transakcji (zawiera wideo)
description: Przewiduj, czy klient jest zagrożony, jeśli przestanie kupować Twoje produkty lub usługi.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: fd8df0f0a168ddfab9e8ad3af9e1f1fc0bc1b7a2
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610525"
---
# <a name="predict-transaction-churn"></a>Przewidywanie rezygnacji z transakcji

Prognozowanie rezygnacji z transakcji pomaga przewidzieć, czy klient nie będzie już kupować Twoich produktów lub usług w danym oknie czasowym.

Należy posiadać wiedzę biznesową, pozwalającą zrozumieć co rezygnacja oznacza dla działalności. Obsługujemy definicje rezygnacji na podstawie czasu, co oznacza, że klient odszedł po okresie braku zakupów.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

W środowiskach opartych na kontach biznesowych można przewidywać rezygnację z transakcji klienta oraz kombinację konta i innego poziomu informacji, takich jak kategoria produktu. Na przykład dodanie wymiarów może pomóc w określeniu, na ile prawdopodobne jest, że klient „Contoso” przestanie kupować kategorię produktów „materiały biurowe”. W przypadku kont biznesowych możemy również użyć AI do wygenerowania listy potencjalnych przyczyn, dla których konto jest zagrożone dla kategorii informacji na poziomie pomocniczym.

> [!TIP]
> Wypróbuj przewidywanie rezygnacji z transakcji za pomocą danych przykładowych: [Przykładowy przewodnik po przewidywaniu rezygnacji z transakcji](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Wymagania wstępne

- Co najmniej [uprawnienia współautora](permissions.md).
- Co najmniej 10 profilów klientów, najlepiej ponad 1000 unikalnych klientów.
- Identyfikator klientów, unikatowy identyfikator umożliwiający dopasowanie transakcji do klientów.
- Dane transakcji dla co najmniej dwóch wybranych okresów, na przykład dwóch do trzech lat historii transakcji. Najlepiej jest, aby dla każdego klienta przypadały przynajmniej dwie transakcje. Historia transakcji musi zawierać:
  - **Identyfikator transakcji**: unikatowy identyfikator zakupu lub transakcji.
  - **Data transakcji**: data zakupu lub transakcji.
  - **Wartość transakcji**: kwota waluty lub wartość liczbowa transakcji.
  - **Unikatowy identyfikator produktu:** identyfikator zakupionego produktu lub usługi, jeśli dane są na poziomie pozycji wiersza.
  - **Czy ta transakcja była zwrotem**: pole typu prawda/fałsz, które określa, czy transakcja była zwrotna, czy nie. Jeśli **Wartość transakcji** jest ujemna, założymy, że nastąpił zwrot.
- Dane działania klienta:
  - Identyfikator klienta, unikatowy identyfikator do mapowania działań do klientów.
  - **Klucz podstawowy**: unikatowy identyfikator działania. Na przykład wizyta w witrynie internetowej lub zapis użytkowania pokazujący, że klient wypróbował próbkę Twojego produktu.
  - **Sygnatura czasowa**: data i godzina zdarzenia identyfikowanego przez klucz podstawowy.
  - **Zdarzenie:** nazwa zdarzenia, którego chcesz użyć. Na przykład pole o nazwie „UserAction” w sklepie spożywczym może być kuponem używanym przez klienta.
  - **Szczegóły:** Szczegółowe informacje o zdarzeniu. Na przykład pole o nazwie „CouponValue” w sklepie spożywczym może zawierać walutę kuponu.
- Mniej niż 20% brakujących wartości w polu dostarczonej encji

W przypadku kont biznesowych (B2B) dodaj dane klientów wyrównane w kierunku bardziej statycznych atrybutów, aby zapewnić najlepsze wyniki modelu:
- **Identyfikator klienta:** unikatowy identyfikator klienta.
- **Data utworzenia:** data początkowego dodania klienta.
- **Województwo:** lokalizacja województwa klienta.
- **Kraj:** kraj klienta.
- **Branża:** typ branży klienta. Na przykład pole o nazwie „Branża” dla ekspresu do kawy może wskazywać, czy był to klient sprzedaży detalicznej.
- **Klasyfikacja:** kategoryzowanie klienta na potrzeby firmy. Na przykład pole o nazwie „ValueSegment” w ekspresie do kawy może być warstwą klienta w zależności od wielkości klienta.

> [!NOTE]
> W przypadku działalności o wysokiej częstotliwości zakupów u klientów (co kilka tygodni) zaleca się wybranie krótszego okna przewidywania i definicji rezygnacji. W przypadku niskiej częstotliwości zakupu (co kilka miesięcy lub raz do roku), wybierz dłuższy przewidywania i definicji rezygnacji.

## <a name="create-a-transaction-churn-prediction"></a>Tworzenie przewidywania rezygnacji z transakcji

1. Przejdź do opcji **Analizy** > **Przewidywania**.

1. Na karcie **Utwórz** wybierz **Model użycia** na kafelku **Model rezygnacji klienta**.

1. Wybierz opcję **Transakcja** dla typu rozsyłania, a następnie wybierz opcję **Rozpocznij**.

1. **Nazwij ten model** i **Nazwa encji wyjściowej**, aby odróżnić je od innych modeli lub encji.

1. Wybierz **Dalej**.

### <a name="define-customer-churn"></a>Definiuj rezygnację klienta

W dowolnym momencie wybierz opcję **Zapisz roboczą**, aby zapisać przewidywanie jako roboczą. Wersja robocza wyświetla się na karcie **Moje prognozy**.

1. Konfiguracja **Okno przewidywania**. Na przykład prognozuj ryzyko odejścia klientów w ciągu najbliższych 90 dni, aby dostosować się do działań marketingowych dotyczących utrzymania klientów. Przewidywanie ryzyka odejścia na dłuższy lub krótszy okres może utrudnić uwzględnienie czynników w profilu ryzyka odejścia, ale zależy to od konkretnych wymagań biznesowych.

1. W polu **Definicja rezygnacji** wprowadź liczbę dni do zdefiniowania rezygnacji. Na przykład, jeśli klient nie dokonał zakupów w ciągu ostatnich 30 dni, może zostać uznany za klienta, który zrezygnował, w przypadku firmy.

1. Wybierz **Dalej**.

### <a name="add-purchase-history"></a>Dodaj historię zakupów

1. Wybierz **Dodaj dane** dla **Historii transakcji klienta**.

1. Wybierz semantyczny typ działania **SalesOrder** lub **SalesOrderLine** zawierającym informacje o historii transakcji. Jeśli działanie nie zostało ustawione, zaznacz **tutaj** i utwórz działanie.

1. W obszarze **Działania**, jeśli atrybuty działania zostały semantycznie zamapowane podczas tworzenia działania, wybierz określone atrybuty lub encję, na których chcesz skupić obliczenia. Jeśli semantyczne mapowanie nie wystąpiło, wybierz opcję **Edytuj** i zamapuj dane.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Okienko boczne po stronie przedstawiające wybranie określone działania w ramach typu semantycznego.":::

1. Wybierz opcję **Dalej** i przejrzyj atrybuty wymagane dla tego modelu.

1. Wybierz pozycję **Zapisz**.

1. Dodaj więcej działań lub wybierz **Dalej**.

# <a name="individual-consumers-b-to-c"></a>[Klienci indywidualni (B2C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Dodawanie dodatkowych danych (opcjonalnie)

1. Wybierz **Dodaj dane** do **Działań klienta**.

1. Wybierz typ działań semantycznych, które zawierają dane do użycia w aplikacji. Jeśli działanie nie zostało ustawione, zaznacz **tutaj** i utwórz działanie.

1. W obszarze **Działania**, jeśli atrybuty działania zostały semantycznie zamapowane podczas tworzenia działania, wybierz określone atrybuty lub encję, na których chcesz skupić obliczenia. Jeśli semantyczne mapowanie nie wystąpiło, wybierz opcję **Edytuj** i zamapuj dane.

1. Wybierz opcję **Dalej** i przejrzyj atrybuty wymagane dla tego modelu.

1. Wybierz pozycję **Zapisz**.

1. Wybierz **Dalej**

# <a name="business-accounts-b-to-b"></a>[Klienci biznesowi (B2B)](#tab/b2b)

### <a name="select-prediction-level"></a>Wybieranie poziomu przewidywania

Większość przewidywań jest tworzona na poziomie klienta. W niektórych przypadkach może to nie być na tyle szczegółowe, aby zaspokoić potrzeby firmy. Użyj tej funkcji na przykład do przewidywania dla gałęzi klienta, a nie dla klienta jako całości.

1. Zaznacz **Wybierz encję dla dodatkowego poziomu**. Jeśli ta opcja nie jest dostępna, upewnij się, że poprzednia sekcja została zakończona.

1. Rozwiń encje, z których chcesz wybrać poziom pomocniczy, lub użyj pola filtru wyszukiwania w celu odfiltrowania wybranych opcji.

1. Wybierz atrybut, który ma być używany jako poziom pomocniczy, a następnie wybierz opcję **Dodaj**.

1. Wybierz **Dalej**.

> [!NOTE]
> Encje dostępne w tej sekcji są wyświetlane, ponieważ mają relację z encją wybraną w poprzedniej sekcji. Jeśli nie widzisz encji, którą chcesz dodać, upewnij się, że jest w niej prawidłowa relacja w obszarze **Relacje**. W przypadku tej konfiguracji można obowiązuje tylko relacja jeden-do-jednego i wiele-do-jednego.

### <a name="add-additional-data-optional"></a>Dodawanie dodatkowych danych (opcjonalnie)

1. Wybierz **Dodaj dane** do **Działań klienta**.

1. Wybierz typ działań semantycznych, które zawierają dane do użycia w aplikacji. Jeśli działanie nie zostało ustawione, zaznacz **tutaj** i utwórz działanie.

1. W obszarze **Działania**, jeśli atrybuty działania zostały semantycznie zamapowane podczas tworzenia działania, wybierz określone atrybuty lub encję, na których chcesz skupić obliczenia. Jeśli semantyczne mapowanie nie wystąpiło, wybierz opcję **Edytuj** i zamapuj dane.

1. Wybierz opcję **Dalej** i przejrzyj atrybuty wymagane dla tego modelu.

1. Wybierz pozycję **Zapisz**.

1. Wybierz **Dalej**

1. Opcjonalnie wybierz opcję **Dodaj dane** dla obszaru **Dane klientów**.

1. Mapuj atrybuty semantyczne na pola własnych danych zidentyfikowanych klientów. Dane w używanych polach nie powinny często się zmieniać, aby zapewnić najlepsze wyniki w modelu. Na przykład wybranie pola „Klasyfikacja”, które zmienia się co miesiąc, będzie zawierać tylko ostatnią wartość używaną w przewidywaniu, nawet jeśli w przeszłości ta sama wartość nie była stosowana dla klienta podczas tworzenia wzorców przewidywania.

1. Wybierz **Dalej**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Podaj opcjonalną listę kont porównawczych

Dodaj listę klientów biznesowych i kont, których chcesz użyć jako testów porównawczych. [Szczegółowe informacje dotyczące tych kont porównawczych](#view-prediction-results) zawierają wynik dotyczący rezygnacji i większość funkcji, które wpływały na przewidywanie ich rezygnacji.

1. Wybierz **+ Dodaj klientów**.

1. Wybierz klientów, którzy pełnią rolę testu porównawczego.

1. Wybierz **Dalej**.

---

### <a name="set-update-schedule"></a>Ustaw harmonogram aktualizacji

1. W kroku **Aktualizacja danych** wybierz częstotliwość ponownego szkolenia modelu. To ustawienie ma znaczenie dla aktualizowania dokładności przewidywań w czasie pozyskiwania nowych danych do Customer Insights. Większość firm może przeprowadzać ponowne szkolenia raz w miesiącu i uzyskać dobrą dokładność przewidywań.

1. Wybierz **Dalej**.

### <a name="review-and-run-the-model-configuration"></a>Przegląd i uruchamianie konfiguracji modelu

W kroku **Przejrzyj i uruchom** przedstawiono podsumowanie konfiguracji i użytkownik może wprowadzić zmiany przed utworzeniem przewidywania.

1. Wybierz **Edytuj** na każdym z etapów, aby przejrzeć i wprowadzić ewentualne zmiany.

1. Jeśli użytkownik jest zadowolony z wprowadzonych opcji, wybiera opcję **Zapisz i uruchom**, aby rozpocząć uruchamianie modelu. Wybierz pozycję **Gotowe**. Podczas tworzenia przewidywanie jest wyświetlana karta **Moje prognozy**. Przeprowadzanie procesu może potrwać kilka godzin, w zależności od ilości danych użytych w przewidywaniu.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Wyświetl wyniki przewidywania

1. Przejdź do opcji **Analizy** > **Przewidywania**.

1. Na karcie **Moje przewidywania** wybierz przewidywanie, które chcesz wyświetlić.

# <a name="individual-consumers-b-to-c"></a>[Klienci indywidualni (B2C)](#tab/b2c)

Na stronie wyników wyszukiwania znajdują się trzy podstawowe sekcje danych:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

# <a name="business-accounts-b-to-b"></a>[Klienci biznesowi (B2B)](#tab/b2b)

Na stronie wyników wyszukiwania znajdują się trzy podstawowe sekcje danych:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

Strona informacyjna **Analiza czynników wpływających** zawiera cztery sekcje danych:

- W prawym okienku wybierz pozycję z listy **Najlepsi klienci** lub **Klienci używani w testach porównawczych**. Obie listy są uporządkowane według zmniejszającej się wartości wyniku dla rezygnacji, niezależnie od tego, czy wynik jest tylko dla klienta, czy też łączny wynik klienta i poziomu pomocniczego, takiego jak kategoria produktu. Wybrany element określa zawartość na tej stronie.

  - **Najlepsi klienci**: lista 10 klientów, których istnieje największe ryzyko rezygnacji i najniższe ryzyko rezygnacji określone na podstawie ich wyników dotyczących rezygnacji.
  - **Klienci używani w testach porównawczych**: lista maksymalnie 10 klientów wybranych podczas konfigurowania modelu.

- **Wynik rezygnacji:** pokazuje wynik rezygnacji dla elementu wybranego w prawym okienku.

- **Rozkład wyników rezygnacji:** pokazuje rozkład wyników rezygnacji między klientami i percentyl, w którym znajduje się wybrany klient.

- **Najważniejsze funkcje zwiększające i zmniejszające ryzyko rezygnacji:** wymienia pięć najważniejszych funkcji, które zwiększały i zmniejszały ryzyko rezygnacji dla elementu wybranego w prawym okienku. Dla każdej funkcji wywierającej wpływ pokazuje wartość funkcji dla tego elementu i jej wpływ na wynik rezygnacji. Jest również wyświetlana średnia wartość każdej funkcji w segmentach klientów z niskim, średnim i wysokim ryzykiem rezygnacji. Pomaga to w lepszym określaniu kontekstu wartości najważniejszych funkcji wywierających wpływ dla wybranego elementu i porównywaniu ich z segmentami klientów o niskim, średnim i wysokim ryzyku rezygnacji.

  - Niskie: klienci lub kombinacje klientów i poziom pomocniczy z wynikiem rezygnacji od 0 do 0,33.
  - Średnie: klienci lub kombinacje klientów i poziomy pomocnicze z wynikiem rezygnacji od 0,33 do 0,66.
  - Wysokie: klienci lub kombinacje klientów i poziomy pomocnicze z wynikiem rezygnacji większym niż 0,66.

  Podczas przewidywania ryzyka na poziomie klienta wszyscy klienci są uwzględniani jako wartości średnie funkcji dla segmentów rezygnacji. W przypadku przewidywania rezygnacji na poziomie pomocniczym dla każdego klienta dane pochodzące z segmentów rezygnacji zależą od poziomu pomocniczego elementu wybranego w okienku bocznym. Na przykład, jeśli element ma poziom pomocniczy w kategorii produktu (materiały biurowe), podczas pobierania średnich wartości funkcji dla segmentów ryzyka są uwzględniane jedynie elementy z materiałami biurowymi. Ta logika jest stosowana w celu zapewnienia uczciwego porównywania wartości funkcji elementu z wartościami średnimi w segmentach o niskim, średnim i wysokim ryzyku.

  W niektórych przypadkach wartość średnia segmentów o niskim, średnim lub wysokim ryzyku jest pusta lub niedostępna, ponieważ nie ma elementów należących do odpowiednich segmentów ryzyka na podstawie powyższej definicji.

  Interpretacja wartości poniżej ogólnie niskich, średnich i wysokich kolumn są inne w przypadku funkcji kategorycznych, takich jak kraj lub sektor. Ponieważ funkcja „średnie” nie ma zastosowania do funkcji kategorycznych, wartości w tych kolumnach to odsetek klientów w segmentach niskie, średnie lub wysokie, które mają tę samą wartość w przypadku funkcji kategorycznych w porównaniu z elementem wybranym w panelu bocznym.

---

 > [!NOTE]
 > W encji wyjściowej dla tego modelu *ChurnScore* pokazuje prawdopodobieństwo rezygnacji, a *IsChurn* jest binarnym poziomem na podstawie wyniku *ChurnScore* z progiem 0,5. Jeśli ten domyślny próg nie działa w tym scenariuszu, [utwórz nowy segment](segments.md#create-a-segment) z wybranym progiem. Nie wszyscy klienci muszą być aktywnymi klientami. Niektórzy z nich mogą nie mieć żadnego działania przez dłuższy czas i są już traktowane jako rezygnacja na podstawie definicji rezygnacji. Przewidywanie ryzyka rezygnacji dla klientów, którzy już zrezygnowali, nie jest przydatne, ponieważ ci odbiorcy nie są dla Ciebie interesujący.
>
> Aby wyświetlić wynik rezygnacji, przejdź do **Dane** > **Encje** i wyświetl kartę danych dla encji wyjściowej zdefiniowanej dla tego modelu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
