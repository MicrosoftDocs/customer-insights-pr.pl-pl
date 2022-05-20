---
title: Przykładowy przewodnik dotyczący prognozowania rezygnacji z transakcji
description: Skorzystaj z tego przykładowego przewodnika, aby wypróbować gotowy model prognozowania rezygnacji z transakcji.
ms.date: 05/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3edbf2a471313379c28db874d7f19c3265a23299
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741332"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Przykładowy przewodnik dotyczący prognozowania rezygnacji z transakcji

Ten przewodnik przeprowadzi Cię przez kompleksowy przykład prognozowania rezygnacji z transakcji w usłudze Customer Insights przy użyciu danych podanych poniżej. Wszystkie dane użyte w tym przewodniku nie są prawdziwymi danymi klientów i są częścią zestawu danych Contoso znajdującego się w środowisku *Wersja demonstracyjna* w ramach subskrypcji Customer Insights.

## <a name="scenario"></a>Scenariusz

Contoso to firma produkująca wysokiej jakości ekspresy do kawy i ekspresy do kawy, które sprzedają za pośrednictwem swojej witryny internetowej Contoso Coffee. Ich celem jest wiedzieć, którzy klienci, którzy zazwyczaj kupują ich produkty regularnie, przestaną być aktywnymi klientami w ciągu najbliższych 60 dni. Wiedza o tym, który z ich klientów **prawdopodobnie odejdzie**, może pomóc im zaoszczędzić wysiłki marketingowe, koncentrując się na ich utrzymaniu.

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

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Przekształć datę urodzenia na datę.":::

1. W polu **Nazwa** w panelu po prawej stronie zmień nazwę źródła danych z **Query** na **eCommerceContacts**

1. Zapisz źródło danych.

### <a name="ingest-online-purchase-data"></a>Przetwarzaj dane zakupów online

1. Dodanie nowego zestawu danych do tego samego źródła danych **eCommerce**. Wybierz ponownie łącznik **tekst/CSV**.

1. Wprowadź adres URL danych **Zakupów w trybie online** https://aka.ms/ciadclassonline.

1. Podczas edytowania danych wybierz opcję **Przekształć** i **Użyj pierwszego wiersza jako nagłówków**.

1. Zaktualizuj typ danych dla kolumn wymienionych poniżej:

   - **PurchasedOn**: Data/godzina
   - **TotalPrice**: waluta
   
1. W polu **Nazwa** w panelu po prawej stronie zmień nazwę źródła danych z **Query** na **eCommercePurchases**.

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

## <a name="task-2---data-unification"></a>Zadanie 2 - ujednolicenie danych

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-transaction-churn-prediction"></a>Zadanie 3 - Skonfiguruj przewidywanie rezygnacji z transakcji

Mając ujednolicone profile klientów, możemy teraz uruchomić przewidywanie rezygnacji z transakcji. Aby uzyskać szczegółowe informacje o krokach, zobacz artykuł [Przewidywanie rezygnacji z transakcji](predict-transactional-churn.md). 

1. Wybierz **Analizy** > **Wykryj** i wybierz korzystanie z **Model rezygnacji klientów**.

1. Wybierz opcję **Transakcyjna** i wybierz pozycję **Rozpocznij pracę**.

1. Nazwij model **Przewidywanie rezygnacji z transakcji eCommerce OOB**, a następnie encję wyjściową **OOBeCommerceChurnPrediction**.

1. Zdefiniować dwa warunki dotyczące modelu rezygnacji:

   * **Okno przewidywania**: **co najmniej 60** dni. To ustawienie określa, jak daleko w przyszłość chcemy przewidywać odpływ klientów.

   * **Definicja rezygnacji**: **co najmniej 60** dni. Czas trwania bez zakupu, po którym klient został uznany za klienta, który zrezygnował.

     :::image type="content" source="media/model-levers.PNG" alt-text="Wybierz dźwignie modelu Okno predykcji i Definicja rezygnacji.":::

1. Wybierz **Historia zakupów (wymagane)** i wybierz pozycję **Dodaj dane** dla historii zakupów.

1. Dodaj encję **eCommercePurchases : eCommerce** i zamapuj pola z eCommerce na odpowiadające im pola wymagane przez model.

1. Dołącz do encji **eCommercePurchases: eCommerce** o identyfikatorze **eCommerceContacts: eCommerce**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Dołączanie encji eCommerce.":::

1. Wybierz przycisk **Dalej**, aby ustawić harmonogram modelu.

   Model musi regularnie trenować, aby uczyć się nowych wzorców, gdy są pozyskiwane nowe dane. Na potrzeby tego przykładu wybierz pozycję **Miesięczny**.

1. Po przejrzeniu wszystkich szczegółów wybierz pozycję **Zapisz i uruchom**.

## <a name="task-4---review-model-results-and-explanations"></a>Zadanie 4 - Przejrzyj wyniki i wyjaśnienia modelu

Pozwól modelowi ukończyć uczenie i ocenianie danych. Możesz teraz przejrzeć wyjaśnienia dotyczące modeli rezygnacji. Aby uzyskać więcej informacji, zobacz temat [Przejrzyj stan i wyniki prognozy](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Zadanie 5 - Utwórz segment klientów o wysokim ryzyku rezygnacji

Uruchomienie modelu produkcyjnego tworzy nową jednostkę, którą możesz zobaczyć **Dane** > **Encje**.   

Możesz utworzyć nowy segment na podstawie encji utworzonej przez model.

1.  Przejdź do **Segmenty**. Wybierz opcję **Nowy** i wybierz pozycję **Utwórz z poziomu** > **Analizy**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Tworzenie segmentu z wynikiem modelu.":::

1. Wybierz punkt końcowy **OOBePrognozaRezygnacjiCommerce** i zdefiniuj segment: 
   - Pole: ChurnScore
   - Operator: większy niż
   - Wartość: 0.6

Segment jest obecnie aktualizowany dynamicznie, co umożliwia identyfikację klientów o wysokim poziomie ryzyka.

Aby uzyskać więcej informacji, zobacz [Tworzenie segmentów i zarządzanie nimi](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
