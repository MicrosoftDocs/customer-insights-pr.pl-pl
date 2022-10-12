---
title: Przewidywanie rezygnacji z subskrypcji (zawiera wideo)
description: Przewiduj, czy istnieje zagrożenie, że klient przestanie używać subskrypcji na produkty lub usługi Twojej firmy.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 7464707864c418bfcc625ddfd245622131434b33
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610249"
---
# <a name="predict-subscription-churn"></a>Przewidywana rezygnacji z subskrypcji

Przewiduj, czy istnieje zagrożenie, że klient przestanie używać subskrypcji na produkty lub usługi Twojej firmy. Dane subskrypcji: obejmują aktywne i nieaktywne subskrypcje dla każdego klienta, więc dla każdego identyfikatora klienta jest wiele wpisów.

Należy posiadać wiedzę biznesową, pozwalającą zrozumieć co rezygnacja oznacza dla działalności. Obsługujemy definicje rezygnacji czasowych, co oznacza, że uważamy, że klient zrezygnował na pewien czas po zakończeniu subskrypcji.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Wypróbuj przewidywanie rezygnacji z subskrypcji za pomocą przykładowych danych: [Przykładowy przewodnik dotyczący prognozowania rezygnacji z subskrypcji (wersja zapoznawcza)](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Wymagania wstępne

- Co najmniej [uprawnienia współautora](permissions.md).
- Co najmniej 10 profilów klientów, najlepiej ponad 1000 unikalnych klientów.
- Identyfikator klientów, unikatowy identyfikator umożliwiający dopasowanie subskrypcji do klientów.
- Dane subskrypcji dla co najmniej podwójnego wybranego okna czasowego. Najlepiej dwa do trzech lat danych subskrypcji. Historia subskrypcji musi zawierać:
  - **Identyfikator subskrypcji:** unikatowy identyfikator subskrypcji.
  - **Data zakończenia subskrypcji:** data wygaśnięcia subskrypcji klienta.
  - **Data rozpoczęcia subskrypcji:** data rozpoczęcia subskrypcji klienta.
  - **Data transakcji:** data wystąpienia zmiany w subskrypcji. Na przykład klient, który kupuję lub anuluje subskrypcję.
  - **Czy jest to subskrypcja cykliczna:** pole logiczne prawda/fałsz które określa, czy subskrypcja zostanie odnowiona z takim samym identyfikatorem subskrypcji bez interwencji klienta
  - **Częstotliwość powtarzania (w miesiącach):** dla subskrypcji cyklicznych miesiąc, na jakim subskrypcja jest odnawiana. Na przykład roczna subskrypcja, która jest automatycznie odnawiana dla klienta co roku na kolejny rok ma wartość 12.
  - **Kwota subskrypcji:** kwota płacona przez klienta za odnowienie subskrypcji. Może to pomóc w określeniu wzorów dla różnych poziomów subskrypcji.
- Dla 50% klientów, dla których ma być obliczona wartość zmian, co najmniej dwa rekordy działań. Szczegóły działań klienta muszą zawierać:
  - **Klucz podstawowy**: unikatowy identyfikator działania. Na przykład wizyta w witrynie sieci Web lub rekord użycia ukazujący, że w klient obejrzał odcinek serialu telewizyjnego.
  - **Sygnatura czasowa**: data i godzina zdarzenia identyfikowanego przez klucz podstawowy.
  - **Zdarzenie:** nazwa zdarzenia, którego chcesz użyć. Na przykład pole o nazwie "UserAction" w usłudze przesyłania strumieniowego wideo może mieć wartość "Obejrzany".
  - **Szczegóły:** Szczegółowe informacje o zdarzeniu. Na przykład pole o nazwie "ShowTitle" w usłudze przesyłania strumieniowego wideo może mieć wartość wideo obejrzanego przez klienta.
- Mniej niż 20% brakujących wartości w polu dostarczonej encji.

## <a name="create-a-subscription-churn-prediction"></a>Utwórz prognozę rezygnacji z subskrypcji

W dowolnym momencie wybierz opcję **Zapisz roboczą**, aby zapisać przewidywanie jako roboczą. Wersja robocza wyświetla się na karcie **Moje prognozy**.

1. Przejdź do opcji **Analizy** > **Przewidywania**.

1. Na karcie **Utwórz** wybierz **Model użycia** na kafelku **Model rezygnacji klienta**.

1. Wybierz opcję **Subskrypcja** dla typu rozsyłania, a następnie wybierz opcję **Rozpocznij**.

1. **Nazwij ten model** i **Nazwa encji wyjściowej**, aby odróżnić je od innych modeli lub encji.

1. Wybierz **Dalej**.

### <a name="define-customer-churn"></a>Definiuj rezygnację klienta

1. Wprowadź liczbę **Dni od zakończenia subskrypcji**, przez które firma uważa, że klient jest w stanie rezygnacji. Ten okres zazwyczaj jest powiązany z działaniami biznesowymi, takimi jak oferty, lub inne działania marketingowe, które usiłują zapobiec utracie klienta.

1. Wprowadź **Liczbę dni w przyszłości na potrzeby przewidywania rezygnacji**. Na przykład prognozuj ryzyko odejścia klientów w ciągu najbliższych 90 dni, aby dostosować się do działań marketingowych dotyczących utrzymania klientów. Przewidywanie ryzyka rezygnacji przez dłuższe lub krótsze okresy może jednak znacznie utrudnić branie pod uwagę czynników w profilu ryzyka rezygnacji w zależności od konkretnych wymagań biznesowych.

1. Wybierz **Dalej**.

### <a name="add-required-data"></a>Dodaj wymagane dane

1. Wybierz **Dodaj dane** dla **Historii subskrypcji**.

1. Wybierz semantyczny typ działania **Subskrypcja**, które zawiera informacje o historii subskrypcji. Jeśli działanie nie zostało ustawione, zaznacz **tutaj** i utwórz działanie.

1. W obszarze **Działania**, jeśli atrybuty działania zostały semantycznie zamapowane podczas tworzenia działania, wybierz określone atrybuty lub encję, na których chcesz skupić obliczenia. Jeśli semantyczne mapowanie nie wystąpiło, wybierz opcję **Edytuj** i zamapuj dane.
  
   :::image type="content" source="media/subscription-churn-required.png" alt-text="Dodawanie wymaganych danych dla modelu rezygnacji z subskrypcji":::

1. Wybierz opcję **Dalej** i przejrzyj atrybuty wymagane dla tego modelu.

1. Wybierz pozycję **Zapisz**.

1. Wybierz **Dodaj dane** do **Działań klienta**.

1. Wybierz typ semantycznego działania, który pozwala uzyskać informacje o działaniu klienta. Jeśli działanie nie zostało ustawione, zaznacz **tutaj** i utwórz działanie.

1. W obszarze **Działania**, jeśli atrybuty działania zostały semantycznie zamapowane podczas tworzenia działania, wybierz określone atrybuty lub encję, na których chcesz skupić obliczenia. Jeśli semantyczne mapowanie nie wystąpiło, wybierz opcję **Edytuj** i zamapuj dane.

1. Wybierz opcję **Dalej** i przejrzyj atrybuty wymagane dla tego modelu.

1. Wybierz pozycję **Zapisz**.

1. Dodaj więcej działań lub wybierz **Dalej**.

### <a name="set-update-schedule"></a>Ustaw harmonogram aktualizacji

1. Wybierz częstotliwość ponownego uczenia modelu. To ustawienie ma znaczenie dla aktualizowania dokładności prognoz, gdy nowe dane są zbierane w Customer Insights. Większość firm może przeprowadzać ponowne szkolenia raz w miesiącu i uzyskać dobrą dokładność przewidywań.

1. Wybierz **Dalej**.

### <a name="review-and-run-the-model-configuration"></a>Przegląd i uruchamianie konfiguracji modelu

W kroku **Przejrzyj i uruchom** przedstawiono podsumowanie konfiguracji i użytkownik może wprowadzić zmiany przed utworzeniem przewidywania.

1. Wybierz **Edytuj** na każdym z etapów, aby przejrzeć i wprowadzić ewentualne zmiany.

1. Jeśli użytkownik jest zadowolony z wprowadzonych opcji, wybiera opcję **Zapisz i uruchom**, aby rozpocząć uruchamianie modelu. Wybierz pozycję **Gotowe**. Podczas tworzenia przewidywanie jest wyświetlana karta **Moje prognozy**. Przeprowadzanie procesu może potrwać kilka godzin, w zależności od ilości danych użytych w przewidywaniu.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Wyświetl wyniki przewidywania

1. Przejdź do opcji **Analizy** > **Przewidywania**.

1. Na karcie **Moje przewidywania** wybierz przewidywanie, które chcesz wyświetlić.

Na stronie wyników wyszukiwania znajdują się trzy podstawowe sekcje danych:

- **Wydajność modelu szkolenia**: oceny A, B lub C wskazują wydajność prognozy i może pomóc w podjęciu decyzji o użyciu wyników przechowywanych w encji wyjściowej.
  
  :::image type="content" source="media/subscription-churn-modelperformance.PNG" alt-text="Obraz pola informacji o wynikach modelu wraz z oceną A.":::

  Oceny są określane na podstawie następujących reguł:
  - **A** kiedy model dokładnie przewidział co najmniej 50% wszystkich prognoz, a odsetek trafnych prognoz dla klientów, którzy zrezygnowali, jest większy od wskaźnika historycznego średniego współczynnika rezygnacji o co najmniej 10%.
  - **B** kiedy model dokładnie przewidział co najmniej 50% wszystkich prognoz, a odsetek trafnych prognoz dla klientów, którzy zrezygnowali, jest większy od wskaźnika historycznego średniego współczynnika rezygnacji do 10%.
  - **C**, kiedy model precyzyjnie przewidział mniej niż 50% łącznych przewidywań, lub kiedy procent dokładnych prognoz dla klientów, którzy zrezygnowali jest mniejszy niż historyczny średni współczynnik rezygnacji.
  
- **Prawdopodobieństwo rezygnacji (liczba klientów)**: grupy klientów na podstawie ich przewidywanego ryzyka rezygnacji. Opcjonalnie można [utworzyć segmenty klientów](prediction-based-segment.md) o wysokim ryzyku rezygnacji. Takie segmenty ułatwiają zrozumienie tego, w którym miejscu powinien się znaleźć próg dla członkostwa w segmencie.  

  :::image type="content" source="media/subscription-churn-resultdistribution.PNG" alt-text="Wykres przedstawiający rozkład wyników rezygnacji, podzielony na zakresy z 0-100%":::

- **Czynniki mające największy wpływ:** Istnieje wiele czynników branych pod uwagę podczas tworzenia przewidywania. Każdy z czynników ma swoją wagę obliczoną dla zagregowanych prognoz tworzonych przez model. Tych czynników można użyć w celu sprawdzenia poprawności wyników przewidywania. Lub użyj tych informacji później, aby [utworzyć segmenty](.//prediction-based-segment.md), które mogą wpłynąć na ryzyko rezygnacji dla klientów.

  :::image type="content" source="media/subscription-churn-influentialfactors.PNG" alt-text="Lista prezentująca czynniki wywierające wpływ i ich znaczenie przy przewidywaniu wyniku rezygnacji.":::

> [!NOTE]
> W encji wyjściowej dla tego modelu *ChurnScore* jest prawdopodobieństwem rezygnacji, a *IsChurn* jest binarnym poziomem na podstawie wyniku *ChurnScore* z progiem 0,5. Jeśli ten domyślny próg nie działa w tym scenariuszu, [utwórz nowy segment](segments.md) z wybranym progiem. Aby wyświetlić wynik rezygnacji, przejdź do **Dane** > **Encje** i wyświetl kartę danych dla encji wyjściowej zdefiniowanej dla tego modelu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
