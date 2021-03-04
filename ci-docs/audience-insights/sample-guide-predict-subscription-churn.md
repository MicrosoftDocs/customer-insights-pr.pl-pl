---
title: Przykładowy przewodnik dotyczący prognozowania rezygnacji z subskrypcji
description: Skorzystaj z tego przykładowego przewodnika, aby wypróbować gotowy model prognozowania rezygnacji z subskrypcji.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3f1019ace424f89320c5a0d5058e928f4cbc7e62
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269850"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="aff78-103">Przykładowy przewodnik dotyczący prognozowania rezygnacji z subskrypcji (wersja zapozawcza)</span><span class="sxs-lookup"><span data-stu-id="aff78-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="aff78-104">Przeprowadzimy Cię przez cały przewodnik przewidywania rezygnacji z subskrypcji, korzystając z przykładowych danych podanych poniżej.</span><span class="sxs-lookup"><span data-stu-id="aff78-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="aff78-105">Scenariusz</span><span class="sxs-lookup"><span data-stu-id="aff78-105">Scenario</span></span>

<span data-ttu-id="aff78-106">Contoso to firma produkująca wysokiej jakości ekspresy do kawy i ekspresy do kawy, które sprzedają za pośrednictwem swojej witryny internetowej Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="aff78-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="aff78-107">Ostatnio rozpoczęły działalność subskrypcyjną, aby klienci regularnie otrzymywali kawę.</span><span class="sxs-lookup"><span data-stu-id="aff78-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="aff78-108">Ich celem jest zrozumienie, którzy subskrybenci mogą anulować subskrypcję w ciągu najbliższych kilku miesięcy.</span><span class="sxs-lookup"><span data-stu-id="aff78-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="aff78-109">Wiedza o tym, który z ich klientów **prawdopodobnie odejdzie**, może pomóc im zaoszczędzić wysiłki marketingowe, koncentrując się na ich utrzymaniu.</span><span class="sxs-lookup"><span data-stu-id="aff78-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="aff78-110">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="aff78-110">Prerequisites</span></span>

- <span data-ttu-id="aff78-111">Co najmniej [Uprawnienia współautora](permissions.md) w Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="aff78-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="aff78-112">Zaleca się, aby zaimplementować poniższe kroki [w nowym środowisku](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="aff78-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="aff78-113">Zadanie 1 - pozyskiwanie danych</span><span class="sxs-lookup"><span data-stu-id="aff78-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="aff78-114">Przejrzyj szczególnie artykuły [dotyczące spożywania danych](data-sources.md) i [importowania źródeł danych przy użyciu łączników Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="aff78-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="aff78-115">Poniższe informacje zakładają, że znasz ogólne zasady przetwarzania danych.</span><span class="sxs-lookup"><span data-stu-id="aff78-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="aff78-116">Pozyskiwanie danych klienta na platformie eCommerce</span><span class="sxs-lookup"><span data-stu-id="aff78-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="aff78-117">Utwórz źródło danych o nazwie **eCommerce**, wybierz opcję importowania i wybierz łącznik typu **tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="aff78-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="aff78-118">Wprowadź adres URL eCommerce kontaktów https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="aff78-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="aff78-119">Podczas edytowania danych wybierz opcję **Przekształć** i **Użyj pierwszego wiersza jako nagłówków**.</span><span class="sxs-lookup"><span data-stu-id="aff78-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="aff78-120">Zaktualizuj typ danych dla kolumn wymienionych poniżej:</span><span class="sxs-lookup"><span data-stu-id="aff78-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="aff78-121">**DateOfBirth**: Data</span><span class="sxs-lookup"><span data-stu-id="aff78-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="aff78-122">**CreatedOn**: Data/Czas/Strefa</span><span class="sxs-lookup"><span data-stu-id="aff78-122">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Przekształcić datę urodzenia na datę.":::

1. <span data-ttu-id="aff78-124">W polu **Nazwa** w panelu po prawej stronie zmień nazwę źródła danych z **Query** na **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="aff78-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="aff78-125">Zapisz źródło danych.</span><span class="sxs-lookup"><span data-stu-id="aff78-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="aff78-126">Przetwarzaj dane klientów ze schematu lojalnościowego</span><span class="sxs-lookup"><span data-stu-id="aff78-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="aff78-127">Utwórz źródło danych o nazwie **LoyaltyScheme**, wybierz opcję importowania i wybierz łącznik typu **tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="aff78-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="aff78-128">Wprowadź adres URL eCommerce kontaktów https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="aff78-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="aff78-129">Podczas edytowania danych wybierz opcję **Przekształć** i **Użyj pierwszego wiersza jako nagłówków**.</span><span class="sxs-lookup"><span data-stu-id="aff78-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="aff78-130">Zaktualizuj typ danych dla kolumn wymienionych poniżej:</span><span class="sxs-lookup"><span data-stu-id="aff78-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="aff78-131">**DateOfBirth**: Data</span><span class="sxs-lookup"><span data-stu-id="aff78-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="aff78-132">**RewardsPoints**: Pełny numer</span><span class="sxs-lookup"><span data-stu-id="aff78-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="aff78-133">**CreatedOn**: Data/godzina</span><span class="sxs-lookup"><span data-stu-id="aff78-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="aff78-134">W polu **Nazwa** w panelu po prawej stronie zmień nazwę źródła danych z **Query** na **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="aff78-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="aff78-135">Zapisz źródło danych.</span><span class="sxs-lookup"><span data-stu-id="aff78-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="aff78-136">Przetwarzaj informacje o subskrypcji</span><span class="sxs-lookup"><span data-stu-id="aff78-136">Ingest subscription information</span></span>

1. <span data-ttu-id="aff78-137">Utwórz źródło danych o nazwie **SubscriptionHistory**, wybierz opcję importowania i wybierz łącznik typu **tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="aff78-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="aff78-138">Wprowadź adres URL eCommerce kontaktów https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="aff78-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="aff78-139">Podczas edytowania danych wybierz opcję **Przekształć** i **Użyj pierwszego wiersza jako nagłówków**.</span><span class="sxs-lookup"><span data-stu-id="aff78-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="aff78-140">Zaktualizuj typ danych dla kolumn wymienionych poniżej:</span><span class="sxs-lookup"><span data-stu-id="aff78-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="aff78-141">**SubscriptioID**: Pełny numer</span><span class="sxs-lookup"><span data-stu-id="aff78-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="aff78-142">**SubscriptionAmount**: waluta</span><span class="sxs-lookup"><span data-stu-id="aff78-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="aff78-143">**SubscriptionEndDate**: Data/godzina</span><span class="sxs-lookup"><span data-stu-id="aff78-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="aff78-144">**SubscriptionStartDate**: Data/godzina</span><span class="sxs-lookup"><span data-stu-id="aff78-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="aff78-145">**TransactionDate**: Data/godzina</span><span class="sxs-lookup"><span data-stu-id="aff78-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="aff78-146">**IsRecurring**: Prawda/Fałsz</span><span class="sxs-lookup"><span data-stu-id="aff78-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="aff78-147">**Is_auto_renew**: Prawda/fałsz</span><span class="sxs-lookup"><span data-stu-id="aff78-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="aff78-148">**RecurringFrequencyInMonths**: pełny numer</span><span class="sxs-lookup"><span data-stu-id="aff78-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="aff78-149">W polu **Nazwa** w panelu po prawej stronie zmień nazwę źródła danych z **Zapytanie** na **SubscriptionHistory**.</span><span class="sxs-lookup"><span data-stu-id="aff78-149">In the **Name** field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="aff78-150">Zapisz źródło danych.</span><span class="sxs-lookup"><span data-stu-id="aff78-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="aff78-151">Przetwarzaj dane klientów z recenzji witryn</span><span class="sxs-lookup"><span data-stu-id="aff78-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="aff78-152">Utwórz źródło danych o nazwie **Strona internetowa**, wybierz opcję importowania i wybierz łącznik typu **tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="aff78-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="aff78-153">Wprowadź adres URL eCommerce kontaktów https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="aff78-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="aff78-154">Podczas edytowania danych wybierz opcję **Przekształć** i **Użyj pierwszego wiersza jako nagłówków**.</span><span class="sxs-lookup"><span data-stu-id="aff78-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="aff78-155">Zaktualizuj typ danych dla kolumn wymienionych poniżej:</span><span class="sxs-lookup"><span data-stu-id="aff78-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="aff78-156">**ReviewRating**: Pełny numer</span><span class="sxs-lookup"><span data-stu-id="aff78-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="aff78-157">**ReviewDate**: Data</span><span class="sxs-lookup"><span data-stu-id="aff78-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="aff78-158">WW polu „Nazwa” w panelu po prawej stronie zmień nazwę źródła danych z **Query** na **webReviews**.</span><span class="sxs-lookup"><span data-stu-id="aff78-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="aff78-159">Zadanie 2 - ujednolicenie danych</span><span class="sxs-lookup"><span data-stu-id="aff78-159">Task 2 - Data unification</span></span>

<span data-ttu-id="aff78-160">Po pozyskaniu danych rozpoczynamy teraz proces **Mapa, dopasuj, scal** aby utworzyć ujednolicony profil klienta.</span><span class="sxs-lookup"><span data-stu-id="aff78-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="aff78-161">Aby uzyskać więcej informacji, zobacz [Ujednolicenie danych](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="aff78-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="aff78-162">Mapuj</span><span class="sxs-lookup"><span data-stu-id="aff78-162">Map</span></span>

1. <span data-ttu-id="aff78-163">Po przyjęciu danych zmapuj kontakty z danych e-commerce i lojalności na popularne typy danych.</span><span class="sxs-lookup"><span data-stu-id="aff78-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="aff78-164">Przejdź **Dane** > **Ujednolicanie** > **Mapuj**.</span><span class="sxs-lookup"><span data-stu-id="aff78-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="aff78-165">Wybierz podmioty, które reprezentują profil klienta - **eCommerceContacts** i **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="aff78-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="ujednolicić źródła danych e-commerce i lojalności.":::

1. <span data-ttu-id="aff78-167">Wybierz opcję **ContactId** jako klucz podstawowy dla opcji **eCommerceContacts** i **LoyaltyID** jako klucz podstawowy dla **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="aff78-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="ujednolicenie LoyaltyId jako klucza podstawowego.":::

### <a name="match"></a><span data-ttu-id="aff78-169">Dopasowywanie</span><span class="sxs-lookup"><span data-stu-id="aff78-169">Match</span></span>

1. <span data-ttu-id="aff78-170">Przejdź do karty **Dopasowywanie** i wybierz **Ustawianie kolejności**.</span><span class="sxs-lookup"><span data-stu-id="aff78-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="aff78-171">Z listy rozwijanej **Głównej** wybierz pozycję **eCommerceContacts: eCommerce** jako źródło podstawowe i dołącz wszystkie rekordy.</span><span class="sxs-lookup"><span data-stu-id="aff78-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="aff78-172">Z listy rozwijanej **Encja 2** wybierz **loyCustomers : LoyaltyScheme** i uwzględnij wszystkie rekordy.</span><span class="sxs-lookup"><span data-stu-id="aff78-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Ujednolicenie dopasowania eCommerce i lojalności.":::

1. <span data-ttu-id="aff78-174">Wybierz **Tworzenie nowej reguły**</span><span class="sxs-lookup"><span data-stu-id="aff78-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="aff78-175">Dodanie pierwszego warunku za pomocą narzędzia FullName.</span><span class="sxs-lookup"><span data-stu-id="aff78-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="aff78-176">Dla elementu eCommerceContacts wybierz pozycję **FullName** z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="aff78-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="aff78-177">Dla elementu loyCustomers wybierz pozycję **FullName** z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="aff78-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="aff78-178">Wybierz menu rozwiajne **Normalizuj** i wybierz **Typ (telefon, nazwa, adres,...)**.</span><span class="sxs-lookup"><span data-stu-id="aff78-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="aff78-179">Ustawianie **Poziomu dokładności**: **Podstawowe** i **Wartość**: **Wysokie**.</span><span class="sxs-lookup"><span data-stu-id="aff78-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="aff78-180">Wprowadź nazwę **FullName, Email** dla nowej reguły.</span><span class="sxs-lookup"><span data-stu-id="aff78-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="aff78-181">Dodaj drugi warunek dla adresu e-mail, zaznaczając opcję **Dodaj warunek**</span><span class="sxs-lookup"><span data-stu-id="aff78-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="aff78-182">W przypadku encji eCommerceContacts wybierz opcję **E-mail** w polu listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="aff78-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="aff78-183">W przypadku encji loyCustomers wybierz opcję **E-mail** w polu listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="aff78-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="aff78-184">Pozostaw puste pole Normalizuj.</span><span class="sxs-lookup"><span data-stu-id="aff78-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="aff78-185">Ustawianie **Poziomu dokładności**: **Podstawowe** i **Wartość**: **Wysokie**.</span><span class="sxs-lookup"><span data-stu-id="aff78-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Należy ujednolicić regułę dotyczącą nazwy i adresu e-mail.":::

7. <span data-ttu-id="aff78-187">Wybierz pozycję **Zapisz** i **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="aff78-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="aff78-188">Scalanie</span><span class="sxs-lookup"><span data-stu-id="aff78-188">Merge</span></span>

1. <span data-ttu-id="aff78-189">Przejdź na kartę **Scal**.</span><span class="sxs-lookup"><span data-stu-id="aff78-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="aff78-190">W elemencie **ContactId** dla encji **loyCustomers** zmień nazwę wyświetlaną na **ContactIdLOYALTY**, aby odróżnić ją od innych przetwarzanych identyfikatorów.</span><span class="sxs-lookup"><span data-stu-id="aff78-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="Zmień nazwę ContactID na identyfikator lojalnościowy.":::

1. <span data-ttu-id="aff78-192">Kliknij przycisk **Zapisz** i **Uruchom**, aby rozpocząć proces scalania.</span><span class="sxs-lookup"><span data-stu-id="aff78-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="aff78-193">Zadanie 3 - Skonfiguruj przewidywanie rezygnacji z subskrypcji</span><span class="sxs-lookup"><span data-stu-id="aff78-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="aff78-194">Dzięki ujednoliconym profilom klienta można teraz uruchomić przewidywanie subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="aff78-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="aff78-195">Aby zapoznać się ze szczegółowymi krokami, zobacz artykuł [Przewidywanie rezygnacji z subskrypcji (wersja zapoznawcza)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="aff78-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="aff78-196">Wybierz **Analizy** > **Wykryj** i wybierz korzystanie z **Model rezygnacji klientów**.</span><span class="sxs-lookup"><span data-stu-id="aff78-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="aff78-197">Wybierz opcję **Subskrypcja** i wybierz pozycję **Rozpocznij pracę**.</span><span class="sxs-lookup"><span data-stu-id="aff78-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="aff78-198">Nazwij model **Przewidywanie rezygnacji z subskrypcji OOB**, a następnie encję wyjściową **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="aff78-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="aff78-199">Zdefiniować dwa warunki dotyczące modelu rezygnacji:</span><span class="sxs-lookup"><span data-stu-id="aff78-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="aff78-200">**Liczba dni od zakończenia subskrypcji**: **co najmniej 60** dni.</span><span class="sxs-lookup"><span data-stu-id="aff78-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="aff78-201">Jeśli klient nie odnowi subskrypcji w tym okresie po zakończeniu subskrypcji, zostanie uznany za rezygnującego.</span><span class="sxs-lookup"><span data-stu-id="aff78-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="aff78-202">**Definicja rezygnacji**: **co najmniej 93** dni.</span><span class="sxs-lookup"><span data-stu-id="aff78-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="aff78-203">Czas trwania modelu przewidywania, którzy klienci mogą odejść.</span><span class="sxs-lookup"><span data-stu-id="aff78-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="aff78-204">Im dalej w przyszłości spojrzysz, tym mniej dokładne wyniki.</span><span class="sxs-lookup"><span data-stu-id="aff78-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Wybierz dźwignie modelu Okno predykcji i Definicja rezygnacji.":::

1. <span data-ttu-id="aff78-206">Wybierz **Dodaj wymagane dane** i wybierz pozycję **Dodaj dane** dla historii subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="aff78-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="aff78-207">Dodaj encję **Subskrypcja : SubscriptionHistory** i zamapuj pola z eCommerce na odpowiadające im pola wymagane przez model.</span><span class="sxs-lookup"><span data-stu-id="aff78-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="aff78-208">Połącz encję **Subskrypcja : SubscriptionHistory** z encją **eCommerceContacts: eCommerce**, nazwij relację **eCommerceSubscription**.</span><span class="sxs-lookup"><span data-stu-id="aff78-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Dołączanie encji eCommerce.":::

1. <span data-ttu-id="aff78-210">W obszarze Działania klienta dodaj encję **webReviews: Website** i zamapuj pola z webReviews na odpowiednie pola wymagane przez model.</span><span class="sxs-lookup"><span data-stu-id="aff78-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="aff78-211">Klucz podstawowy: ReviewId</span><span class="sxs-lookup"><span data-stu-id="aff78-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="aff78-212">Znacznik czasu: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="aff78-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="aff78-213">Zdarzenie: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="aff78-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="aff78-214">Skonfiguruj działanie dotyczące recenzji witryn.</span><span class="sxs-lookup"><span data-stu-id="aff78-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="aff78-215">Wybierz **Przegląd** działań i dołącz do encji **webReviews : Website** z **eCommerceContacts: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="aff78-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="aff78-216">Wybierz przycisk **Dalej**, aby ustawić harmonogram modelu.</span><span class="sxs-lookup"><span data-stu-id="aff78-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="aff78-217">Model musi regularnie trenować, aby uczyć się nowych wzorców, gdy są pozyskiwane nowe dane.</span><span class="sxs-lookup"><span data-stu-id="aff78-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="aff78-218">Na potrzeby tego przykładu wybierz pozycję **Miesięczny**.</span><span class="sxs-lookup"><span data-stu-id="aff78-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="aff78-219">Po przejrzeniu wszystkich szczegółów wybierz pozycję **Zapisz i uruchom**.</span><span class="sxs-lookup"><span data-stu-id="aff78-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="aff78-220">Zadanie 4 - Przejrzyj wyniki i wyjaśnienia modelu</span><span class="sxs-lookup"><span data-stu-id="aff78-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="aff78-221">Pozwól modelowi ukończyć uczenie i ocenianie danych.</span><span class="sxs-lookup"><span data-stu-id="aff78-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="aff78-222">Możesz teraz przejrzeć wyjaśnienia dotyczące modelu rezygnacji z subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="aff78-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="aff78-223">Aby uzyskać więcej informacji, zobacz temat [Przejrzyj stan i wyniki prognozy](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="aff78-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="aff78-224">Zadanie 5 - Utwórz segment klientów o wysokim ryzyku rezygnacji</span><span class="sxs-lookup"><span data-stu-id="aff78-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="aff78-225">Uruchomienie modelu produkcyjnego tworzy nową jednostkę, którą możesz zobaczyć **Dane** > **Encje**.</span><span class="sxs-lookup"><span data-stu-id="aff78-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="aff78-226">Możesz utworzyć nowy segment na podstawie encji utworzonej przez model.</span><span class="sxs-lookup"><span data-stu-id="aff78-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="aff78-227">Przejdź do **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="aff78-227">Go to **Segments**.</span></span> <span data-ttu-id="aff78-228">Wybierz opcję **Nowy** i wybierz pozycję **Utwórz z poziomu** > **Analizy**.</span><span class="sxs-lookup"><span data-stu-id="aff78-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Tworzenie segmentu z wynikiem modelu.":::

1. <span data-ttu-id="aff78-230">Wybierz opcję **OOBSubscriptionChurnPrediction** punkt końcowy i zdefiniuj segment:</span><span class="sxs-lookup"><span data-stu-id="aff78-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="aff78-231">Pole: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="aff78-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="aff78-232">Operator: większy niż</span><span class="sxs-lookup"><span data-stu-id="aff78-232">Operator: greater than</span></span>
   - <span data-ttu-id="aff78-233">Wartość: 0.6</span><span class="sxs-lookup"><span data-stu-id="aff78-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Skonfiguruj segment rezygnacji z subskrypcji.":::

<span data-ttu-id="aff78-235">Masz teraz dynamicznie aktualizowany segment, który identyfikuje klientów o wysokim ryzyku rezygnacji z subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="aff78-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="aff78-236">Aby uzyskać więcej informacji, zobacz [Tworzenie segmentów i zarządzanie nimi](segments.md).</span><span class="sxs-lookup"><span data-stu-id="aff78-236">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]