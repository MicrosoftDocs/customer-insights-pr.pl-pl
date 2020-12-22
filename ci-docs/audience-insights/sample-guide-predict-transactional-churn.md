---
title: Przykładowy przewodnik dotyczący prognozowania rezygnacji z transakcji
description: Skorzystaj z tego przykładowego przewodnika, aby wypróbować gotowy model prognozowania rezygnacji z transakcji.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 055708ed3f9f468cad83ecf976a460814bf05199
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643606"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="34528-103">Przykładowy przewodnik dotyczący prognozowania rezygnacji z transakcji (wersja zapozawcza)</span><span class="sxs-lookup"><span data-stu-id="34528-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="34528-104">Ten przewodnik przeprowadzi Cię przez kompleksowy przykład prognozowania rezygnacji z transakcji w usłudze Customer Insights przy użyciu danych podanych poniżej.</span><span class="sxs-lookup"><span data-stu-id="34528-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="34528-105">Wszystkie dane użyte w tym przewodniku nie są prawdziwymi danymi klientów i są częścią zestawu danych Contoso znajdującego się w środowisku *Wersja demonstracyjna* w ramach subskrypcji Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="34528-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="34528-106">Scenariusz</span><span class="sxs-lookup"><span data-stu-id="34528-106">Scenario</span></span>

<span data-ttu-id="34528-107">Contoso to firma produkująca wysokiej jakości ekspresy do kawy i ekspresy do kawy, które sprzedają za pośrednictwem swojej witryny internetowej Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="34528-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="34528-108">Ich celem jest wiedzieć, którzy klienci, którzy zazwyczaj kupują ich produkty regularnie, przestaną być aktywnymi klientami w ciągu najbliższych 60 dni.</span><span class="sxs-lookup"><span data-stu-id="34528-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="34528-109">Wiedza o tym, który z ich klientów **prawdopodobnie odejdzie**, może pomóc im zaoszczędzić wysiłki marketingowe, koncentrując się na ich utrzymaniu.</span><span class="sxs-lookup"><span data-stu-id="34528-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="34528-110">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="34528-110">Prerequisites</span></span>

- <span data-ttu-id="34528-111">Co najmniej [Uprawnienia współautora](permissions.md) w Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="34528-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="34528-112">Zaleca się, aby zaimplementować poniższe kroki [w nowym środowisku](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="34528-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="34528-113">Zadanie 1 - pozyskiwanie danych</span><span class="sxs-lookup"><span data-stu-id="34528-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="34528-114">Przejrzyj szczególnie artykuły [dotyczące spożywania danych](data-sources.md) i [importowania źródeł danych przy użyciu łączników Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="34528-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="34528-115">Poniższe informacje zakładają, że znasz ogólne zasady przetwarzania danych.</span><span class="sxs-lookup"><span data-stu-id="34528-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="34528-116">Pozyskiwanie danych klienta na platformie eCommerce</span><span class="sxs-lookup"><span data-stu-id="34528-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="34528-117">Utwórz źródło danych o nazwie **eCommerce**, wybierz opcję importowania i wybierz łącznik typu **tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="34528-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="34528-118">Wprowadź adres URL eCommerce kontaktów https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="34528-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="34528-119">Podczas edytowania danych wybierz opcję **Przekształć** i **Użyj pierwszego wiersza jako nagłówków**.</span><span class="sxs-lookup"><span data-stu-id="34528-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="34528-120">Zaktualizuj typ danych dla kolumn wymienionych poniżej:</span><span class="sxs-lookup"><span data-stu-id="34528-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="34528-121">**DateOfBirth**: Data</span><span class="sxs-lookup"><span data-stu-id="34528-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="34528-122">**CreatedOn**: Data/Czas/Strefa</span><span class="sxs-lookup"><span data-stu-id="34528-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="34528-123">![Przekształć datę urodzenia na datę](media/ecommerce-dob-date.PNG "przekształcić datę urodzenia na datę")</span><span class="sxs-lookup"><span data-stu-id="34528-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="34528-124">WW polu „Nazwa” w panelu po prawej stronie zmień nazwę źródła danych z **Query** na **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="34528-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="34528-125">Zapisz źródło danych.</span><span class="sxs-lookup"><span data-stu-id="34528-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="34528-126">Przetwarzaj dane zakupów online</span><span class="sxs-lookup"><span data-stu-id="34528-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="34528-127">Dodanie nowego zestawu danych do tego samego źródła danych **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="34528-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="34528-128">Wybierz ponownie łącznik **tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="34528-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="34528-129">Wprowadź adres URL danych **Zakupów w trybie online** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="34528-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="34528-130">Podczas edytowania danych wybierz opcję **Przekształć** i **Użyj pierwszego wiersza jako nagłówków**.</span><span class="sxs-lookup"><span data-stu-id="34528-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="34528-131">Zaktualizuj typ danych dla kolumn wymienionych poniżej:</span><span class="sxs-lookup"><span data-stu-id="34528-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="34528-132">**PurchasedOn**: Data/godzina</span><span class="sxs-lookup"><span data-stu-id="34528-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="34528-133">**TotalPrice**: waluta</span><span class="sxs-lookup"><span data-stu-id="34528-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="34528-134">WW polu „Nazwa” w panelu po prawej stronie zmień nazwę źródła danych z **Query** na **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="34528-134">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="34528-135">Zapisz źródło danych.</span><span class="sxs-lookup"><span data-stu-id="34528-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="34528-136">Przetwarzaj dane klientów ze schematu lojalnościowego</span><span class="sxs-lookup"><span data-stu-id="34528-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="34528-137">Utwórz źródło danych o nazwie **LoyaltyScheme**, wybierz opcję importowania i wybierz łącznik typu **tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="34528-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="34528-138">Wprowadź adres URL eCommerce kontaktów https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="34528-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="34528-139">Podczas edytowania danych wybierz opcję **Przekształć** i **Użyj pierwszego wiersza jako nagłówków**.</span><span class="sxs-lookup"><span data-stu-id="34528-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="34528-140">Zaktualizuj typ danych dla kolumn wymienionych poniżej:</span><span class="sxs-lookup"><span data-stu-id="34528-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="34528-141">**DateOfBirth**: Data</span><span class="sxs-lookup"><span data-stu-id="34528-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="34528-142">**RewardsPoints**: Pełny numer</span><span class="sxs-lookup"><span data-stu-id="34528-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="34528-143">**CreatedOn**: Data/godzina</span><span class="sxs-lookup"><span data-stu-id="34528-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="34528-144">WW polu „Nazwa” w panelu po prawej stronie zmień nazwę źródła danych z **Query** na **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="34528-144">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="34528-145">Zapisz źródło danych.</span><span class="sxs-lookup"><span data-stu-id="34528-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="34528-146">Zadanie 2 - ujednolicenie danych</span><span class="sxs-lookup"><span data-stu-id="34528-146">Task 2 - Data unification</span></span>

<span data-ttu-id="34528-147">Po pozyskaniu danych rozpoczynamy teraz proces **Mapa, dopasuj, scal** aby utworzyć ujednolicony profil klienta.</span><span class="sxs-lookup"><span data-stu-id="34528-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="34528-148">Aby uzyskać więcej informacji, zobacz [Ujednolicenie danych](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="34528-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="34528-149">Mapuj</span><span class="sxs-lookup"><span data-stu-id="34528-149">Map</span></span>

1. <span data-ttu-id="34528-150">Po przyjęciu danych zmapuj kontakty z danych e-commerce i lojalności na popularne typy danych.</span><span class="sxs-lookup"><span data-stu-id="34528-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="34528-151">Przejdź **Dane** > **Ujednolicanie** > **Mapuj**.</span><span class="sxs-lookup"><span data-stu-id="34528-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="34528-152">Wybierz podmioty, które reprezentują profil klienta - **eCommerceContacts** i **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="34528-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="ujednolicić źródła danych e-commerce i lojalności.":::

1. <span data-ttu-id="34528-154">Wybierz opcję **ContactId** jako klucz podstawowy dla opcji **eCommerceContacts** i **LoyaltyID** jako klucz podstawowy dla **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="34528-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="ujednolicenie LoyaltyId jako klucza podstawowego.":::

### <a name="match"></a><span data-ttu-id="34528-156">Dopasowywanie</span><span class="sxs-lookup"><span data-stu-id="34528-156">Match</span></span>

1. <span data-ttu-id="34528-157">Przejdź do karty **Dopasowywanie** i wybierz **Ustawianie kolejności**.</span><span class="sxs-lookup"><span data-stu-id="34528-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="34528-158">Z listy rozwijanej **Głównej** wybierz pozycję **eCommerceContacts: eCommerce** jako źródło podstawowe i dołącz wszystkie rekordy.</span><span class="sxs-lookup"><span data-stu-id="34528-158">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="34528-159">Z listy rozwijanej **Encja 2** wybierz **loyCustomers : LoyaltyScheme** i uwzględnij wszystkie rekordy.</span><span class="sxs-lookup"><span data-stu-id="34528-159">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Ujednolicenie dopasowania eCommerce i lojalności.":::

1. <span data-ttu-id="34528-161">Wybierz **Tworzenie nowej reguły**</span><span class="sxs-lookup"><span data-stu-id="34528-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="34528-162">Dodanie pierwszego warunku za pomocą narzędzia FullName.</span><span class="sxs-lookup"><span data-stu-id="34528-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="34528-163">Dla elementu eCommerceContacts wybierz pozycję **FullName** z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="34528-163">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="34528-164">Dla elementu loyCustomers wybierz pozycję **FullName** z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="34528-164">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="34528-165">Wybierz menu rozwiajne **Normalizuj** i wybierz **Typ (telefon, nazwa, adres,...)**.</span><span class="sxs-lookup"><span data-stu-id="34528-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="34528-166">Ustawianie **Poziomu dokładności**: **Podstawowe** i **Wartość**: **Wysokie**.</span><span class="sxs-lookup"><span data-stu-id="34528-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="34528-167">Wprowadź nazwę **FullName, Email** dla nowej reguły.</span><span class="sxs-lookup"><span data-stu-id="34528-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="34528-168">Dodaj drugi warunek dla adresu e-mail, zaznaczając opcję **Dodaj warunek**</span><span class="sxs-lookup"><span data-stu-id="34528-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="34528-169">W przypadku encji eCommerceContacts wybierz opcję **E-mail** w polu listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="34528-169">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="34528-170">W przypadku encji loyCustomers wybierz opcję **E-mail** w polu listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="34528-170">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="34528-171">Pozostaw puste pole Normalizuj.</span><span class="sxs-lookup"><span data-stu-id="34528-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="34528-172">Ustawianie **Poziomu dokładności**: **Podstawowe** i **Wartość**: **Wysokie**.</span><span class="sxs-lookup"><span data-stu-id="34528-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Należy ujednolicić regułę dotyczącą nazwy i adresu e-mail.":::

7. <span data-ttu-id="34528-174">Wybierz pozycję **Zapisz** i **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="34528-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="34528-175">Scalanie</span><span class="sxs-lookup"><span data-stu-id="34528-175">Merge</span></span>

1. <span data-ttu-id="34528-176">Przejdź na kartę **Scal**.</span><span class="sxs-lookup"><span data-stu-id="34528-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="34528-177">W elemencie **ContactId** dla encji **loyCustomers** zmień nazwę wyświetlaną na **ContactIdLOYALTY**, aby odróżnić ją od innych przetwarzanych identyfikatorów.</span><span class="sxs-lookup"><span data-stu-id="34528-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="Zmień nazwę ContactID na identyfikator lojalnościowy.":::

1. <span data-ttu-id="34528-179">Kliknij przycisk **Zapisz** i **Uruchom**, aby rozpocząć proces scalania.</span><span class="sxs-lookup"><span data-stu-id="34528-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="34528-180">Zadanie 3 - Skonfiguruj przewidywanie rezygnacji z transakcji</span><span class="sxs-lookup"><span data-stu-id="34528-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="34528-181">Dzięki ujednoliconym profilom klienta można teraz uruchomić przewidywanie subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="34528-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="34528-182">Aby zapoznać się ze szczegółowymi krokami, zobacz artykuł [Przewidywanie rezygnacji z subskrypcji (wersja zapoznawcza)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="34528-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="34528-183">Wybierz **Analizy** > **Wykryj** i wybierz korzystanie z **Model rezygnacji klientów**.</span><span class="sxs-lookup"><span data-stu-id="34528-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="34528-184">Wybierz opcję **Transakcyjna** i wybierz pozycję **Rozpocznij pracę**.</span><span class="sxs-lookup"><span data-stu-id="34528-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="34528-185">Nazwij model **Przewidywanie rezygnacji z transakcji eCommerce OOB**, a następnie encję wyjściową **OOBeCommerceChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="34528-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="34528-186">Zdefiniować dwa warunki dotyczące modelu rezygnacji:</span><span class="sxs-lookup"><span data-stu-id="34528-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="34528-187">**Okno przewidywania**: **co najmniej 60** dni.</span><span class="sxs-lookup"><span data-stu-id="34528-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="34528-188">To ustawienie określa, jak daleko w przyszłość chcemy przewidywać odpływ klientów.</span><span class="sxs-lookup"><span data-stu-id="34528-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="34528-189">**Definicja rezygnacji**: **co najmniej 60** dni.</span><span class="sxs-lookup"><span data-stu-id="34528-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="34528-190">Czas trwania bez zakupu, po którym klient został uznany za klienta, który zrezygnował.</span><span class="sxs-lookup"><span data-stu-id="34528-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="Wybierz dźwignie modelu Okno predykcji i Definicja rezygnacji.":::

1. <span data-ttu-id="34528-192">Wybierz **Historia zakupów (wymagane)** i wybierz pozycję **Dodaj dane** dla historii subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="34528-192">Select **Purchase History (required)** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="34528-193">Dodaj encję **eCommercePurchases : eCommerce** i zamapuj pola z eCommerce na odpowiadające im pola wymagane przez model.</span><span class="sxs-lookup"><span data-stu-id="34528-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="34528-194">Dołącz do encji **eCommercePurchases: eCommerce** o identyfikatorze **eCommerceContacts: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="34528-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Dołączanie encji eCommerce.":::

1. <span data-ttu-id="34528-196">Wybierz przycisk **Dalej**, aby ustawić harmonogram modelu.</span><span class="sxs-lookup"><span data-stu-id="34528-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="34528-197">Model musi regularnie trenować, aby uczyć się nowych wzorców, gdy są pozyskiwane nowe dane.</span><span class="sxs-lookup"><span data-stu-id="34528-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="34528-198">Na potrzeby tego przykładu wybierz pozycję **Miesięczny**.</span><span class="sxs-lookup"><span data-stu-id="34528-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="34528-199">Po przejrzeniu wszystkich szczegółów wybierz pozycję **Zapisz i uruchom**.</span><span class="sxs-lookup"><span data-stu-id="34528-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="34528-200">Zadanie 4 - Przejrzyj wyniki i wyjaśnienia modelu</span><span class="sxs-lookup"><span data-stu-id="34528-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="34528-201">Pozwól modelowi ukończyć uczenie i ocenianie danych.</span><span class="sxs-lookup"><span data-stu-id="34528-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="34528-202">Możesz teraz przejrzeć wyjaśnienia dotyczące modelu rezygnacji z subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="34528-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="34528-203">Aby uzyskać więcej informacji, zobacz temat [Przejrzyj stan i wyniki prognozy](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="34528-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="34528-204">Zadanie 5 - Utwórz segment klientów o wysokim ryzyku rezygnacji</span><span class="sxs-lookup"><span data-stu-id="34528-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="34528-205">Uruchomienie modelu produkcyjnego tworzy nową jednostkę, którą możesz zobaczyć **Dane** > **Encje**.</span><span class="sxs-lookup"><span data-stu-id="34528-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="34528-206">Możesz utworzyć nowy segment na podstawie encji utworzonej przez model.</span><span class="sxs-lookup"><span data-stu-id="34528-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="34528-207">Przejdź do **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="34528-207">Go to **Segments**.</span></span> <span data-ttu-id="34528-208">Wybierz opcję **Nowy** i wybierz pozycję **Utwórz z poziomu** > **Analizy**.</span><span class="sxs-lookup"><span data-stu-id="34528-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Tworzenie segmentu z wynikiem modelu.":::

1. <span data-ttu-id="34528-210">Wybierz opcję **OOBSubscriptionChurnPrediction** punkt końcowy i zdefiniuj segment:</span><span class="sxs-lookup"><span data-stu-id="34528-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="34528-211">Pole: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="34528-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="34528-212">Operator: większy niż</span><span class="sxs-lookup"><span data-stu-id="34528-212">Operator: greater than</span></span>
   - <span data-ttu-id="34528-213">Wartość: 0.6</span><span class="sxs-lookup"><span data-stu-id="34528-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Skonfiguruj segment rezygnacji z subskrypcji.":::

<span data-ttu-id="34528-215">Masz teraz dynamicznie aktualizowany segment, który identyfikuje klientów o wysokim ryzyku rezygnacji z subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="34528-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="34528-216">Aby uzyskać więcej informacji, zobacz [Tworzenie segmentów i zarządzanie nimi](segments.md).</span><span class="sxs-lookup"><span data-stu-id="34528-216">For more information, see [Create and manage segments](segments.md).</span></span>
