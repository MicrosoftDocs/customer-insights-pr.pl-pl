---
title: Przewodnik po przykładach prognozowania rekomendacji produktów
description: Skorzystaj z tego przykładowego przewodnika, aby wypróbować model prognozowania rekomendacji produktu po wyjęciu z pudełka.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 2b42a89e3f4ec8cf4f0769128b8536973365f1cb
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610157"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Przewodnik po przykładach prognozowania rekomendacji produktów

Ten przewodnik przeprowadzi użytkownika przez cały przykład przewidywania rekomendacji produktów, korzystając z przykładowych danych. Zaleca się, aby wypróbować to przewidywanie [w nowym środowisku](manage-environments.md).

## <a name="scenario"></a>Scenariusz

Contoso to firma produkująca wysokiej jakości maszyny do barów kawowych. Produkty są dostępne w witrynie firmy Contoso Coffee. Ich celem jest zrozumienie, które produkty powinni polecać swoim stałym klientom. Wiedza na temat tego, co **klienci prawdopodobnie kupią**, może pomóc im w zapisaniu działań marketingowych dzięki skupieniu się na określonych elementach.

## <a name="prerequisites"></a>Wymagania wstępne

- Co najmniej [Uprawnienia współautora](permissions.md) w Customer Insights.

## <a name="task-1---ingest-data"></a>Zadanie 1 - pozyskiwanie danych

Przejrzyj artykuły [dotyczące pozyskiwania danych](data-sources.md) i [łączenie ze źródłem danych Power Query](connect-power-query.md). Poniższe informacje zakładają, że znasz ogólne zasady przetwarzania danych.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Pozyskiwanie danych klienta na platformie eCommerce

1. Utwórz źródło danych Power Query o nazwie **Handel elektroniczny**, wybierz opcję importowania i wybierz łącznik typu **tekst/CSV**.

1. Wprowadź adres URL kontaktów handlu elektronicznego: https://aka.ms/ciadclasscontacts.

1. Podczas edytowania danych wybierz opcję **Przekształć**, a następnie **Użyj pierwszego wiersza jako nagłówków**.

1. Zaktualizuj typ danych dla kolumn wymienionych poniżej:
   - **DateOfBirth**: Data
   - **CreatedOn**: Data/Czas/Strefa

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Przekształcić datę urodzenia na datę.":::

1. WW polu **Nazwa** w panelu po prawej stronie zmień nazwę źródła danych **eCommerceContacts**.

1. **Zapisz** źródło danych.

### <a name="ingest-online-purchase-data"></a>Przetwarzaj dane zakupów online

1. Dodanie nowego zestawu danych do tego samego źródła danych **eCommerce**. Wybierz ponownie łącznik **tekst/CSV**.

1. Wprowadź adres URL danych zakupów w trybie online https://aka.ms/ciadclassonline.

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

## <a name="task-4---configure-product-recommendation-prediction"></a>Zadanie 4 — Konfigurowanie rekomendacji przewidywanie

Mając ujednolicone profile klientów i utworzone działanie, możemy teraz uruchomić predykcję rekomendacji produktów.

1. Przejdź do opcji **Analizy** > **Przewidywania**.

1. Na karcie **Utwórz** wybierz **Model użycia** na kafelku **Rekomendacje produktów (wersja zapoznawcza)**.

1. Wybierz **Rozpocznij**.

1. Nazwij **Model rekomendacji produktu OOB przewidywanie** i encji wyjściowej **OOBProductRecommendationModelPrediction**.

1. Wybierz **Dalej**.

1. Zdefiniuj preferencje modelu:
   - **Liczba produktów**: **5**, to ustawienie określa, ile produktów ma być zalecane dla klientów.
   - **Oczekiwane powtórzenie zakupu**: **Tak**, aby uwzględnić wcześniej zakupione produkty w rekomendacji.
   - **Okno historii:** **365 dni**, aby określić, jak długo model będzie wyglądał wstecz przed ponownie zalecając produkt.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modelowe preferencje dotyczące modelu rekomendacji produktów.":::

1. Wybierz **Dalej**.

1. W kroku **Dodaj historię produktu** wybierz opcję **Dodaj dane**.

1. Wybierz obiekt **SalesOrderLine** i encję eCommercePurchases i wybierz opcję **Dalej**. Wymagane dane są automatycznie wypełniane z działania. Wybierz **Zapisz**, a następnie **Dalej**.

1. Pomiń kroki **Dodaj informacje o produkcie** i **Filtry produktów**, ponieważ nie mamy danych dotyczących informacji o produkcie.

1. W kroku **Aktualizacje danych** ustaw **Miesięcznie** dla harmonogram modelu.

1. Wybierz **Dalej**.

1. Po przejrzeniu wszystkich szczegółów wybierz pozycję **Zapisz i uruchom**.

## <a name="task-5---review-model-results-and-explanations"></a>Zadanie 5 - Przejrzyj wyniki i wyjaśnienia modelu

Pozwól modelowi ukończyć uczenie i ocenianie danych. Przejrzyj [objaśnienia dotyczące modelu rekomendacji produktów](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-purchased-products"></a>Zadanie 6 — Tworzenie segmentu wysoko zakupionych produktów

Uruchomienie modelu powoduje utworzenie nowej encji wymienionej w **Dane** > **Encje**. Możesz utworzyć nowy segment na podstawie encji utworzonej przez model.

1. Na stronie wyników wybierz opcję **Utwórz segment**.

1. Utwórz regułę, używając encji **OOBProductRecommendationModelPrediction** i zdefiniuj segment:
   - **Pole**: ProductID
   - **Wartość**: Wybierz trzy pierwsze identyfikatory produktów

1. Wybierz opcję **Zapisz** i **Uruchom** segment.

Masz teraz dynamicznie aktualizowany segment identyfikujący klientów, którzy mogą być zainteresowani zakupem pięciu najbardziej polecanych produktów. Aby uzyskać więcej informacji, zobacz [Tworzenie segmentów i zarządzanie nimi](segments.md).

> [!TIP]
> Na stronie **Segmenty** można także utworzyć segment dla modelu przewidywania modelu, wybierając opcję **Nowy** i wybierając opcję **Utwórz z** >  **Analizy**. Aby uzyskać więcej informacji, zobacz [Tworzenie nowego segmentu za pomocą szybkich segmentów](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
