---
title: Przewodnik po przykładach prognozowania rekomendacji produktów
description: Skorzystaj z tego przykładowego przewodnika, aby wypróbować model prognozowania rekomendacji produktu po wyjęciu z pudełka.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 20072d14b160e54f5ad044adc1de6c079bf790e4
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595286"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="d3e0c-103">Przykładowy przewodnik dotyczący prognozowania rekomendacji produktów (podgląd)</span><span class="sxs-lookup"><span data-stu-id="d3e0c-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="d3e0c-104">Przeprowadzimy Cię przez cały przykład przewidywania rekomendacji produktów, korzystając z przykładowych danych podanych poniżej.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="d3e0c-105">Scenariusz</span><span class="sxs-lookup"><span data-stu-id="d3e0c-105">Scenario</span></span>

<span data-ttu-id="d3e0c-106">Contoso to firma produkująca wysokiej jakości ekspresy do kawy i ekspresy do kawy, które sprzedają za pośrednictwem swojej witryny internetowej Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="d3e0c-107">Ich celem jest zrozumienie, które produkty powinni polecać swoim stałym klientom.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="d3e0c-108">Wiedza na temat tego, co **klienci prawdopodobnie kupią**, może pomóc im w zapisaniu działań marketingowych dzięki skupieniu się na określonych elementach.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d3e0c-109">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="d3e0c-109">Prerequisites</span></span>

- <span data-ttu-id="d3e0c-110">Co najmniej [Uprawnienia współautora](permissions.md) w Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="d3e0c-111">Zaleca się, aby zaimplementować poniższe kroki [w nowym środowisku](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="d3e0c-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="d3e0c-112">Zadanie 1 - pozyskiwanie danych</span><span class="sxs-lookup"><span data-stu-id="d3e0c-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="d3e0c-113">Przejrzyj szczególnie artykuły [dotyczące spożywania danych](data-sources.md) i [importowania źródeł danych przy użyciu łączników Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="d3e0c-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="d3e0c-114">Poniższe informacje zakładają, że znasz ogólne zasady przetwarzania danych.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="d3e0c-115">Pozyskiwanie danych klienta na platformie eCommerce</span><span class="sxs-lookup"><span data-stu-id="d3e0c-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="d3e0c-116">Utwórz źródło danych o nazwie **eCommerce**, wybierz opcję importowania i wybierz łącznik typu **tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="d3e0c-117">Wprowadź adres URL eCommerce kontaktów https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="d3e0c-118">Podczas edytowania danych wybierz opcję **Przekształć** i **Użyj pierwszego wiersza jako nagłówków**.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="d3e0c-119">Zaktualizuj typ danych dla kolumn wymienionych poniżej:</span><span class="sxs-lookup"><span data-stu-id="d3e0c-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="d3e0c-120">**DateOfBirth**: Data</span><span class="sxs-lookup"><span data-stu-id="d3e0c-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="d3e0c-121">**CreatedOn**: Data/Czas/Strefa</span><span class="sxs-lookup"><span data-stu-id="d3e0c-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Przekształcić datę urodzenia na datę.":::

5. <span data-ttu-id="d3e0c-123">WW polu „Nazwa” w panelu po prawej stronie zmień nazwę źródła danych z **Query** na **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="d3e0c-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="d3e0c-124">**Zapisz** źródło danych.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="d3e0c-125">Przetwarzaj dane zakupów online</span><span class="sxs-lookup"><span data-stu-id="d3e0c-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="d3e0c-126">Dodanie nowego zestawu danych do tego samego źródła danych **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="d3e0c-127">Wybierz ponownie łącznik **tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="d3e0c-128">Wprowadź adres URL danych **Zakupów w trybie online** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="d3e0c-129">Podczas edytowania danych wybierz opcję **Przekształć** i **Użyj pierwszego wiersza jako nagłówków**.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="d3e0c-130">Zaktualizuj typ danych dla kolumn wymienionych poniżej:</span><span class="sxs-lookup"><span data-stu-id="d3e0c-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="d3e0c-131">**PurchasedOn**: Data/godzina</span><span class="sxs-lookup"><span data-stu-id="d3e0c-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="d3e0c-132">**TotalPrice**: waluta</span><span class="sxs-lookup"><span data-stu-id="d3e0c-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="d3e0c-133">W polu **Nazwa** w panelu w okienku bocznym zmień nazwę źródła danych z **Query** na **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="d3e0c-134">Zapisz źródło danych.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-134">Save the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="d3e0c-135">Przetwarzaj dane klientów ze schematu lojalnościowego</span><span class="sxs-lookup"><span data-stu-id="d3e0c-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="d3e0c-136">Utwórz źródło danych o nazwie **LoyaltyScheme**, wybierz opcję importowania i wybierz łącznik typu **tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="d3e0c-137">Wprowadź adres URL eCommerce kontaktów https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="d3e0c-138">Podczas edytowania danych wybierz opcję **Przekształć** i **Użyj pierwszego wiersza jako nagłówków**.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="d3e0c-139">Zaktualizuj typ danych dla kolumn wymienionych poniżej:</span><span class="sxs-lookup"><span data-stu-id="d3e0c-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="d3e0c-140">**DateOfBirth**: Data</span><span class="sxs-lookup"><span data-stu-id="d3e0c-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="d3e0c-141">**RewardsPoints**: Pełny numer</span><span class="sxs-lookup"><span data-stu-id="d3e0c-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="d3e0c-142">**CreatedOn**: Data/godzina</span><span class="sxs-lookup"><span data-stu-id="d3e0c-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="d3e0c-143">W polu **Nazwa** w panelu po prawej stronie zmień nazwę źródła danych z **Query** na **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="d3e0c-144">Zapisz źródło danych.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-144">Save the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="d3e0c-145">Zadanie 2 - ujednolicenie danych</span><span class="sxs-lookup"><span data-stu-id="d3e0c-145">Task 2 - Data unification</span></span>

<span data-ttu-id="d3e0c-146">Po pozyskaniu danych rozpoczynamy teraz proces **Mapa, dopasuj, scal** aby utworzyć ujednolicony profil klienta.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-146">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="d3e0c-147">Aby uzyskać więcej informacji, zobacz [Ujednolicenie danych](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="d3e0c-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="d3e0c-148">Mapuj</span><span class="sxs-lookup"><span data-stu-id="d3e0c-148">Map</span></span>

1. <span data-ttu-id="d3e0c-149">Po przyjęciu danych zmapuj kontakty z danych e-commerce i lojalności na popularne typy danych.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="d3e0c-150">Przejdź **Dane** > **Ujednolicanie** > **Mapuj**.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="d3e0c-151">Wybierz podmioty, które reprezentują profil klienta - **eCommerceContacts** i **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![ujednolicić źródła danych e-commerce i lojalności.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="d3e0c-153">Wybierz opcję **ContactId** jako klucz podstawowy dla opcji **eCommerceContacts** i **LoyaltyID** jako klucz podstawowy dla **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![ujednolicenie LoyaltyId jako klucza podstawowego.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="d3e0c-155">Dopasowywanie</span><span class="sxs-lookup"><span data-stu-id="d3e0c-155">Match</span></span>

1. <span data-ttu-id="d3e0c-156">Przejdź do karty **Dopasowywanie** i wybierz **Ustawianie kolejności**.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="d3e0c-157">Z listy rozwijanej **Głównej** wybierz pozycję **eCommerceContacts: eCommerce** jako źródło podstawowe i dołącz wszystkie rekordy.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="d3e0c-158">Z listy rozwijanej **Encja 2** wybierz **loyCustomers : LoyaltyScheme** i uwzględnij wszystkie rekordy.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Ujednolicenie dopasowania eCommerce i lojalności.](media/unify-match-order.png)

4. <span data-ttu-id="d3e0c-160">Wybierz **Tworzenie nowej reguły**</span><span class="sxs-lookup"><span data-stu-id="d3e0c-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="d3e0c-161">Dodanie pierwszego warunku za pomocą narzędzia FullName.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="d3e0c-162">Dla elementu eCommerceContacts wybierz pozycję **FullName** z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="d3e0c-163">Dla elementu loyCustomers wybierz pozycję **FullName** z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="d3e0c-164">Wybierz menu rozwiajne **Normalizuj** i wybierz **Typ (telefon, nazwa, adres,...)**.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="d3e0c-165">Ustawianie **Poziomu dokładności**: **Podstawowe** i **Wartość**: **Wysokie**.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="d3e0c-166">Wprowadź nazwę **FullName, Email** dla nowej reguły.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="d3e0c-167">Dodaj drugi warunek dla adresu e-mail, zaznaczając opcję **Dodaj warunek**</span><span class="sxs-lookup"><span data-stu-id="d3e0c-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="d3e0c-168">W przypadku encji eCommerceContacts wybierz opcję **E-mail** w polu listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="d3e0c-169">W przypadku encji loyCustomers wybierz opcję **E-mail** w polu listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="d3e0c-170">Pozostaw puste pole Normalizuj.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="d3e0c-171">Ustawianie **Poziomu dokładności**: **Podstawowe** i **Wartość**: **Wysokie**.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Należy ujednolicić regułę dotyczącą nazwy i adresu e-mail.](media/unify-match-rule.png)

7. <span data-ttu-id="d3e0c-173">Wybierz pozycję **Zapisz** i **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="d3e0c-174">Scalanie</span><span class="sxs-lookup"><span data-stu-id="d3e0c-174">Merge</span></span>

1. <span data-ttu-id="d3e0c-175">Przejdź na kartę **Scal**.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="d3e0c-176">W elemencie **ContactId** dla encji **loyCustomers** zmień nazwę wyświetlaną na **ContactIdLOYALTY**, aby odróżnić ją od innych przetwarzanych identyfikatorów.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![Zmień nazwę ContactID na identyfikator lojalnościowy.](media/unify-merge-contactid.png)

1. <span data-ttu-id="d3e0c-178">Kliknij przycisk **Zapisz** i **Uruchom**, aby rozpocząć proces scalania.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="d3e0c-179">Zadanie 3 — Konfigurowanie rekomendacji przewidywanie</span><span class="sxs-lookup"><span data-stu-id="d3e0c-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="d3e0c-180">Dzięki ujednoliconym profilom klienta można teraz uruchomić przewidywanie subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="d3e0c-181">Przejdź do **Analizy** > **Przewidywania** i wybierz **Rekomendacje produktów**.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="d3e0c-182">Wybierz **Rozpocznij**.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-182">Select **Get started**.</span></span>

1. <span data-ttu-id="d3e0c-183">Nazwij **Model rekomendacji produktu OOB przewidywanie** i encji wyjściowej **OOBProductRecommendationModelPrediction**.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="d3e0c-184">Zdefiniować trzy warunki dotyczące modelu:</span><span class="sxs-lookup"><span data-stu-id="d3e0c-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="d3e0c-185">**Liczba produktów**: ustaw tę wartość na **5**.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="d3e0c-186">To ustawienie określa, ile produktów ma być zalecane dla klientów.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="d3e0c-187">**Sugestie dotyczące produktów, które zostały ostatnio zakupione?**: Wybierz opcję **Tak**, aby wskazać, że produkty mają zostać zakupione wcześniej przez klientów.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-187">**Suggest products customers have recently purchased?**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="d3e0c-188">**Okno wglądu w przeszłość**: wybierz co najmniej **365 dni**.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="d3e0c-189">To ustawienie definiuje, jak daleko model spojrzy wstecz na aktywność klienta, aby użyć go jako danych wejściowych do jego zaleceń.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modelowe preferencje dotyczące modelu rekomendacji produktów.":::

1. <span data-ttu-id="d3e0c-191">Wybierz **Wymagane dane** i wybierz pozycję **Dodaj dane** dla historii zakupów.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="d3e0c-192">Dodaj encję **eCommercePurchases : eCommerce** i zamapuj pola z eCommerce na odpowiadające im pola wymagane przez model.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="d3e0c-193">Dołącz do encji **eCommercePurchases: eCommerce** o identyfikatorze **eCommerceContacts: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Dołączanie encji eCommerce.](media/model-purchase-join.png)

1. <span data-ttu-id="d3e0c-195">Wybierz przycisk **Dalej**, aby ustawić harmonogram modelu.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="d3e0c-196">Model musi regularnie trenować, aby uczyć się nowych wzorców, gdy są pozyskiwane nowe dane.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="d3e0c-197">Na potrzeby tego przykładu wybierz pozycję **Miesięczny**.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="d3e0c-198">Po przejrzeniu wszystkich szczegółów wybierz pozycję **Zapisz i uruchom**.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="d3e0c-199">Zadanie 4 - Przejrzyj wyniki i wyjaśnienia modelu</span><span class="sxs-lookup"><span data-stu-id="d3e0c-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="d3e0c-200">Pozwól modelowi ukończyć uczenie i ocenianie danych.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="d3e0c-201">Możesz teraz przejrzeć objaśnienia dotyczące modelu rekomendacji produktów.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="d3e0c-202">Aby uzyskać więcej informacji, zobacz temat [Przejrzyj stan i wyniki prognozy](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="d3e0c-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="d3e0c-203">Zadanie 5 — Tworzenie segmentu wysoko zakupionych produktów</span><span class="sxs-lookup"><span data-stu-id="d3e0c-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="d3e0c-204">Uruchomienie modelu produkcyjnego tworzy nową jednostkę, którą możesz zobaczyć **Dane** > **Encje**.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="d3e0c-205">Możesz utworzyć nowy segment na podstawie encji utworzonej przez model.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="d3e0c-206">Przejdź do **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-206">Go to **Segments**.</span></span> <span data-ttu-id="d3e0c-207">Wybierz opcję **Nowy** i wybierz pozycję **Utwórz z poziomu** > **Analizy**.</span><span class="sxs-lookup"><span data-stu-id="d3e0c-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Tworzenie segmentu z wynikiem modelu.](media/segment-intelligence.png)

1. <span data-ttu-id="d3e0c-209">Wybierz opcję **OOBProductRecommendationModelPrediction** punkt końcowy i zdefiniuj segment:</span><span class="sxs-lookup"><span data-stu-id="d3e0c-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="d3e0c-210">Pole: ProductID</span><span class="sxs-lookup"><span data-stu-id="d3e0c-210">Field: ProductID</span></span>
   - <span data-ttu-id="d3e0c-211">Operator: wartość</span><span class="sxs-lookup"><span data-stu-id="d3e0c-211">Operator: Value</span></span>
   - <span data-ttu-id="d3e0c-212">Wartość: Wybierz trzy pierwsze identyfikatory produktów</span><span class="sxs-lookup"><span data-stu-id="d3e0c-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Tworzenie segmentu na stronie wyników modelu.":::

<span data-ttu-id="d3e0c-214">Masz teraz dynamicznie aktualizowany segment, który identyfikuje klientów, którzy są bardziej skłonni do zakupu trzech najbardziej polecanych produktów</span><span class="sxs-lookup"><span data-stu-id="d3e0c-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="d3e0c-215">Aby uzyskać więcej informacji, zobacz [Tworzenie segmentów i zarządzanie nimi](segments.md).</span><span class="sxs-lookup"><span data-stu-id="d3e0c-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]