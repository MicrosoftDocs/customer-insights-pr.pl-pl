---
title: Przykładowy przewodnik dotyczący prognozowania rezygnacji z transakcji
description: Skorzystaj z tego przykładowego przewodnika, aby wypróbować gotowy model prognozowania rezygnacji z transakcji.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 19befa17524aba4543f0d8a5f5f7d6f5a88b2322f1264b88fa0b31641610592a
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7029458"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a>Przykładowy przewodnik dotyczący prognozowania rezygnacji z transakcji (wersja zapozawcza)

Ten przewodnik przeprowadzi Cię przez kompleksowy przykład prognozowania rezygnacji z transakcji w usłudze Customer Insights przy użyciu danych podanych poniżej. Żadne dane użyte w tym przewodniku nie są prawdziwymi danymi klientów i są częścią zbioru danych Contoso znajdującego się w środowisku *Demo* w ramach subskrypcji Customer Insights.

## <a name="scenario"></a>Scenariusz

Contoso to firma produkująca wysokiej jakości maszyny do barów, które sprzedaje za pośrednictwem witryny sieci Web firmy Contoso Coffee. Ich celem jest wiedzieć, którzy klienci, którzy zazwyczaj kupują ich produkty regularnie, przestaną być aktywnymi klientami w ciągu najbliższych 60 dni. Wiedza o tym, który z ich klientów **prawdopodobnie odejdzie**, może pomóc im zaoszczędzić wysiłki marketingowe, koncentrując się na ich utrzymaniu.

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

Po pozyskaniu danych rozpoczynamy teraz proces **Mapa, dopasuj, scal** aby utworzyć ujednolicony profil klienta. Aby uzyskać więcej informacji, zobacz [Ujednolicenie danych](data-unification.md).

### <a name="map"></a>Mapuj

1. Po przyjęciu danych zmapuj kontakty z danych e-commerce i lojalności na popularne typy danych. Przejdź **Dane** > **Ujednolicanie** > **Mapuj**.

1. Wybierz podmioty, które reprezentują profil klienta - **eCommerceContacts** i **loyCustomers**. 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="ujednolicić źródła danych e-commerce i lojalności.":::

1. Wybierz opcję **ContactId** jako klucz podstawowy dla opcji **eCommerceContacts** i **LoyaltyID** jako klucz podstawowy dla **loyCustomers**.

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="ujednolicenie LoyaltyId jako klucza podstawowego.":::

### <a name="match"></a>Dopasowywanie

1. Przejdź do karty **Dopasowywanie** i wybierz **Ustawianie kolejności**.

1. Na liście rozwijanej **Podstawowe** wybierz pozycję **Kontakty eCommerceContacts : eCommerce** jako główne źródło i uwzględnij wszystkie rekordy.

1. Na liście rozwijanej **Encja 2** wybierz pozycję **loyCustomers : LoyaltyScheme** i wybierz wszystkie rekordy.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Ujednolicenie dopasowania eCommerce i lojalności.":::

1. Wybierz **Tworzenie nowej reguły**

1. Dodanie pierwszego warunku za pomocą narzędzia FullName.

   * W przypadku kontaktów eCommerce z listy rozwijanej wybierz opcję **FullName**.
   * W przypadku kontaktów loyCustomers z listy rozwijanej wybierz opcję **FullName**.
   * Wybierz menu rozwiajne **Normalizuj** i wybierz **Typ (telefon, nazwa, adres,...)**.
   * Ustawianie **Poziomu dokładności**: **Podstawowe** i **Wartość**: **Wysokie**.

1. Wprowadź nazwę **FullName, Email** dla nowej reguły.

   * Dodaj drugi warunek dla adresu e-mail, zaznaczając opcję **Dodaj warunek**
   * W przypadku encji kontakty eCommerce wybierz pozycję **EMail** na liście rozwijanej.
   * W przypadku encji loyCustomers wybierz pozycję **EMail** na liście rozwijanej. 
   * Pozostaw puste pole Normalizuj. 
   * Ustawianie **Poziomu dokładności**: **Podstawowe** i **Wartość**: **Wysokie**.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Należy ujednolicić regułę dotyczącą nazwy i adresu e-mail.":::

7. Wybierz pozycję **Zapisz** i **Uruchom**.

### <a name="merge"></a>Scalanie

1. Przejdź na kartę **Scal**.

1. W elemencie **ContactId** dla encji **loyCustomers** zmień nazwę wyświetlaną na **ContactIdLOYALTY**, aby odróżnić ją od innych przetwarzanych identyfikatorów.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="Zmień nazwę ContactID na identyfikator lojalnościowy.":::

1. Kliknij przycisk **Zapisz** i **Uruchom**, aby rozpocząć proces scalania.



## <a name="task-3---configure-transaction-churn-prediction"></a>Zadanie 3 - Skonfiguruj przewidywanie rezygnacji z transakcji

Dzięki ujednoliconym profilom klienta można teraz uruchomić przewidywanie subskrypcji. Aby zapoznać się ze szczegółowymi krokami, zobacz artykuł [Przewidywanie rezygnacji z subskrypcji (wersja zapoznawcza)](predict-subscription-churn.md). 

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]
