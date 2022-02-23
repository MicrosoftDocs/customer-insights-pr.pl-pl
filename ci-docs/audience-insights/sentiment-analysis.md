---
title: Analiza opinii dla opinii klientów
description: Dowiedz się, jak użyć modelu analizy opinii na podstawie opinii klientów w programie Dynamics 365 Customer Insights.
ms.date: 12/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 8a4473c1c395bbcf8efa2bfa24cddb82e1784279
ms.sourcegitcommit: 15ec8c5f54242feda9489e7665726ec5e0983dc9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/19/2022
ms.locfileid: "8008778"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analizowanie opinii klienta (wersja zapoznawcza)

W dzisiejszych czasach klienci oczekują wysokiej jakości produktów, usług i doświadczeń. Szczególnie klienci, którzy dzielą się swoimi opiniami. Analizowanie coraz większej ilości danych bez obniżania dokładności i wyższych kosztów pracy jest bardzo trudne dla organizacji. Dynamics 365 Customer Insights oferuje model analizy opinii klientów umożliwiający organizacjom analizowanie ich danych dokładniej i przy niższej cenie.

Analiza nastrojów umożliwia syntezę nastrojów klientów i identyfikację aspektów biznesowych jako możliwości poprawy. Ta funkcja Customer Insights pomaga zrozumieć, co działa dobrze i czym należy się zająć. Skoncentruj się na najistotniejszych i najbardziej wpływowych obszarach działalności, aby poprawić wrażenia klientów. Ostatecznie może pomóc w prowadzeniu działań biznesowych, które umożliwiają doświadczenia, które skutkują wysoką satysfakcją i lojalnością klientów.

## <a name="overview"></a>Omówienie

Funkcja analizy opinii generuje dwie analizy pochodne dla każdego identyfikatora klienta. Wynik opinii (od -5 do 5) oraz lista odpowiednich aspektów biznesowych (obszarów działalności) razem ułatwiają zrozumienie opinii klientów. 

Te informacje mogą pomóc w osiągnięciu następujących wyników: 
- Uzyskiwanie przeglądu opinii klientów na temat marki lub organizacji
- Identyfikuj klientów z negatywnym sentymentem, aby skoncentrować swoje kampanie i zaangażowania oraz optymalizować pod kątem wyższego zwrotu  
- Zidentyfikuj aspekty biznesowe z problemami wskazanymi przez klientów  
- Segmentuj klientów na podstawie ich sentymentu do prowadzenia spersonalizowanych kampanii z ukierunkowaną sprzedażą, marketingiem i działaniami wsparcia
- Optymalizowanie operacji biznesowych przez adresowanie obszarów, w których wymieniono klientów lub szanse sprzedaży
- Rozpoznaj aspekty biznesowe, które dobrze sobie radzą i nagradzaj zadowolonych klientów poprzez programy lojalnościowe i promocyjne

Aby upewnić się, że możesz zaufać wynikom modeli, zapewniamy przejrzyste informacje o tym, jak modele podejmują decyzje. Otrzymasz listę słów, które wpłynęły na decyzję modeli o przypisaniu konkretnego wyniku nastrojów lub aspektu biznesowego do komentarzy w ramach opinii.  

Używamy dwóch **modeli przetwarzania języka naturalnego (NLP)**: pierwszy przypisuje każdemu komentarzowi opinii ocenę tonacji. Drugi model wiąże każdą informację zwrotną ze wszystkimi mającymi zastosowanie aspektami biznesowymi. Modele są szkolone na danych publicznych ze źródeł w mediach społecznościowych, handlu detalicznym, restauracjach, produktach konsumenckich i branży motoryzacyjnej.    
  
Wstępnie zdefiniowane aspekty biznesowe modelu do powiązania z danymi zwrotnymi obejmują:
-   Zarządzanie klientami
-   Finalizacja zakupu i płatność
-   Obsługa klienta
-   Odbiór w sklepie
-   Wysyłanie i odbieranie paczek
-   Zamówienia w przedsprzedaży
-   Cena
-   Prywatność i zabezpieczenia
-   Promocje i nagrody
-   Paragon i gwarancja
-   Zwrot, wymiana i anulowanie
-   Dokładność realizacji
-   Jakość witryny internetowej / aplikacji

> [!NOTE]
> Obecnie obsługujemy tylko analizę sentymentu na podstawie opinii klientów w języku angielskim. Więcej języków będzie obsługiwanych w przyszłości. Jeśli zostanie przesłana opinia w innych językach, model nadal będzie zwracał wyniki. Wyniki te nie będą jednak dokładne. 

## <a name="prerequisites"></a>Wymagania wstępne

Analiza nastrojów opiera się na informacjach zwrotnych tekstowych, które przeszły przez [proces ujednolicenia danych](data-unification.md). Zdecydowanie zalecamy wcześniejsze [skonfigurowanie encji danych opinii jako encji aktywności typu semantycznego](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (typ opinii). 

Aby skonfigurować model analizy opinii, potrzebne są uprawnienia [współautor użytkownika](permissions.md).

Usługa Customer Insights może przetworzyć do 10 milionów rekordów opinii dla pojedynczego uruchomienia modelu. Model może analizować komentarze do 128 słów. Jeśli komentarz opinii jest dłuższy, w analizie są uwzględniane tylko pierwsze 128 słów.

### <a name="data-requirements"></a>Wymagania dotyczące danych
  
Wymagane są następujące atrybuty danych:
- Unified Customer ID (DOD) w celu dopasowania tekstowych rekordów danych opinii do poszczególnych klientów. Ten identyfikator jest wynikiem [procesu ujednolicania danych](data-unification.md).
- Identyfikator opinii
- Sygnatura czasowa opinii
- Tekst opinii   

> [!TIP]
> Analiza nastrojów wymaga informacji zwrotnej tekstowej od Twoich klientów. Obecnie można skonfigurować tylko jeden obiekt opinii. Jeśli istnieje wiele encji opinii, możesz połączyć je w dodatku Power Query przed rozpoczęciem pozyskiwania danych.

## <a name="configure-a-sentiment-analysis"></a>Skonfiguruj analizę sentymentu 

1. W Customer Insights przejdź do **Analizy** > **Przewidywania**.

1. W kafelku **Analiza opinii klientów** wybierz opcję **Użyj modelu**.

1. W okienku **Analiza opinii klienta (podgląd)** wybierz opcję **Wprowadzenie**.

1. W kroku **Nazwa modelu** podaj **Nazwę** dla analizy. 

1. Podaj **Nazwa encji wyjściowej aspektu biznesowego** i **Nazwa encji wyjściowej oceny nastrojów**, a następnie wybierz **Następny**.

1. W kroku **Wymagane dane** wybierz opcję **Dodaj dane**.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Dodaj przepływ danych w modelu analizy sentymentu.":::

1. W okienku **Dodawanie danych** wybierz z listy typ **opinii**.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Krok konfiguracji w celu wybrania działań zwrotnych do analizy sentymentu.":::

1. Wybierz działania do użycia w tej analizie nastrojów, a następnie wybierz **Dalej**.
 
1. Przypisz atrybuty w swoich danych do atrybutów modelu. Wybierz pozycję **Zapisz**, aby zastosować swoje wybory. 

1. Zostanie wyświetlony stan mapowania danych. Wybierz **Dalej**, aby kontynuować. 

1. W kroku **Przegląd szczegółów modelu** sprawdź poprawność konfiguracji analizy opinii. Można wrócić do dowolnego części przewidywanie konfiguracji. Wybierz opcję **Zapisz i uruchom** w celu rozpoczęcia analizy. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Krok przeglądu dla modelu nastrojów pokazującego wszystkie skonfigurowane elementy.":::

1. Wybierz **Wykonane**, aby wystawić dane konfiguracyjne. Proces może potrwać kilka godzin w zależności od ilości wykorzystywanych danych. 

## <a name="review-analysis-status"></a>Sprawdź stan analizy

1.  Wybierz **Analizy** > **Przewidywania** i wybierz kartę **Moje przewidywania**.
2.  Wybierz przewidywania do przeglądu.
- **Nazwa przewidywania**: Nazwa przewidywania podana podczas jej tworzenia.
- **Typ przewidywania**: typ modelu używanego przez przewidywanie.
- **Encja wyjściowa**: Nazwa encji, w której mają być przechowywane wyniki przewidywania. Przejdź do **Dane** > **Encje** w celu znalezienia encji o tej nazwie.
- **Przewidywane pole**: To pole jest wypełniane tylko w przypadku niektórych typów prognoz i nie jest używane w przewidywaniu długookresowej wartości klienta.
- **Stan**: Stan przebiegu przewidywania.
  - **W kolejce**: Prognoza czeka na zakończenie innych procesów.
  - **Odświeżanie**: przewidywanie jest obecnie uruchomione w celu utworzenia wyników, które będą przepływać na encję wyjściową.
  - **Niepowodzenie**: uruchomienie przewidywanie zakończyło się niepowodzeniem. Aby uzyskać więcej informacji, przejrzyj dzienniki.
  - **Zakończono pomyślnie**: przewidywanie zakończyło się sukcesem. Wybierz Wyświetl pod elipsami pionowymi, aby przewidzieć wyniki.
- **Edytowano**: Data konfiguracji dla przewidywania została zmieniona.
- **Data ostatniego odświeżenia**: Data odświeżenia wyników prognozy w encji wyjściowej.

## <a name="manage-sentiment-analysis"></a>Zarządzaj analizą opinii

Możesz optymalizować, rozwiązywać problemy, odświeżać lub usuwać prognozy. Zapoznaj się z raportem użyteczności danych wejściowych, aby dowiedzieć się, jak przyspieszyć przewidywanie i zwiększyć jego wiarygodność. Aby uzyskać więcej informacji, zobacz [Zarządzaj przewidywaniami](manage-predictions.md).

## <a name="review-analysis-results"></a>Sprawdź wyniki analizy
 
1. Wybierz **Analizy** > **Przewidywania** i wybierz kartę **Moje przewidywania**. 
1. Wybierz nazwę prognozy, której wyniki chcesz sprawdzić. W tym przypadku wybierz analizę opinii, którą chcesz przejrzeć. 

### <a name="summary-tab"></a>Karta Podsumowanie

Na stronie wyników znajdują się cztery podstawowe sekcje danych. 

- **Średni wynik opinii**: Pomaga zrozumieć ogólny sentyment wśród wszystkich klientów. Wyniki opinii są pogrupowane w trzy kategorie: 
  1.    Negatywne (-5 > 2)
  2.    Obojętny (-1 > 1)
  3.    Pozytywne (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Wizualna reprezentacja ogólnego sentymentu klientów.":::

- **Dystrybucja klientów według wyników opinii**: Klienci są podzieleni na grupy negatywne, neutralne i pozytywne na podstawie ich wyników nastrojów. Przesuń kursor nad słupkami w histografiach, aby zobaczyć liczbę klientów i średni wynik opinii w każdej grupie. Te dane mogą pomóc w [tworzeniu segmentów klientów](segments.md) na podstawie wyników opinii klientów.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Wykres słupkowy przedstawiający nastroje klientów w trzech grupach nastrojów.":::

- **Średni wynik opinii w czasie**: opinie klientów mogą się w czasie zmieniać. Przedstawiamy trendy w nastrojach Twoich klientów dla zakresu czasowego Twoich danych. Ten widok może pomóc w ocenie wpływu sezonowych promocji, premier produktów lub innych ograniczonych czasowo interwencji na nastroje klientów. Wykres można zobaczyć, wybierając z menu rozwijanego rok zainteresowania. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Wykres historii z wynikiem nastrojów w czasie przedstawionym w postaci linii.":::
 
- **Sentyment w różnych aspektach biznesowych**: W tej tabeli wymieniono średnie nastroje w różnych aspektach biznesowych. Pomoże Ci ocenić, które aspekty Twojej firmy już satysfakcjonują klientów, a które wymagają większej uwagi. Rekordy opinii, które nie są wyrównane do żadnego z obsługiwanych aspektów biznesowych, są skategoryzowane w obszarze **Inne**. Tabela jest domyślnie posortowana alfabetycznie. Sortowanie można zmodyfikować, wybierając nagłówek tabeli.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Lista aspektów biznesowych wraz z powiązaną wartością sentymentu i liczbą wymieniających go klientów.":::
 
  Wybierz nazwę aspektu biznesowego, aby zobaczyć dodatkowe informacje, w jaki sposób aspekt biznesowy jest identyfikowany przez model. W tym okienku znajdują się dwie części: 

  - **Wpływowe słowa**: pokazuje najważniejsze słowa, które wpłynęły na identyfikację aspektu biznesowego przez model AI w informacjach zwrotnych od klientów. 
    **Pokaż obraźliwe słowa**: pozwala uwzględnić obraźliwe słowa na liście z oryginalnych danych opinii klientów. Ta funkcja jest domyślnie wyłączona.  Maskowanie obraźliwych słów jest oparte na modelu AI i może nie wykryć wszystkich obraźliwych słów. Kontynuujemy iterację i szkolenie klasyfikatora w celu uzyskania optymalnej wydajności. Jeśli wykryjesz obraźliwe słowo, które nie zostało odfiltrowane zgodnie z oczekiwaniami, daj nam znać. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Lista wpływowych słów z przełącznikiem, aby pokazać lub ukryć obraźliwe słowa.":::
 
  - **Przykładowe opinie**: Pokazuje aktualne rekordy opinii w Twoich danych. Słowa są kodowane kolorami zgodnie z ich wpływem na identyfikację aspektu biznesowego. 


### <a name="influential-words-analysis-tab"></a>Zakładka Analiza wpływowych słów

Istnieją trzy sekcje dodatkowych informacji, które wyjaśniają, jak działa model sentymentu.
  
1. **Najważniejsze wyrazy wpływające na pozytywne opinie**: pokazuje najlepsze wyrazy, które wpływają na identyfikację pozytywnej opinii klienta w modelu AI.  
2. **Najważniejsze wyrazy wpływające na negatywne opinie**: pokazuje najlepsze wyrazy, które wpływają na identyfikację negatywnej opinii klienta w modelu AI.  
3. **Przykładowe opinie**: Pokazuje rzeczywiste rekordy opinii, jeden z negatywną, a drugi z pozytywną opinią. Wyrazy w rekordach opinii są wyróżniane zgodnie z ich znaczeniem dla przypisanego wyniku opinii. Słowa, które przyczyniają się do pozytywnego wyniku opinii są zaznaczone na zielono. Słowa wpływające na wynik ujemny są wyróżnione na czerwono.
   Zaznacz **opcję Więcej informacji**, aby załadować więcej przykładów opinii, które dostarczają więcej informacji i kontekstu działania modelu opinii.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Przykłady analizy opinii klientów w opinii klientów.":::
 
**Pokaż obraźliwe słowa**: pozwala uwzględnić obraźliwe słowa na liście z oryginalnych danych opinii klientów. Ta funkcja jest domyślnie wyłączona.  Maskowanie obraźliwych słów jest oparte na modelu AI i może nie wykryć wszystkich obraźliwych słów. Kontynuujemy iterację i szkolenie klasyfikatora w celu uzyskania optymalnej wydajności. Jeśli wykryjesz obraźliwe słowo, które nie zostało odfiltrowane zgodnie z oczekiwaniami, daj nam znać. 

## <a name="act-on-analysis-results"></a>Działaj na podstawie wyników analizy

Tworzenie nowych segmentów klientów można łatwo rozpocząć na stronie z wynikami analizy sentymentu, wybierając **Utwórz segmenty** w górnej części strony z wynikami modelu.

:::image type="content" source="media/create-segment-model.png" alt-text="Pasek poleceń z opcjami dotyczącymi modeli predykcyjnych.":::
 
## <a name="potential-bias"></a>Potencjalne odchylenie

Podobnie jak w przypadku każdej funkcji, która wykorzystuje predykcyjną sztuczną inteligencję, należy być świadomym potencjalnego błędu w danych używanych do przewidywania nastrojów klientów. Na przykład, jeśli zbierasz opinie tylko cyfrowo, możesz przegapić opinie klientów, którzy prowadzą z Tobą interesy głównie osobiście, co może mieć wpływ na wyniki funkcji.

Ponieważ funkcja ta wykorzystuje zautomatyzowane środki do oceny danych i dokonywania prognoz na podstawie tych danych, może być wykorzystywana jako metoda profilowania, zgodnie z definicją tego terminu w ogólnym rozporządzeniu o ochronie danych („RODO”). Korzystanie z tej funkcji do przetwarzania danych może podlegać RODO lub innym prawom lub regulacjom. Jesteś odpowiedzialny za zapewnienie, że korzystanie z usługi Dynamics 365 Customer Insights, w tym analiza nastrojów, jest zgodne ze wszystkimi obowiązującymi przepisami i regulacjami, w tym przepisami dotyczącymi prywatności, danych osobowych, danych biometrycznych, ochrony danych i poufności komunikacji.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

