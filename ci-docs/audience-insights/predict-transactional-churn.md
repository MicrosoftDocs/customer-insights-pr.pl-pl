---
title: Przewidywanie rezygnacji z transakcji
description: Przewiduj, czy klient jest zagrożony, jeśli przestanie kupować Twoje produkty lub usługi.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 28c89693239393d93b7a816535b8c3fffe353935
ms.sourcegitcommit: e57d51ae3cc233f7b6185c074c66efd9800c02c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/14/2021
ms.locfileid: "6559418"
---
# <a name="transactional-churn-prediction-preview"></a>Przewidywanie rezygnacji z transakcji (wersja zapoznawcza)

Prognozowanie rezygnacji z transakcji pomaga przewidzieć, czy klient nie będzie już kupować Twoich produktów lub usług w danym oknie czasowym. Nowe przewidywania mogą być tworzone w **Analizy** > **Przewidywania**. Wybierz **Moje przewidywania**, aby wyświetlić inne utworzone przewidywania.

> [!TIP]
> Wypróbuj samouczek, aby uzyskać translacyjne przewidywanie rezygnacji z przykładowych danych: [Przykładowy przewodnik dotyczący prognozowania rezygnacji z transakcji (wersja zapoznawcza)](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Wymagania wstępne

- Co najmniej [Uprawnienia współautora](permissions.md) w Customer Insights.
- Wiedza biznesowa, pozwalająca zrozumieć co rezygnacja oznacza dla Twojej działalności. Obsługujemy definicje rezygnacji na podstawie czasu, co oznacza, że klient odszedł po okresie braku zakupów.
- Dane o transakcjach/zakupach oraz ich historii:
    - Identyfikatory transakcji w celu rozróżnienia zakupionych/transakcji.
    - Identyfikatory klientów, aby odpowiadały transakcjom klientów.
    - Daty zdarzeń transakcji, które określają daty, w których doszło do transakcji.
    - Schemat danych semantycznych dla operacji zakupu/transakcji wymaga następujących informacji:
        - **Identyfikator transakcji:** unikatowy identyfikator zakupu lub transakcji.
        - **Data transakcji:** Data zakupu lub transakcji.
        - **Wartość transakcji:** Kwota waluty/wartości liczbowej transakcji/pozycji.
        - (Opcjonalnie) **Unikatowy identyfikator produktu:** Identyfikator zakupionego produktu lub usługi, jeśli dane są na poziomie pozycji wiersza.
        - (Opcjonalnie) **Czy ta transakcja była zwrotem:** pole typu prawda/fałsz, które określa, czy transakcja była zwrotna, czy nie. Jeśli **Wartość transakcji** jest ujemna, Microsoft będzie również używać tych informacji do wywnioskowania, że nastąpił zwrot.
- (Opcjonalnie) Dane o działaniach klientów:
    - Identyfikatory działań w celu wyróżnienia działań tego samego typu.
    - Identyfikatory klientów, umożliwiające mapowanie działań do klientów.
    - Informacje o działaniu zawierające nazwę i datę działania.
    - Schemat danych semantycznych dla działań klientów zawiera:
        - **Klucz podstawowy:** Unikatowy identyfikator działania. Na przykład wizyta w witrynie internetowej lub zapis użytkowania pokazujący, że klient wypróbował próbkę Twojego produktu.
        - **Sygnatura czasowa:** Data i godzina zdarzenia identyfikowanego przez klucz podstawowy.
        - **Zdarzenie:** Określ nazwę zdarzenia, które chcesz użyć. Na przykład pole o nazwie „UserAction” w sklepie spożywczym może być kuponem używanym przez klienta.
        - **Szczegóły:** Szczegółowe informacje o zdarzeniu. Na przykład pole o nazwie „CouponValue” w sklepie spożywczym może zawierać walutę kuponu.
- Sugerowana charakterystyka danych:
    - Wystarczające dane historyczne: dane transakcji dla co najmniej podwójnego wybranego okna czasowego. Najlepiej, dwa do trzech lat historii transakcji. 
    - Wiele zakupów na klienta: idealnie przynajmniej dwie transakcje na klienta.
    - Liczba klientów: co najmniej 10 profilów klientów, najlepiej ponad 1000 unikalnych klientów. Model zakończy z niepowodzeniem, jeśli będzie mniej niż 10 klientów oraz niewystarczające dane historycznych.
    - Pełność danych: mniej niż 20% brakujących wartości w polu danych dostarczonej encji.

> [!NOTE]
> W przypadku działalności o wysokiej częstotliwości zakupów u klientów (co kilka tygodni) zaleca się wybranie krótszego okna przewidywania i definicji rezygnacji. W przypadku niskiej częstotliwości zakupu (co kilka miesięcy lub raz do roku), wybierz dłuższy przewidywania i definicji rezygnacji.

## <a name="create-a-transactional-churn-prediction"></a>Utwórz prognozę rezygnacji z transakcji

1. W Customer Insights przejdź do **Analizy** > **Przewidywania**.

1. Wybierz kafelek **Model rezygnacji klientów (wersja zapoznawcza)** i wybierz opcję **Użyj tego modelu**.
   
1. W okienku **Model rezygnacji klientów** wybierz opcję **Transakcyjne** i wybierz pozycję **Rozpocznij**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Zrzut ekranu z wybraną opcją transakcyjną w okienku modelu rezygnacji klientów.":::

### <a name="name-model"></a>Nadaj nazwę modelowi

1. Podaj nazwę modelu odróżniającą go od innych modeli.

1. Podaj nazwę encji wyjściowej używając wyłącznie liter i cyfr, bez żadnych spacji. To jest nazwa, której będzie używać encja modelowa. 

1. Wybierz **Dalej**.

### <a name="define-customer-churn"></a>Definiuj rezygnację klienta

1. Ustaw przedział dni na prognozowanie rezygnacji w polu **Zidentyfikuj klientów, którzy mogą odejść w następnym**. Na przykład prognozuj ryzyko odejścia klientów w ciągu najbliższych 90 dni, aby dostosować się do działań marketingowych dotyczących utrzymania klientów. Przewidywanie ryzyka odejścia na dłuższy lub krótszy okres może utrudnić uwzględnienie czynników w profilu ryzyka odejścia, ale zależy to od konkretnych wymagań biznesowych. 
   >[!TIP]
   > W dowolnym momencie możesz wybrać **Zapisz i zamknij**, aby zapisać przewidywanie jako wersję roboczą. Aby kontynuować, należy znaleźć przewidywanie w wersji roboczej na karcie **Moje przewidywania**.

1. Wprowadź liczbę dni do zdefiniowania rezygnacji w polu **Klient odszedł, jeśli nie dokonał zakupów w:**. Na przykład, jeśli klient nie dokonał zakupów w ciągu ostatnich 30 dni, może zostać uznany za klienta, który zrezygnował, w przypadku Twojej firmy. 

1. Wybierz **Dalej**, aby kontynuować

### <a name="add-required-data"></a>Dodaj wymagane dane

1. Wybierz opcję **Dodaj dane** do **Historii zakupu** i wybierz encję, która dostarcza informacje historyczne dotyczące transakcji i zakupu, jak to opisano w sekcji [wymagania wstępne](#prerequisites).

1. Zmapuj pola semantyczne na atrybuty w encji historii zakupu i wybierz przycisk **Dalej**. Aby zapoznać się z opisami pól, należy zapoznać się z [wymaganiami wstępnymi](#prerequisites).

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="Mapowanie pól semantycznych encji zakupu.":::

1. Jeśli poniższe pola nie są wypełnione, skonfiguruj relację z encji historii zakupu do encji klient.
    1. Wybierz **Encja historii zakupów**.
    1. Wybierz **Pole**, które identyfikuje klienta w encji historii zakupu. Musi ono być powiązane z podstawowym identyfikatorem klienta encji Klient.
    1. Wybierz **encję Klient** pasującą do podstawowej encji klienta.
    1. Wprowadź nazwę, która opisuje relację.

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="Strona historii zakupów pokazująca tworzenie relacji z klientem.":::
   
1. Wybierz **Dalej**.

1. Możesz też wybrać pozycję **Dodaj dane** do **Działań klienta**. Wybierz encję, która dostarcza informacje o działaniu klienta w sposób opisany w sekcji wymagania wstępne.

1. Zmapuj pola semantyczne na atrybuty w encji działań klienta i wybierz przycisk **Dalej**. Aby zapoznać się z opisami pól, należy zapoznać się z [wymaganiami wstępnymi](#prerequisites).

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="Zamapuj pola klientów na dane transakcji.":::

1. Wybierz typ działania odpowiadający typowi działania klienta, które konfigurujesz. Wybierz opcję **Utwórz nowy** i wybierz dostępny typ działania lub utwórz nowy typ.

1. Należy skonfigurować relację od encji działania klienta do encji Klient.
    1. Wybierz pole, które identyfikuje klienta w tabeli aktywności klientów. Może być bezpośrednio powiązany z głównym identyfikatorem klienta encji klienta.
    1. Wybierz encję Klient pasującą do podstawowej encji Klient
    1. Wprowadź nazwę, która opisuje relację.

1. Wybierz pozycję **Zapisz**.

1. Jeśli istnieją inne działania dotyczące klientów, które mają zostać uwzględnione, powtórz te kroki.

1. Wybierz **Dalej**.

### <a name="set-schedule-and-review-configuration"></a>Konfigurowanie harmonogramu i przeglądu konfiguracji

1. Ustaw częstotliwość ponownego uczenia modelu. To ustawienie jest ważne, aby zaktualizować dokładność prognoz w miarę pozyskiwania nowych danych. Większość firm może przeprowadzać ponowne szkolenia raz w miesiącu i uzyskać dobrą dokładność przewidywań.

1. Wybierz **Dalej**.

1. Przejrzyj konfigurację prognozy. Aby wrócić do poprzednich kroków, można wybrać opcję **Edycji** pod pokazaną wartością. Można też wybrać krok konfiguracji ze wskaźnika postępu.

1. Jeśli wszystkie wartości są poprawnie skonfigurowane, wybierz **Zapisz i uruchom**, aby rozpocząć proces przewidywania. Na karcie **Moje przewidywania** można sprawdzić stan przewidywań. Przeprowadzanie procesu może potrwać kilka godzin, w zależności od ilości danych użytych w przewidywaniu.

## <a name="review-a-prediction-status-and-results"></a>Przejrzyj stan przewidywania i wyniki

1. Wybierz **Analizy** > **Przewidywania** i wybierz kartę **Moje przewidywania**.

1. Wybierz przewidywania do przeglądu.
   - **Nazwa przewidywania:** Nazwa przewidywania podana podczas jej tworzenia..
   - **Typ przewidywania:** typ modelu używanego przez przewidywanie
   - **Encja wyjściowa:** Nazwa encji, w której mają być przechowywane wyniki przewidywania. Encję o tej nazwie można znaleźć w **Dane** > **Encje**.    
     W encji wyjściowej *ChurnScore* jest prawdopodobieństwem rezygnacji, a *IsChurn* jest binarnym poziomem na podstawie wyniku *ChurnScore* z progiem 0,5. Domyślny próg może nie działać w tym scenariuszu. [Utwórz nowy segment](segments.md#create-a-new-segment) z wybranym progiem.
     Nie wszyscy klienci muszą być aktywnymi klientami. Niektórzy z nich mogą nie mieć żadnego działania przez dłuższy czas i są już traktowane jako rezygnacja na podstawie definicji rezygnacji. Przewidywanie ryzyka rezygnacji dla klientów, którzy już zrezygnowali, nie jest przydatne, ponieważ nie są oni odbiorcami stanowiącymi podmiot zainteresowania.
   - **Przewidywane pole:** To pole jest wypełniane tylko w przypadku niektórych typów przewidywań i nie jest używane w przewidywaniu rezygnacji.
   - **Stan:** Stan przebiegu przewidywania.
        - **W kolejce:** Przewidywanie oczekuje na uruchomienie innych procesów.
        - **Odświeżanie:** przewidywanie jest obecnie uruchomione w celu wyprodukowania wyników, które będą przepływać na encję wyjściową.
        - **Niepowodzenie:** uruchomienie przewidywanie zakończyło się niepowodzeniem. Aby uzyskać więcej informacji, [przejrzyj dzienniki](manage-predictions.md#troubleshoot-a-failed-prediction).
        - **Zakończono pomyślnie:** przewidywanie zakończyło się sukcesem. Wybierz **Widok** pod pionowymi wielokropkami, aby przejrzeć przewidywanie
   - **Edytowano:** Data konfiguracji dla przewidywania została zmieniona.
   - **Ostatnie odświeżenie:** Data odświeżonych wyników przewidywania w encji wyjściowej.

1. Zaznacz pionowy wielokropek obok przewidywania, dla którego chcesz przejrzeć wyniki, i wybierz **Widok**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Wyświetl kontrolkę, aby zobaczyć wyniki prognozy.":::   

1. Na stronie wyników wyszukiwania znajdują się trzy podstawowe sekcje danych:
    1. **Wydajność modelu szkoleniowego:** A, B i C są możliwymi wynikami. Ten wynik wskazuje wydajność przewidywania i może pomóc w podjęciu decyzji w zakresie korzystania z wyników przechowywanych w encji wyjściowej. Wyniki są określane na podstawie następujących reguł:
         
         - **A** kiedy model dokładnie przewidział co najmniej 50% wszystkich prognoz, a odsetek trafnych prognoz dla klientów, którzy zrezygnowali, jest większy od wskaźnika bazowego o co najmniej 10%.
            
         - **B** kiedy model dokładnie przewidział co najmniej 50% wszystkich prognoz, a odsetek trafnych prognoz dla klientów, którzy zrezygnowali, jest do 10% większy niż poziom bazowy.
            
         - **C** kiedy model dokładnie przewidział mniej niż 50% wszystkich prognoz lub odsetek trafnych prognoz dla klientów, którzy zrezygnowali, jest do 10% mniejszsy niż poziom bazowy.
               
         - **Linia bazowa** przyjmuje dane wejściowe w oknie czasowym prognozy dla modelu (na przykład jeden rok), a model tworzy różne ułamki czasu, dzieląc je przez 2, aż osiągnie jeden miesiąc lub mniej. Wykorzystuje te ułamki do stworzenia reguły biznesowej dla klientów, którzy nie dokonali zakupów w tym przedziale czasowym. Tych klientów uważa się za utraconych. Jako model bazowy wybrano regułę biznesową opartą na czasie z największą zdolnością przewidywania, kto prawdopodobnie odejdzie.
            
    1. **Prawdopodobieństwo rezygnacji (liczba klientów):** Grupy klientów na podstawie ich przewidywanego ryzyka rezygnacji. Te dane mogą pomóc później, jeśli chcesz utworzyć segment klientów z dużym ryzykiem rezygnacji. Takie segmenty ułatwiają zrozumienie tego, w którym miejscu powinien się znaleźć próg dla członkostwa w segmencie.
       
    1. **Czynniki mające największy wpływ:** Istnieje wiele czynników branych pod uwagę podczas tworzenia przewidywania. Każdy z czynników ma swoją wagę obliczoną dla zagregowanych prognoz tworzonych przez model. Tych czynników można użyć w celu sprawdzenia poprawności wyników przewidywania. Można też użyć tych informacji później, aby [utworzyć segmenty](segments.md), które mogą wpłynąć na ryzyko rezygnacji dla klientów.

## <a name="manage-predictions"></a>Zarządzaj przewidywaniami

Można optymalizować, rozwiązywać problemy, odświeżać lub usuwać przewidywania. Zapoznaj się z raportem użyteczności danych wejściowych, aby dowiedzieć się, jak przyspieszyć przewidywanie i zwiększyć jego wiarygodność. Aby uzyskać więcej informacji, zobacz [Zarządzaj przewidywaniami](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
