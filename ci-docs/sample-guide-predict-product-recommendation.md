---
title: Przewodnik po przykładach prognozowania rekomendacji produktów
description: Skorzystaj z tego przykładowego przewodnika, aby wypróbować model prognozowania rekomendacji produktu po wyjęciu z pudełka.
ms.date: 05/16/2022
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
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762699"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Przewodnik po przykładach prognozowania rekomendacji produktów

Przeprowadzimy Cię przez cały przykład przewidywania rekomendacji produktów, korzystając z przykładowych danych podanych poniżej.

## <a name="scenario"></a>Scenariusz

Contoso to firma produkująca wysokiej jakości ekspresy do kawy i ekspresy do kawy, które sprzedają za pośrednictwem swojej witryny internetowej Contoso Coffee. Ich celem jest zrozumienie, które produkty powinni polecać swoim stałym klientom. Wiedza na temat tego, co **klienci prawdopodobnie kupią**, może pomóc im w zapisaniu działań marketingowych dzięki skupieniu się na określonych elementach.

## <a name="prerequisites"></a>Wymagania wstępne

- Co najmniej [Uprawnienia współautora](permissions.md) w Customer Insights.
- Zaleca się, aby zaimplementować poniższe kroki [w nowym środowisku](manage-environments.md).

## <a name="task-1---ingest-data"></a>Zadanie 1 - pozyskiwanie danych

Przejrzyj w szczególności artykuły [dotyczące pozyskiwania danych](data-sources.md) i [importowania źródeł danych za pomocą łączników usługi Power Query](connect-power-query.md). Poniższe informacje zakładają, że znasz ogólne zasady przetwarzania danych.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Pozyskiwanie danych klienta na platformie eCommerce

1. Utwórz źródło danych o nazwie **eCommerce**, wybierz opcję importowania i wybierz łącznik typu **tekst/CSV**.

1. Wprowadź adres URL eCommerce kontaktów: [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Podczas edytowania danych wybierz opcję **Przekształć** i **Użyj pierwszego wiersza jako nagłówków**.

1. Zaktualizuj typ danych dla kolumn wymienionych poniżej:
   - **DateOfBirth**: Data
   - **CreatedOn**: Data/Czas/Strefa

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Przekształcić datę urodzenia na datę.":::

1. WW polu „Nazwa” w panelu po prawej stronie zmień nazwę źródła danych z **Query** na **eCommerceContacts**

1. **Zapisz** źródło danych.

### <a name="ingest-online-purchase-data"></a>Przetwarzaj dane zakupów online

1. Dodanie nowego zestawu danych do tego samego źródła danych **eCommerce**. Wybierz ponownie łącznik **tekst/CSV**.

1. Wprowadź adres URL danych **Zakupów w trybie online** [https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline).

1. Podczas edytowania danych wybierz opcję **Przekształć** i **Użyj pierwszego wiersza jako nagłówków**.

1. Zaktualizuj typ danych dla kolumn wymienionych poniżej:
   - **PurchasedOn**: Data/godzina
   - **TotalPrice**: waluta

1. W polu **Nazwa** w panelu w okienku bocznym zmień nazwę źródła danych z **Query** na **eCommercePurchases**.

1. **Zapisz** źródło danych.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Przetwarzaj dane klientów ze schematu lojalnościowego

1. Utwórz źródło danych o nazwie **LoyaltyScheme**, wybierz opcję importowania i wybierz łącznik typu **tekst/CSV**.

1. Wprowadź adres URL eCommerce kontaktów [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty).

1. Podczas edytowania danych wybierz opcję **Przekształć** i **Użyj pierwszego wiersza jako nagłówków**.

1. Zaktualizuj typ danych dla kolumn wymienionych poniżej:
   - **DateOfBirth**: Data
   - **RewardsPoints**: Pełny numer
   - **CreatedOn**: Data/godzina

1. W polu **Nazwa** w panelu po prawej stronie zmień nazwę źródła danych z **Query** na **loyCustomers**.

1. **Zapisz** źródło danych.

## <a name="task-2---data-unification"></a>Zadanie 2 - ujednolicenie danych

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>Zadanie 3 — Konfigurowanie rekomendacji przewidywanie

Mając ujednolicone profile klientów, możemy teraz uruchomić predykcję rekomendacji produktów.

1. Przejdź do **Analizy** > **Przewidywania** i wybierz **Rekomendacje produktów**.

1. Wybierz **Rozpocznij**.

1. Nazwij **Model rekomendacji produktu OOB przewidywanie** i encji wyjściowej **OOBProductRecommendationModelPrediction**.

1. Zdefiniować trzy warunki dotyczące modelu:

   - **Liczba produktów**: ustaw tę wartość na **5**. To ustawienie określa, ile produktów ma być zalecane dla klientów.

   - **Oczekiwane powtórzenie zakupu**: wybierz opcję **Tak**, aby wskazać, że produkty mają być dołączane do rekomendacji, które zostały zakupione przez klientów.

   - **Okno wglądu w przeszłość**: wybierz co najmniej **365 dni**. To ustawienie definiuje, jak daleko model spojrzy wstecz na aktywność klienta, aby użyć go jako danych wejściowych do jego zaleceń.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modelowe preferencje dotyczące modelu rekomendacji produktów.":::

1. W kroku **Dodaj wymagane dane** wybierz opcję **Dodaj dane**.

1. W okienku **Dodaj dane** wybierz **SalesOrderLine** jako jednostkę historii zakupów. W tym momencie prawdopodobnie nie jest jeszcze skonfigurowany. Otwórz łącze w panelu, aby utworzyć aktywność, wykonując następujące kroki:
   1. Wprowadź **Nazwę działania** i wybierz *eCommercePurchases:eCommerce* jako **Encja aktywności**. **Klucz podstawowy** to *PurchaseId*.
   1. Zdefiniuj i nazwij relację do encji *eCommerceContacts:eCommerce* i wybierz **ContactId** jako klucz obcy.
   1. Aby ujednolicić aktywność, ustaw **Aktywność wydarzenia** jako *ŁącznaCena*, a Znacznik czasowy do *ZakupionoDnia*. Możesz określić więcej pól, jak opisano w [Działania klienta](activities.md).
   1. Dla **Typu działania** wybierz wartość *WierszZleceniaZakupu*. Zmapuj następujące pola aktywności:
      - ID wiersza zamówienia: IDZamówienia
      - ID zamówienia: IDZamówienia
      - Dane dotyczące zamówienia: ZakupioneDnia
      - Identyfikator produktu/usługi: IDProduktu
      - Kwota: RazemCena
   1. Przejrzyj i zakończ ćwiczenie, zanim wrócisz do konfiguracji modelu.

1. Wracając do etapu **Wybierania aktywności**, wybierz nowo utworzoną aktywność w sekcji **Aktualności**. Wybierz **Dalej**, a mapowanie atrybutów jest już wypełnione. Wybierz **Zapisz**.

1. W tym przykładowym przewodniku pomijamy zestawy **Dodaj informacje o produkcie** i **Filtry produktów**, ponieważ nie mamy danych dotyczących informacji o produkcie.

1. W kroku **Aktualizacja danych** ustaw harmonogram modelu.

   Model musi regularnie trenować, aby uczyć się nowych wzorców, gdy są pozyskiwane nowe dane. Na potrzeby tego przykładu wybierz pozycję **Miesięczny**.

1. Po przejrzeniu wszystkich szczegółów wybierz pozycję **Zapisz i uruchom**. Za pierwszym razem uruchomienie modelu zajmie kilka minut.

## <a name="task-4---review-model-results-and-explanations"></a>Zadanie 4 - Przejrzyj wyniki i wyjaśnienia modelu

Pozwól modelowi ukończyć uczenie i ocenianie danych. Możesz teraz przejrzeć objaśnienia dotyczące modelu rekomendacji produktów. Aby uzyskać więcej informacji, zobacz temat [Przejrzyj stan i wyniki prognozy](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Zadanie 5 — Tworzenie segmentu wysoko zakupionych produktów

Uruchomienie modelu produkcyjnego tworzy nową jednostkę, którą możesz zobaczyć **Dane** > **Encje**.

Możesz utworzyć nowy segment na podstawie encji utworzonej przez model.

1. Przejdź do **Segmenty**. Wybierz opcję **Nowy** i wybierz pozycję **Utwórz z poziomu Analizy**.

   ![Tworzenie segmentu z wynikiem modelu.](media/segment-intelligence.png)

1. Wybierz opcję **OOBProductRecommendationModelPrediction** punkt końcowy i zdefiniuj segment:

   - Pole: ProductID
   - Wartość: Wybierz trzy pierwsze identyfikatory produktów

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Tworzenie segmentu na stronie wyników modelu.":::

Masz teraz dynamicznie aktualizowany segment identyfikujący klientów, którzy mogą być zainteresowani zakupem trzech najbardziej polecanych produktów.

Aby uzyskać więcej informacji, zobacz [Tworzenie segmentów i zarządzanie nimi](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
