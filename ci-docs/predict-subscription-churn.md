---
title: Przewidywanie rezygnacji z subskrypcji (zawiera wideo)
description: Przewiduj, czy istnieje zagrożenie, że klient przestanie używać subskrypcji na produkty lub usługi Twojej firmy.
ms.date: 08/19/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 72aa38242df21181f142833db03c825574455986
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171062"
---
# <a name="subscription-churn-prediction"></a>Przewidywanie zmian subskrypcji

Prognoza rezygnacji z subskrypcji pomaga przewidzieć, czy istnieje zagrożenie, że klient przestanie używać subskrypcji na produkty lub usługi Twojej firmy. Nową prognozę rezygnacji z subskrypcji można utworzyć na stronie **Analizy** > **Przewidywania**. Wybierz **Moje przewidywania**, aby wyświetlić inne utworzone przewidywania.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Wypróbuj samouczek, aby uzyskać przewidywanie rezygnacji z subskrypcji za pomocą przykładowych danych: [Przykładowy przewodnik dotyczący prognozowania rezygnacji z subskrypcji (wersja zapoznawcza)](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Wymagania wstępne

- Co najmniej [uprawnienia współautora](permissions.md).
- Wiedza biznesowa, pozwalająca zrozumieć co rezygnacja oznacza dla Twojej działalności. Obsługujemy definicje rezygnacji czasowych, co oznacza, że uważamy, że klient zrezygnował na pewien czas po zakończeniu subskrypcji.
- Dane dotyczące subskrypcji i ich historii:
    - Identyfikatory subskrypcji umożliwiające rozróżnianie subskrypcji.
    - Identyfikatory klientów, umożliwiające dopasowanie subskrypcji do klientów.
    - Daty zdarzeń subskrypcji definiujące daty rozpoczęcia, daty zakończenia oraz daty, w których wystąpiły zdarzenia subskrypcji.
    - Informacje o subskrypcji określające, czy jest to cykliczna subskrypcja oraz jak często jest odnawiana.
    - Schemat danych semantycznych dla subskrypcji wymaga następujących informacji:
        - **Identyfikator subskrypcji:** Unikatowy identyfikator subskrypcji.
        - **Data zakończenia subskrypcji:** Data wygaśnięcia subskrypcji klienta.
        - **Data rozpoczęcia subskrypcji:** Data rozpoczęcia subskrypcji klienta.
        - **Data transakcji:** Data wystąpienia zmiany w subskrypcji. Na przykład klient, który kupuję lub anuluje subskrypcję.
        - **Czy jest to subskrypcja cykliczna:** Pole logiczne prawda/fałsz które określa, czy subskrypcja zostanie odnowiona z takim samym identyfikatorem subskrypcji bez interwencji klienta
        - **Częstotliwość powtarzania (w miesiącach):** Dla subskrypcji cyklicznych jest to okres, na jaki subskrypcja jest odnawiana. Jest to wartość określana w miesiącach. Na przykład roczna subskrypcja, która jest automatycznie odnawiana dla klienta co roku na kolejny rok ma wartość 12.
        - (Opcjonalnie) **Kwota subskrypcji:** Kwota płacona przez klienta za odnowienie subskrypcji. Może to pomóc w określeniu wzorów dla różnych poziomów subskrypcji.
- Dane dotyczące działań klienta:
    - Identyfikatory działań w celu wyróżnienia działań tego samego typu.
    - Identyfikatory klientów, umożliwiające mapowanie działań do klientów.
    - Informacje o działaniu zawierające nazwę i datę działania.
    - Schemat danych semantycznych dla działań klientów zawiera:
        - **Klucz podstawowy:** Unikatowy identyfikator działania. Na przykład wizyta w witrynie sieci Web lub rekord użycia ukazujący, że w klient obejrzał odcinek serialu telewizyjnego.
        - **Sygnatura czasowa:** Data i godzina zdarzenia identyfikowanego przez klucz podstawowy.
        - **Zdarzenie:** Określ nazwę zdarzenia, które chcesz użyć. Na przykład pole o nazwie "UserAction" w usłudze przesyłania strumieniowego wideo może mieć wartość "Obejrzany".
        - **Szczegóły:** Szczegółowe informacje o zdarzeniu. Na przykład pole o nazwie "ShowTitle" w usłudze przesyłania strumieniowego wideo może mieć wartość wideo obejrzanego przez klienta.
- Sugerowana charakterystyka danych:
    - Wystarczające dane historyczne: dane subskrypcji dla co najmniej podwójnego wybranego okna czasowego. Najlepiej dwa do trzech lat danych subskrypcji.
    - Stan subskrypcji: dane obejmują aktywne i nieaktywne subskrypcje dla każdego klienta, więc dla każdego identyfikatora klienta jest wiele wpisów.
    - Liczba klientów: co najmniej 10 profilów klientów, najlepiej ponad 1000 unikalnych klientów. Model zakończy z niepowodzeniem, jeśli będzie mniej niż 10 klientów oraz niewystarczające dane historycznych.
    - Pełność danych: mniej niż 20% brakujących wartości w polu danych dostarczonej encji.
   
   > [!NOTE]
   > Dla 50% klientów, dla których ma być obliczona wartość zmian, muszą być co najmniej dwa rekordy działań.

## <a name="create-a-subscription-churn-prediction"></a>Utwórz prognozę rezygnacji z subskrypcji

1. Przejdź do opcji **Analizy** > **Przewidywania**.
1. Wybierz kafelek **Model rezygnacji z subskrypcji** i wybierz opcję **Użyj tego modelu**.
   > [!div class="mx-imgBorder"]
   > ![Kafelek Model rezygnacji z subskrypcji z przyciskiem Użyj tego modelu.](media/subscription-churn-usethismodel.PNG "Kafelek Model rezygnacji z subskrypcji z przyciskiem Użyj tego modelu")

### <a name="name-model"></a>Nadaj nazwę modelowi

1. Podaj nazwę modelu odróżniającą go od innych modeli.
1. Podaj nazwę encji wyjściowej używając wyłącznie liter i cyfr, bez żadnych spacji. To jest nazwa, której będzie używać encja modelowa. Następnie wybierz **Dalej**.

### <a name="define-customer-churn"></a>Definiuj rezygnację klienta

1. Wprowadź liczbę **Dni od zakończenia subskrypcji**, przez które firma uważa, że klient jest w stanie rezygnacji. Ten okres zazwyczaj jest powiązany z działaniami biznesowymi, takimi jak oferty, lub inne działania marketingowe, które usiłują zapobiec utracie klienta.
1. Wpisz w liczbę **Dni, które mają zostać przeanalizowane w przyszłości w celu przewidywania zmian**, aby ustawić okno przewidywania zmian. Na przykład w celu przewidywania ryzyka zmian w pracy z klientami w ciągu najbliższych 90 dni w celu dostosowania się do działań w zakresie przechowywania marketingu. Przewidywanie ryzyka rezygnacji przez dłuższe lub krótsze okresy może jednak znacznie utrudnić branie pod uwagę czynników w profilu ryzyka rezygnacji w zależności od konkretnych wymagań biznesowych. Wybierz **Dalej**, aby kontynuować
   >[!TIP]
   > W dowolnym momencie można wybrać opcję **Zapisz roboczą**, aby zapisać przewidywanie jako roboczą. Aby kontynuować, należy znaleźć przewidywanie w wersji roboczej na karcie **Moje przewidywania**.

### <a name="add-required-data"></a>Dodaj wymagane dane

1. Wybierz **Dodaj dane** dla **Historii subskrypcji** i wybierz encję, która dostarcza informacje o historii subskrypcji, jak to opisano w [wymagania wstępne](#prerequisites).
1. Jeśli poniższe pola nie są wypełnione, skonfiguruj relację z encji historii subskrypcji na encję Klient.
    1. Wybierz **Encja historii subskrypcji**.
    1. Wybierz **Pole**, które identyfikuje klienta w encji historii subskrypcji. Musi ono być powiązane z podstawowym identyfikatorem klienta encji Klient.
    1. Wybierz **encję Klient** pasującą do podstawowej encji klienta.
    1. Wprowadź nazwę, która opisuje relację.
       > [!div class="mx-imgBorder"]
       > ![Strona historii subskrypcji prezentująca utworzenie relacji z klientem.](media/subscription-churn-subscriptionhistoryrelationship.PNG "Strona historii subskrypcji prezentująca utworzenie relacji z klientem")
1. Wybierz **Dalej**.
1. Zmapuj pola semantyczne na atrybuty w encji historii subskrypcji i wybierz **Zapisz**. Aby zapoznać się z opisami pól, należy zapoznać się z [wymaganiami wstępnymi](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Strona historii subskrypcji prezentująca atrybuty semantyczne, które są mapowane na pola wybranej encji historii subskrypcji.](media/subscription-churn-subscriptionhistorymapping.PNG "Strona historii subskrypcji prezentująca atrybuty semantyczne, które są mapowane na pola wybranej encji historii subskrypcji")
1. Wybierz **Dodaj dane** dla **Działania klienta** i wybierz encję, która dostarcza informacje o działania klienta, jak to opisano w wymaganiach wstępnych.
1. Wybierz typ działania odpowiadający typowi działania klienta, które konfigurujesz.  Wybierz **Utwórz nowy** i podaj nazwę, jeśli nie widzisz opcji odpowiadającej potrzebnemu typowi działania.
1. Należy skonfigurować relację od encji działania klienta do encji Klient.
    1. Wybierz pole, które identyfikuje klienta w tabeli działania klienta, które może być bezpośrednio związany z podstawowym identyfikatorem klienta w encji Klient.
    1. Wybierz encję Klient pasującą do podstawowej encji Klient
    1. Wprowadź nazwę, która opisuje relację.
1. Wybierz **Dalej**.
1. Zmapuj pola semantyczne na atrybuty w encji działania klienta i wybierz **Zapisz**. Aby zapoznać się z opisami pól, należy zapoznać się z [wymaganiami wstępnymi](#prerequisites).
1. (Opcjonalnie) Jeśli istnieją inne działania klientów, które mają zostać uwzględnione, powtórz powyższe kroki.
   > [!div class="mx-imgBorder"]
   > ![Definiowanie relacji encji.](media/subscription-churn-customeractivitiesmapping.PNG "Strona działań klienta prezentująca atrybuty semantyczne, które są mapowane na pola w wybranej encji działań klienta")
1. Wybierz **Dalej**.

### <a name="set-schedule-and-review-configuration"></a>Konfigurowanie harmonogramu i przeglądu konfiguracji

1. Ustaw częstotliwość ponownego uczenia modelu. To ustawienie ma znaczenie dla aktualizowania dokładności prognoz, gdy nowe dane są zbierane w Customer Insights. Większość firm może przeprowadzać ponowne szkolenia raz w miesiącu i uzyskać dobrą dokładność przewidywań.
1. Wybierz **Dalej**.
1. Przejrzyj konfigurację. Aby powrócić do dowolnej części konfiguracji przewidywania wybierz **Edytuj** w obszarze ukazanej wartości. Można też wybrać krok konfiguracji ze wskaźnika postępu.
1. Jeśli wszystkie wartości są poprawnie skonfigurowane, wybierz **Zapisz i uruchom**, aby rozpocząć proces przewidywania. Na karcie **Moje przewidywania** można sprawdzić stan przewidywań. Przeprowadzanie procesu może potrwać kilka godzin, w zależności od ilości danych użytych w przewidywaniu.

## <a name="review-a-prediction-status-and-results"></a>Przejrzyj stan przewidywania i wyniki

1. Przejdź do karty **Moje przewidywania** w **Analiza** > **Przewidywania**.
   > [!div class="mx-imgBorder"]
   > ![Wyświetl na stronie Moje przewidywania.](media/subscription-churn-mypredictions.PNG "Wyświetl na stronie Moje przewidywania")
1. Wybierz przewidywania do przeglądu.
   - **Nazwa przewidywania:** Nazwa przewidywania podawana podczas jego tworzenia.
   - **Typ przewidywania:** Typ modelu używanego na potrzeby przewidywania
   - **Encja wyjściowa:** Nazwa encji, w której mają być przechowywane wyniki przewidywania. Encję o tej nazwie można znaleźć w **Dane** > **Encje**.    
     W encji wyjściowej *ChurnScore* jest prawdopodobieństwem rezygnacji, a *IsChurn* jest binarnym poziomem na podstawie wyniku *ChurnScore* z progiem 0,5. Domyślny próg może nie działać w tym scenariuszu. [Utwórz nowy segment](segments.md#create-a-segment) z wybranym progiem.
   - **Pole przewidywane:** To pole jest wypełniane tylko w przypadku niektórych typów przewidywań, i nie jest używane w przewidywaniu rezygnacji z subskrypcji.
   - **Stan:** Bieżący stan uruchomienia przewidywania.
        - **W kolejce:** Przewidywanie oczekuje obecnie na uruchomienie innych procesów.
        - **Odświeżanie:** Przewidywanie ma obecnie w toku etap "ocena" przetwarzania, aby wyprodukować wyniki, które przepłyną do encji wyjściowej.
        - **Niepowodzenie:** przewidywanie zakończyło się niepowodzeniem. Wybierz **Dzienniki**, aby otrzymać więcej szczegółowych informacji.
        - **Powodzenie:** przewidywanie zakończyło się pomyślnie. Wybierz **Widok** pod pionowymi wielokropkami, aby przejrzeć przewidywanie
   - **Edytowano:** Data konfiguracji dla przewidywania została zmieniona.
   - **Ostatnie odświeżenie:** Data odświeżonych wyników przewidywania w encji wyjściowej.
1. Zaznacz pionowy wielokropek obok przewidywania, dla którego chcesz przejrzeć wyniki, i wybierz **Widok**.
   > [!div class="mx-imgBorder"]
   > ![Widok opcji w menu pionowych wielokropków dla przewidywania, w tym edytowanie, odświeżanie, wyświetlanie, dzienniki i usuwanie.](media/subscription-churn-verticalellipses.PNG "Widok opcji w menu pionowych wielokropków dla przewidywania, w tym edytowanie, odświeżanie, wyświetlanie, dzienniki i usuwanie")
1. Na stronie wyników wyszukiwania znajdują się trzy podstawowe sekcje danych:
    1. **Wydajność modelu szkoleniowego:** A, B i C są możliwymi wynikami. Ten wynik wskazuje wydajność przewidywania i może pomóc w podjęciu decyzji w zakresie korzystania z wyników przechowywanych w encji wyjściowej.
        - Wyniki są określane na podstawie następujących reguł:
            - **A** Kiedy model precyzyjnie przewidział co najmniej 50% łącznych przewidywań, i kiedy procent dokładnych prognoz dla klientów, którzy zrezygnowali jest większy niż historyczny średni współczynnik rezygnacji o co najmniej 10% historycznego średniego współczynnika rezygnacji.
            - **B** Kiedy model precyzyjnie przewidział co najmniej 50% łącznych przewidywań, i kiedy procent dokładnych prognoz dla klientów, którzy zrezygnowali jest do 10% większy niż historyczny średni współczynnik rezygnacji średniego współczynnika rezygnacji.
            - **C**, kiedy model precyzyjnie przewidział mniej niż 50% łącznych przewidywań, lub kiedy procent dokładnych prognoz dla klientów, którzy zrezygnowali jest mniejszy niż historyczny średni współczynnik rezygnacji.
               > [!div class="mx-imgBorder"]
               > ![Widok wyniku wydajności modelu.](media/subscription-churn-modelperformance.PNG "Widok wyniku wydajności modelu")
    1. **Prawdopodobieństwo rezygnacji (liczba klientów):** Grupy klientów na podstawie ich przewidywanego ryzyka rezygnacji. Te dane mogą pomóc później, jeśli chcesz utworzyć segment klientów z dużym ryzykiem rezygnacji. Takie segmenty ułatwiają zrozumienie tego, w którym miejscu powinien się znaleźć próg dla członkostwa w segmencie.
       > [!div class="mx-imgBorder"]
       > ![Wykres przedstawiający rozkład wyników rezygnacji, podzielony na zakresy z 0–100%.](media/subscription-churn-resultdistribution.PNG "Wykres przedstawiający rozkład wyników rezygnacji, podzielony na zakresy z 0-100%")
    1. **Czynniki mające największy wpływ:** Istnieje wiele czynników branych pod uwagę podczas tworzenia przewidywania. Każdy z czynników ma swoje znaczenie obliczane dla zagregowanych przewidywań tworzonych przez model. Tych czynników można użyć w celu sprawdzenia poprawności wyników przewidywania. Można też użyć tych informacji później, aby [utworzyć segmenty](segments.md), które mogą wpłynąć na ryzyko rezygnacji dla klientów.
       > [!div class="mx-imgBorder"]
       > ![Lista prezentująca czynniki wywierające wpływ i ich znaczenie przy przewidywaniu wyniku rezygnacji.](media/subscription-churn-influentialfactors.PNG "Lista prezentująca czynniki wywierające wpływ i ich znaczenie przy przewidywaniu wyniku rezygnacji")

## <a name="manage-predictions"></a>Zarządzaj przewidywaniami

Można optymalizować, rozwiązywać problemy, odświeżać lub usuwać przewidywania. Zapoznaj się z raportem użyteczności danych wejściowych, aby dowiedzieć się, jak przyspieszyć przewidywanie i zwiększyć jego wiarygodność. Aby uzyskać więcej informacji, zobacz [Zarządzaj przewidywaniami](manage-predictions.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
