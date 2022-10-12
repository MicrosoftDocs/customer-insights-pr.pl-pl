---
title: Przykładowy przewodnik dotyczący prognozowania rezygnacji z subskrypcji
description: Skorzystaj z tego przykładowego przewodnika, aby wypróbować gotowy model prognozowania rezygnacji z subskrypcji.
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610019"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Przykładowy przewodnik dotyczący prognozowania rezygnacji z subskrypcji

Ten przewodnik przeprowadza po przewidywaniu rezygnacji z subskrypcji, korzystając z przykładowych danych. Zaleca się, aby wypróbować to przewidywanie [w nowym środowisku](manage-environments.md).

## <a name="scenario"></a>Scenariusz

Contoso to firma produkująca wysokiej jakości maszyny do barów kawowych. Produkty są dostępne w witrynie firmy Contoso Coffee. Ostatnio rozpoczęły działalność subskrypcyjną, aby klienci regularnie otrzymywali kawę. Ich celem jest zrozumienie, którzy subskrybenci mogą anulować subskrypcję w ciągu najbliższych kilku miesięcy. Wiedza o tym, który z ich klientów **prawdopodobnie odejdzie**, może pomóc im zaoszczędzić wysiłki marketingowe, koncentrując się na ich utrzymaniu.

## <a name="prerequisites"></a>Wymagania wstępne

- Co najmniej [Uprawnienia współautora](permissions.md) w Customer Insights.

## <a name="task-1---ingest-data"></a>Zadanie 1 - pozyskiwanie danych

Przejrzyj artykuły [dotyczące pozyskiwania danych](data-sources.md) i [łączenie ze źródłem danych Power Query](connect-power-query.md). Poniższe informacje zakładają, że znasz ogólne zasady przetwarzania danych.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Pozyskiwanie danych klienta na platformie eCommerce

1. Utwórz źródło danych Power Query o nazwie **Handel elektroniczny**, wybierz opcję importowania i wybierz łącznik typu **tekst/CSV**.

1. Wprowadź adres URL eCommerce kontaktów https://aka.ms/ciadclasscontacts.

1. Podczas edytowania danych wybierz opcję **Przekształć**, a następnie **Użyj pierwszego wiersza jako nagłówków**.

1. Zaktualizuj typ danych dla kolumn wymienionych poniżej:
   - **DateOfBirth**: Data
   - **CreatedOn**: Data/Czas/Strefa

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Przekształcić datę urodzenia na datę.":::

1. WW polu **Nazwa** w panelu po prawej stronie zmień nazwę źródła danych **eCommerceContacts**

1. Zapisz źródło danych.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Przetwarzaj dane klientów ze schematu lojalnościowego

1. Utwórz źródło danych o nazwie **LoyaltyScheme** i wybierz łącznik typu **tekst/CSV**.

1. Wprowadź adres URL klientów lojalnościowych https://aka.ms/ciadclasscustomerloyalty.

1. Podczas edytowania danych wybierz opcję **Przekształć**, a następnie **Użyj pierwszego wiersza jako nagłówków**.

1. Zaktualizuj typ danych dla kolumn wymienionych poniżej:
   - **DateOfBirth**: Data
   - **RewardsPoints**: Pełny numer
   - **CreatedOn**: Data/godzina

1. WW polu **Nazwa** w panelu po prawej stronie zmień nazwę źródła danych na **loyCustomers**.

1. Zapisz źródło danych.

### <a name="ingest-subscription-information"></a>Przetwarzaj informacje o subskrypcji

1. Utwórz źródło danych o nazwie **SubscriptionHistory** i wybierz łącznik typu **tekst/CSV**.

1. Wprowadź adres URL dla subskrypcji https://aka.ms/ciadchurnsubscriptionhistory.

1. Podczas edytowania danych wybierz opcję **Przekształć**, a następnie **Użyj pierwszego wiersza jako nagłówków**.

1. Zaktualizuj typ danych dla kolumn wymienionych poniżej:
   - **SubscriptioID**: Pełny numer
   - **SubscriptionAmount**: waluta
   - **SubscriptionEndDate**: Data/godzina
   - **SubscriptionStartDate**: Data/godzina
   - **TransactionDate**: Data/godzina
   - **IsRecurring**: Prawda/Fałsz
   - **Is_auto_renew**: Prawda/fałsz
   - **RecurringFrequencyInMonths**: pełny numer

1. W polu **Nazwa** w prawym panelu zmień nazwę źródła danych z Zapytanie na **SubscriptionHistory**.

1. Zapisz źródło danych.

### <a name="ingest-customer-data-from-website-reviews"></a>Przetwarzaj dane klientów z recenzji witryn

1. Utwórz źródło danych o nazwie **Strona internetowa** i wybierz łącznik typu **tekst/CSV**.

1. Wprowadź adres URL dla opinii w witrynie internetowej https://aka.ms/ciadclasswebsite.

1. Podczas edytowania danych wybierz opcję **Przekształć**, a następnie **Użyj pierwszego wiersza jako nagłówków**.

1. Zaktualizuj typ danych dla kolumn wymienionych poniżej:
   - **ReviewRating**: Pełny numer
   - **ReviewDate**: Data

1. W polu **Nazwa** w prawym panelu zmień nazwę źródła danych z Zapytanie na **webReviews**.

## <a name="task-2---data-unification"></a>Zadanie 2 - ujednolicenie danych

Przegląd artykułu [o ujednolicaniu danych](data-unification.md). Poniższe informacje zakładają, że znasz ogólne zasady ujednolicania danych.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Zadanie 3 — utwórz działanie historii transakcji

Przejrzyj artykuł [o działaniach dotyczących klienta](activities.md). Poniższe informacje zakładają, że znasz ogólne zasady tworzenia działań.

1. Utwórz działanie o nazwie **SubscriptionHistory** z encją *Subskrypcja* i jej kluczem podstawowym **CustomerId**.

1. Utwórz relację między elementami *SubscriptionHistory:Subscription* i *eCommerceContacts:eCommerce* z elementem **CustomerID** jako kluczem obcym, który ma połączyć te dwie encje.

1. Wybierz **SubscriptionType** dla **EventActivity** i **SubscriptionEndDate** dla **TimeStamp**.

1. Wybierz opcję **Subskrypcja** dla **Typu działania** i semantycznie przemapuj dane działań.

1. Uruchom działanie.

1. Dodaj inne działanie klienta i zamapuj jego nazwy pól na odpowiednie pola:
   - Jednostka aktywności klienta: Recenzje:Strona internetowa
   - Klucz podstawowy: Website.Reviews.ReviewId
   - Timestamp: Website.Reviews.ReviewDate
   - Zdarzenie (nazwa działania): Website.Reviews.ActivityTypeDisplay
   - Szczegóły (kwota lub wartość): Website.Reviews.ReviewRating

1. Uruchom działanie.

## <a name="task-4---configure-the-subscription-churn-prediction"></a>Zadanie 4 - Skonfiguruj przewidywanie rezygnacji z subskrypcji

Dzięki ujednoliconym profilom klienta i utworzonemu działaniu można teraz uruchomić przewidywanie subskrypcji. Aby uzyskać szczegółowe informacje o krokach, zobacz [Przewidywanie rezygnacji z subskrypcji](predict-subscription-churn.md).

1. Przejdź do opcji **Analizy** > **Przewidywania**.

1. Na karcie **Utwórz** wybierz **Model użycia** na kafelku **Model rezygnacji klienta**.

1. Wybierz opcję **Subskrypcja** dla typu rozsyłania, a następnie wybierz opcję **Rozpocznij**.

1. Nazwij model **Przewidywanie rezygnacji z subskrypcji OOB**, a następnie encję wyjściową **OOBSubscriptionChurnPrediction**.

1. Zdefiniuj preferencje modelu:
   - **Dni od zakończenia subskrypcji**: **60** dni oznacza, że klient jest uważany za utraconego, jeśli nie odnowi subskrypcji w tym okresie po zakończeniu subskrypcji.
   - **Dni do zbadania przyszłej przyszłości**: **93** dni, czyli czas trwania, dla którego model przewiduje, którzy klienci mogą zrezygnować. Im dalej w przyszłości spojrzysz, tym mniej dokładne wyniki.

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="Wybierz preferencje modelu i definicję rezygnacji.":::

1. Wybierz **Dalej**.

1. W kroku **Wymagane dane** wybierz opcję **Dodaj dane**, aby udostępnić historię subskrypcji.

1. Wybierz obiekt **Subskrypcja** i encję SubscriptionHistory i wybierz opcję **Dalej**. Wymagane dane są automatycznie wypełniane z działania. Wybierz pozycję **Zapisz**.

1. W działaniach klienta wybierz **Dodaj dane**.

1. W tym przykładzie dodaj działanie przeglądu sieci Web.

1. Wybierz **Dalej**.

1. W kroku **Aktualizacje danych** ustaw **Miesięcznie** dla harmonogram modelu.

1. Po przejrzeniu wszystkich szczegółów wybierz pozycję **Zapisz i uruchom**.

## <a name="task-5---review-model-results-and-explanations"></a>Zadanie 5 - Przejrzyj wyniki i wyjaśnienia modelu

Pozwól modelowi ukończyć uczenie i ocenianie danych. Przejrzyj wyjaśnienia dotyczące modeli rezygnacji z subskrypcji. Aby uzyskać więcej informacji, zobacz [Wyświetl wyniki przewidywania](predict-subscription-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Zadanie 6 - Utwórz segment klientów o wysokim ryzyku rezygnacji

Uruchomienie modelu powoduje utworzenie nowej encji wymienionej w **Dane** > **Encje**. Możesz utworzyć nowy segment na podstawie encji utworzonej przez model.

1. Na stronie wyników wybierz opcję **Utwórz segment**.

1. Utwórz regułę, używając encji **OOBSubscriptionChurnPrediction** i zdefiniuj segment:
   - **Pole**: ChurnScore
   - **Operator**: większy niż
   - **Wartość**: 0,6

1. Wybierz opcję **Zapisz** i **Uruchom** segment.

Masz teraz dynamicznie aktualizowany segment, który identyfikuje klientów o wysokim ryzyku rezygnacji z subskrypcji. Aby uzyskać więcej informacji, zobacz [Tworzenie segmentów i zarządzanie nimi](segments.md).

> [!TIP]
> Na stronie **Segmenty** można także utworzyć segment dla modelu przewidywania modelu, wybierając opcję **Nowy** i wybierając opcję **Utwórz z** >  **Analizy**. Aby uzyskać więcej informacji, zobacz [Tworzenie nowego segmentu za pomocą szybkich segmentów](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
