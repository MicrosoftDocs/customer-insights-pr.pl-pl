---
title: Przykładowy przewodnik po prognozowaniu wartości całego cyklu życia klienta (CLV)
description: Skorzystaj z tego przykładowego przewodnika, aby wypróbować model predykcji customer lifetime value.
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609651"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Przykładowy przewodnik po prognozowaniu wartości całego cyklu życia klienta (CLV)

Ten przewodnik przedstawia cały przykład przewidywania okresu istnienia klienta (CLV) w Customer Insights na podstawie przykładowych danych. Zaleca się, aby wypróbować to przewidywanie [w nowym środowisku](manage-environments.md).

## <a name="scenario"></a>Scenariusz

Contoso to firma produkująca wysokiej jakości maszyny do barów kawowych. Produkty są dostępne w witrynie firmy Contoso Coffee. Firma chce zrozumieć wartość (przychód), jaką jej klienci mogą wygenerować w ciągu najbliższych 12 miesięcy. Znajomość oczekiwanej wartości klientów w ciągu najbliższych 12 miesięcy pomoże im ukierunkować działania marketingowe na klientów o wysokiej wartości.

## <a name="prerequisites"></a>Wymagania wstępne

- Co najmniej [uprawnienia współautora](permissions.md).

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

1. **Zapisz** źródło danych.

### <a name="ingest-online-purchase-data"></a>Przetwarzaj dane zakupów online

1. Dodanie nowego zestawu danych do tego samego źródła danych **eCommerce**. Wybierz ponownie łącznik **tekst/CSV**.

1. Wprowadź adres URL danych **Zakupów w trybie online** https://aka.ms/ciadclassonline.

1. Podczas edytowania danych wybierz opcję **Przekształć**, a następnie **Użyj pierwszego wiersza jako nagłówków**.

1. Zaktualizuj typ danych dla kolumn wymienionych poniżej:
   - **PurchasedOn**: Data/godzina
   - **TotalPrice**: waluta

1. W polu **Nazwa** w panelu w okienku bocznym zmień nazwę źródła danych z Query na **eCommercePurchases**.

1. **Zapisz** źródło danych.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Przetwarzaj dane klientów ze schematu lojalnościowego

1. Utwórz źródło danych o nazwie **LoyaltyScheme** i wybierz łącznik typu **tekst/CSV**.

1. Wprowadź adres URL klientów lojalnościowych https://aka.ms/ciadclasscustomerloyalty.

1. Podczas edytowania danych wybierz opcję **Przekształć**, a następnie **Użyj pierwszego wiersza jako nagłówków**.

1. Zaktualizuj typ danych dla kolumn wymienionych poniżej:
   - **DateOfBirth**: Data
   - **RewardsPoints**: Pełny numer
   - **CreatedOn**: Data/godzina

1. WW polu **Nazwa** w panelu po prawej stronie zmień nazwę źródła danych na **loyCustomers**.

1. **Zapisz** źródło danych.

### <a name="ingest-customer-data-from-website-reviews"></a>Przetwarzaj dane klientów z recenzji witryn

1. Utwórz źródło danych o nazwie **Strona internetowa** i wybierz łącznik typu **tekst/CSV**.

1. Wprowadź adres URL dla opinii w witrynie internetowej https://aka.ms/CI-ILT/WebReviews.

1. Podczas edytowania danych wybierz opcję **Przekształć**, a następnie **Użyj pierwszego wiersza jako nagłówków**.

1. Zaktualizuj typ danych dla kolumn wymienionych poniżej:
   - **ReviewRating**: Liczba dziesiętna
   - **ReviewDate**: Data

1. W polu **Nazwa** w prawym panelu zmień nazwę źródła danych z Zapytanie na **Oceny**.

1. **Zapisz** źródło danych.

## <a name="task-2---data-unification"></a>Zadanie 2 - ujednolicenie danych

Przegląd artykułu [o ujednolicaniu danych](data-unification.md). Poniższe informacje zakładają, że znasz ogólne zasady ujednolicania danych.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Zadanie 3 — utwórz działanie historii transakcji

Przejrzyj artykuł [o działaniach dotyczących klienta](activities.md). Poniższe informacje zakładają, że znasz ogólne zasady tworzenia działań.

1. Utwórz działanie o nazwie **eCommercePurchases** z encją *eCommercePurchases:eCommerce* i jej kluczem podstawowym **PurchaseId**.

1. Utwórz relację między elementami *eCommercePurchases:eCommerce* i *eCommerceContacts:eCommerce* z elementem **ContactID** jako kluczem obcym, który ma połączyć te dwie encje.

1. Wybierz **TotalPrice** dla **EventActivity** i **PurchasedOn** dla **TimeStamp**.

1. Wybierz opcję **SalesOrderLine** dla **Typu działania** i semantycznie przemapuj dane działań.

1. Uruchom działanie.

1. Dodaj inne działanie klienta i zamapuj jego nazwy pól na odpowiednie pola:
   - **Jednostka aktywności**: Reviews:Website
   - **Klucz podstawowy**: ReviewId
   - **Sygnatura czasowa**: ReviewDate
   - **Działanie zdarzenia**: ActivityTypeDisplay
   - **Więcej informacji**: ReviewRating
   - **Typ działań**: ocena

1. Uruchom działanie.

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>Zadanie 4 — Skonfiguruj prognozę długookresowej wartości klienta

Dzięki ujednoliconym profilom klientów i utworzonemu działaniu możemy teraz uruchomić przewidywanie wartości życia klienta (CLV). Aby wyświetlić szczegółowe kroki, zobacz temat [Przewidywanie wartości okresu istnienia klienta](predict-customer-lifetime-value.md).

1. Przejdź do opcji **Analizy** > **Przewidywania**.

1. Na karcie **Utwórz** wybierz **Model użycia** na kafelku **Wartość istnienia klienta**.

1. Wybierz **Rozpocznij**.

1. Nazwij model **Przewidywanie OOB eCommerce CLV** i jednostkę wyjściową  **OOBeCommerceCLVPrediction**.

1. Zdefiniuj preferencje modelu:
   - **Okres przewidywania**: **12 miesięcy lub 1 rok**, aby określić, jak daleko w przyszłości przewidzieć CLV.
   - **Aktywni klienci**: **Zezwól modelowi na obliczenie interwału zakupów**, który jest przedziałem czasu, w którym klient musiał mieć co najmniej jedną transakcję, aby zostać uznanym za aktywną.
   - **Klient o wysokiej wartości**: ręcznie zdefiniuj klientów o wysokiej wartości jako **najlepsze 30% aktywnych klientów**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Krok preferencji w doświadczeniu z przewodnikiem dla modelu CLV.":::

1. Wybierz **Dalej**.

1. W kroku **Wymagane dane** wybierz opcję **Dodaj dane**, aby udostępnić dane historii transakcji.

    :::image type="content" source="media/clv-model-required.png" alt-text="Dodaj wymagany krok danych w doświadczeniu z przewodnikiem dla modelu CLV.":::

1. Wybierz obiekt **SalesOrderLine** i encję eCommercePurchases i wybierz opcję **Dalej**. Wymagane dane są automatycznie wypełniane z działania. Wybierz **Zapisz**, a następnie **Dalej**.

1. Krok **Dodatkowe dane (opcjonalnie)** umożliwia dodanie większej liczby danych dotyczących działań klienta, by uzyskać więcej szczegółowych danych dla interakcji z klientem. W tym przykładzie wybierz opcję **Dodaj dane** i dodaj działanie przeglądu sieci Web.

1. Wybierz **Dalej**.

1. W kroku **Aktualizacje danych** ustaw **Miesięcznie** dla harmonogram modelu.

1. Wybierz **Dalej**.

1. Po przejrzeniu wszystkich szczegółów wybierz pozycję **Zapisz i uruchom**.

## <a name="task-5---review-model-results-and-explanations"></a>Zadanie 5 - Przejrzyj wyniki i wyjaśnienia modelu

Pozwól modelowi ukończyć uczenie i ocenianie danych. Przejrzyj [wyniki i objaśnienia modelu CLV](predict-customer-lifetime-value.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-value-customers"></a>Zadanie 6 — Tworzenie segmentu klientów o wysokiej wartości

Uruchomienie modelu powoduje utworzenie nowej encji wymienionej w **Dane** > **Encje**. Możesz utworzyć nowy segment klientów na podstawie jednostki utworzonej przez model.

1. Na stronie wyników wybierz opcję **Utwórz segment**.

1. Utwórz regułę, używając encji **OOBeCommerceCLVPrediction** i zdefiniuj segment:
   - **Pole**: CLVScore
   - **Operator**: większy niż
   - **Wartość**: 1500

1. Wybierz opcję **Zapisz** i **Uruchom** segment.

Masz teraz segment, który identyfikuje klientów, którzy według przewidywań wygenerują ponad 1500 USD przychodu w ciągu najbliższych 12 miesięcy. Ten segment jest aktualizowany dynamicznie, jeśli pozyskuje się więcej danych. Aby uzyskać więcej informacji, zobacz [Tworzenie segmentów i zarządzanie nimi](segments.md).

> [!TIP]
> Na stronie **Segmenty** można także utworzyć segment dla modelu przewidywania modelu, wybierając opcję **Nowy** i wybierając opcję **Utwórz z** >  **Analizy**. Aby uzyskać więcej informacji, zobacz [Tworzenie nowego segmentu za pomocą szybkich segmentów](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
