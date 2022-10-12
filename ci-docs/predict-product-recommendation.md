---
title: Przewiduj rekomendacje produktów
description: Przewiduj produkty, które klient prawdopodobnie kupi lub z którymi będzie miał do czynienia.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 0057d6796bb60db44d08b58d9e0daaf6e7c90fde
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610295"
---
# <a name="predict-product-recommendations"></a>Przewiduj rekomendacje produktów

Model rekomendacji produktowych tworzy zestawy predykcyjnych rekomendacji produktowych. Rekomendacje opierają się na wcześniejszych zachowaniach zakupowych i klientach o podobnych wzorcach zakupowych. Ten model jest modelem dla poszczególnych osób (B2C).

Należy posiadać wiedzę biznesową pozwalającą zrozumieć różne rodzaje produktów dla firmy i sposób interakcji z nimi klientów. Wspieramy polecanie produktów, które zostały wcześniej zakupione przez Państwa klientów lub rekomendacje nowych produktów.

Polecane produkty mogą podlegać lokalnym przepisom i ustawom oraz oczekiwaniom klientów, których model nie bierze pod uwagę, gdyż nie jest do tego przeznaczony. Zatem użytkownik **musi przejrzeć rekomendacje przed dostarczenia ich klientom**, aby upewnić się, że są zgodne z obowiązującymi przepisami i rozporządzeniami oraz oczekiwaniami klientów dotyczącymi produktów, które mogą być polecane.

Ponadto dane wyjściowe tego modelu przedstawiają zalecenia na podstawie identyfikatora produktu. Mechanizm dostawy musi zamapować przewidziane identyfikatory produktów na odpowiednią zawartość dla klientów, biorąc pod uwagę lokalizację, zawartość obrazów i inne specyficzne dla biznesu zawartości lub zachowanie.

> [!TIP]
> Sprawdź zalecenia dotyczące produktu przewidywanie przykładowych danych: [Przewodnik po przykładach prognozowania rekomendacji produktów](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Wymagania wstępne

- Co najmniej [uprawnienia współautora](permissions.md)
- Co najmniej 100 klientów, najlepiej więcej niż 10 000 klientów.
- Identyfikator klienta, unikalny identyfikator umożliwiający dopasowanie transakcji do indywidualnego klienta
- Co najmniej jeden rok danych transakcji, najlepiej dwa do trzech lat, aby uwzględnić pewną sezonowość. Najlepiej jest, aby dla każdego identyfikatora klienta było to co najmniej trzy transakcje. Historia transakcji musi zawierać:
  - **Identyfikator transakcji**: unikatowy identyfikator zakupu lub transakcji.
  - **Data transakcji**: data zakupu lub transakcji.
  - **Wartość transakcji:** wartość liczbowa zakupu lub transakcji.
  - **Unikatowy identyfikator produktu:** identyfikator zakupionego produktu lub usługi, jeśli dane są na poziomie pozycji wiersza.
  - **Zakup lub zwrot:** wartość logiczna prawda/fałsz, gdzie wartość *true* określa, że transakcja była zwrotem. Jeśli dane dotyczące zakupu lub zwrotu nie zostaną podane w modelu, a **Wartość transakcji** jest ujemna, założymy, że chodzi o zwrot.
- Encja danych katalogu produktów w celu użycia jako filtru produktów.

> [!NOTE]
> - Model wymaga historii transakcji klientów, w której transakcje to dane opisujące interakcję z produktem użytkownika. Może to być na przykład zakup produktu, udział w szkoleniu lub w wydarzeniu.
> - Można skonfigurować tylko jedną encję historii transakcji. Jeśli istnieje wiele encji zakupu, połącz je w usłudze Power Query przed pozyskaniem danych.
> - Jeśli zamówienie i szczegóły zamówienia to różne encje, przed użyciem w modelu należy je połączyć. Model nie działa tylko z identyfikatorem zamówienia lub identyfikatorem odbioru w encji.

## <a name="create-a-product-recommendation-prediction"></a>Utwórz prognozę rekomendacji produktu

W dowolnym momencie wybierz opcję **Zapisz roboczą**, aby zapisać przewidywanie jako roboczą. Wersja robocza wyświetla się na karcie **Moje prognozy**.

1. Przejdź do opcji **Analizy** > **Przewidywania**.

1. Na karcie **Utwórz** wybierz **Model użycia** na kafelku **Rekomendacje produktów (wersja zapoznawcza)**.

1. Wybierz **Rozpocznij**.

1. **Nazwij ten model** i **Nazwa encji wyjściowej**, aby odróżnić je od innych modeli lub encji.

1. Wybierz **Dalej**.

### <a name="define-product-recommendation-preferences"></a>Definiowanie preferencji rekomendacji produktów

1. Ustaw **Liczba produktów**, które mają być zalecane klientowi. Ta wartość zależy od tego, jak Twoja metoda dostawy wypełnia dane.

1. Wybierz, czy chcesz uwzględnić produkty, które poprzednio kupili klienci, w polu **Oczekiwane powtórzenie zakupów**.

1. Ustawienie **Okno wglądu w przeszłość** z ramami czasowymi, które model bierze pod uwagę przed ponownym poleceniem produktu użytkownikowi. Można na przykład wskazać, że klient kupuje komputer przenośny co dwa lata. Model patrzy na historię zakupu przez ostatnie dwa lata i po znalezieniu pozycji, zostanie ona odfiltrowana z polecanych.

1. Wybierz **Dalej**

### <a name="add-purchase-history"></a>Dodaj historię zakupów

1. Wybierz **Dodaj dane** dla **Historii transakcji klienta**.

1. Wybierz semantyczny typ działania **SalesOrderLine** i wybierz typ działania w okienku bocznym zawierającym wymagane informacje o historii transakcji lub zakupów. Jeśli działanie nie zostało ustawione, zaznacz **tutaj** i utwórz działanie.

1. W obszarze **Działania**, jeśli atrybuty działania zostały semantycznie zamapowane podczas tworzenia działania, wybierz określone atrybuty lub encję, na których chcesz skupić obliczenia. Jeśli semantyczne mapowanie nie wystąpiło, wybierz opcję **Edytuj** i zamapuj dane.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Okienko boczne po stronie przedstawiające wybranie określone działania w ramach typu semantycznego.":::

1. Wybierz opcję **Dalej** i przejrzyj atrybuty wymagane dla tego modelu.

1. Wybierz pozycję **Zapisz**.

1. Wybierz **Dalej**.

### <a name="add-product-information-and-filters"></a>Dodaj informacje o produkcie i filtry

Czasami tylko niektóre produkty są korzystne lub odpowiednie dla tworzonego typu przewidywania. Użyj filtrów produktu, które pozwalają zidentyfikować podzbiór produktów o specyficznej charakterystyce, który jest polecany klientom. Model będzie używać wszystkich dostępnych produktów do poznania wzorców, ale do tworzenia wyniku będzie używać tylko produktów pasujących do filtru produktu.

1. Dodaj encję katalogu produktów zawierającą informacje o każdym produkcie. Zmapuj wymagane informacje i wybierz **Zapisz**.

1. Wybierz **Dalej**.

1. Wybierz **Filtry produktu**:

   - **Brak filtrów**: użyj wszystkich produktów w przewidywaniu polecanych.

   - **Zdefiniuj określone filtry produktu**: użyj określonych produktów w przewidywaniu polecanych. W okienku **Atrybutów katalogu produktów** wybierz atrybuty z Encji katalogu produktów, które chcesz uwzględnić w filtrze.

     :::image type="content" source="media/product-filters-sidepane.png" alt-text="Okienko boczne pokazujące trybuty w encji katalogu produktu w celu wybrania filtrów produktów.":::

1. Określ, czy chcesz, by filtr produktów używał **i** lub **lub**, by logicznie łączyć wybór atrybutów z katalogu produktów.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Przykładowa konfiguracja filtrów produktu w połączeniu z łącznikami logicznymi AND.":::

1. Wybierz **Dalej**.

### <a name="set-update-schedule"></a>Ustaw harmonogram aktualizacji

1. Wybierz częstotliwość ponownego uczenia modelu. To ustawienie ma znaczenie dla aktualizowania dokładności przewidywań w czasie pozyskiwania nowych danych do Customer Insights. Większość firm może przeprowadzać ponowne szkolenia raz w miesiącu i uzyskać dobrą dokładność przewidywań.

1. Wybierz **Dalej**.

### <a name="review-and-run-the-model-configuration"></a>Przegląd i uruchamianie konfiguracji modelu

W kroku **Przejrzyj i uruchom** przedstawiono podsumowanie konfiguracji i użytkownik może wprowadzić zmiany przed utworzeniem przewidywania.

1. Wybierz **Edytuj** na każdym z etapów, aby przejrzeć i wprowadzić ewentualne zmiany.

1. Jeśli użytkownik jest zadowolony z wprowadzonych opcji, wybiera opcję **Zapisz i uruchom**, aby rozpocząć uruchamianie modelu. Wybierz pozycję **Gotowe**. Podczas tworzenia przewidywanie jest wyświetlana karta **Moje prognozy**. Przeprowadzanie procesu może potrwać kilka godzin, w zależności od ilości danych użytych w przewidywaniu.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Wyświetl wyniki przewidywania

1. Przejdź do opcji **Analizy** > **Przewidywania**.

1. Na karcie **Moje przewidywania** wybierz przewidywanie, które chcesz wyświetlić.

Na stronie wyników znajduje się pięć podstawowych sekcji danych.

- **Wydajność modelu:** Oceny A, B lub C wskazują wydajność prognozy i może pomóc w podjęciu decyzji o użyciu wyników przechowywanych w encji wyjściowej.
  
  :::image type="content" source="media/product-recommendation-modelperformance.PNG" alt-text="Obraz wyniku wydajności modelu wraz z oceną A.":::

  Oceny są określane na podstawie następujących reguł:
  - **A**, gdy metryka „Powodzenie @ K” jest o co najmniej 10% większa niż plan bazowy.
  - **B**, gdy metryka „Powodzenie @ K” jest 0% do 10% większa niż plan bazowy.
  - **C**, gdy metryka „Powodzenie @ K” jest mniejsza niż plan bazowy.
  - **Plan bazowy**: model bierze najczęściej polecane produkty według liczby zakupów wśród wszystkich klientów + wykorzystuje wyuczone reguły zidentyfikowane przez model = zestaw rekomendacji dla klientów. Prognozy są następnie porównywane z najlepszymi produktami, obliczonymi na podstawie liczby klientów, którzy kupili produkt. Jeśli klient ma co najmniej jeden produkt w swoich polecanych produktach, który był również widoczny w najczęściej kupowanych produktach, jest on traktowany jako część linii bazowej. Na przykład gdyby było 10 z tych klientów, którzy zakupili zalecany produkt spośród 100 wszystkich klientów, wartość bazowa wyniosłaby 10%.
  - **Powodzenie @ K**: tworzone są rekomendacje dla wszystkich klientów i porównywane z zestawem sprawdzania ważności za okres transakcji. Na przykład, w okresie 12 miesięcy, miesiąc 12 jest odłożony jako zbiór danych do walidacji. Jeśli model przewiduje przynajmniej jedną rzecz, którą kupisz w 12 miesiącu na podstawie tego, czego nauczył się w ciągu ostatnich 11 miesięcy, klient zwiększy wskaźnik „Success @ K”.

- **Większość sugerowanych produktów (z zestawieniem):** pięć najlepszych produktów, które zostały przewidziane dla klientów.
  
  :::image type="content" source="media/product-recommendation-topproducts.PNG" alt-text="Wykres przedstawiający 5 najbardziej zalecanych produktów.":::

- **Kluczowe czynniki rekomendacji:** model korzysta z historii transakcji klientów w celu tworzenia rekomendacji produktów. Zawiera informacje o wzorcach opartych na wcześniejszych zakupach i znajduje podobieństwa między klientami a produktami. Te podobieństwa są następnie wykorzystywane do generowania rekomendacji produktów.
  Poniższe czynniki mogą mieć wpływ na rekomendacje produktu generowane przez model.
  - **Transakcje z przeszłości**: zalecany produkt został oparty na wzorcach zakupu z przeszłości. Na przykład model może polecić *Mysz Surface Arc*, jeśli ktoś w ostatnim czasie kupił *Książka Surface 3* i *Długopis Surface*. Model nauczył się, że w przeszłości wielu klientów kupiło *Mysz Surface Arc* po kupieniu *Książki Surface 3* i *Długopisu Surface*.
  - **Podobieństwo klientów**: zalecany produkt został wcześniej zakupiony przez innych klientów, którzy wykazują podobne wzorce zakupu. Na przykład Janowi polecono *Słuchawki Surface 2*, ponieważ Joanna i Bartosz ostatnio kupili tablet *Słuchawki Surface 2*. Zdaniem modelu Jan jest podobny do Joanny i Bartosza, ponieważ w przeszłości miał podobne wzorce zakupu.
  - **Podobieństwo produktu**: zalecany produkt jest podobny do produktów zakupionych wcześniej przez klienta. Model uznaje dwa produkty za podobne, jeśli były one kupowane łącznie lub przez podobnych klientów. Ktoś na przykład otrzymuje rekomendację dotyczącą *Napędu przenośnego USB*, ponieważ wcześniej zakupił kartę *Adapter USB-C do USB*. Model uzna, że *Napęd przenośny USB* podobny do modelu *Adaptera USB-C do USB* w oparciu o historyczne wzorce zakupu.

  Każda rekomendacja produktu jest zależna od jednego lub większej liczby czynników. Wartość procentowa rekomendacji, w której każdy czynnik odegrał rolę, został zobrazowany za pomocą wykresu. W poniższym przykładzie na 100% rekomendacji miały wpływ transakcje z przeszłości, 60% według podobieństwa klienta i 22% według podobieństwa produktu. Przesuń kursor nad słupki na wykresie, aby zobaczyć dokładny procent wpływu czynników.
  
  :::image type="content" source="media/product-recommendation-keyrecommendationfactors.png" alt-text="Kluczowe czynniki rekomendacji, których nauczyć się model do wygenerowania rekomendacji produktów.":::

- **Dane statystyczne**: przegląd liczby transakcji, klientów i produktów, które model wziął pod uwagę. Jest to oparte na danych wejściowych używanych do nauczenia się wzorców i generowania rekomendacji produktów.

  :::image type="content" source="media/product-recommendation-datastatistics.png" alt-text="Dane statystyczne dotyczące wprowadzonych danych używanych przez model w celu uczenia się wzorców.":::
  
  Model wykorzystuje wszystkie dostępne dane do uczenia się wzorców. Dlatego jeśli w konfiguracji modelu używane jest filtrowanie produktu, ta sekcja pokazuje łączną liczbę produktów przeanalizowanych w modelu w celu nauczenia się wzorców, która może się różnić od liczby produktów, które spełniają zdefiniowane kryteria filtrowania. Filtrowanie dotyczy danych wyjściowych wygenerowanych przez model.

- **Przykładowe rekomendacje dotyczące produktów**: próbka zaleceń, które według modelu mogą zostać zakupione przez klienta. Po dodaniu katalogu produktów identyfikatory produktów są zastępowane nazwami produktów.

  :::image type="content" source="media/product-recommendation-highconfidence.PNG" alt-text="Lista przedstawiająca sugestie o wysokim poziomie zaufania dla wybranej grupy klientów indywidualnych.":::

> [!NOTE]
> In encji wyjściowej dla tego modelu *Wynik* jest miarą ilościową rekomendacji. Model poleca produkty z wyższym wynikiem niż produkty z niższym. Aby wyświetlić wynik, przejdź do **Dane** > **Encje** i wyświetl kartę danych dla encji wyjściowej zdefiniowanej dla tego modelu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
