---
title: Przewodnik po przykładach prognozowania rekomendacji produktów
description: Skorzystaj z tego przykładowego przewodnika, aby wypróbować model prognozowania rekomendacji produktu po wyjęciu z pudełka.
ms.date: 02/10/2021
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ee873d9b7caa5f891cb2d5b8c665dec90ad0e59
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270520"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a>Przykładowy przewodnik dotyczący prognozowania rekomendacji produktów (podgląd)

Przeprowadzimy Cię przez cały przykład przewidywania rekomendacji produktów, korzystając z przykładowych danych podanych poniżej.

## <a name="scenario"></a>Scenariusz

Contoso to firma produkująca wysokiej jakości ekspresy do kawy i ekspresy do kawy, które sprzedają za pośrednictwem swojej witryny internetowej Contoso Coffee. Ich celem jest zrozumienie, które produkty powinni polecać swoim stałym klientom. Wiedza na temat tego, co **klienci prawdopodobnie kupią**, może pomóc im w zapisaniu działań marketingowych dzięki skupieniu się na określonych elementach.

## <a name="prerequisites"></a>Wymagania wstępne

- Co najmniej [Uprawnienia współautora](permissions.md) w Customer Insights.
- Zaleca się, aby zaimplementować poniższe kroki [w nowym środowisku](manage-environments.md).

## <a name="task-1---ingest-data"></a>Zadanie 1 - pozyskiwanie danych

Przejrzyj szczególnie artykuły [dotyczące spożywania danych](data-sources.md) i [importowania źródeł danych przy użyciu łączników Power Query](connect-power-query.md). Poniższe informacje zakładają, że znasz ogólne zasady przetwarzania danych.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Pozyskiwanie danych klienta na platformie eCommerce

1. Utwórz źródło danych o nazwie **eCommerce**, wybierz opcję importowania i wybierz łącznik typu **tekst/CSV**.

1. Wprowadź adres URL eCommerce kontaktów https://aka.ms/ciadclasscontacts.

1. Podczas edytowania danych wybierz opcję **Przekształć** i **Użyj pierwszego wiersza jako nagłówków**.

1. Zaktualizuj typ danych dla kolumn wymienionych poniżej:
   - **DateOfBirth**: Data
   - **CreatedOn**: Data/Czas/Strefa

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Przekształcić datę urodzenia na datę.":::

5. WW polu „Nazwa” w panelu po prawej stronie zmień nazwę źródła danych z **Query** na **eCommerceContacts**

6. **Zapisz** źródło danych.

### <a name="ingest-online-purchase-data"></a>Przetwarzaj dane zakupów online

1. Dodanie nowego zestawu danych do tego samego źródła danych **eCommerce**. Wybierz ponownie łącznik **tekst/CSV**.

1. Wprowadź adres URL danych **Zakupów w trybie online** https://aka.ms/ciadclassonline.

1. Podczas edytowania danych wybierz opcję **Przekształć** i **Użyj pierwszego wiersza jako nagłówków**.

1. Zaktualizuj typ danych dla kolumn wymienionych poniżej:
   - **PurchasedOn**: Data/godzina
   - **TotalPrice**: waluta

1. W polu **Nazwa** w panelu w okienku bocznym zmień nazwę źródła danych z **Query** na **eCommercePurchases**.

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

Po pozyskaniu danych rozpoczynamy teraz proces **Mapa, dopasuj, scal** aby utworzyć ujednolicony profil klienta. Aby uzyskać więcej informacji, zobacz [Ujednolicenie danych](data-unification.md).

### <a name="map"></a>Mapuj

1. Po przyjęciu danych zmapuj kontakty z danych e-commerce i lojalności na popularne typy danych. Przejdź **Dane** > **Ujednolicanie** > **Mapuj**.

2. Wybierz podmioty, które reprezentują profil klienta - **eCommerceContacts** i **loyCustomers**.

   ![ujednolicić źródła danych e-commerce i lojalności.](media/unify-ecommerce-loyalty.png)

3. Wybierz opcję **ContactId** jako klucz podstawowy dla opcji **eCommerceContacts** i **LoyaltyID** jako klucz podstawowy dla **loyCustomers**.

   ![ujednolicenie LoyaltyId jako klucza podstawowego.](media/unify-loyaltyid.png)

### <a name="match"></a>Dopasowywanie

1. Przejdź do karty **Dopasowywanie** i wybierz **Ustawianie kolejności**.

2. Z listy rozwijanej **Głównej** wybierz pozycję **eCommerceContacts: eCommerce** jako źródło podstawowe i dołącz wszystkie rekordy.

3. Z listy rozwijanej **Encja 2** wybierz **loyCustomers : LoyaltyScheme** i uwzględnij wszystkie rekordy.

   ![Ujednolicenie dopasowania eCommerce i lojalności.](media/unify-match-order.png)

4. Wybierz **Tworzenie nowej reguły**

5. Dodanie pierwszego warunku za pomocą narzędzia FullName.

   - Dla elementu eCommerceContacts wybierz pozycję **FullName** z listy rozwijanej.
   - Dla elementu loyCustomers wybierz pozycję **FullName** z listy rozwijanej.
   - Wybierz menu rozwiajne **Normalizuj** i wybierz **Typ (telefon, nazwa, adres,...)**.
   - Ustawianie **Poziomu dokładności**: **Podstawowe** i **Wartość**: **Wysokie**.

6. Wprowadź nazwę **FullName, Email** dla nowej reguły.

   - Dodaj drugi warunek dla adresu e-mail, zaznaczając opcję **Dodaj warunek**
   - W przypadku encji eCommerceContacts wybierz opcję **E-mail** w polu listy rozwijanej.
   - W przypadku encji loyCustomers wybierz opcję **E-mail** w polu listy rozwijanej.
   - Pozostaw puste pole Normalizuj.
   - Ustawianie **Poziomu dokładności**: **Podstawowe** i **Wartość**: **Wysokie**.

   ![Należy ujednolicić regułę dotyczącą nazwy i adresu e-mail.](media/unify-match-rule.png)

7. Wybierz pozycję **Zapisz** i **Uruchom**.

### <a name="merge"></a>Scalanie

1. Przejdź na kartę **Scal**.

1. W elemencie **ContactId** dla encji **loyCustomers** zmień nazwę wyświetlaną na **ContactIdLOYALTY**, aby odróżnić ją od innych przetwarzanych identyfikatorów.

   ![Zmień nazwę ContactID na identyfikator lojalnościowy.](media/unify-merge-contactid.png)

1. Kliknij przycisk **Zapisz** i **Uruchom**, aby rozpocząć proces scalania.

## <a name="task-3---configure-product-recommendation-prediction"></a>Zadanie 3 — Konfigurowanie rekomendacji przewidywanie

Dzięki ujednoliconym profilom klienta można teraz uruchomić przewidywanie subskrypcji.

1. Przejdź do **Analizy** > **Przewidywania** i wybierz **Rekomendacje produktów**.

1. Wybierz **Rozpocznij**.

1. Nazwij **Model rekomendacji produktu OOB przewidywanie** i encji wyjściowej **OOBProductRecommendationModelPrediction**.

1. Zdefiniować trzy warunki dotyczące modelu:

   - **Liczba produktów**: ustaw tę wartość na **5**. To ustawienie określa, ile produktów ma być zalecane dla klientów.

   - **Sugestie dotyczące produktów, które zostały ostatnio zakupione?**: Wybierz opcję **Tak**, aby wskazać, że produkty mają zostać zakupione wcześniej przez klientów.

   - **Okno wglądu w przeszłość**: wybierz co najmniej **365 dni**. To ustawienie definiuje, jak daleko model spojrzy wstecz na aktywność klienta, aby użyć go jako danych wejściowych do jego zaleceń.
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modelowe preferencje dotyczące modelu rekomendacji produktów.":::

1. Wybierz **Wymagane dane** i wybierz pozycję **Dodaj dane** dla historii zakupów.

1. Dodaj encję **eCommercePurchases : eCommerce** i zamapuj pola z eCommerce na odpowiadające im pola wymagane przez model.

1. Dołącz do encji **eCommercePurchases: eCommerce** o identyfikatorze **eCommerceContacts: eCommerce**.

   ![Dołączanie encji eCommerce.](media/model-purchase-join.png)

1. Wybierz przycisk **Dalej**, aby ustawić harmonogram modelu.

   Model musi regularnie trenować, aby uczyć się nowych wzorców, gdy są pozyskiwane nowe dane. Na potrzeby tego przykładu wybierz pozycję **Miesięczny**.

1. Po przejrzeniu wszystkich szczegółów wybierz pozycję **Zapisz i uruchom**.


## <a name="task-4---review-model-results-and-explanations"></a>Zadanie 4 - Przejrzyj wyniki i wyjaśnienia modelu

Pozwól modelowi ukończyć uczenie i ocenianie danych. Możesz teraz przejrzeć objaśnienia dotyczące modelu rekomendacji produktów. Aby uzyskać więcej informacji, zobacz temat [Przejrzyj stan i wyniki prognozy](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Zadanie 5 — Tworzenie segmentu wysoko zakupionych produktów

Uruchomienie modelu produkcyjnego tworzy nową jednostkę, którą możesz zobaczyć **Dane** > **Encje**.

Możesz utworzyć nowy segment na podstawie encji utworzonej przez model.

1. Przejdź do **Segmenty**. Wybierz opcję **Nowy** i wybierz pozycję **Utwórz z poziomu** > **Analizy**.

   ![Tworzenie segmentu z wynikiem modelu.](media/segment-intelligence.png)

1. Wybierz opcję **OOBProductRecommendationModelPrediction** punkt końcowy i zdefiniuj segment:

   - Pole: ProductID
   - Operator: wartość
   - Wartość: Wybierz trzy pierwsze identyfikatory produktów

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Tworzenie segmentu na stronie wyników modelu.":::

Masz teraz dynamicznie aktualizowany segment, który identyfikuje klientów, którzy są bardziej skłonni do zakupu trzech najbardziej polecanych produktów 

Aby uzyskać więcej informacji, zobacz [Tworzenie segmentów i zarządzanie nimi](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]