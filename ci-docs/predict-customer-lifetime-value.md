---
title: Przewidywanie wartości okresu istnienia klienta (CLV)
description: Potencjalne przychody aktywnych klientów w przyszłości.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- ci-custom-models
- customerInsights
ms.openlocfilehash: f27462ac327027e50e23387ac9f75a671db9a86d
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610387"
---
# <a name="predict-customer-lifetime-value-clv"></a>Przewidywanie wartości okresu istnienia klienta (CLV)

Przewiduj potencjalną wartość (przychód), jaką indywidualni aktywni klienci przyniosą Twojej firmie w określonym okresie w przyszłości. To przewidywanie umożliwia:

- Identyfikowanie klientów o wysokiej wartości i przetwarzanie tych informacji.
- Twórz strategiczne segmenty klientów w oparciu o ich potencjalną wartość, aby prowadzić spersonalizowane kampanie z ukierunkowaną sprzedażą, marketingiem i działaniami wsparcia.
- Kieruj rozwojem produktu, koncentrując się na funkcjach zwiększających wartość tego klienta.
- Zoptymalizuj strategię sprzedaży lub marketingu i dokładniej przydziel budżet na potrzeby dotarcia do klientów.
- Rozpoznawaj i nagradzaj wartościowych klientów za pomocą programów lojalnościowych lub programów nagród.

Określ, co CLV oznacza dla działalności firmy. Obsługujemy prognozowanie CLV oparte na transakcjach. Przewidywana wartość klienta jest oparta na historii transakcji biznesowych. Rozważ utworzenie kilku modeli z różnymi preferencjami wejściowymi i porównaj wyniki modeli, aby zobaczyć, który scenariusz modelu najlepiej odpowiada potrzebom biznesowym.

> [!TIP]
> Spróbuj użyć narzędzia przewidywania CLV za pomocą przykładowych danych: [Przykładowy przewodnik po prognozowaniu wartości całego cyklu życia klienta (CLV)](sample-guide-predict-clv.md).

## <a name="prerequisites"></a>Wymagania wstępne

- Co najmniej uprawnienia [współautora](permissions.md)
- Co najmniej 100 unikatowych klientów, najlepiej więcej niż 10 000 klientów
- Identyfikator klienta, unikalny identyfikator umożliwiający dopasowanie transakcji do indywidualnego klienta
- Przynajmniej rok historii transakcji, najlepiej dwa do trzech lat. Idealnie, co najmniej dwie do trzech transakcji na identyfikator klienta, najlepiej w wielu datach. Historia transakcji musi zawierać:
  - **Identyfikator transakcji**: niepowtarzalny identyfikator każdej transakcji
  - **Data transakcji**: data lub sygnatura czasowa każdej transakcji
  - **Kwota transakcji**: wartość pieniężna (na przykład przychód lub marża zysku) każdej transakcji
  - **Etykieta przypisana do zwrotów**: wartość logiczna wskazująca prawda/fałsz, czy transakcja jest zwrotem
  - **Identyfikator produktu**: Identyfikator produktu, którego dotyczy transakcja
- Dane dotyczące działań klienta:
  - **Klucz podstawowy**: unikatowy identyfikator działania
  - **Sygnatura czasowa**: data i godzina zdarzenia identyfikowanego przez klucz podstawowy
  - **Zdarzenie (nazwa działania)**: nazwa zdarzenia, którego chcesz użyć
  - **Szczegóły (kwota lub wartość)**: Szczegółowe informacje dotyczące działania klienta
- Dodatkowe dane, takie jak:
  - Działania w sieci: historia odwiedzin witryny lub historia wiadomości e-mail
  - Działania lojalnościowe: historia gromadzenia i wykorzystania punktów lojalnościowych
  - Obsługa klienta dziennika: zgłoszenia, skargi lub historii zwrotów
  - Informacje o profilu klienta
- Mniej niż 20% brakujących wartości w wymaganych polach

> [!NOTE]
> Można skonfigurować tylko jedną encję historii transakcji. Jeśli istnieje wiele encji zakupu lub transakcji, możesz połączyć je w usłudze Power Query przed pozyskaniem danych.

## <a name="create-a-customer-lifetime-value-prediction"></a>Utwórz prognozę wartości okresu istnienia klienta

W dowolnym momencie wybierz opcję **Zapisz roboczą**, aby zapisać przewidywanie jako roboczą. Wersja robocza wyświetla się na karcie **Moje prognozy**.

1. Przejdź do opcji **Analizy** > **Przewidywania**.

1. Na karcie **Utwórz** wybierz **Model użycia** na kafelku **Wartość istnienia klienta**.

1. Wybierz **Rozpocznij**.

1. **Nazwij ten model** i **Nazwa encji wyjściowej**, aby odróżnić je od innych modeli lub encji.

1. Wybierz **Dalej**.

### <a name="define-model-preferences"></a>Zdefiniuj preferencje modelu

1. Ustaw **Okres przewidywania**, aby określić, jak daleko w przyszłości chcesz przewidzieć CLV. Domyślnie jednostka jest ustawiona na miesiące.

   > [!TIP]
   > Aby dokładnie przewidzieć CLV dla ustawionego okresu, wymagany jest porównywalny okres danych historycznych. Na przykład, jeśli chcesz prognozować CLV na następne 12 miesięcy, musisz mieć co najmniej 18–24 miesiące danych historycznych.

1. Ustaw przedział czasu, w którym klient musiał mieć co najmniej jedną transakcję, aby zostać uznanym za aktywną. Model będzie przewidywać CLV tylko dla **aktywnych klientów**.
   - **Zezwól modelowi na obliczenie interwału zakupów (zalecane)**: model analizuje dane i określa okres na podstawie historycznych zakupów.
   - **Ręczne ustawianie interwału**: okres dla definicji aktywnego klienta.

1. Zdefiniuj wartość procentową **klienta o wysokiej wartości**.
    - **Model obliczania (zalecane)**: w modelu jest używana reguła 80/20. Odsetek klientów, którzy przyczynili się do 80% skumulowanych przychodów Twojej firmy w okresie historycznym, to klienci o dużej wartości. Zwykle mniej niż 30-40% klientów przyczynia się do 80% skumulowanych przychodów. Jednak liczba ta może się różnić w zależności od Twojej firmy i branży.
    - **Procent aktywnych klientów o najwyższej wartości**: konkretne procenty dla klienta o wysokiej wartości. Na przykład wprowadź **25**, aby zdefiniować klientów o wysokiej wartości jako najwyższe 25% przyszłych płacących klientów.

    Jeśli Twoja firma definiuje klientów o dużej wartości w inny sposób, [daj nam znać, z przyjemnością dowiemy się więcej](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Wybierz **Dalej**.

### <a name="add-required-data"></a>Dodaj wymagane dane

1. Wybierz **Dodaj dane** dla **Historii transakcji klienta**.

1. Wybierz semantyczny typ działania **SalesOrder** lub **SalesOrderLine** zawierającym informacje o historii transakcji. Jeśli działanie nie zostało ustawione, zaznacz **tutaj** i utwórz działanie.

1. W obszarze **Działania**, jeśli atrybuty działania zostały semantycznie zamapowane podczas tworzenia działania, wybierz określone atrybuty lub encję, na których chcesz skupić obliczenia. Jeśli semantyczne mapowanie nie wystąpiło, wybierz opcję **Edytuj** i zamapuj dane.
  
   :::image type="content" source="media/CLV-add-required.PNG" alt-text="Dodawanie wymaganych danych dla modelu CLV":::

1. Wybierz opcję **Dalej** i przejrzyj atrybuty wymagane dla tego modelu.

1. Wybierz pozycję **Zapisz**.

1. Dodaj więcej działań lub wybierz **Dalej**.

### <a name="add-optional-activity-data"></a>Dodaj opcjonalne dane dotyczące działań

Dane odzwierciedlające kluczowe interakcje z klientami (takie jak internet, obsługa klienta i dzienniki zdarzeń) dodają kontekst do rekordów transakcji. Więcej wzorców znalezionych w danych o aktywności klientów może poprawić dokładność prognoz.

1. Wybierz **Dodaj dane** w opcji **Popraw jakość wyników analiz modelu dzięki dodatkowym danym dotyczącym działań**.

1. Wybierz typ działania dopasowania do typu działania klienta, które jest dodawane. Jeśli działanie nie zostało ustawione, zaznacz **tutaj** i utwórz działanie.

1. W obszarze **Działania**, jeśli atrybuty działania zostały zamapowane podczas tworzenia działania, wybierz określone atrybuty lub encję, na których chcesz skupić obliczenia. Jeśli mapowanie nie wystąpiło, wybierz opcję **Edytuj** i zamapuj dane.

1. Wybierz opcję **Dalej** i przejrzyj atrybuty wymagane dla tego modelu.

1. Wybierz pozycję **Zapisz**.

1. Wybierz **Dalej**.

1. [Dodaj opcjonalne dane klienta](#add-optional-customer-data) lub wybierz opcję **Dalej** i przejdź do [ustawiania harmonogramu aktualizacji](#set-update-schedule).

### <a name="add-optional-customer-data"></a>Dodaj opcjonalne dane klienta

Wybierz jeden z 18 najczęściej używanych atrybutów profilu klienta, które mają być używane jako wprowadzenie do modelu. Te atrybuty mogą prowadzić do bardziej spersonalizowanych, trafnych i praktycznych wyników modelu w przypadku zastosowań biznesowych.

Na przykład: firma Contoso Coffee chce przewidzieć wartość życiową klienta, aby dotrzeć do klientów o wysokiej wartości ze spersonalizowaną ofertą związaną z wprowadzeniem na rynek ich nowego ekspresu do kawy. Firma Contoso używa modelu CLV i dodaje wszystkie 18 atrybutów profilu klienta, aby zobaczyć, które czynniki wpływają na klientów o najwyższej wartości. Uważają, że lokalizacja klienta jest dla nich najważniejszym czynnikiem.
Dzięki tym informacjom organizują lokalne wydarzenie z okazji uruchomienia ekspresu do kawy i współpracują z lokalnymi sprzedawcami w celu uzyskania spersonalizowanych ofert i specjalnych wrażeń podczas wydarzenia. Bez tych informacji firma Contoso mogła wysłać tylko ogólne marketingowe wiadomości e-mail i stracić możliwość personalizacji dla tego lokalnego segmentu swoich klientów o wysokiej wartości.

1. Wybierz **Dodaj dane** w opcji **Jeszcze bardziej popraw jakość wyników analiz modelu dzięki dodatkowym danym klientów**.

1. Dla opcji **Encja** wybierz pozycję **Klient: CustomerInsights**, aby wybrać ujednolicony profil klienta mapowany na dane atrybutu klienta. Jako **identyfikator klienta** wybierz pozycję **System.Customer.CustomerId**.

1. Mapowanie większej liczby pól, jeśli dane są dostępne w ujednoliconych profilach klientów.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Przykład zamapowanych pól dla danych profilu klienta.":::

1. Wybierz pozycję **Zapisz**.

1. Wybierz **Dalej**.

### <a name="set-update-schedule"></a>Ustaw harmonogram aktualizacji

1. Wybierz częstotliwość ponownego uaktualnienia modelu na podstawie najnowszych danych. To ustawienie ma znaczenie dla aktualizowania dokładności przewidywań w czasie pozyskiwania nowych danych do Customer Insights. Większość firm może przeprowadzać ponowne szkolenia raz w miesiącu i uzyskać dobrą dokładność przewidywań.

1. Wybierz **Dalej**.

### <a name="review-and-run-the-model-configuration"></a>Przegląd i uruchamianie konfiguracji modelu

W kroku **Przejrzyj i uruchom** przedstawiono podsumowanie konfiguracji i użytkownik może wprowadzić zmiany przed utworzeniem przewidywania.

1. Wybierz **Edytuj** na każdym z etapów, aby przejrzeć i wprowadzić ewentualne zmiany.

1. Jeśli użytkownik jest zadowolony z wprowadzonych opcji, wybiera opcję **Zapisz i uruchom**, aby rozpocząć uruchamianie modelu. Wybierz pozycję **Gotowe**. Podczas tworzenia przewidywanie jest wyświetlana karta **Moje prognozy**. Przeprowadzanie procesu może potrwać kilka godzin, w zależności od ilości danych użytych w przewidywaniu.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Wyświetl wyniki przewidywania

1. Przejdź do opcji **Analizy** > **Przewidywania**.

1. Na karcie **Moje przewidywania** wybierz przewidywanie, które chcesz wyświetlić.

Na stronie wyników wyszukiwania znajdują się trzy podstawowe sekcje danych.

- **Wydajność modelu szkolenia**: oceny A, B lub C wskazują wydajność prognozy i może pomóc w podjęciu decyzji o użyciu wyników przechowywanych w encji wyjściowej.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Obraz pola informacji o wynikach modelu wraz z oceną A.":::

  Aplikacja Customer Insights oceni, jak model AI przeprowadził przewidywanie klientów wysokiej jakości w porównaniu do modelu odniesienia.

  Oceny są określane na podstawie następujących reguł:
  - **A** kiedy model dokładnie przewidział co najmniej 5% więcej wartościowych klientów w porównaniu z modelem bazowym.
  - **B** gdy model dokładnie przewidział od 0 do 5% więcej klientów o wysokiej wartości w porównaniu z modelem bazowym.
  - **C**, gdy model dokładnie przewidział mniej wartościowych klientów w porównaniu z modelem bazowym.
  
  Wybierz [**Dowiedz się o tym wyniku**](#learn-about-the-score), by otworzyć okienko **Klasyfikacji modelu**, które pokazuje dalsze szczegóły dotyczące wydajności modelu AI i modelu odniesienia. Pomoże to w lepszym poznaniu podstawowych metryk wydajności modelu oraz sposobu pochodnego końcowej oceny wydajności modelu. Model bazowy wykorzystuje podejście nie oparte na sztucznej inteligencji do obliczania wartości klienta od początku śledzenia na podstawie historycznych zakupów dokonanych przez klientów.

- **Wartość klientów według procentu**: klienci o niskiej i wysokiej wartości są wyświetlani na wykresie. Najedź kursorem na słupki na histogramie by zobaczyć liczbę klientów w każdej grupie i średnią wartość CLV tej grupy. Opcjonalnie możesz [utworzyć segmenty klientów](prediction-based-segment.md) na podstawie ich prognoz CLV.
  
   :::image type="content" source="media/CLV-value-percent.png" alt-text="Wartość klientów wg procentu dla modelu CLV":::

- **Czynniki mające największy wpływ**: Podczas tworzenia prognozy CLV na podstawie danych wejściowych dostarczonych do modelu AI brane są pod uwagę różne czynniki. Każdy z czynników ma swoje znaczenie obliczane dla zagregowanych przewidywań tworzonych przez model. Tych czynników można użyć w celu sprawdzenia poprawności wyników przewidywania. Czynniki te zapewniają również lepszy wgląd w najbardziej wpływowe czynniki, które przyczyniły się do przewidywania CLV u wszystkich klientów.
  
   :::image type="content" source="media/CLV-influence-factors.png" alt-text="Czynniki mające największy wpływ dla modelu CLV":::

### <a name="learn-about-the-score"></a>Zapoznaj się z informacjami o wyniku

Standardowa formuła używana do obliczania CLV według modelu bazowego:

 _**CLV dla każdego klienta** = średni miesięczny zakup dokonany przez klienta w aktywnym oknie klienta * Liczba miesięcy w okresie prognozowania CLV * Ogólny wskaźnik utrzymania wszystkich klientów_

Model AI jest porównywany z modelem bazowym w oparciu o dwie metryki wydajności modelu.
  
- **Wskaźnik sukcesu w przewidywaniu wartościowych klientów**

  Zobacz różnicę w przewidywaniu klientów o dużej wartości za pomocą modelu AI w porównaniu z modelem bazowym. Na przykład wskaźnik sukcesu 84% oznacza, że spośród wszystkich klientów o dużej wartości w danych szkoleniowych model sztucznej inteligencji był w stanie dokładnie uchwycić 84%. Następnie porównujemy ten wskaźnik sukcesu ze wskaźnikiem sukcesu modelu bazowego, aby zgłosić względną zmianę. Ta wartość służy do przypisywania oceny modelowi.

- **Metryki błędów**

  Przeglądanie ogólnej wydajności modelu pod kątem błędu w przewidywaniu przyszłych wartości. Do oceny tego błędu używamy ogólnej metryki Root Mean Squared Error (RMSE). RMSE to standardowy sposób pomiaru błędu modelu przy prognozowaniu danych ilościowych. Wartość RMSE modelu AI jest porównywana z wartością RMSE modelu bazowego i zgłaszana jest względna różnica.

Model AI nadaje priorytet dokładnemu rankingowi klientów zgodnie z wartością, jaką wnoszą do Twojej firmy. Tak więc do wyliczenia ostatecznej oceny modelu wykorzystuje się tylko wskaźnik sukcesu przewidywania klientów o wysokiej wartości. Metryka RMSE jest wrażliwa na wartości odstające. W scenariuszach, w których masz niewielki odsetek klientów z wyjątkowo wysokimi wartościami zakupów, ogólna metryka RMSE może nie dawać pełnego obrazu wydajności modelu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
