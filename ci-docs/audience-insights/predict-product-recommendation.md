---
title: Przewidywanie rekomendacji produktów
description: Przewiduj produkty, które klient prawdopodobnie kupi lub z którymi będzie miał do czynienia.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 5ae78b6bbc51fd8a25bc408050a23479698a1414
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598076"
---
# <a name="product-recommendation-prediction-preview"></a>Przewidywanie rekomendacji produktów (wersja zapoznawcza)

Model rekomendacji produktowych tworzy zestawy predykcyjnych rekomendacji produktowych. Rekomendacje opierają się na wcześniejszych zachowaniach zakupowych i klientach o podobnych wzorcach zakupowych. Możesz tworzyć nowe prognozy rekomendacji produktów na stronie **Analizy** > **Przewidywania**. Wybierz **Moje przewidywania**, aby wyświetlić inne utworzone przewidywania.

Zalecenia dotyczące produktów mogą podlegać lokalnym prawom i regulacjom, a także oczekiwaniom klientów, których model nie jest specjalnie uwzględniany.  Jako użytkownik tej funkcji predykcyjnej **musisz zapoznać się z zaleceniami przed dostarczeniem ich klientom**, aby upewnić się, że przestrzegasz wszelkich obowiązujących przepisów i regulacji, a także oczekiwań klientów dotyczących tego, co możesz zalecić. 

Ponadto dane wyjściowe tego modelu przedstawi zalecenia na podstawie identyfikatora produktu. Twój mechanizm dostarczania będzie musiał uwzględniać przewidywane identyfikatory produktów i mapować je na odpowiednie treści, aby klienci mogli uwzględnić lokalizację, zawartość obrazu i inne specyficzne dla firmy treści lub zachowania.

## <a name="sample-guide"></a>Przykładowy przewodnik

Jeśli chcesz spróbować tej funkcji, ale nie masz danych, które spełniają poniższe wymagania, możesz [utworzyć przykładową implementację](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Wymagania wstępne

- Co najmniej [Uprawnienia współautora](permissions.md) w Customer Insights.
- Wiedza biznesowa pozwalająca zrozumieć różne rodzaje produktów dla Twojej firmy i sposób interakcji z nimi klientów. Wspieramy polecanie produktów, które zostały wcześniej zakupione przez Państwa klientów lub rekomendacje nowych produktów.
- Dane o transakcjach, zakupach oraz ich historii:
    - Identyfikatory transakcji w celu rozróżnienia zakupionych lub transakcji.
    - Identyfikatory klientów do mapowania transakcji na klientów.
    - Daty zdarzeń transakcji określające daty, w których doszło do transakcji.
    - (Opcjonalnie) Informacje o identyfikatorze produktu dla transakcji.
    - (opcjonalnie) Jeśli transakcja jest zwrotem, czy nie.
    - Schemat danych semantycznych wymaga następujących informacji:
        - **Identyfikator transakcji:** unikatowy identyfikator zakupu lub transakcji.
        - **Data transakcji:** Data zakupu lub transakcji.
        - **Wartość transakcji:** Wartość liczbowa zakupu lub transakcji.
        - **Unikatowy identyfikator produktu:** Identyfikator zakupionego produktu lub usługi, jeśli dane są na poziomie pozycji wiersza.
        - (Opcjonalnie) **Zakup czy zwrot:** pole typu prawda/fałsz, które określa, czy transakcja była zwrotna, czy nie. Jeśli **Wartość transakcji** jest ujemna, Microsoft będzie również używać tych informacji do wywnioskowania, że nastąpił zwrot.


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

1. Jeśli ostatnio *nie* poleca się zakupu produktów, należy ustawić **Okno wglądu w przeszłość**. To ustawienie określa ramy czasowe, które model bierze pod uwagę przed ponownym poleceniem produktu użytkownikowi. Na przykład wskaż, że klient kupuje laptopa co 2 lata. To okno przejrzy historię zakupów z ostatnich 2 lat, a jeśli znajdą przedmiot, zostanie on odfiltrowany z rekomendacji.

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

### <a name="set-schedule-and-review-configuration"></a>Konfigurowanie harmonogramu i przeglądu konfiguracji

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
   - **Przewidywane pole:** To pole jest wypełniane tylko w przypadku niektórych typów przewidywań i nie jest używane w przewidywaniu rezygnacji.
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

1. Na stronie wyników wyszukiwania znajdują się trzy podstawowe sekcje danych:
    1. **Wydajność modelu szkoleniowego:** A, B i C są możliwymi wynikami. Ten wynik wskazuje wydajność przewidywania i może pomóc w podjęciu decyzji w zakresie korzystania z wyników przechowywanych w encji wyjściowej.
        - Wyniki są określane na podstawie następujących reguł:
            - **A** Model zostanie uznany za jakość **A**, jeśli wskaźnik „Success @ K” jest co najmniej o 10% wyższy od wartości bazowej. 
            - **B** Model zostanie uznany za jakość **B**, jakość, jeśli wskaźnik „Success @ K” jest od 0 do 10% wyższy niż wartość bazowa.
            - **C** Model zostanie uznany za jakość **C**, jakość, jeśli metryka „Success @ K” jest mniejsza niż wartość bazowa.
               
               > [!div class="mx-imgBorder"]
               > ![Widok wyniku wydajności modelu](media/product-recommendation-modelperformance.PNG "Widok wyniku wydajności modelu")
            - **Model odniesienia**: Model bierze najczęściej polecane produkty według liczby zakupów wśród wszystkich klientów i wykorzystuje wyuczone reguły zidentyfikowane przez model, aby utworzyć zestaw rekomendacji dla klientów. Prognozy są następnie porównywane z najlepszymi produktami, obliczonymi na podstawie liczby klientów, którzy kupili produkt. Jeśli klient ma co najmniej jeden produkt w swoich polecanych produktach, który był również widoczny w najczęściej kupowanych produktach, jest on traktowany jako część linii bazowej. Gdyby było 10 z tych klientów, którzy zakupili zalecany produkt spośród 100 wszystkich klientów, wartość bazowa wyniosłaby 10%.
            - **Powodzenie @ K**: Korzystając z zestawu walidacyjnego okresów transakcji, tworzone są rekomendacje dla wszystkich klientów i porównywane z zestawem walidacyjnym transakcji. Na przykład, w okresie 12 miesięcy, miesiąc 12 może zostać odłożony jako zbiór danych do walidacji. Jeśli model przewiduje przynajmniej jedną rzecz, którą kupisz w 12 miesiącu na podstawie tego, czego nauczył się w ciągu ostatnich 11 miesięcy, klient zwiększy wskaźnik „Success @ K”.
    
    1. **Najczęściej sugerowane produkty (z zestawieniem):** 5 najlepszych produktów przewidzianych dla Twoich klientów.
       > [!div class="mx-imgBorder"]
       > ![Wykres przedstawiający 5 najbardziej zalecanych produktów](media/product-recommendation-topproducts.PNG "Wykres przedstawiający 5 najbardziej zalecanych produktów")
    
    1. **Pewne rekomendacje dotyczące produktów**: Próbka zaleceń przekazanych klientom, które według modelu mogą zostać zakupione przez klienta.
       > [!div class="mx-imgBorder"]
       > ![Lista przedstawiająca sugestie o wysokim poziomie zaufania dla wybranej grupy klientów indywidualnych](media/product-recommendation-highconfidence.PNG "Lista przedstawiająca sugestie o wysokim poziomie zaufania dla wybranej grupy klientów indywidualnych")

## <a name="fix-a-failed-prediction"></a>Poprawianie nieudanego przewidywania

1. Przejdź do karty **Moje przewidywania** w **Analiza** > **Przewidywania**.

1. Wybierz przewidywanie, dla którego chcesz wyświetlić dzienniki błędów i wybierz **Dzienniki**.

1. Przejrzyj wszystkie błędy. Istnieje kilka typów błędów, które mogą wystąpić, i opisują one jaki warunek spowodował błąd. Na przykład błąd polegający na tym, że jest zbyt mało danych, aby dokładnie przeprowadzić przewidywanie, jest zwykle rozwiązywany dzięki załadowaniu dodatkowych danych do Customer Insights.

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