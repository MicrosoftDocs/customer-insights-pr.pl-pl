---
title: Przewidywanie Wartość okresu istnienia klienta (CLV)
description: Potencjalne przychody aktywnych klientów w przyszłości.
ms.date: 02/05/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 835a9f3371a8c1b1a10d5c6901c03e1df5379d3d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595822"
---
# <a name="customer-lifetime-value-clv-prediction-preview"></a>Przewidywanie Wartości okresu istnienia klienta (wersja zapoznawcza)

Przewiduj potencjalną wartość (przychód), jaką indywidualni aktywni klienci przyniosą Twojej firmie w określonym okresie w przyszłości. Ta funkcja umożliwia osiągnięcie różnych celów: 
- Identyfikowanie klientów o wysokiej wartości i przetwarzanie tych informacji
- Twórz strategiczne segmenty klientów w oparciu o ich potencjalną wartość, aby prowadzić spersonalizowane kampanie z ukierunkowaną sprzedażą, marketingiem i działaniami wsparcia
- Kieruj rozwojem produktu, koncentrując się na funkcjach zwiększających wartość klienta
- Zoptymalizuj strategię sprzedaży lub marketingu i dokładniej przydziel budżet na potrzeby dotarcia do klientów
- Rozpoznawaj i nagradzaj wartościowych klientów za pomocą programów lojalnościowych lub programów nagród 

## <a name="prerequisites"></a>Wymagania wstępne

Zanim zaczniesz, zastanów się, co CLV oznacza dla Twojej firmy. Obecnie obsługujemy prognozowanie CLV oparte na transakcjach. Przewidywana wartość klienta jest oparta na historii transakcji biznesowych. Aby utworzyć przewidywanie trzeba mieć co najmniej uprawnienia [współautora](permissions.md).

Ponieważ konfigurowanie i uruchamianie modelu CLV nie zajmuje dużo czasu, rozważ utworzenie kilku modeli z różnymi preferencjami wejściowymi i porównaj wyniki modeli, aby zobaczyć, który scenariusz modelu najlepiej odpowiada Twoim potrzebom biznesowym.

###  <a name="data-requirements"></a>Wymagania dotyczące danych

Poniższe dane są wymagane, a jeśli oznaczono je jako opcjonalne, zalecane w celu zwiększenia wydajności modelu. Im więcej danych może przetworzyć model, tym dokładniejsza będzie prognoza. Dlatego zachęcamy do pozyskiwania większej ilości danych o aktywności klientów, jeśli są dostępne.

- Identyfikator klienta: Unikalny identyfikator umożliwiający dopasowanie transakcji do indywidualnego klienta

- Historia transakcji: Historyczny dziennik transakcji z poniższym semantycznym schematem danych
    - Identyfikator transakcji: niepowtarzalny identyfikator każdej transakcji
    - Data transakcji: data, najlepiej sygnatura czasowa każdej transakcji
    - Kwota transakcji: wartość pieniężna (na przykład przychód lub marża zysku) każdej transakcji
    - Etykieta przypisana do zwrotów (opcjonalnie): wartość logiczna wskazująca, czy transakcja jest zwrotem 
    - Identyfikator produktu (opcjonalnie): Identyfikator produktu, którego dotyczy transakcja

- Dodatkowe dane (opcjonalnie), na przykład
    - Działania w sieci: historia odwiedzin na stronie, historia e-maili
    - Działania lojalnościowe: historia gromadzenia i wykorzystania punktów lojalnościowych
    - Obsługa klienta dziennika, zgłoszenia, skargi lub historii zwrotów
- Dane o działaniach klientów (opcjonalnie):
    - Identyfikatory działań w celu wyróżnienia działań tego samego typu
    - Identyfikatory klientów, umożliwiające mapowanie działań do klientów
    - Informacje o działaniu zawierające nazwę i datę działania
    - Semantyczny schemat danych dla działań obejmuje: 
        - Klucz podstawowy: Unikatowy identyfikator działania
        - Sygnatura czasowa: Data i godzina zdarzenia identyfikowanego przez klucz podstawowy
        - Zdarzenie (nazwa działania): Nazwa wydarzenia, którego chcesz użyć
        - Szczegóły (kwota lub wartość): Szczegółowe informacje dotyczące działania klienta

## <a name="create-a-customer-lifetime-value-prediction"></a>Utwórz prognozę wartości okresu istnienia klienta

1. W analizach odbiorców przejdź do **Analizy** > **Przewidywania**.

1. Wybierz kafelek **Wartość okresu istnienia klienta** i wybierz opcję **Użyj modelu**. 

1. W okienku **Wartość okresu istnienia klienta (podgląd)** wybierz opcję **Wprowadzenie**.

1. **Nazwij ten model** i **Nazwa encji wyjściowej**, aby odróżnić je od innych modeli lub encji.

1. Wybierz **Dalej**.

### <a name="define-model-preferences"></a>Zdefiniuj preferencje modelu

1. Ustaw **Okres przewidywania**, aby określić, jak daleko w przyszłości chcesz przewidzieć CLV.    
   Domyślnie jednostka jest ustawiona na miesiące. Można zmienić go na lata, aby w przyszłości wyglądać dalej.

   > [!TIP]
   > Aby dokładnie przewidzieć CLV dla ustawionego okresu, potrzebujesz porównywalnego okresu danych historycznych. Na przykład, jeśli chcesz prognozować na następne 12 miesięcy, zaleca się, aby mieć co najmniej 18-24 miesiące danych historycznych.

1. Określ, co **Aktywni klienci** oznaczają dla firmy. Ustaw przedział czasu, w którym klient musiał mieć co najmniej jedną transakcję, aby zostać uznanym za aktywną. Model będzie przewidywał tylko CLV dla aktywnych klientów. 
   - **Zezwól modelowi na obliczenie interwału zakupów (zalecane)**: Model analizuje Twoje dane i określa okres na podstawie historycznych zakupów.
   - **Ustaw interwał ręcznie**: Jeśli masz określoną definicję biznesową aktywnego klienta, wybierz tę opcję i odpowiednio ustaw przedział czasu.

1. Definiować wartość procentową **Klienta o wysokiej wartości**, aby umożliwić modelowi dostarczanie wyników zgodnych z definicją biznesową.
    - **Model obliczania (zalecane)**: Model analizuje dane i na podstawie historii transakcji klientów określa, jaka wartość może być dla Twojej firmy klientem. Model wykorzystuje regułę heurystyczną (inspirowaną regułą 80/20 lub zasadą pareto), aby znaleźć odsetek klientów o wysokiej wartości. Odsetek klientów, którzy przyczynili się do 80% skumulowanych przychodów Twojej firmy w okresie historycznym, to klienci o dużej wartości. Zwykle mniej niż 30-40% klientów przyczynia się do 80% skumulowanych przychodów. Jednak liczba ta może się różnić w zależności od Twojej firmy i branży.    
    - **Procent najbardziej aktywnych klientów**: Zdefiniuj klientów o dużej wartości dla swojej firmy jako percentyl najlepiej płacących aktywnych klientów. Na przykład możesz użyć tej opcji, aby zdefiniować klientów o wysokiej wartości jako 20% przyszłych płacących klientów.

    Jeśli Twoja firma definiuje klientów o dużej wartości w inny sposób, [daj nam znać, z przyjemnością dowiemy się więcej](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Wybierz pozycję **Dalej**, aby przejść do następnego kroku.

### <a name="add-required-data"></a>Dodaj wymagane dane

1. W kroku **Wymagane dane** wybierz opcję **Dodaj dane** do **Historia transakcji klienta** i wybierz encję, która dostarcza informacje historyczne dotyczące transakcji, jak to opisano w sekcji [wymagania wstępne](#prerequisites).

1. Zmapuj pola semantyczne na atrybuty w encji historii zakupu i wybierz przycisk **Dalej**.

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="Obraz przedstawiający krok konfiguracji w celu zmapowania atrybutów danych dla wymaganych danych.":::
 
1. Jeśli poniższe pola nie są wypełnione, skonfiguruj relację z encji historii zakupu do encji *Klient* i wybierz **Zapisz**.
    1. Wybierz jednostkę historii transakcji.
    1. Wybierz pole, które identyfikuje klienta w encji historii zakupu. Musi ono być powiązane z podstawowym identyfikatorem klienta encji Klient.
    1. Wybierz encję, która pasuje do Twojej podstawowej encji klienta.
    1. Wprowadź nazwę, która opisuje relację.

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="Obraz przedstawiający krok konfiguracji w celu zdefiniowania relacji z jednostką klienta.":::

1. Wybierz **Dalej**.

### <a name="add-optional-data"></a>Dodaj dane opcjonalne

Dane odzwierciedlające kluczowe interakcje z klientami (takie jak internet, obsługa klienta i dzienniki zdarzeń) dodają kontekst do rekordów transakcji. Więcej wzorców znalezionych w danych o aktywności klientów może poprawić dokładność prognoz. 

1. W kroku **Dodatkowe dane (opcjonalnie)** wybierz opcję **Dodaj dane**. Wybierz encję czynności klienta, która dostarcza informacje o działaniu klienta w sposób opisany w sekcji [wymagania wstępne](#prerequisites).

1. Zmapuj pola semantyczne na atrybuty w encji działań klienta i wybierz przycisk **Dalej**.

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="Obraz przedstawiający krok konfiguracji w celu zmapowania pól na dodatkowe dane.":::

1. Wybierz typ działania dopasowania do typu działania klienta, które jest dodawane. Wybierz jeden z istniejących typów działań lub dodaj nowy typ działania.

1. Skonfiguruj relację z encji działania klienta z encją *Klient*.
    
    1. Wybierz pole, które identyfikuje klienta w tabeli aktywności klientów. Może być bezpośrednio powiązany z głównym identyfikatorem *Klienta* encji klienta.
    1. Wybierz encję *Klient* pasującą do podstawowej encji *Klienta*.
    1. Wprowadź nazwę, która opisuje relację.

   :::image type="content" source="media/clv-additional-data.png" alt-text="Obraz przedstawiający krok w przepływie konfiguracji służący do dodawania dodatkowych danych i konfigurowania czynności z wypełnionymi przykładami.":::

1. Wybierz pozycję **Zapisz**.    
    Dodaj więcej danych, jeśli chcesz uwzględnić inne działania klientów.

1. Wybierz **Dalej**.

### <a name="set-update-schedule"></a>Ustaw harmonogram aktualizacji

1. W kroku **Harmonogram aktualizacji danych** wybierz częstotliwość ponownego uaktualnienia modelu na podstawie najnowszych danych. To ustawienie jest ważne, aby zaktualizować dokładność prognoz w miarę pozyskiwania nowych danych ze statystyk odbiorców. Większość firm może przeprowadzać ponowne szkolenia raz w miesiącu i uzyskać dobrą dokładność przewidywań.

1. Wybierz **Dalej**.


### <a name="review-and-run-the-model-configuration"></a>Przegląd i uruchamianie konfiguracji modelu

1. W kroku **Przegląd szczegółów modelu** sprawdź poprawność konfiguracji przewidywania. Aby powrócić do dowolnej części konfiguracji przewidywania wybierz **Edytuj** w obszarze ukazanej wartości. Możesz także wybrać krok konfiguracji ze wskaźnika postępu.

1. Jeśli wszystkie wartości zostały skonfigurowane poprawnie, wybierz opcję **Zapisz i uruchom**, aby rozpocząć uruchamianie modelu. Na karcie **Moje prognozy** można zobaczyć stan przewidywanie danych. Przeprowadzanie procesu może potrwać kilka godzin, w zależności od ilości danych użytych w przewidywaniu.

## <a name="review-prediction-status-and-results"></a>Przeglądanie przewidywanie wyników

### <a name="review-prediction-status"></a>Przeglądanie przewidywania danych

1.  Wybierz **Analizy** > **Przewidywania** i wybierz kartę **Moje przewidywania**.
2.  Wybierz przewidywania do przeglądu.

- **Nazwa przewidywania**: Nazwa przewidywania podana podczas jej tworzenia.
- **Typ przewidywania**: typ modelu używanego przez przewidywanie
- **Encja wyjściowa**: Nazwa encji, w której mają być przechowywane wyniki przewidywania. Przejdź do **Dane** > **Encje** w celu znalezienia encji o tej nazwie.
- **Przewidywane pole**: To pole jest wypełniane tylko w przypadku niektórych typów prognoz i nie jest używane w przewidywaniu długookresowej wartości klienta.
- **Stan**: Stan przebiegu przewidywania.
    - **W kolejce**: Prognoza czeka na zakończenie innych procesów.
    - **Odświeżanie**: przewidywanie jest obecnie uruchomione w celu utworzenia wyników, które będą przepływać na encję wyjściową.
    - **Niepowodzenie**: uruchomienie przewidywanie zakończyło się niepowodzeniem. Aby uzyskać więcej informacji, [przejrzyj dzienniki](#troubleshoot-a-failed-prediction).
    - **Zakończono pomyślnie**: przewidywanie zakończyło się sukcesem. Wybierz **Wyświetl** pod elipsami pionowymi, aby przewidzieć wyniki.
- **Edytowano**: Data konfiguracji dla przewidywania została zmieniona.
- **Ostatnie odświeżenie**: Data odświeżonych wyników przewidywania w encji wyjściowej.


### <a name="review-prediction-results"></a>Przeglądanie wyników przewidywania

1. Wybierz **Analizy** > **Przewidywania** i wybierz kartę **Moje przewidywania**.

1. Wybierz prognozę, dla której chcesz przejrzeć wyniki.

Na stronie wyników wyszukiwania znajdują się trzy podstawowe sekcje danych.

- **Wydajność modelu szkoleniowego**: A, B lub C to możliwe oceny. Ta ocena wskazuje wydajność prognozy i może pomóc w podjęciu decyzji o użyciu wyników przechowywanych w encji wyjściowej. Wybierz opcję **Dowiedz się więcej o tej ocenie**, aby lepiej poznać podstawowe metryki wydajności modelu oraz sposób pochodny końcowej oceny wydajności modelu.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Obraz pola informacji o wynikach modelu wraz z oceną A.":::

  Korzystając z definicji klientów o dużej wartości, podanej podczas konfigurowania prognozy, system ocenia, jak model sztucznej inteligencji radził sobie w przewidywaniu klientów o dużej wartości w porównaniu z modelem bazowym.    

  Oceny są określane na podstawie następujących reguł:
  - A kiedy model dokładnie przewidział co najmniej 5% więcej wartościowych klientów w porównaniu z modelem bazowym.
  - B gdy model dokładnie przewidział od 0 do 5% więcej klientów o wysokiej wartości w porównaniu z modelem bazowym.
  - C, gdy model dokładnie przewidział mniej wartościowych klientów w porównaniu z modelem bazowym.

  W okienku **Klasyfikacji modelu** pokazuje dalsze szczegóły dotyczące wydajności modelu AI i modelu bazowego. Model bazowy wykorzystuje podejście nie oparte na sztucznej inteligencji do obliczania wartości klienta od początku śledzenia na podstawie historycznych zakupów dokonanych przez klientów.     
  Standardowa formuła używana do obliczania CLV według modelu bazowego:    

  *CLV dla każdego klienta = Średni miesięczny zakup dokonany przez klienta w aktywnym oknie klienta * Liczba miesięcy w okresie prognozowania CLV * Ogólny wskaźnik utrzymania wszystkich klientów*

  Model AI jest porównywany z modelem bazowym w oparciu o dwie metryki wydajności modelu.
  
  - **Wskaźnik sukcesu w przewidywaniu wartościowych klientów**

    Zobacz różnicę w przewidywaniu klientów o dużej wartości za pomocą modelu AI w porównaniu z modelem bazowym. Na przykład wskaźnik sukcesu 84% oznacza, że spośród wszystkich klientów o dużej wartości w danych szkoleniowych model sztucznej inteligencji był w stanie dokładnie uchwycić 84%. Następnie porównujemy ten wskaźnik sukcesu ze wskaźnikiem sukcesu modelu bazowego, aby zgłosić względną zmianę. Ta wartość służy do przypisywania oceny modelowi.

  - **Metryki błędów**
    
    Inna metryka umożliwia przeglądanie ogólnej wydajności modelu pod kątem błędu w przewidywaniu przyszłych wartości. Do oceny tego błędu używamy ogólnej metryki Root Mean Squared Error (RMSE). RMSE to standardowy sposób pomiaru błędu modelu przy prognozowaniu danych ilościowych. Wartość RMSE modelu AI jest porównywana z wartością RMSE modelu bazowego i zgłaszana jest względna różnica.

  Model AI nadaje priorytet dokładnemu rankingowi klientów zgodnie z wartością, jaką wnoszą do Twojej firmy. Tak więc do wyliczenia ostatecznej oceny modelu wykorzystuje się tylko wskaźnik sukcesu przewidywania klientów o wysokiej wartości. Metryka RMSE jest wrażliwa na wartości odstające. W scenariuszach, w których masz niewielki odsetek klientów z wyjątkowo wysokimi wartościami zakupów, ogólna metryka RMSE może nie dawać pełnego obrazu wydajności modelu.   

- **Wartość klientów wg percentylu**: Korzystając z Twojej definicji klientów o dużej wartości, klienci są grupowani na klientów o niskiej i wysokiej wartości, na podstawie ich prognoz CLV, i są przedstawiani na wykresie. Po najechaniu kursorem na słupki na histogramie można zobaczyć liczbę klientów w każdej grupie i średnią wartość CLV tej grupy. Te dane mogą pomóc, jeśli chcesz [utworzyć segmenty klientów](segments.md) na podstawie ich prognoz CLV.

- **Czynniki mające największy wpływ**: Podczas tworzenia prognozy CLV na podstawie danych wejściowych dostarczonych do modelu AI brane są pod uwagę różne czynniki. Każdy z czynników ma swoje znaczenie obliczane dla zagregowanych przewidywań tworzonych przez model. Tych czynników można użyć w celu sprawdzenia poprawności wyników przewidywania. Czynniki te zapewniają również lepszy wgląd w najbardziej wpływowe czynniki, które przyczyniły się do przewidywania CLV u wszystkich klientów.

## <a name="refresh-a-prediction"></a>Odświeżanie przewidywania

Prognozy są automatycznie odświeżane według [harmonogramu odświeżania danych](system.md#schedule-tab) zgodnie z stawieniami skonfigurowanymi w ustawieniach. Można je również ręcznie odświeżyć.

1. Wybierz **Analizy** > **Przewidywania** i wybierz kartę **Moje przewidywania**.
2. Wybierz pionowy wielokropek obok przewidywania, które chcesz odświeżyć.
3. Wybierz **Odśwież**.

## <a name="delete-a-prediction"></a>Usuń przewidywanie

Usunięcie przewidywanie usuwa również jej encję wyjściową.

1. Wybierz **Analizy** > **Przewidywania** i wybierz kartę **Moje przewidywania**.
2. Wybierz pionowy wielokropek obok przewidywania, które chcesz usunąć.
3. Wybierz **Usuń**.

## <a name="troubleshoot-a-failed-prediction"></a>Rozwiązywanie problemów dotyczących nieudanych przewidywań

1. Wybierz **Analizy** > **Przewidywania** i wybierz kartę **Moje przewidywania**.
2. Zaznacz wielokropek pionowy obok etykiety przewidywań, dla których chcesz wyświetlić dzienniki błędów.
3. Wybierz **Dzienniki**.
4. Przejrzyj wszystkie błędy. Istnieje kilka typów błędów, które mogą wystąpić, i opisują one jaki warunek spowodował błąd. Na przykład błąd, w przypadku którego nie ma wystarczającej ilości danych do dokładnego przewidzenia, jest zwykle usuwany przez załadowanie większej ilości danych do statystyk odbiorców.


[!INCLUDE[footer-include](../includes/footer-banner.md)]