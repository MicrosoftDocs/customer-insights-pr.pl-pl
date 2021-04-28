---
title: Przewidywanie rekomendacji produktów
description: Przewiduj produkty, które klient prawdopodobnie kupi lub z którymi będzie miał do czynienia.
ms.date: 03/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: e46e31131a2dd5235af8221eafcd2e1d1394f3d4
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906777"
---
# <a name="product-recommendation-prediction-preview"></a>Przewidywanie rekomendacji produktów (wersja zapoznawcza)

Model rekomendacji produktowych tworzy zestawy predykcyjnych rekomendacji produktowych. Rekomendacje opierają się na wcześniejszych zachowaniach zakupowych i klientach o podobnych wzorcach zakupowych. Możesz tworzyć nowe prognozy rekomendacji produktów na stronie **Analizy** > **Przewidywania**. Wybierz **Moje przewidywania**, aby wyświetlić inne utworzone przewidywania.

Polecane produkty mogą podlegać lokalnym przepisom i ustawom oraz oczekiwaniom klientów, których model nie bierze pod uwagę, gdyż nie jest do tego przeznaczony.  Użytkownik tej predykcyjnej funkcji **musi przejrzeć rekomendacje przed dostarczenia ich klientom**, aby upewnić się, że są zgodne z obowiązującymi przepisami i rozporządzeniami oraz oczekiwaniami klientów dotyczącymi produktów, które mogą być polecane. 

Ponadto dane wyjściowe tego modelu przedstawi zalecenia na podstawie identyfikatora produktu. Mechanizm dostawy będzie musiał zamapować przewidziane identyfikatory produktów na odpowiednią zawartość dla klientów, biorąc pod uwagę lokalizację, zawartość obrazów i inne specyficzne dla biznesu zawartości lub zachowanie.

## <a name="sample-guide"></a>Przykładowy przewodnik

Jeśli chcesz spróbować tej funkcji, ale nie masz danych, które spełniają poniższe wymagania, możesz [utworzyć przykładową implementację](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Wymagania wstępne

- Co najmniej [Uprawnienia współautora](permissions.md) w Customer Insights.

- Wiedza biznesowa pozwalająca zrozumieć różne rodzaje produktów dla Twojej firmy i sposób interakcji z nimi klientów. Wspieramy polecanie produktów, które zostały wcześniej zakupione przez Państwa klientów lub rekomendacje nowych produktów.

- Dane o transakcjach, zakupach oraz ich historii:
    - Identyfikatory transakcji w celu rozróżnienia zakupionych lub transakcji.
    - Identyfikatory klientów do mapowania transakcji na klientów.
    - Daty zdarzeń transakcji określające daty, w których doszło do transakcji.
    - Informacje o identyfikatorze produktu dla transakcji.
    - (Opcjonalnie) Encja danych katalogu produktów w celu użycia filtru produktów.
    - (opcjonalnie) Jeśli transakcja jest zwrotem, czy nie.
    - Schemat danych semantycznych wymaga następujących informacji:
        - **Identyfikator transakcji:** unikatowy identyfikator zakupu lub transakcji.
        - **Data transakcji:** Data zakupu lub transakcji.
        - **Wartość transakcji:** Wartość liczbowa zakupu lub transakcji.
        - **Unikatowy identyfikator produktu:** Identyfikator zakupionego produktu lub usługi, jeśli dane są na poziomie pozycji wiersza.
        - (Opcjonalnie) **Zakup lub zwrot:** pole wartości logicznych, w którym wartość *true* określa, że transakcja była zwrotem. Jeśli dane dotyczące zakupu lub zwrotu nie zostaną podane w modelu, a **Wartość transakcji** jest ujemna, użyjemy tych informacji do założenia, że chodzi o zwrot.
- Sugerowana charakterystyka danych:
    - Wystarczające dane historyczne: co najmniej jeden rok danych transakcji, najlepiej dwa do trzech lat, aby uwzględnić pewną sezonowość.
    - Wiele zakupów na klienta: trzy lub więcej transakcji na identyfikator klienta
    - Liczba klientów: co najmniej 100 klientów, najlepiej więcej niż 10 000 klientów. Model zawiedzie w przypadku mniej niż 100 klientów.

> [!NOTE]
> - Model wymaga historii transakcji klientów. Definicja transakcji jest dosyć elastyczna. Wszystkie dane opisujące interakcję produktu z użytkownikiem mogą działać jako dane wejściowe. Może to być na przykład zakup produktu, udział w szkoleniu lub w wydarzeniu.
> - Obecnie można skonfigurować tylko jedną encję historii transakcji. Jeśli istnieje wiele encji zakupu, zbierz je w Power Query przed pozyskaniem danych.
> - Jeśli zamówienie i szczegóły zamówienia to różne encje, przed użyciem w modelu należy je połączyć. Model nie działa tylko z identyfikatorem zamówienia lub identyfikatorem odbioru w encji.


## <a name="create-a-product-recommendation-prediction"></a>Utwórz prognozę rekomendacji produktu

1. W Customer Insights przejdź do **Analizy** > **Przewidywania**.

1. Wybierz kafelek **Model rekomendacji produktów (wersja zapoznawcza)** i wybierz opcję **Użyj tego modelu**.
   > [!div class="mx-imgBorder"]
   > ![Kafelek modelu rekomendacji produktu z przyciskiem Użyj tego modelu](media/product-recommendation-usethismodel.PNG "Kafelek modelu rekomendacji produktu z przyciskiem Użyj tego modelu")

1. Przejrzyj informacje dotyczące wymagań modelu. Jeśli masz wymagane dane, wybierz opcję **Wprowadzenie**.

### <a name="name-model"></a>Nadaj nazwę modelowi

1. Podaj nazwę modelu odróżniającą go od innych modeli.

1. Wprowadź nazwę jednostki wyjściowej, używając samych liter i cyfr, bez spacji. To jest nazwa, której będzie używać encja modelowa. Następnie wybierz **Dalej**.

### <a name="define-product-recommendation-configuration"></a>Definiowanie konfiguracji rekomendacji produktów

1. Ustaw **Liczba produktów**, które mają być zalecane dla klienta. Ta wartość zależy od tego, jak Twoja metoda dostawy wypełnia dane. Jeśli możesz polecić trzy produkty, ustaw odpowiednio tę wartość.
   
   >[!TIP]
   > W dowolnym momencie możesz wybrać **Zapisz i zamknij**, aby zapisać przewidywanie jako wersję roboczą. Wersja robocza tego przewidywanie się na karcie **Moje prognozy**.

1. Wybierz, jeśli chcesz **Sugerować produkty, które klienci kupili ostatnio**.

1. Jeśli ostatnio *nie* poleca się zakupu produktów, należy ustawić **Okno wglądu w przeszłość**. To ustawienie określa ramy czasowe, które model bierze pod uwagę przed ponownym poleceniem produktu użytkownikowi. Można na przykład wskazać, że klient kupuje komputer przenośny co dwa lata. W tym oknie będzie widoczna historia zakupu za ostatnie dwa lata i po znalezienie pozycji, zostanie ona odfiltrowana z polecanych.

1. Wybierz **Dalej**

### <a name="add-required-data"></a>Dodaj wymagane dane

1. Wybierz opcję **Dodaj dane** do **Historia transakcji klienta** i wybierz encję, która dostarcza informacje historyczne dotyczące transakcji i zakupu, jak to opisano w sekcji [wymagania wstępne](#prerequisites).

1. Zmapuj pola semantyczne na atrybuty w encji historii zakupu i wybierz przycisk **Dalej**. Aby zapoznać się z opisami pól, należy zapoznać się z [wymaganiami wstępnymi](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Definiowanie relacji encji](media/product-recommendation-purchasehistorymapping.PNG "Strona historii zakupów pokazująca atrybuty semantyczne, które są mapowane na pola w wybranej encji historii zakupów")

1. Jeśli pola nie są wypełnione, skonfiguruj relację między jednostką historii zakupów a jednostką *Klient*.
    1. Wybierz **Encja historii zakupów**.
    1. Wybierz **Pole**, które identyfikuje klienta w encji historii zakupu. Musi ono być powiązane z podstawowym identyfikatorem *Klienta* encji Klient.
    1. Wybierz **encję Klient** pasującą do podstawowej encji klienta.
    1. Wprowadź nazwę, która opisuje relację.
       > [!div class="mx-imgBorder"]
       > ![Strona historii zakupów pokazująca tworzenie relacji z klientem](media/model-purchase-join.png "Strona historii zakupów pokazująca tworzenie relacji z klientem")

1. Wybierz pozycję **Zapisz**.

1. Wybierz **Dalej**.

### <a name="configure-product-filters"></a>Konfiguruj filtry produktów

Czasami tylko niektóre produkty są korzystne lub odpowiednie dla tworzonego typu przewidywania. Filtry produktu pozwalają zidentyfikować podzbiór produktów o specyficznej charakterystyce, który jest polecany klientom. Model będzie używać wszystkich dostępnych produktów do poznania wzorców, ale do tworzenia wyniku będzie używać tylko produktów pasujących do filtru produktu.

1. W kroku **Dodaj informacje o produkcie** dodaj katalog produktów z informacjami o każdym produkcie. Zmapuj informacje wymagane w opcji **Dalej**.

3. W kroku **Filtry produktu** wybierz jedną z poniższych opcji.

   * **Brak filtrów**: użyj wszystkich produktów w przewidywaniu polecanych.

   * **Zdefiniuj określone filtry produktu**: użyj określonych produktów w przewidywaniu polecanych.

1. Wybierz **Dalej**.

1. Po wybraniu definiowania filtru produktu należy go teraz zdefiniować. W okienku **Atrybutów katalogu produktów** wybierz atrybuty z *Encji katalogu produktów*, które chcesz uwzględnić w filtrze.

   :::image type="content" source="media/product-filters-sidepane.png" alt-text="Okienko boczne pokazujące trybuty w encji katalogu produktu w celu wybrania filtrów produktów.":::

1. Określ, czy chcesz, by filtr produktów używał łączników **i** lub **lub**, by logicznie łączyć wybór atrybutów z katalogu produktów.
   
   :::image type="content" source="media/product-filters-sample.png" alt-text="Przykładowa konfiguracja filtrów produktu w połączeniu z łącznikami logicznymi AND.":::

1. Wybierz **Dalej**.

### <a name="set-update-schedule-and-review-configuration"></a>Ustaw harmonogram aktualizacji i konfigurację przeglądu

1. Ustaw częstotliwość ponownego uczenia modelu. To ustawienie ma znaczenie dla aktualizowania dokładności przewidywań w czasie importowania nowych danych do Customer Insights. Większość firm może przeprowadzać ponowne szkolenia raz w miesiącu i uzyskać dobrą dokładność przewidywań.

1. Wybierz **Dalej**.

1. Przejrzyj konfigurację. Aby powrócić do dowolnej części konfiguracji przewidywania wybierz **Edytuj** w obszarze ukazanej wartości. Można też wybrać krok konfiguracji ze wskaźnika postępu.

1. Jeśli wszystkie wartości są poprawnie skonfigurowane, wybierz **Zapisz i uruchom**, aby rozpocząć proces przewidywania. Na karcie **Moje przewidywania** można sprawdzić stan przewidywań. Przeprowadzanie procesu może potrwać kilka godzin, w zależności od ilości danych użytych w przewidywaniu.

## <a name="review-a-prediction-status-and-results"></a>Przejrzyj stan przewidywania i wyniki

1. Przejdź do karty **Moje przewidywania** w **Analiza** > **Przewidywania**.
   > [!div class="mx-imgBorder"]
   > ![Wyświetl na stronie Moje przewidywania](media/product-recommendation-mypredictions.PNG "Wyświetl na stronie Moje przewidywania")

1. Wybierz przewidywania do przeglądu.
   - **Nazwa przewidywania:** Nazwa przewidywania podawana podczas jego tworzenia.
   - **Typ przewidywania:** Typ modelu używanego na potrzeby przewidywania
   - **Encja wyjściowa:** Nazwa encji, w której mają być przechowywane wyniki przewidywania. Encję o tej nazwie można znaleźć w **Dane** > **Encje**.    
      *Wynik* w encji wyjściowej jest miarą ilościową rekomendacji. Model poleca produkty z wyższym wynikiem niż produkty z niższym.
   - **Pole z prognozami:** to pole jest wypełniane tylko przez niektóre typy prognoz i nie jest używane w przewidywaniach rekomendacji produktu.
   - **Stan:** Bieżący stan uruchomienia przewidywania.
        - **W kolejce:** Przewidywanie oczekuje obecnie na uruchomienie innych procesów.
        - **Odświeżanie:** Przewidywanie ma obecnie w toku etap "ocena" przetwarzania, aby wyprodukować wyniki, które przepłyną do encji wyjściowej.
        - **Niepowodzenie:** przewidywanie zakończyło się niepowodzeniem. Wybierz **Dzienniki**, aby otrzymać więcej szczegółowych informacji.
        - **Powodzenie:** przewidywanie zakończyło się pomyślnie. Wybierz **Widok** pod pionowymi wielokropkami, aby przejrzeć przewidywanie
   - **Edytowano:** Data konfiguracji dla przewidywania została zmieniona.
   - **Ostatnie odświeżenie:** Data odświeżonych wyników przewidywania w encji wyjściowej.

1. Zaznacz pionowy wielokropek obok przewidywania, dla którego chcesz przejrzeć wyniki, i wybierz **Widok**.
   > [!div class="mx-imgBorder"]
   > ![Widok opcji w menu pionowych wielokropków dla przewidywania, w tym edytowanie, odświeżanie, wyświetlanie, dzienniki i usuwanie](media/product-recommendation-verticalellipses.PNG "Widok opcji w menu pionowych wielokropków dla przewidywania, w tym edytowanie, odświeżanie, wyświetlanie, dzienniki i usuwanie")

1. Na stronie wyników znajduje się pięć podstawowych sekcji danych:
    1. **Wydajność modelu szkoleniowego:** A, B i C są możliwymi wynikami. Ten wynik wskazuje wydajność przewidywania i może pomóc w podjęciu decyzji w zakresie korzystania z wyników przechowywanych w encji wyjściowej.
        - Wyniki są określane na podstawie następujących reguł:
            - **A** Model zostanie uznany za jakość **A**, jeśli wskaźnik „Success @ K” jest co najmniej o 10% wyższy od wartości bazowej. 
            - **B** Model zostanie uznany jako jakości **B**, jeśli wskaźnik metryczny „Success @ K” jest od 0% do 10% wyższy niż wartość bazowa.
            - **C** Model zostanie uznany jako jakości **C**, jeśli wskaźnik metryczny „Success @ K” jest niższy niż wartość bazowa.
               
               > [!div class="mx-imgBorder"]
               > ![Widok wyniku wydajności modelu](media/product-recommendation-modelperformance.PNG "Widok wyniku wydajności modelu")
            - **Model odniesienia**: Model bierze najczęściej polecane produkty według liczby zakupów wśród wszystkich klientów i wykorzystuje wyuczone reguły zidentyfikowane przez model, aby utworzyć zestaw rekomendacji dla klientów. Prognozy są następnie porównywane z najlepszymi produktami, obliczonymi na podstawie liczby klientów, którzy kupili produkt. Jeśli klient ma co najmniej jeden produkt w swoich polecanych produktach, który był również widoczny w najczęściej kupowanych produktach, jest on traktowany jako część linii bazowej. Gdyby było 10 z tych klientów, którzy zakupili zalecany produkt spośród 100 wszystkich klientów, wartość bazowa wyniosłaby 10%.
            - **Powodzenie @ K**: Korzystając z zestawu walidacyjnego okresów transakcji, tworzone są rekomendacje dla wszystkich klientów i porównywane z zestawem walidacyjnym transakcji. Na przykład, w okresie 12 miesięcy, miesiąc 12 może zostać odłożony jako zbiór danych do walidacji. Jeśli model przewiduje przynajmniej jedną rzecz, którą kupisz w 12 miesiącu na podstawie tego, czego nauczył się w ciągu ostatnich 11 miesięcy, klient zwiększy wskaźnik „Success @ K”.
    
    1. **Większość sugerowanych produktów (z zestawieniem):** pięć najlepszych produktów, które zostały przewidziane dla klientów.
       > [!div class="mx-imgBorder"]
       > ![Wykres przedstawiający 5 najbardziej zalecanych produktów](media/product-recommendation-topproducts.PNG "Wykres przedstawiający 5 najbardziej zalecanych produktów")
    
    1. **Kluczowe czynniki rekomendacji:** model korzysta z historii transakcji klientów w celu tworzenia rekomendacji produktów. Zawiera informacje o wzorcach opartych na wcześniejszych zakupach i znajduje podobieństwa między klientami a produktami. Te podobieństwa są następnie wykorzystywane do generowania rekomendacji produktów.
    Poniżej przedstawiono czynniki, które mogą mieć wpływ na rekomendacje produktu generowane przez model. 
        - **Transakcje z przeszłości:** wzorce zakupu w przeszłości zostały użyte przez model do wygenerowania rekomendacji produktów. Na przykład model może polecić _Mysz Surface Arc_, jeśli ktoś w ostatnim czasie kupił _Książka Surface 3_ i _Długopis Surface_. Model nauczył się, że w przeszłości wielu klientów kupiło _Mysz Surface Arc_ po kupieniu _Książki Surface 3_ i _Długopisu Surface_.
        - **Podobieństwo klientów**: zalecany produkt został wcześniej zakupiony przez innych klientów, którzy wykazują podobne wzorce zakupu. Na przykład Janowi polecono _Słuchawki Surface 2_, ponieważ Joanna i Bartosz ostatnio kupili tablet _Słuchawki Surface 2_. Zdaniem modelu Jan jest podobny do Joanny i Bartosza, ponieważ w przeszłości miał podobne wzorce zakupu.
        - **Podobieństwo produktu**: zalecany produkt jest podobny do produktów zakupionych wcześniej przez klienta. Model uznaje dwa produkty za podobne, jeśli były one kupowane łącznie lub przez podobnych klientów. Ktoś na przykład otrzymuje rekomendację dotyczącą _Napędu przenośnego USB_, ponieważ wcześniej zakupił kartę _Adapter USB-C do USB_. Model uzna, że _Napęd przenośny USB_ podobny do modelu _Adaptera USB-C do USB_ w oparciu o historyczne wzorce zakupu.

        Każda rekomendacja produktu jest zależna od jednego lub większej liczby czynników. Wartość procentowa rekomendacji, w której każdy czynnik odegrał rolę, został zobrazowany za pomocą wykresu. W poniższym przykładzie na 100% rekomendacji miały wpływ transakcje z przeszłości, 60% według podobieństwa klienta i 22% według podobieństwa produktu. Przesuń kursor nad słupki na wykresie, aby zobaczyć dokładny procent wpływu czynników.

        > [!div class="mx-imgBorder"]
        > ![Kluczowe czynniki wpływające na rekomendacje](media/product-recommendation-keyrecommendationfactors.png "Kluczowe czynniki rekomendacji, których nauczyć się model do wygenerowania rekomendacji produktów")
       
     
   1. **Dane statystyczne**: umożliwia przegląd liczby transakcji, klientów i produktów, które model wziął pod uwagę. Jest to oparte na danych wejściowych używanych do nauczenia się wzorców i generowania rekomendacji produktów.

      > [!div class="mx-imgBorder"]
      > ![Statystyki danych](media/product-recommendation-datastatistics.png "Dane statystyczne dotyczące wprowadzonych danych używanych przez model w celu uczenia się wzorców")

      Ta sekcja przedstawia statystyki dotyczące punktów danych używanych przez model w celu nauczenia się wzorców i wygenerowania rekomendacji produktów. Filtrowanie, skonfigurowane w konfiguracji modelu, ma zastosowanie do danych wyjściowych wygenerowanych przez model. Jednak model wykorzystuje wszystkie dostępne dane do uczenia się wzorców. Dlatego jeśli w konfiguracji modelu używane jest filtrowanie produktu, ta sekcja pokaże łączną liczbę produktów przeanalizowanych w modelu w celu nauczenia się wzorców, która może się różnić od liczby produktów, które spełniają zdefiniowane kryteria filtrowania.

   1. **Pewne rekomendacje dotyczące produktów**: Próbka zaleceń przekazanych klientom, które według modelu mogą zostać zakupione przez klienta.    
      Po dodaniu katalogu produktów identyfikatory produktów są zastępowane nazwami produktów. Nazwy produktów zawierają bardziej intuicyjne i praktyczne informacje o przewidywaniu.
       > [!div class="mx-imgBorder"]
       > ![Lista przedstawiająca sugestie o wysokim poziomie zaufania dla wybranej grupy klientów indywidualnych](media/product-recommendation-highconfidence.PNG "Lista przedstawiająca sugestie o wysokim poziomie zaufania dla wybranej grupy klientów indywidualnych")

## <a name="fix-a-failed-prediction"></a>Poprawianie nieudanego przewidywania

1. Przejdź do karty **Moje przewidywania** w **Analiza** > **Przewidywania**.

1. Wybierz przewidywanie, dla którego chcesz wyświetlić dzienniki błędów i wybierz **Dzienniki**.

1. Przejrzyj wszystkie błędy. Istnieje kilka typów błędów, które mogą wystąpić, i opisują one jaki warunek spowodował błąd. Na przykład komunikat o błędzie, informujący o niedostatecznej liczbie danych potrzebnych do dokładnego przewidywania jest zazwyczaj rozwiązany dzięki załadowaniu większej ilości danych do programu Customer Insights.

## <a name="refresh-a-prediction"></a>Odświeżanie przewidywania

Prognozy są automatycznie odświeżane według [harmonogramu odświeżania danych](system.md#schedule-tab) zgodnie z stawieniami skonfigurowanymi w ustawieniach.

1. Przejdź do karty **Moje przewidywania** w **Analiza** > **Przewidywania**.

1. Wybierz pionowy wielokropek obok przewidywania, które chcesz odświeżyć.

1. Wybierz **Odśwież**.

## <a name="delete-a-prediction"></a>Usuń przewidywanie

Usunięcie prognozy spowoduje również usunięcie jej jednostki wyjściowej.

1. Przejdź do karty **Moje przewidywania** w **Analiza** > **Przewidywania**.

1. Wybierz pionowy wielokropek obok przewidywania, które chcesz usunąć.

1. Wybierz **Usuń**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
