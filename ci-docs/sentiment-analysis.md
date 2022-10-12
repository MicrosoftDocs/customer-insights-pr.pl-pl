---
title: Analizowanie opinii dla opinii klienta (wersja zapoznawcza)
description: Dowiedz się, jak użyć modelu analizy opinii na podstawie opinii klientów w programie Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 61ce9fb18efa6152dddb2e31f4fd0366a31ac2c7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610479"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analizowanie opinii klienta (wersja zapoznawcza)

Analiza nastrojów umożliwia syntezę nastrojów klientów i identyfikację aspektów biznesowych jako możliwości poprawy. Ta funkcja Customer Insights pomaga zrozumieć, co działa dobrze i czym należy się zająć. Może pomóc w prowadzeniu działań biznesowych, które umożliwiają doświadczenia, które skutkują wysoką satysfakcją i lojalnością klientów.

## <a name="overview"></a>Omówienie

Funkcja analizy opinii generuje dwie analizy pochodne dla każdego identyfikatora klienta. Wynik opinii (od -5 do 5) oraz lista odpowiednich aspektów biznesowych (obszarów działalności), które razem ułatwiają zrozumienie opinii klientów.

Dzięki analizie możesz:
- Uzyskiwanie przeglądu opinii klientów na temat marki lub organizacji
- Identyfikuj klientów z negatywnym sentymentem, aby skoncentrować swoje kampanie i zaangażowania oraz optymalizować pod kątem wyższego zwrotu  
- Zidentyfikuj aspekty biznesowe z problemami wskazanymi przez klientów  
- Segmentuj klientów na podstawie ich sentymentu do prowadzenia spersonalizowanych kampanii z ukierunkowaną sprzedażą, marketingiem i działaniami wsparcia
- Optymalizowanie operacji biznesowych przez adresowanie obszarów, w których wymieniono klientów lub szanse sprzedaży
- Rozpoznaj aspekty biznesowe, które dobrze sobie radzą i nagradzaj zadowolonych klientów poprzez programy lojalnościowe i promocyjne

Model oferuje listę słów, które wpłynęły na decyzję modelu o przypisaniu konkretnego wyniku nastrojów lub aspektu biznesowego do komentarzy w ramach opinii.  

Używamy dwóch **modeli przetwarzania języka naturalnego (NLP)**: pierwszy przypisuje każdemu komentarzowi opinii ocenę tonacji. Drugi model wiąże każdą informację zwrotną ze wszystkimi mającymi zastosowanie aspektami biznesowymi. Modele są szkolone na danych publicznych ze źródeł w mediach społecznościowych, handlu detalicznym, restauracjach, produktach konsumenckich i branży motoryzacyjnej.
  
Wstępnie zdefiniowane aspekty biznesowe modelu do powiązania z danymi zwrotnymi obejmują:
- Zarządzanie klientami
- Finalizacja zakupu i płatność
- Obsługa klienta
- Odbiór w sklepie
- Wysyłanie i odbieranie paczek
- Zamówienia w przedsprzedaży
- Cena
- Prywatność i zabezpieczenia
- Promocje i nagrody
- Paragon i gwarancja
- Zwrot, wymiana i anulowanie
- Dokładność realizacji
- Jakość witryny internetowej / aplikacji

> [!NOTE]
> Obecnie obsługujemy tylko analizę sentymentu na podstawie opinii klientów w języku angielskim. Więcej języków będzie obsługiwanych w przyszłości. Jeśli zostanie przesłana opinia w innych językach, model nadal będzie zwracał wyniki. Wyniki te nie będą jednak dokładne.

## <a name="prerequisites"></a>Wymagania wstępne

- Co najmniej [uprawnienia współautora](permissions.md)
- [Ujednolicone](data-unification.md) dane opinii tekstowej. Zdecydowanie zalecamy [skonfigurowanie encji danych opinii jako encji aktywności typu semantycznego](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (typ opinii).
- Unified Customer ID (UCID) z ujednolicania danych w celu dopasowania tekstowych rekordów danych opinii do poszczególnych klientów.
- Identyfikator opinii
- Sygnatura czasowa opinii
- Tekst opinii

Usługa Customer Insights może przetworzyć do 10 milionów rekordów opinii dla pojedynczego uruchomienia modelu. Model może analizować komentarze do 128 słów. Jeśli komentarz opinii jest dłuższy, w analizie są uwzględniane tylko pierwsze 128 słów.

> [!NOTE]
> Można skonfigurować tylko jeden obiekt opinii. Jeśli istnieje wiele encji opinii, połącz je w usłudze Power Query przed pozyskaniem danych.

## <a name="configure-a-sentiment-analysis"></a>Skonfiguruj analizę sentymentu

1. Przejdź do opcji **Analizy** > **Przewidywania**.

1. Na karcie **Utwórz** wybierz **Model użycia** na kafelku **Analiza opinii klient (wersja zapoznawcza)**.

1. Wybierz **Rozpocznij**.

1. Podaj **Nazwę** analizy i podaj **Nazwę encji wyjściowej aspektu biznesowego** i **Nazwę encji wyjściowej oceny nastrojów**.

1. Wybierz **Dalej**.

1. Wybierz **Dodaj dane** do **Opinia klienta**.

1. Wybierz typ działania semantycznego **Opinie** zawierające dane opinii. Jeśli działanie nie zostało ustawione, zaznacz **tutaj** i utwórz działanie.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Krok konfiguracji w celu wybrania działań zwrotnych do analizy sentymentu.":::

1. Wybierz działania do użycia w tej analizie nastrojów, a następnie wybierz **Dalej**.

1. Przypisz atrybuty w swoich danych do atrybutów modelu. 

1. Wybierz pozycję **Zapisz**.

1. Wybierz **Dalej**. W kroku **Przejrzyj i uruchom** przedstawiono podsumowanie konfiguracji i użytkownik może wprowadzić zmiany przed utworzeniem analizy.

1. Wybierz **Edytuj** na każdym z etapów, aby przejrzeć i wprowadzić ewentualne zmiany.

1. Jeśli użytkownik jest zadowolony z wprowadzonych opcji, wybiera opcję **Zapisz i uruchom**, aby rozpocząć uruchamianie modelu. Wybierz pozycję **Gotowe**. Podczas tworzenia przewidywanie jest wyświetlana karta **Moje prognozy**. Przeprowadzanie procesu może potrwać kilka godzin, w zależności od ilości danych użytych w przewidywaniu.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-analysis-results"></a>wyświetl wyniki analizy

1. Przejdź do opcji **Analizy** > **Przewidywania**.

1. Na karcie **Moje przewidywania** wybierz przewidywanie, które chcesz wyświetlić.

Istnieją dwie karty wyników.

### <a name="sumary-tab"></a>Karta Podsumowanie

Na stronie wyników znajdują się cztery podstawowe sekcje danych.

- **Średni wynik opinii**:wyniki sentymentów pomagają zrozumieć ogólny sentyment wśród wszystkich klientów.
  - **Negatywne** (-5 > 2)
  - **Obojętne** (-1 > 1)
  - **Pozytywne** (2 > 5)
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Wizualna reprezentacja ogólnego sentymentu klientów.":::

- **Dystrybucja klientów według wyników opinii**: Klienci są podzieleni na grupy negatywne, neutralne i pozytywne na podstawie ich wyników nastrojów. Przesuń kursor nad słupkami w histografiach, aby zobaczyć liczbę klientów i średni wynik opinii w każdej grupie. Te dane mogą pomóc w [tworzeniu segmentów klientów](prediction-based-segment.md) na podstawie wyników opinii klientów.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Wykres słupkowy przedstawiający nastroje klientów w trzech grupach nastrojów.":::

- **Średni wynik opinii w czasie**: opinie klientów mogą się w czasie zmieniać. Przedstawiamy trendy w nastrojach Twoich klientów dla zakresu czasowego Twoich danych. Ten widok pomoże w ocenie wpływu sezonowych promocji, premier produktów lub innych ograniczonych czasowo interwencji na nastroje klientów. Wykres można zobaczyć, wybierając z menu rozwijanego rok zainteresowania.

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Wykres historii z wynikiem nastrojów w czasie przedstawionym w postaci linii.":::

- **Sentyment w różnych aspektach biznesowych**: średnie sentymenty w aspektach biznesowych pomagają ocenić, które aspekty działalności już wpływają na klientów lub wymagają więcej uwagi. Rekordy opinii, które nie są wyrównane do żadnego z obsługiwanych aspektów biznesowych, są skategoryzowane w obszarze **Inne**. Posortuj dane, wybierając dowolną kolumnę.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Lista aspektów biznesowych wraz z powiązaną wartością sentymentu i liczbą wymieniających go klientów.":::

  Wybierz nazwę aspektu biznesowego, aby zobaczyć, w jaki sposób aspekt biznesowy jest identyfikowany przez model:

  - **Wpływowe słowa**: najważniejsze słowa, które wpłynęły na identyfikację aspektu biznesowego przez model AI w informacjach zwrotnych od klientów.
    **Pokaż obraźliwe słowa**: pozwala uwzględnić obraźliwe słowa na liście z oryginalnych danych opinii klientów. Ta funkcja jest domyślnie wyłączona.  Maskowanie obraźliwych słów jest oparte na modelu AI i może nie wykryć wszystkich obraźliwych słów. Jeśli wykryjesz obraźliwe słowo, które nie zostało odfiltrowane zgodnie z oczekiwaniami, daj nam znać.

    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Lista wpływowych słów z przełącznikiem, aby pokazać lub ukryć obraźliwe słowa.":::

  - **Przykładowe opinie**: aktualne rekordy opinii w danych. Słowa są kodowane kolorami zgodnie z ich wpływem na identyfikację aspektu biznesowego.

### <a name="influential-words-analysis-tab"></a>Zakładka Analiza wpływowych słów

Istnieją trzy sekcje dodatkowych informacji, które wyjaśniają, jak działa model sentymentu.
  
- **Najważniejsze wyrazy wpływające na pozytywne opinie**: najlepsze wyrazy, które wpływają na identyfikację pozytywnej opinii klienta w modelu AI.  

- **Najważniejsze wyrazy wpływające na negatywne opinie**: najlepsze wyrazy, które wpływają na identyfikację negatywnej opinii klienta w modelu AI.

- **Przykładowe opinie**: rzeczywiste rekordy opinii, jeden z negatywną, a drugi z pozytywną opinią. Wyrazy w rekordach opinii są wyróżniane zgodnie z ich znaczeniem dla przypisanego wyniku opinii. Słowa, które przyczyniają się do pozytywnego wyniku opinii są zaznaczone na zielono. Słowa wpływające na wynik ujemny są wyróżnione na czerwono.
   Wybierz **Zobacz więcej**, aby załadować więcej próbek opinii.
  
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Przykłady analizy opinii klientów w opinii klientów.":::

**Pokaż obraźliwe słowa**: pozwala uwzględnić obraźliwe słowa na liście z oryginalnych danych opinii klientów. Ta funkcja jest domyślnie wyłączona.  Maskowanie obraźliwych słów jest oparte na modelu AI i może nie wykryć wszystkich obraźliwych słów. Jeśli wykryjesz obraźliwe słowo, które nie zostało odfiltrowane zgodnie z oczekiwaniami, daj nam znać.

## <a name="act-on-analysis-results"></a>Działaj na podstawie wyników analizy

Aby utworzyć nowe segmenty klientów można łatwo rozpocząć na stronie z wynikami analizy sentymentu, wybierając **Utwórz segmenty** w górnej części strony z wynikami modelu.

## <a name="potential-bias"></a>Potencjalne odchylenie

Podobnie jak w przypadku każdej funkcji, która wykorzystuje predykcyjną sztuczną inteligencję, należy być świadomym potencjalnego błędu w danych używanych do przewidywania nastrojów klientów. Na przykład, jeśli zbierasz opinie tylko cyfrowo, możesz przegapić opinie klientów, którzy prowadzą z Tobą interesy głównie osobiście, co może mieć wpływ na wyniki funkcji.

Ponieważ funkcja ta wykorzystuje zautomatyzowane środki do oceny danych i dokonywania prognoz na podstawie tych danych, może być wykorzystywana jako metoda profilowania, zgodnie z definicją tego terminu w ogólnym rozporządzeniu o ochronie danych („RODO”). Korzystanie z tej funkcji do przetwarzania danych może podlegać RODO lub innym prawom lub regulacjom. Jesteś odpowiedzialny za zapewnienie, że korzystanie z usługi Dynamics 365 Customer Insights, w tym analiza nastrojów, jest zgodne ze wszystkimi obowiązującymi przepisami i regulacjami, w tym przepisami dotyczącymi prywatności, danych osobowych, danych biometrycznych, ochrony danych i poufności komunikacji.

[!INCLUDE [footer-include](includes/footer-banner.md)]

