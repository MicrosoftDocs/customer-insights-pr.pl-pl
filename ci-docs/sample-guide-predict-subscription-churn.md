---
title: Przykładowy przewodnik dotyczący prognozowania rezygnacji z subskrypcji
description: Skorzystaj z tego przykładowego przewodnika, aby wypróbować gotowy model prognozowania rezygnacji z subskrypcji.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 5a8eeafecacef3d0bb4a798b698cf490423ca98d
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741424"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Przykładowy przewodnik dotyczący prognozowania rezygnacji z subskrypcji

Przeprowadzimy Cię przez cały przewodnik przewidywania rezygnacji z subskrypcji, korzystając z przykładowych danych podanych poniżej. 

## <a name="scenario"></a>Scenariusz

Contoso to firma produkująca wysokiej jakości ekspresy do kawy i ekspresy do kawy, które sprzedają za pośrednictwem swojej witryny internetowej Contoso Coffee. Ostatnio rozpoczęły działalność subskrypcyjną, aby klienci regularnie otrzymywali kawę. Ich celem jest zrozumienie, którzy subskrybenci mogą anulować subskrypcję w ciągu najbliższych kilku miesięcy. Wiedza o tym, który z ich klientów **prawdopodobnie odejdzie**, może pomóc im zaoszczędzić wysiłki marketingowe, koncentrując się na ich utrzymaniu.

## <a name="prerequisites"></a>Wymagania wstępne

- Co najmniej [Uprawnienia współautora](permissions.md) w Customer Insights.
- Zaleca się, aby zaimplementować poniższe kroki [w nowym środowisku](manage-environments.md).

## <a name="task-1---ingest-data"></a>Zadanie 1 - pozyskiwanie danych

Przejrzyj w szczególności artykuły [dotyczące pozyskiwania danych](data-sources.md) i [importowania źródeł danych za pomocą łączników usługi Power Query](connect-power-query.md). Poniższe informacje zakładają, że znasz ogólne zasady przetwarzania danych. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Pozyskiwanie danych klienta na platformie eCommerce

1. Utwórz źródło danych o nazwie **eCommerce**, wybierz opcję importowania i wybierz łącznik typu **tekst/CSV**.

1. Wprowadź adres URL eCommerce kontaktów https://aka.ms/ciadclasscontacts.

1. Podczas edytowania danych wybierz opcję **Przekształć** i **Użyj pierwszego wiersza jako nagłówków**.

1. Zaktualizuj typ danych dla kolumn wymienionych poniżej:

   - **DateOfBirth**: Data
   - **CreatedOn**: Data/Czas/Strefa

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Przekształcić datę urodzenia na datę.":::

1. W polu **Nazwa** w panelu po prawej stronie zmień nazwę źródła danych z **Query** na **eCommerceContacts**

1. Zapisz źródło danych.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Przetwarzaj dane klientów ze schematu lojalnościowego

1. Utwórz źródło danych o nazwie **LoyaltyScheme**, wybierz opcję importowania i wybierz łącznik typu **tekst/CSV**.

1. Wprowadź adres URL eCommerce kontaktów https://aka.ms/ciadclasscustomerloyalty.

1. Podczas edytowania danych wybierz opcję **Przekształć** i **Użyj pierwszego wiersza jako nagłówków**.

1. Zaktualizuj typ danych dla kolumn wymienionych poniżej:

   - **DateOfBirth**: Data
   - **RewardsPoints**: Pełny numer
   - **CreatedOn**: Data/godzina

1. W polu **Nazwa** w panelu po prawej stronie zmień nazwę źródła danych z **Query** na **loyCustomers**.

1. Zapisz źródło danych.

### <a name="ingest-subscription-information"></a>Przetwarzaj informacje o subskrypcji

1. Utwórz źródło danych o nazwie **SubscriptionHistory**, wybierz opcję importowania i wybierz łącznik typu **tekst/CSV**.

1. Wprowadź adres URL eCommerce kontaktów https://aka.ms/ciadchurnsubscriptionhistory.

1. Podczas edytowania danych wybierz opcję **Przekształć** i **Użyj pierwszego wiersza jako nagłówków**.

1. Zaktualizuj typ danych dla kolumn wymienionych poniżej:

   - **SubscriptioID**: Pełny numer
   - **SubscriptionAmount**: waluta
   - **SubscriptionEndDate**: Data/godzina
   - **SubscriptionStartDate**: Data/godzina
   - **TransactionDate**: Data/godzina
   - **IsRecurring**: Prawda/Fałsz
   - **Is_auto_renew**: Prawda/fałsz
   - **RecurringFrequencyInMonths**: pełny numer

1. W polu **Nazwa** w panelu po prawej stronie zmień nazwę źródła danych z **Zapytanie** na **SubscriptionHistory**.

1. Zapisz źródło danych.

### <a name="ingest-customer-data-from-website-reviews"></a>Przetwarzaj dane klientów z recenzji witryn

1. Utwórz źródło danych o nazwie **Strona internetowa**, wybierz opcję importowania i wybierz łącznik typu **tekst/CSV**.

1. Wprowadź adres URL eCommerce kontaktów https://aka.ms/ciadclasswebsite.

1. Podczas edytowania danych wybierz opcję **Przekształć** i **Użyj pierwszego wiersza jako nagłówków**.

1. Zaktualizuj typ danych dla kolumn wymienionych poniżej:

   - **ReviewRating**: Pełny numer
   - **ReviewDate**: Data

1. WW polu „Nazwa” w panelu po prawej stronie zmień nazwę źródła danych z **Query** na **webReviews**.

## <a name="task-2---data-unification"></a>Zadanie 2 - ujednolicenie danych

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-the-subscription-churn-prediction"></a>Zadanie 3 - Skonfiguruj przewidywanie rezygnacji z subskrypcji

Dzięki ujednoliconym profilom klienta można teraz uruchomić przewidywanie subskrypcji. Aby uzyskać szczegółowe informacje o krokach, zobacz artykuł [Przewidywanie rezygnacji z subskrypcji](predict-subscription-churn.md). 

1. Wybierz **Analizy** > **Wykryj** i wybierz korzystanie z **Model rezygnacji klientów**.

1. Wybierz opcję **Subskrypcja** i wybierz pozycję **Rozpocznij pracę**.

1. Nazwij model **Przewidywanie rezygnacji z subskrypcji OOB**, a następnie encję wyjściową **OOBSubscriptionChurnPrediction**.

1. Zdefiniować dwa warunki dotyczące modelu rezygnacji:

   * **Liczba dni od zakończenia subskrypcji**: **co najmniej 60** dni. Jeśli klient nie odnowi subskrypcji w tym okresie po zakończeniu subskrypcji, zostanie uznany za rezygnującego. 

   * **Definicja rezygnacji**: **co najmniej 93** dni. Czas trwania modelu przewidywania, którzy klienci mogą odejść. Im dalej w przyszłości spojrzysz, tym mniej dokładne wyniki.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Wybierz dźwignie modelu Okno predykcji i Definicja rezygnacji.":::

1. Wybierz **Dodaj wymagane dane** i wybierz pozycję **Dodaj dane** dla historii subskrypcji.

1. Dodaj encję **Subskrypcja : SubscriptionHistory** i zamapuj pola z eCommerce na odpowiadające im pola wymagane przez model.

1. Połącz encję **Subskrypcja : SubscriptionHistory** z encją **eCommerceContacts: eCommerce**, nazwij relację **eCommerceSubscription**.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Dołączanie encji eCommerce.":::

1. W obszarze Działania klienta dodaj encję **webReviews: Website** i zamapuj pola z webReviews na odpowiednie pola wymagane przez model. 
   - Klucz podstawowy: ReviewId
   - Znacznik czasu: ReviewDate
   - Zdarzenie: ReviewRating

1. Skonfiguruj działanie dotyczące recenzji witryn. Wybierz **Przegląd** działań i dołącz do encji **webReviews : Website** z **eCommerceContacts: eCommerce**.

1. Wybierz przycisk **Dalej**, aby ustawić harmonogram modelu.

   Model musi regularnie trenować, aby uczyć się nowych wzorców, gdy są pozyskiwane nowe dane. Na potrzeby tego przykładu wybierz pozycję **Miesięczny**.

1. Po przejrzeniu wszystkich szczegółów wybierz pozycję **Zapisz i uruchom**.

## <a name="task-4---review-model-results-and-explanations"></a>Zadanie 4 - Przejrzyj wyniki i wyjaśnienia modelu

Pozwól modelowi ukończyć uczenie i ocenianie danych. Możesz teraz przejrzeć wyjaśnienia dotyczące modelu rezygnacji z subskrypcji. Aby uzyskać więcej informacji, zobacz temat [Przejrzyj stan i wyniki prognozy](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Zadanie 5 - Utwórz segment klientów o wysokim ryzyku rezygnacji

Uruchomienie modelu produkcyjnego tworzy nową jednostkę, którą możesz zobaczyć **Dane** > **Encje**.   

Możesz utworzyć nowy segment na podstawie encji utworzonej przez model.

1.  Przejdź do **Segmenty**. Wybierz opcję **Nowy** i wybierz pozycję **Utwórz z poziomu** > **Analizy**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Tworzenie segmentu z wynikiem modelu.":::

1. Wybierz opcję **OOBSubscriptionChurnPrediction** punkt końcowy i zdefiniuj segment: 
   - Pole: ChurnScore
   - Operator: większy niż
   - Wartość: 0.6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Skonfiguruj segment rezygnacji z subskrypcji.":::

Masz teraz dynamicznie aktualizowany segment, który identyfikuje klientów o wysokim ryzyku rezygnacji z subskrypcji.

Aby uzyskać więcej informacji, zobacz [Tworzenie segmentów i zarządzanie nimi](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]