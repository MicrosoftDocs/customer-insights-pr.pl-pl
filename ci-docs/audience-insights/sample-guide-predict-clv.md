---
title: Przykładowy przewodnik po prognozowaniu wartości całego cyklu życia klienta
description: Skorzystaj z tego przykładowego przewodnika, aby wypróbować model predykcji customer lifetime value.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 73d294a285b4ad706bec7fe925c1daa0b839ddd6
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129958"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="f833a-103">Przykładowy przewodnik po prognozowaniu wartości całego cyklu życia klienta (CLV)</span><span class="sxs-lookup"><span data-stu-id="f833a-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="f833a-104">Ten przewodnik przeprowadzi Cię przez cały przykład przewidywania okresu istnienia klienta (CLV) w Customer Insights na podstawie przykładowych danych.</span><span class="sxs-lookup"><span data-stu-id="f833a-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="f833a-105">Scenariusz</span><span class="sxs-lookup"><span data-stu-id="f833a-105">Scenario</span></span>

<span data-ttu-id="f833a-106">Contoso to firma, która produkuje wysokiej jakości kawę i ekspresy do kawy.</span><span class="sxs-lookup"><span data-stu-id="f833a-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="f833a-107">Sprzedają produkty za pośrednictwem swojej strony internetowej Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="f833a-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="f833a-108">Firma chce zrozumieć wartość (przychód), jaką jej klienci mogą wygenerować w ciągu najbliższych 12 miesięcy.</span><span class="sxs-lookup"><span data-stu-id="f833a-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="f833a-109">Znajomość oczekiwanej wartości klientów w ciągu najbliższych 12 miesięcy pomoże im ukierunkować działania marketingowe na klientów o wysokiej wartości.</span><span class="sxs-lookup"><span data-stu-id="f833a-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f833a-110">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="f833a-110">Prerequisites</span></span>

- <span data-ttu-id="f833a-111">Przynajmniej [uprawnienia Współautora](permissions.md) w zakresie analiz odbiorców.</span><span class="sxs-lookup"><span data-stu-id="f833a-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="f833a-112">Zaleca się, aby zaimplementować poniższe kroki [w nowym środowisku](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="f833a-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="f833a-113">Zadanie 1 - pozyskiwanie danych</span><span class="sxs-lookup"><span data-stu-id="f833a-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="f833a-114">Zapoznaj się z artykułami [na temat pobierania danych](data-sources.md) i [importowania źródeł danych za pomocą łączników Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="f833a-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="f833a-115">Poniższe informacje zakładają, że znasz ogólne zasady przetwarzania danych.</span><span class="sxs-lookup"><span data-stu-id="f833a-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="f833a-116">Pozyskiwanie danych klienta na platformie eCommerce</span><span class="sxs-lookup"><span data-stu-id="f833a-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="f833a-117">Utwórz źródło danych o nazwie **eCommerce**, wybierz opcję importowania i wybierz łącznik typu **tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="f833a-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="f833a-118">Wprowadź adres URL eCommerce kontaktów [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="f833a-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="f833a-119">Podczas edytowania danych wybierz opcję  **Przekształć**  i  **Użyj pierwszego wiersza jako nagłówków**.</span><span class="sxs-lookup"><span data-stu-id="f833a-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="f833a-120">Zaktualizuj typ danych dla kolumn wymienionych poniżej:</span><span class="sxs-lookup"><span data-stu-id="f833a-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="f833a-121">**DateOfBirth**: Data</span><span class="sxs-lookup"><span data-stu-id="f833a-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="f833a-122">**CreatedOn**: Data/Czas/Strefa</span><span class="sxs-lookup"><span data-stu-id="f833a-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Przekształcić datę urodzenia na datę.":::

1. <span data-ttu-id="f833a-124">WW polu „Nazwa” w panelu po prawej stronie zmień nazwę źródła danych z **Query** na **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="f833a-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="f833a-125">**Zapisz** źródło danych.</span><span class="sxs-lookup"><span data-stu-id="f833a-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="f833a-126">Przetwarzaj dane zakupów online</span><span class="sxs-lookup"><span data-stu-id="f833a-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="f833a-127">Dodanie nowego zestawu danych do tego samego źródła danych **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="f833a-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="f833a-128">Wybierz ponownie łącznik **tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="f833a-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="f833a-129">Wprowadź adres URL danych **Zakupów w trybie online** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="f833a-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="f833a-130">Podczas edytowania danych wybierz opcję **Przekształć** i **Użyj pierwszego wiersza jako nagłówków**.</span><span class="sxs-lookup"><span data-stu-id="f833a-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="f833a-131">Zaktualizuj typ danych dla kolumn wymienionych poniżej:</span><span class="sxs-lookup"><span data-stu-id="f833a-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="f833a-132">**PurchasedOn**: Data/godzina</span><span class="sxs-lookup"><span data-stu-id="f833a-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="f833a-133">**TotalPrice**: waluta</span><span class="sxs-lookup"><span data-stu-id="f833a-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="f833a-134">W polu **Nazwa** w panelu w okienku bocznym zmień nazwę źródła danych z **Query** na **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="f833a-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="f833a-135">**Zapisz** źródło danych.</span><span class="sxs-lookup"><span data-stu-id="f833a-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="f833a-136">Przetwarzaj dane klientów ze schematu lojalnościowego</span><span class="sxs-lookup"><span data-stu-id="f833a-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="f833a-137">Utwórz źródło danych o nazwie **LoyaltyScheme**, wybierz opcję importowania i wybierz łącznik typu **tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="f833a-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="f833a-138">Wprowadź adres URL eCommerce kontaktów https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="f833a-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="f833a-139">Podczas edytowania danych wybierz opcję **Przekształć** i **Użyj pierwszego wiersza jako nagłówków**.</span><span class="sxs-lookup"><span data-stu-id="f833a-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="f833a-140">Zaktualizuj typ danych dla kolumn wymienionych poniżej:</span><span class="sxs-lookup"><span data-stu-id="f833a-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="f833a-141">**DateOfBirth**: Data</span><span class="sxs-lookup"><span data-stu-id="f833a-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="f833a-142">**RewardsPoints**: Pełny numer</span><span class="sxs-lookup"><span data-stu-id="f833a-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="f833a-143">**CreatedOn**: Data/godzina</span><span class="sxs-lookup"><span data-stu-id="f833a-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="f833a-144">W polu **Nazwa** w panelu po prawej stronie zmień nazwę źródła danych z **Query** na **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="f833a-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="f833a-145">**Zapisz** źródło danych.</span><span class="sxs-lookup"><span data-stu-id="f833a-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="f833a-146">Przetwarzaj dane klientów z recenzji witryn</span><span class="sxs-lookup"><span data-stu-id="f833a-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="f833a-147">Utwórz źródło danych o nazwie **Strona internetowa**, wybierz opcję importowania i wybierz łącznik typu **tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="f833a-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="f833a-148">Wprowadź adres URL eCommerce kontaktów https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="f833a-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="f833a-149">Podczas edytowania danych wybierz opcję **Przekształć** i **Użyj pierwszego wiersza jako nagłówków**.</span><span class="sxs-lookup"><span data-stu-id="f833a-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="f833a-150">Zaktualizuj typ danych dla kolumn wymienionych poniżej:</span><span class="sxs-lookup"><span data-stu-id="f833a-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="f833a-151">**ReviewRating**: Liczba dziesiętna</span><span class="sxs-lookup"><span data-stu-id="f833a-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="f833a-152">**ReviewDate**: Data</span><span class="sxs-lookup"><span data-stu-id="f833a-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="f833a-153">W polu „Nazwa” w prawym panelu zmień nazwę źródła danych z **Zapytanie** na **Recenzje**.</span><span class="sxs-lookup"><span data-stu-id="f833a-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="f833a-154">**Zapisz** źródło danych.</span><span class="sxs-lookup"><span data-stu-id="f833a-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="f833a-155">Zadanie 2 - ujednolicenie danych</span><span class="sxs-lookup"><span data-stu-id="f833a-155">Task 2 - Data unification</span></span>

<span data-ttu-id="f833a-156">Po przyswojeniu danych rozpoczynamy proces ujednolicenia danych w celu utworzenia ujednoliconego profilu klienta.</span><span class="sxs-lookup"><span data-stu-id="f833a-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="f833a-157">Aby uzyskać więcej informacji, zobacz [Ujednolicenie danych](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="f833a-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="f833a-158">Mapuj</span><span class="sxs-lookup"><span data-stu-id="f833a-158">Map</span></span>

1. <span data-ttu-id="f833a-159">Po przyjęciu danych zmapuj kontakty z danych e-commerce i lojalności na popularne typy danych.</span><span class="sxs-lookup"><span data-stu-id="f833a-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="f833a-160">Przejdź **Dane** > **Ujednolicanie** > **Mapuj**.</span><span class="sxs-lookup"><span data-stu-id="f833a-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="f833a-161">Wybierz podmioty, które reprezentują profil klienta - **eCommerceContacts** i **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="f833a-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="f833a-162">Następnie wybierz pozycję **Zastosuj**.</span><span class="sxs-lookup"><span data-stu-id="f833a-162">Then, select **Apply**.</span></span>

   ![ujednolicić źródła danych e-commerce i lojalności.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="f833a-164">Wybierz opcję **ContactId** jako klucz podstawowy dla opcji **eCommerceContacts** i **LoyaltyID** jako klucz podstawowy dla **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="f833a-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![ujednolicenie LoyaltyId jako klucza podstawowego.](media/unify-loyaltyid.png)

1. <span data-ttu-id="f833a-166">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f833a-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="f833a-167">Dopasowywanie</span><span class="sxs-lookup"><span data-stu-id="f833a-167">Match</span></span>

1. <span data-ttu-id="f833a-168">Przejdź do karty **Dopasowywanie** i wybierz **Ustawianie kolejności**.</span><span class="sxs-lookup"><span data-stu-id="f833a-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="f833a-169">Z listy rozwijanej **Głównej** wybierz pozycję **eCommerceContacts: eCommerce** jako źródło podstawowe i dołącz wszystkie rekordy.</span><span class="sxs-lookup"><span data-stu-id="f833a-169">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="f833a-170">Z listy rozwijanej **Encja 2** wybierz **loyCustomers : LoyaltyScheme** i uwzględnij wszystkie rekordy.</span><span class="sxs-lookup"><span data-stu-id="f833a-170">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Ujednolicenie dopasowania eCommerce i lojalności.](media/unify-match-order.png)

1. <span data-ttu-id="f833a-172">Wybierz **Dodaj regułę**</span><span class="sxs-lookup"><span data-stu-id="f833a-172">Select **Add rule**</span></span>

1. <span data-ttu-id="f833a-173">Dodanie pierwszego warunku za pomocą narzędzia FullName.</span><span class="sxs-lookup"><span data-stu-id="f833a-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="f833a-174">Dla elementu eCommerceContacts wybierz pozycję **FullName** z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="f833a-174">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="f833a-175">Dla elementu loyCustomers wybierz pozycję **FullName** z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="f833a-175">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="f833a-176">Wybierz menu rozwiajne **Normalizuj** i wybierz **Typ (telefon, nazwa, adres,...)**.</span><span class="sxs-lookup"><span data-stu-id="f833a-176">Select the **Normalize** drop-down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="f833a-177">Ustawianie **Poziomu dokładności**: **Podstawowe** i **Wartość**: **Wysokie**.</span><span class="sxs-lookup"><span data-stu-id="f833a-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="f833a-178">Wprowadź nazwę **FullName, Email** dla nowej reguły.</span><span class="sxs-lookup"><span data-stu-id="f833a-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="f833a-179">Dodaj drugi warunek dla adresu e-mail, zaznaczając opcję **Dodaj warunek**</span><span class="sxs-lookup"><span data-stu-id="f833a-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="f833a-180">W przypadku encji eCommerceContacts wybierz opcję **E-mail** w polu listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="f833a-180">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="f833a-181">W przypadku encji loyCustomers wybierz opcję **E-mail** w polu listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="f833a-181">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="f833a-182">Pozostaw puste pole Normalizuj.</span><span class="sxs-lookup"><span data-stu-id="f833a-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="f833a-183">Ustawianie **Poziomu dokładności**: **Podstawowe** i **Wartość**: **Wysokie**.</span><span class="sxs-lookup"><span data-stu-id="f833a-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Należy ujednolicić regułę dotyczącą nazwy i adresu e-mail.](media/unify-match-rule.png)

1. <span data-ttu-id="f833a-185">Wybierz pozycję **Gotowe**.</span><span class="sxs-lookup"><span data-stu-id="f833a-185">Select **Done**.</span></span>

1. <span data-ttu-id="f833a-186">Wybierz pozycję **Zapisz** i **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="f833a-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="f833a-187">Scalanie</span><span class="sxs-lookup"><span data-stu-id="f833a-187">Merge</span></span>

1. <span data-ttu-id="f833a-188">Przejdź na kartę **Scal**.</span><span class="sxs-lookup"><span data-stu-id="f833a-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="f833a-189">W elemencie **ContactId** dla encji **loyCustomers** zmień nazwę wyświetlaną na **ContactIdLOYALTY**, aby odróżnić ją od innych przetwarzanych identyfikatorów.</span><span class="sxs-lookup"><span data-stu-id="f833a-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![Zmień nazwę ContactID na identyfikator lojalnościowy.](media/unify-merge-contactid.png)

1. <span data-ttu-id="f833a-191">Wybierz **Zapisz** i **Uruchom scalanie i procesy podrzędne**.</span><span class="sxs-lookup"><span data-stu-id="f833a-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="f833a-192">Zadanie 3 — Skonfiguruj prognozę długookresowej wartości klienta</span><span class="sxs-lookup"><span data-stu-id="f833a-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="f833a-193">Dzięki ujednoliconym profilom klientów możemy teraz uruchomić przewidywanie wartości życia klienta.</span><span class="sxs-lookup"><span data-stu-id="f833a-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="f833a-194">Aby uzyskać szczegółowe informacje o krokach, zobacz temat [Wartość przewidywanie czasu życia klienta (wersja zapoznawcza)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="f833a-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="f833a-195">Przejdź do **Analizy**  > **Przewidywania** i wybierz **Model wartości okresu istnienia klienta**.</span><span class="sxs-lookup"><span data-stu-id="f833a-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="f833a-196">Przejdź przez informacje w okienku bocznym i wybierz **Rozpoczynanie pracy**.</span><span class="sxs-lookup"><span data-stu-id="f833a-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="f833a-197">Nazwij model **Przewidywanie OOB eCommerce CLV** i jednostkę wyjściową  **OOBeCommerceCLVPrediction**.</span><span class="sxs-lookup"><span data-stu-id="f833a-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="f833a-198">Zdefiniuj preferencje modelu dla modelu CLV:</span><span class="sxs-lookup"><span data-stu-id="f833a-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="f833a-199">**Czas przewidywania**: **12 miesięcy do roku 1**.</span><span class="sxs-lookup"><span data-stu-id="f833a-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="f833a-200">To ustawienie określa, jak daleko w przyszłość należy przewidzieć długoterminową wartość klienta.</span><span class="sxs-lookup"><span data-stu-id="f833a-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="f833a-201">**Aktywni klienci**: określ, co aktywni klienci oznaczają dla firmy.</span><span class="sxs-lookup"><span data-stu-id="f833a-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="f833a-202">Ustaw historyczny przedział czasowy, w którym klient musiał mieć co najmniej jedną transakcję, aby można go było uznać za aktywną.</span><span class="sxs-lookup"><span data-stu-id="f833a-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="f833a-203">Model będzie przewidywał tylko CLV dla aktywnych klientów.</span><span class="sxs-lookup"><span data-stu-id="f833a-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="f833a-204">Wybierz pomiędzy pozwoleniem modelowi na obliczenie okresu czasu na podstawie historycznych danych transakcji lub podaniem konkretnych ram czasowych.</span><span class="sxs-lookup"><span data-stu-id="f833a-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="f833a-205">W tym przykładowym przewodniku **załóżmy, że model oblicza interwał zakupu**, co jest opcją domyślną.</span><span class="sxs-lookup"><span data-stu-id="f833a-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="f833a-206">**Klienci o wysokiej wartości**: zdefiniuj klientów o wysokiej wartości jako wartość procentową klientów najwyższej klasy.</span><span class="sxs-lookup"><span data-stu-id="f833a-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="f833a-207">Model wykorzystuje te dane wejściowe, aby dostarczyć wyniki, które pasują do Twojej biznesowej definicji klientów o wysokiej wartości.</span><span class="sxs-lookup"><span data-stu-id="f833a-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="f833a-208">Możesz zdecydować, czy model definiuje klientów o wysokiej wartości.</span><span class="sxs-lookup"><span data-stu-id="f833a-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="f833a-209">Wykorzystuje regułę heurystyczną, która wyprowadza percentyl.</span><span class="sxs-lookup"><span data-stu-id="f833a-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="f833a-210">Możesz również zdefiniować klientów o wysokiej wartości jako procent najlepszych przyszłych płacących klientów.</span><span class="sxs-lookup"><span data-stu-id="f833a-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="f833a-211">W tym przykładowym przewodniku ręcznie definiujemy klientów o wysokiej wartości jako **najlepszych 30% aktywnych płacących klientów** i wybieramy **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="f833a-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Krok preferencji w doświadczeniu z przewodnikiem dla modelu CLV.":::

1. <span data-ttu-id="f833a-213">W kroku **Wymagane dane** wybierz opcję **Dodaj dane**, aby udostępnić dane historii transakcji.</span><span class="sxs-lookup"><span data-stu-id="f833a-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="f833a-214">Dodaj encję **eCommercePurchases : eCommerce** i zmapuj atrybuty wymagane przez model:</span><span class="sxs-lookup"><span data-stu-id="f833a-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="f833a-215">Identyfikator transakcji: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="f833a-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="f833a-216">Data transakcji: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="f833a-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="f833a-217">Kwota transakcji: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="f833a-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="f833a-218">Identyfikator produktu: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="f833a-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="f833a-219">Wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="f833a-219">Select **Next**.</span></span>

1. <span data-ttu-id="f833a-220">Konfigurowanie relacji między encją **eCommercePurchases : eCommerce** a encją **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="f833a-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="f833a-221">Krok **Dodatkowe dane (opcjonalnie)** umożliwia dodanie większej liczby danych dotyczących działań klienta.</span><span class="sxs-lookup"><span data-stu-id="f833a-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="f833a-222">Te dane mogą pomóc uzyskać więcej informacji na temat interakcji klientów z Twoją firmą, co może przyczynić się do CLV.</span><span class="sxs-lookup"><span data-stu-id="f833a-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="f833a-223">Dodanie kluczowych interakcji z klientami, takich jak dzienniki internetowe, dzienniki obsługi klienta lub historia programu nagród, może poprawić dokładność prognoz.</span><span class="sxs-lookup"><span data-stu-id="f833a-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="f833a-224">Wybierz opcję **Dodaj dane**, aby uwzględnić więcej danych dotyczących działań klienta.</span><span class="sxs-lookup"><span data-stu-id="f833a-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="f833a-225">Dodaj encję aktywności klienta i zmapuj jej nazwy pól na odpowiednie pola wymagane przez model:</span><span class="sxs-lookup"><span data-stu-id="f833a-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="f833a-226">Jednostka aktywności klienta: Recenzje:Strona internetowa</span><span class="sxs-lookup"><span data-stu-id="f833a-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="f833a-227">Klucz podstawowy: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="f833a-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="f833a-228">Timestamp: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="f833a-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="f833a-229">Zdarzenie (nazwa działania): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="f833a-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="f833a-230">Szczegóły (kwota lub wartość): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="f833a-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="f833a-231">Wybierz opcję **Dalej** i skonfiguruj działanie oraz relację między danymi transakcji a danymi klienta:</span><span class="sxs-lookup"><span data-stu-id="f833a-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="f833a-232">Typ aktywności: Wybierz istniejącą</span><span class="sxs-lookup"><span data-stu-id="f833a-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="f833a-233">Etykieta aktywności: Recenzja</span><span class="sxs-lookup"><span data-stu-id="f833a-233">Activity label: Review</span></span>
   - <span data-ttu-id="f833a-234">Odpowiadająca etykieta: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="f833a-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="f833a-235">Encja Klienta: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="f833a-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="f833a-236">Relacja: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="f833a-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="f833a-237">Wybierz przycisk **Dalej**, aby ustawić harmonogram modelu.</span><span class="sxs-lookup"><span data-stu-id="f833a-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="f833a-238">Model musi regularnie trenować, aby uczyć się nowych wzorców, gdy są pozyskiwane nowe dane.</span><span class="sxs-lookup"><span data-stu-id="f833a-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="f833a-239">W tym przykładzie wybierz pozycję **Miesięcznie**.</span><span class="sxs-lookup"><span data-stu-id="f833a-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="f833a-240">Po przejrzeniu wszystkich szczegółów wybierz pozycję **Zapisz i uruchom**.</span><span class="sxs-lookup"><span data-stu-id="f833a-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="f833a-241">Zadanie 4 - Przejrzyj wyniki i wyjaśnienia modelu</span><span class="sxs-lookup"><span data-stu-id="f833a-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="f833a-242">Pozwól modelowi ukończyć uczenie i ocenianie danych.</span><span class="sxs-lookup"><span data-stu-id="f833a-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="f833a-243">Następnie możesz przejrzeć wyniki i wyjaśnienia modelu CLV.</span><span class="sxs-lookup"><span data-stu-id="f833a-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="f833a-244">Aby uzyskać więcej informacji, zobacz temat [Przejrzyj stan i wyniki prognozy](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="f833a-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="f833a-245">Zadanie 5 — Tworzenie segmentu klientów o wysokiej wartości</span><span class="sxs-lookup"><span data-stu-id="f833a-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="f833a-246">Uruchomienie modelu powoduje utworzenie nowej encji wymienionej w **Dane** > **Encje**.</span><span class="sxs-lookup"><span data-stu-id="f833a-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="f833a-247">Możesz utworzyć nowy segment klientów na podstawie jednostki utworzonej przez model.</span><span class="sxs-lookup"><span data-stu-id="f833a-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="f833a-248">Przejdź do **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="f833a-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="f833a-249">Wybierz opcję **Nowy** i wybierz pozycję **Utwórz z poziomu** > **Analizy**.</span><span class="sxs-lookup"><span data-stu-id="f833a-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Tworzenie segmentu z wynikiem modelu.](media/segment-intelligence.png)

1. <span data-ttu-id="f833a-251">Wybierz encję **OOBeCommerceCLVPrediction** i zdefiniuj segment:</span><span class="sxs-lookup"><span data-stu-id="f833a-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="f833a-252">Pole: CLVScore</span><span class="sxs-lookup"><span data-stu-id="f833a-252">Field: CLVScore</span></span>
  - <span data-ttu-id="f833a-253">Operator: większy niż</span><span class="sxs-lookup"><span data-stu-id="f833a-253">Operator: greater than</span></span>
  - <span data-ttu-id="f833a-254">Wartość: 1500</span><span class="sxs-lookup"><span data-stu-id="f833a-254">Value: 1500</span></span>

1. <span data-ttu-id="f833a-255">Wybierz opcję **Przegląd** i **Zapisz** segment.</span><span class="sxs-lookup"><span data-stu-id="f833a-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="f833a-256">Masz teraz segment, który identyfikuje klientów, którzy według przewidywań wygenerują ponad 1500 USD przychodu w ciągu najbliższych 12 miesięcy.</span><span class="sxs-lookup"><span data-stu-id="f833a-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="f833a-257">Ten segment jest aktualizowany dynamicznie, jeśli pozyskuje się więcej danych.</span><span class="sxs-lookup"><span data-stu-id="f833a-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="f833a-258">Aby uzyskać więcej informacji, zobacz [Tworzenie segmentów i zarządzanie nimi](segments.md).</span><span class="sxs-lookup"><span data-stu-id="f833a-258">For more information, see [Create and manage segments](segments.md).</span></span>
