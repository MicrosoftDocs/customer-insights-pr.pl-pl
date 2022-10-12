---
title: Przykładowy przewodnik dotyczący prognozowania rezygnacji z transakcji
description: Skorzystaj z tego przykładowego przewodnika, aby wypróbować gotowy model prognozowania rezygnacji z transakcji.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609697"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Przykładowy przewodnik dotyczący prognozowania rezygnacji z transakcji

Ten przewodnik przeprowadza po przewidywaniu rezygnacji transakcyjnej, korzystając z przykładowych danych. Zaleca się, aby wypróbować to przewidywanie [w nowym środowisku](manage-environments.md).

## <a name="scenario"></a>Scenariusz

Contoso to firma produkująca wysokiej jakości maszyny do barów kawowych. Produkty są dostępne w witrynie firmy Contoso Coffee. Ich celem jest wiedzieć, którzy klienci, którzy zazwyczaj kupują ich produkty regularnie, przestaną być aktywnymi klientami w ciągu najbliższych 60 dni. Wiedza o tym, który z ich klientów **prawdopodobnie odejdzie**, może pomóc im zaoszczędzić wysiłki marketingowe, koncentrując się na ich utrzymaniu.

## <a name="prerequisites"></a>Wymagania wstępne

- Co najmniej [uprawnienia współautora](permissions.md).

## <a name="task-1---ingest-data"></a>Zadanie 1 - pozyskiwanie danych

Przejrzyj artykuły [dotyczące pozyskiwania danych](data-sources.md) i [łączenie ze źródłem danych Power Query](connect-power-query.md). Poniższe informacje zakładają, że znasz ogólne zasady przetwarzania danych.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Pozyskiwanie danych klienta na platformie eCommerce

1. Utwórz źródło danych o nazwie **handel elektroniczny** i wybierz łącznik typu **tekst/CSV**.

1. Wprowadź adres URL eCommerce kontaktów https://aka.ms/ciadclasscontacts.

1. Podczas edytowania danych wybierz opcję **Przekształć**, a następnie **Użyj pierwszego wiersza jako nagłówków**.

1. Zaktualizuj typ danych dla kolumn wymienionych poniżej:

   - **DateOfBirth**: Data
   - **CreatedOn**: Data/Czas/Strefa

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Przekształć datę urodzenia na datę.":::

1. WW polu **Nazwa** w panelu po prawej stronie zmień nazwę źródła danych **eCommerceContacts**

1. Zapisz źródło danych.

### <a name="ingest-online-purchase-data"></a>Przetwarzaj dane zakupów online

1. Dodanie nowego zestawu danych do tego samego źródła danych **eCommerce**. Wybierz ponownie łącznik **tekst/CSV**.

1. Wprowadź adres URL danych zakupów w trybie online https://aka.ms/ciadclassonline.

1. Podczas edytowania danych wybierz opcję **Przekształć**, a następnie **Użyj pierwszego wiersza jako nagłówków**.

1. Zaktualizuj typ danych dla kolumn wymienionych poniżej:

   - **PurchasedOn**: Data/godzina
   - **TotalPrice**: waluta

1. WW polu **Nazwa** w panelu po prawej stronie zmień nazwę źródła danych na **eCommercePurchases**.

1. Zapisz źródło danych.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Przetwarzaj dane klientów ze schematu lojalnościowego

1. Utwórz źródło danych o nazwie **LoyaltyScheme** i wybierz łącznik typu **tekst/CSV**.

1. Wprowadź adres URL eCommerce kontaktów https://aka.ms/ciadclasscustomerloyalty.

1. Podczas edytowania danych wybierz opcję **Przekształć**, a następnie **Użyj pierwszego wiersza jako nagłówków**.

1. Zaktualizuj typ danych dla kolumn wymienionych poniżej:

   - **DateOfBirth**: Data
   - **RewardsPoints**: Pełny numer
   - **CreatedOn**: Data/godzina

1. WW polu **Nazwa** w panelu po prawej stronie zmień nazwę źródła danych na **loyCustomers**.

1. Zapisz źródło danych.

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

## <a name="task-4---configure-transaction-churn-prediction"></a>Zadanie 4 - Skonfiguruj przewidywanie rezygnacji z transakcji

Mając ujednolicone profile klientów i działań, możemy teraz uruchomić przewidywanie rezygnacji z transakcji.

1. Przejdź do opcji **Analizy** > **Przewidywania**.

1. Na karcie **Utwórz** wybierz **Model użycia** na **Model rezygnacji klienta**.

1. Wybierz opcję **Transakcyjne** dla typu rozsyłania, a następnie wybierz opcję **Rozpocznij**.

1. Nazwij model **Przewidywanie rezygnacji z transakcji eCommerce OOB**, a następnie encję wyjściową **OOBeCommerceChurnPrediction**.

1. Wybierz **Dalej**.

1. Zdefiniuj preferencje modelu:

   - **Okno przewidywania**: **60** to ustawienie określa, jak daleko w przyszłość chcemy przewidywać odpływ klientów.

   - **Definicja rezygnacji**: **60** czas trwania bez zakupu, po którym klient został uznany za klienta, który zrezygnował.

     :::image type="content" source="media/model-levers.PNG" alt-text="Wybierz preferencje modelu Okno predykcji i Definicja rezygnacji.":::

1. Wybierz **Dalej**.

1. Wybierz **Historia zakupów (wymagane)** i wybierz pozycję **Dodaj dane** dla historii zakupów.

1. Wybierz obiekt **SalesOrderLine** i encję eCommercePurchases i wybierz opcję **Dalej**. Wymagane dane są automatycznie wypełniane z działania. Wybierz **Zapisz**, a następnie **Dalej**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Dołączanie encji eCommerce.":::

1. Pomiń krok **Dodatkowe dane (opcjonalnie)**.

1. W kroku **Aktualizacje danych** ustaw **Miesięcznie** dla harmonogram modelu.

1. Po przejrzeniu wszystkich szczegółów wybierz pozycję **Zapisz i uruchom**.

## <a name="task-5---review-model-results-and-explanations"></a>Zadanie 5 - Przejrzyj wyniki i wyjaśnienia modelu

Pozwól modelowi ukończyć uczenie i ocenianie danych. Przejrzyj wyjaśnienia dotyczące modeli rezygnacji. Aby uzyskać więcej informacji, zobacz [Wyświetl wyniki przewidywania](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Zadanie 6 - Utwórz segment klientów o wysokim ryzyku rezygnacji

Uruchomienie modelu produkcji powoduje utworzenie nowej encji wymienionej w **Dane** > **Encje**. Możesz utworzyć nowy segment na podstawie encji utworzonej przez model.

1. Na stronie wyników wybierz opcję **Utwórz segment**.

1. Utwórz regułę, używając encji **OOBeCommerceChurnPrediction** i zdefiniuj segment:
   - **Pole**: ChurnScore
   - **Operator**: większy niż
   - **Wartość**: 0,6

1. Wybierz opcję **Zapisz** i **Uruchom** segment.

Segment jest obecnie aktualizowany dynamicznie, co umożliwia identyfikację klientów o wysokim poziomie ryzyka. Aby uzyskać więcej informacji, zobacz [Tworzenie segmentów i zarządzanie nimi](segments.md).

> [!TIP]
> Na stronie **Segmenty** można także utworzyć segment dla modelu przewidywania modelu, wybierając opcję **Nowy** i wybierając opcję **Utwórz z** >  **Analizy**. Aby uzyskać więcej informacji, zobacz [Tworzenie nowego segmentu za pomocą szybkich segmentów](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
