---
title: Przykładowy przewodnik po prognozowaniu wartości całego cyklu życia klienta (CLV)
description: Skorzystaj z tego przykładowego przewodnika, aby wypróbować model predykcji customer lifetime value.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 2013533ed225a396d21e51e63297d7608ce58ac6
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051650"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Przykładowy przewodnik po prognozowaniu wartości całego cyklu życia klienta (CLV)

Ten przewodnik przeprowadzi Cię przez cały przykład przewidywania okresu istnienia klienta (CLV) w Customer Insights na podstawie przykładowych danych.

## <a name="scenario"></a>Scenariusz

Contoso to firma produkująca wysokiej jakości maszyny do barów kawowych. Produkty są dostępne w witrynie firmy Contoso Coffee. Firma chce zrozumieć wartość (przychód), jaką jej klienci mogą wygenerować w ciągu najbliższych 12 miesięcy. Znajomość oczekiwanej wartości klientów w ciągu najbliższych 12 miesięcy pomoże im ukierunkować działania marketingowe na klientów o wysokiej wartości.

## <a name="prerequisites"></a>Wymagania wstępne

- Co najmniej [Uprawnienia współautora](permissions.md) w Customer Insights.
- Zaleca się, aby zaimplementować poniższe kroki [w nowym środowisku](manage-environments.md).

## <a name="task-1---ingest-data"></a>Zadanie 1 - pozyskiwanie danych

Przejrzyj artykuły [dotyczące pozyskiwania danych](data-sources.md) i [importowania źródeł danych za pomocą łączników usługi Power Query](connect-power-query.md). Poniższe informacje zakładają, że znasz ogólne zasady przetwarzania danych.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Pozyskiwanie danych klienta na platformie eCommerce

1. Utwórz źródło danych o nazwie **eCommerce**, wybierz opcję importowania i wybierz łącznik typu **tekst/CSV**.

1. Wprowadź adres URL eCommerce kontaktów [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Podczas edytowania danych wybierz opcję  **Przekształć**  i  **Użyj pierwszego wiersza jako nagłówków**.

1. Zaktualizuj typ danych dla kolumn wymienionych poniżej:
   - **DateOfBirth**: Data
   - **CreatedOn**: Data/Czas/Strefa

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Przekształcić datę urodzenia na datę.":::

1. WW polu „Nazwa” w panelu po prawej stronie zmień nazwę źródła danych z **Query** na **eCommerceContacts**

1. **Zapisz** źródło danych.

### <a name="ingest-online-purchase-data"></a>Przetwarzaj dane zakupów online

1. Dodanie nowego zestawu danych do tego samego źródła danych **eCommerce**. Wybierz ponownie łącznik **tekst/CSV**.

1. Wprowadź adres URL danych **Zakupów w trybie online** https://aka.ms/ciadclassonline.

1. Podczas edytowania danych wybierz opcję **Przekształć** i **Użyj pierwszego wiersza jako nagłówków**.

1. Zaktualizuj typ danych dla kolumn wymienionych poniżej:
   - **PurchasedOn**: Data/godzina
   - **TotalPrice**: waluta

1. W polu **Nazwa** w panelu w okienku bocznym zmień nazwę źródła danych z **Query** na **eCommercePurchases**.

1. **Zapisz** źródło danych.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Przetwarzaj dane klientów ze schematu lojalnościowego

1. Utwórz źródło danych o nazwie **LoyaltyScheme**, wybierz opcję importowania i wybierz łącznik typu **tekst/CSV**.

1. Wprowadź adres URL eCommerce kontaktów https://aka.ms/ciadclasscustomerloyalty.

1. Podczas edytowania danych wybierz opcję **Przekształć** i **Użyj pierwszego wiersza jako nagłówków**.

1. Zaktualizuj typ danych dla kolumn wymienionych poniżej:
   - **DateOfBirth**: Data
   - **RewardsPoints**: Pełny numer
   - **CreatedOn**: Data/godzina

1. W polu **Nazwa** w panelu po prawej stronie zmień nazwę źródła danych z **Query** na **loyCustomers**.

1. **Zapisz** źródło danych.

### <a name="ingest-customer-data-from-website-reviews"></a>Przetwarzaj dane klientów z recenzji witryn

1. Utwórz źródło danych o nazwie **Strona internetowa**, wybierz opcję importowania i wybierz łącznik typu **tekst/CSV**.

1. Wprowadź adres URL eCommerce kontaktów https://aka.ms/CI-ILT/WebReviews.

1. Podczas edytowania danych wybierz opcję **Przekształć** i **Użyj pierwszego wiersza jako nagłówków**.

1. Zaktualizuj typ danych dla kolumn wymienionych poniżej:

   - **ReviewRating**: Liczba dziesiętna
   - **ReviewDate**: Data

1. W polu „Nazwa” w prawym panelu zmień nazwę źródła danych z **Zapytanie** na **Recenzje**.

1. **Zapisz** źródło danych.

## <a name="task-2---data-unification"></a>Zadanie 2 - ujednolicenie danych

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>Zadanie 3 — Skonfiguruj prognozę długookresowej wartości klienta

Dzięki ujednoliconym profilom klientów możemy teraz uruchomić przewidywanie wartości życia klienta. Aby wyświetlić szczegółowe kroki, zobacz temat [Przewidywanie wartości okresu istnienia klienta](predict-customer-lifetime-value.md).

1. Przejdź do **Analizy**  > **Przewidywania** i wybierz **Model wartości okresu istnienia klienta**.

1. Przejdź przez informacje w okienku bocznym i wybierz **Rozpoczynanie pracy**.

1. Nazwij model **Przewidywanie OOB eCommerce CLV** i jednostkę wyjściową  **OOBeCommerceCLVPrediction**.

1. Zdefiniuj preferencje modelu dla modelu CLV:
   - **Czas przewidywania**: **12 miesięcy do roku 1**. To ustawienie określa, jak daleko w przyszłość należy przewidzieć długoterminową wartość klienta.
   - **Aktywni klienci**: określ, co aktywni klienci oznaczają dla firmy. Ustaw historyczny przedział czasowy, w którym klient musiał mieć co najmniej jedną transakcję, aby można go było uznać za aktywną. Model będzie przewidywał tylko CLV dla aktywnych klientów. Wybierz pomiędzy pozwoleniem modelowi na obliczenie okresu czasu na podstawie historycznych danych transakcji lub podaniem konkretnych ram czasowych. W tym przykładowym przewodniku **załóżmy, że model oblicza interwał zakupu**, co jest opcją domyślną.
   - **Klienci o wysokiej wartości**: zdefiniuj klientów o wysokiej wartości jako wartość procentową klientów najwyższej klasy. Model wykorzystuje te dane wejściowe, aby dostarczyć wyniki, które pasują do Twojej biznesowej definicji klientów o wysokiej wartości. Możesz zdecydować, czy model definiuje klientów o wysokiej wartości. Wykorzystuje regułę heurystyczną, która wyprowadza percentyl. Możesz również zdefiniować klientów o wysokiej wartości jako procent najlepszych przyszłych płacących klientów. W tym przykładowym przewodniku ręcznie definiujemy klientów o wysokiej wartości jako **najlepszych 30% aktywnych płacących klientów** i wybieramy **Dalej**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Krok preferencji w doświadczeniu z przewodnikiem dla modelu CLV.":::

1. W kroku **Wymagane dane** wybierz opcję **Dodaj dane**, aby udostępnić dane historii transakcji.

1. Dodaj encję **eCommercePurchases : eCommerce** i zmapuj atrybuty wymagane przez model:
   - Identyfikator transakcji: eCommerce.eCommercePurchases.PurchaseId
   - Data transakcji: eCommerce.eCommercePurchases.PurchasedOn
   - Kwota transakcji: eCommerce.eCommercePurchases.TotalPrice
   - Identyfikator produktu: eCommerce.eCommercePurchases.ProductId

1. Wybierz **Dalej**.

1. Konfigurowanie relacji między encją **eCommercePurchases : eCommerce** a encją **eCommerceContacts : eCommerce**.

1. Krok **Dodatkowe dane (opcjonalnie)** umożliwia dodanie większej liczby danych dotyczących działań klienta. Te dane mogą pomóc uzyskać więcej informacji na temat interakcji klientów z Twoją firmą, co może przyczynić się do CLV. Dodanie kluczowych interakcji z klientami, takich jak dzienniki internetowe, dzienniki obsługi klienta lub historia programu nagród, może poprawić dokładność prognoz. Wybierz opcję **Dodaj dane**, aby uwzględnić więcej danych dotyczących działań klienta.

1. Dodaj encję aktywności klienta i zmapuj jej nazwy pól na odpowiednie pola wymagane przez model:
   - Jednostka aktywności klienta: Recenzje:Strona internetowa
   - Klucz podstawowy: Website.Reviews.ReviewId
   - Timestamp: Website.Reviews.ReviewDate
   - Zdarzenie (nazwa działania): Website.Reviews.ActivityTypeDisplay
   - Szczegóły (kwota lub wartość): Website.Reviews.ReviewRating

1. Wybierz opcję **Dalej** i skonfiguruj działanie oraz relację między danymi transakcji a danymi klienta:  
   - Typ aktywności: Wybierz istniejącą
   - Etykieta aktywności: Recenzja
   - Odpowiadająca etykieta: Website.Reviews.UserId
   - Encja Klienta: eCommerceContacts:eCommerce
   - Relacja: WebsiteReviews

1. Wybierz przycisk **Dalej**, aby ustawić harmonogram modelu.

   Model musi regularnie trenować, aby uczyć się nowych wzorców, gdy są pozyskiwane nowe dane. W tym przykładzie wybierz pozycję **Miesięcznie**.

1. Po przejrzeniu wszystkich szczegółów wybierz pozycję **Zapisz i uruchom**.

## <a name="task-4---review-model-results-and-explanations"></a>Zadanie 4 - Przejrzyj wyniki i wyjaśnienia modelu

Pozwól modelowi ukończyć uczenie i ocenianie danych. Następnie możesz przejrzeć wyniki i wyjaśnienia modelu CLV. Aby uzyskać więcej informacji, zobacz temat [Przejrzyj stan i wyniki prognozy](predict-customer-lifetime-value.md#review-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-value-customers"></a>Zadanie 5 — Tworzenie segmentu klientów o wysokiej wartości

Uruchomienie modelu powoduje utworzenie nowej encji wymienionej w **Dane** > **Encje**. Możesz utworzyć nowy segment klientów na podstawie jednostki utworzonej przez model.

1. Przejdź do **Segmenty**. 

1. Wybierz opcję **Nowy** i wybierz pozycję **Utwórz z poziomu** > **Analizy**.

   ![Tworzenie segmentu z wynikiem modelu.](media/segment-intelligence.png)

1. Wybierz encję **OOBeCommerceCLVPrediction** i zdefiniuj segment:
  - Pole: CLVScore
  - Operator: większy niż
  - Wartość: 1500

1. Wybierz opcję **Przegląd** i **Zapisz** segment.

Masz teraz segment, który identyfikuje klientów, którzy według przewidywań wygenerują ponad 1500 USD przychodu w ciągu najbliższych 12 miesięcy. Ten segment jest aktualizowany dynamicznie, jeśli pozyskuje się więcej danych.

Aby uzyskać więcej informacji, zobacz [Tworzenie segmentów i zarządzanie nimi](segments.md).
