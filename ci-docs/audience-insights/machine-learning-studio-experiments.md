---
title: Doświadczenia z Machine Learning Studio (klasyczne)
description: Korzystanie z modeli Machine Learning Studio (klasycznych) w Dynamics 365 Customer Insights.
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: ameetj
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b979dd177b7c6de1971c02a69748006d041e4d2c3e49a3639dba03212bd7acf9
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033736"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>Użyj modeli opartych na Azure Machine Learning Studio (klasyczna)

Zunifikowane dane w Dynamics 365 Customer Insights są źródłem budowania modeli uczenia maszynowego, które mogą generować dodatkowe informacje o firmie. Customer Insights integruje się z Machine Learning Studio (klasycznym), aby używać własnych modeli niestandardowych. Aby zobaczyć, jak modele opracowane w Azure Machine Learning są zintegrowane z Customer Insights, zobacz [Eksperymenty usługi Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Wymagania wstępne

- Dostęp do Customer Insights
- Aktywna subskrypcja Azure Enterprise
- [Ujednolicone profile klientów](data-unification.md)
- Konfiguracja [Eksportowanie encji do magazynu obiektów Blob Azure](export-azure-blob-storage.md)

## <a name="set-up-machine-learning-studio-classic"></a>Skonfiguruj usługę Machine Learning Studio Classic

W pierwszym kroku musimy utworzyć obszar roboczy i otworzyć Machine Learning Studio (klasyczne).

1. Przejdź do [https://www.portal.azure.com](https://www.portal.azure.com/) i zaloguj się.

1. Wybierz **Utwórz zasób**.

1. Wyszukaj **Obszar roboczy Machine Learning Studio** i wybierz **Utwórz**.

1. Wprowadź wymagane informacje szczegółowe, aby [utworzyć obszar roboczy](/azure/machine-learning/studio/create-workspace). Wybierz **Warstwa cenowa planu usług sieci Web** na podstawie ilości danych do zaimportowania. W celu zapewnienia optymalnej wydajności należy wybrać **Lokalizację**, która znajduje się najbliżej.

1. Po utworzeniu zasobu zostanie wyświetlony pulpit nawigacyjny Obszar roboczy Machine Learning Studio. Wybierz **Uruchom Machine Learning Studio**.

   ![Interfejs użytkownika Azure Machine Learning Studio.](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>Praca z Azure Machine Learning Studio

Teraz możesz utworzyć nowy eksperyment lub zaimportować istniejący szablon eksperymentu z galerii przykładów. Istnieją przykładowe eksperymenty dla trzech standardowych scenariuszy:

- [Przewidywanie rezygnacji](#churn-analysis)

- [Wartość okresu istnienia klienta](#customer-lifetime-value-prediction)

- [Rekomendacje dotyczące produktu lub następne najlepsze działanie](#productrecommendation-or-next-best-action)

1. W przypadku tworzenia nowego eksperymentu lub korzystania z szablonu eksperymentu z galerii należy skonfigurować właściwości **Importuj dane**. Skorzystaj z przewodnika lub bezpośrednio podaj szczegóły, aby uzyskać dostęp do usługi Azure Blob Storage, która zawiera Twoje dane.  

   ![Eksperyment Azure Machine Learning Studio.](media/azure-machine-learning-studio-experiment.png)

1. Teraz można utworzyć dostosowany potok przetwarzania w celu oczyszczenia i wstępnego przetworzenia danych, wyodrębnienia funkcji i wyuczenia odpowiedniego modelu.

1. Przetestuj i zoptymalizuj wydajność modelu.

1. Jeśli jakość modelu jest zadowalająca, wybierz **Konfigurowanie usługi sieci Web** > **Predykcyjna usługa sieci Web**. Ta opcja powoduje zaimportowanie wyszkolonych modeli i potoku funkcji z eksperymentu szkoleniowego do usługi predykcyjnej. Usługa predykcyjna może wziąć kolejny zestaw danych wejściowych ze schematem użytym w doświadczeniu szkoleniowym w celu sporządzenia przewidywań.

   ![Konfigurowanie predykcyjnej usługi sieci Web.](media/predictive-webservice-control.png)

1. Po pomyślnym wyniku predykcyjnej usługi sieci Web można ją wdrożyć na potrzeby automatycznego planowania. Aby usługa sieci Web działała z Customer Insights, wybierz **Wdróż usługę sieci Web** > **Wdróż usługę sieci Web [Nowa] Wersja zapoznawcza**. [Więcej informacji na temat wdrażania usługi sieci Web](/azure/machine-learning/studio/deploy-a-machine-learning-web-service).

   ![Wdrażania predykcyjnej usługi sieci Web.](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>Przykładowe modele z galerii

Dla modeli w tym artykule użyjemy fikcyjnego scenariusza Contoso Hotel. Contoso Hotel gromadzi następujące dane:

- Dane CRM złożone z działania Pobyty w hotelu. Zestaw danych zawiera informacje o datach pobytu każdego zarejestrowanego klienta. Zawiera także informacje o rezerwacji, typach pokojów, szczegółach wydatków itp. Dane obejmują cztery lata, od stycznia 2014 do stycznia 2018.
- Profile klientów gości hotelu. Te profile zawierają informacje o każdym kliencie, takie jak imię i nazwisko, data urodzenia, adres pocztowy, płeć i numer telefonu.
- Korzystanie z usług oferowanych przez hotel, takich jak spa, pranie, sieć WiFi lub kurier. Te informacje są rejestrowane dla każdego zarejestrowanego klienta. Zazwyczaj korzystanie z usług jest powiązane z pobytem. W niektórych przypadkach z usług mogą korzystać klienci, którzy nie zatrzymali się w hotelu.

## <a name="churn-analysis"></a>Analiza zmian

Analiza zmian jest stosowana do różnych obszarów biznesowych. W tym przykładzie zajmiemy się analizą zmian, szczególnie w kontekście opisanych powyżej usług hotelowych. Zawiera przykład kompleksowego model potoku, który może pełnić rolę punktu wyjścia każdego innego typu modeli zmian.

### <a name="definition-of-churn"></a>Definicja zmian

Definicja zmian może się różnić w zależności od scenariusza. W tym przykładzie gość, który nie odwiedził hotelu w ubiegłym roku powinien zostać oznaczony jako klient, który zrezygnował.  

Szablon eksperymentu może zostać zaimportowany z galerii. W pierwszej kolejności upewnij się, że importujesz dane dotyczące **Działanie Pobyt w hotelu**, **Dane klienta** i **Dane dotyczące użytkowania usługi** z magazynu obiektów Blob Azure.

   ![Importowanie danych dla modelu zmian.](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>Funkcje

W zależności od definicji zmian, w pierwszej kolejności identyfikujemy surowe funkcje, które będą miały wpływ na etykietę. Następnie przetwarzamy te surowe funkcje na funkcje liczbowe, które mogą być używane z modelami Uczenie maszynowe. Integracja danych jest wykonywana w programie Customer Insights, dzięki czemu można przyłączyć się do tych tabel przy użyciu *Identyfikatora klienta*.

   ![Dołącz zaimportowane dane.](media/join-imported-data.png)

Zapewnienie funkcji dla konstruowania modelu dla analizy zmian może być nieco trudne. Dane są funkcją czasu z nowym działaniem hotelu odnotowywanym codziennie. Podczas zapewniania funkcji chcemy wygenerować statyczne funkcje z danych dynamicznych. W tym przypadku generujemy wiele funkcji z działania w hotelu z oknem przesuwanym obejmującym jeden rok. Ponadto rozwijamy funkcje kategorii, takie jak typ pokoju lub typ rezerwacji, na różne funkcje, korzystając z kodowania jednokrotnego.  

Ostateczna lista funkcji:

| **Numer**  | **Original_Column**          | **Funkcje pochodne**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | Typ pokoju                    | RoomTypeLargeCount, RoomTypeSmallCount                                                                                                    |
| 2           | Typ rezerwacji                 | BookingTypeOnlineCount, BookingTypePhoneCallCount                                                                                         |
| 3           | Kategoria podróży              | TravelCategoryBusinessCount, TravelCategoryLeisureCount                                                                                   |
| 100           | Wydana kwota w dolarach                | TotalDollarSpent                                                                                                                          |
| 5           | Data zameldowania się i Wymeldowanie  | StayDayCount, StayDayCount2016, StayDayCount2015, StayDayCount2014, StayCount, StayCount2016. StayCount2015, StayCount2014                |
| 6           | Wykorzystanie usług                | UsageTenure, ConciergeUsage, CourierUsage, DryCleaningUsage, GymUsage, PhoneUsage, RestaurantUsage, SpaUsage, TelevisionUsage, WifiUsage  |

### <a name="model-selection"></a>Wybór modelu

Teraz musimy wybrać optymalny algorytm. W tym przypadku większość funkcji opiera się na funkcjach będących kategoriami. Zazwyczaj sprawdzają się modele bazujące na drzewie decyzji. Jeśli są dostępne tylko funkcje liczbowe, sieć neuronowa może być lepszą opcją. Wektorowa maszyna pomocnicza (SVM) również jest dobrym kandydatem w takich sytuacjach; w celu wyodrębnienia najlepszej wydajności konieczne jest jednak przeprowadzenie dostosowania. Wybieramy **Dwuklasowe drzewo decyzji** jako pierwszy model, a **Dwuklasowy model SVM** jako drugi. Usługa Azure Machine Learning Studio umożliwia testowanie A/B, więc korzystniej jest zacząć od dwóch modeli, a nie jednego.

Na następującym rysunku przedstawiono model szkoleń i potok oceny z Azure Machine Learning Studio:

![Model zmian w Azure Machine Learning Studio.](media/azure-machine-learning-model.png)

Stosujemy również technikę o nazwie **Ważność funkcji Permutacja**, ważny aspekt optymalizacyjny modelu. Wbudowane modele mają znikomy wgląd we wpływ konkretnej funkcji na końcowe przewidywanie. Kalkulator ważności funkcji używa niestandardowego algorytmu w celu obliczenia wpływu poszczególnych funkcji na wyniki dla określonego modelu. Ważność funkcji jest znormalizowana w zakresie od +1 do -1. Negatywny wpływ oznacza, że odpowiednia funkcja ma szkodliwy wpływ na wyniki i powinna zostać usunięta z modelu. Dodatni wpływ oznacza, że funkcja jest znacząco przyczynia się do przewidywania. Te wartości nie są współczynnikami korelacji, ponieważ są różnymi metrykami. Aby uzyskać więcej informacji, zobacz [Ważność funkcji Permutacja](/azure/machine-learning/studio-module-reference/permutation-feature-importance).

Cały [eksperyment zmian jest dostępny w Galeria sztucznej inteligencji platformy Azure](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp).

## <a name="customer-lifetime-value-prediction"></a>Przewidywanie Wartość okresu istnienia klienta

Obliczanie wartości okresu istnienia klienta (CLTV) jest jedną z kluczowych metryk, które mogą być używane w działalności biznesowej do oceny i segmentacji klientów. W przypadku działalności hotelowej znajomość klientów jest kwestią kluczową. Na przykład zrozumienie czynników, które tworzą dobrych klientów, to podstawowe informacje. Pomaga to kierownictwu hotelu ocenić, na jakich funkcjach należy się skupić, aby je usprawnić, a przez to zaspokoić najlepszych klientów. Te decyzje mogą mieć bezpośredni wpływ na sprzedaż i zarobki.  

### <a name="definition-of-cltv"></a>Definicja CLTV

W tym przykładzie definiujemy CLTV klienta jako łączną kwotę w dolarach, jaką klient ma wydać w ciągu następnych 365 dni. W celu przewidzenia tej wartości użyjemy danych dla wszystkich klientów z ostatnich trzech lat.

### <a name="featurization"></a>Funkcje

W tym przypadku zapewnianie funkcji będzie znacznie przypominać scenariusz zmian. Etykiety i przewidywane wartości są jednak inne niż określone powyżej.

### <a name="model-selection"></a>Wybór modelu

Przewidywanie CLTV to problem regresji, ponieważ przewidywana wartość jest zmienną ciągłą o wartości dodatniej. W zależności od właściwości funkcji wybieramy **Regresję drzewa decyzji** jako jeden algorytm i **Regresję sieci neuronowej** jako kolejny algorytm szkolenia modelu.

## <a name="product-recommendation-or-next-best-action"></a>Rekomendacje dotyczące produktu lub Następne najlepsze działanie

Zalecenie dotyczące produktu w scenariuszu hotelu jest interpretowane jako rekomendowanie usług oferowanych klientom w hotelu. Zamierzeniem jest wybranie odpowiednich usług dla klientów, aby ich użycie zostało zmaksymalizowane. Jest to podobne do rekomendacji filmów dla usługi strumieniowego przesyłania wideo.

### <a name="definition-of-product-recommendation-or-next-best-action"></a>Definicja rekomendacji produktu lub Następne najlepsze działanie

Cel jest definiowany jako maksymalizacja kwoty w dolarach za skorzystanie z usług dzięki najlepszemu dopasowaniu usług do klientów hotelu, w zależności od ich zainteresowań.

### <a name="featurization"></a>Funkcje

Podobnie jak w przypadku modelu zmiany, dołączamy ServiceCustomerID hotelu z CustomerID, aby zbudować rekomendacje w sposób konsekwentny dla CustomerID.

![Funkcje modelu rekomendacji.](media/azure-machine-learning-model-featurization.png)

Dane pochodzą z trzech różnych encji a funkcje się od nich wywodzą. Zapewnienie funkcji dla problemu rekomendacji jest inne niż scenariusze zmian lub CLTV. Model rekomendacji wymaga danych wejściowych w formie trzech zestawów funkcji.

### <a name="model-selection"></a>Wybór modelu

Przewidujemy produkty lub usługi, korzystając z algorytmu o nazwie **Trenowanie modułu rekomendowania Matchbox**, aby przeszkolić model rekomendacji.

![Algorytm rekomendacji produktów.](media/azure-machine-learning-model-recommendation-algorithm.png)

Trzy porty wejściowe dotyczące modelu **Trenowanie modułu rekomendowania Matchbox** bierze dane dotyczące użytkowania usługi szkoleń, opis klienta (opcjonalnie) i opis usługi. Istnieją trzy różne sposoby oceniania modelu. Jeden jest dla oceny modelu, gdzie wynik Znormalizowany skumulowany zysk rabatowy (NDCG) jest obliczany w celu nadania rangi ocenionym elementom. W tym doświadczeniu wynik NDCG wynosi 0,97. Pozostałe dwie opcje to ocenianie modelu ba całym zalecanym katalogu usług lub ocenianie tylko na podstawie elementów, z których użytkownicy nie korzystali wcześniej.

Przyglądając się bliżej dystrybucji rekomendacji w odniesieniu do całego katalogu usług zauważyliśmy, że telefon, Sieć Wi-Fi i kurier są najpopularniejszymi usługami, jakie można zarekomendować. Jest to zgodne z tym, czego dowiedzieliśmy się z rozkładu danych korzystania z usług:

![Wynik modelu rekomendacji.](media/azure-machine-learning-model-output.png)

Cały [eksperyment rekomendacji produktów można zobaczyć w Galerii sztucznej inteligencji platformy Azure.](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>Modele niestandardowe integracji

Aby wykorzystać te przewidywania w Customer Insights, należy **wyeksportować** przewidywania wraz z identyfikatorami klientów. [Wyeksportuj je w tej samej lokalizacji magazynu obiektów Azure Blob](/azure/storage/common/storage-import-export-data-from-blobs), w której są eksportowane dane źródłowe. Przewidywana usługa sieci Web może być zaplanowana do regularnego uruchamiana i aktualizowania wyników.

Dane generowane w ramach modelu niestandardowego mogą zostać użyte do dalszego wzbogacenia danych klientów. Aby uzyskać więcej informacji, zobacz [Niestandardowe modele uczenia maszynowego](custom-models.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]