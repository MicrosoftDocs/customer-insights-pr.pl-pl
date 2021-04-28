---
title: Działania klienta
description: Zdefiniować działania klienta i wyświetlić je na osiach czasu na klientach.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 0c728fad4ed00d1bf085fed60057211861b3a195
ms.sourcegitcommit: f0855bd7762b1f0a1d3dd5259e23c95e1b0a6a93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/07/2021
ms.locfileid: "5866420"
---
# <a name="customer-activities"></a><span data-ttu-id="8326e-103">Działania klienta</span><span class="sxs-lookup"><span data-stu-id="8326e-103">Customer activities</span></span>

<span data-ttu-id="8326e-104">Łącząc działania klientów z [różnych źródeł danych](data-sources.md) w Dynamics 365 Customer Insights do tworzenia osi czasu, będącej listą działań</span><span class="sxs-lookup"><span data-stu-id="8326e-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="8326e-105">Dodawaj oś czasu w aplikacjach usługi Dynamics 365 za pomocą rozwiązania [dodatku Customer Card](customer-card-add-in.md) lub pulpitu nawigacyjnego Power BI.</span><span class="sxs-lookup"><span data-stu-id="8326e-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="8326e-106">Definiuj działanie</span><span class="sxs-lookup"><span data-stu-id="8326e-106">Define an activity</span></span>

<span data-ttu-id="8326e-107">Źródła danych mogą zawierać encje z danymi transakcyjnymi i danymi działań z wielu źródeł danych.</span><span class="sxs-lookup"><span data-stu-id="8326e-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="8326e-108">Zidentyfikuj te encje i wybierz działania, które mają być wyświetlane na osi czasu klienta.</span><span class="sxs-lookup"><span data-stu-id="8326e-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="8326e-109">Wybierz encję zawierającą docelowe działanie lub działania.</span><span class="sxs-lookup"><span data-stu-id="8326e-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="8326e-110">Encja musi zawierać co najmniej jeden atrybut typu **Data**, który ma zostać uwzględniony na osi czasu klienta, i nie można dodawać encji bez pól **Data**.</span><span class="sxs-lookup"><span data-stu-id="8326e-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="8326e-111">Formant **Dodaj działanie** jest wyłączany jeśli nie zostanie znaleziona taka encja.</span><span class="sxs-lookup"><span data-stu-id="8326e-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="8326e-112">W analizach odbiorców przejdź do **Dane** > **Działania**.</span><span class="sxs-lookup"><span data-stu-id="8326e-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="8326e-113">Wybierz opcję **Dodaj działanie**, aby rozpocząć proces konfigurowania działania z przewodnikiem.</span><span class="sxs-lookup"><span data-stu-id="8326e-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="8326e-114">W kroku **Dane działania** ustaw wartości następujących pól:</span><span class="sxs-lookup"><span data-stu-id="8326e-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="8326e-115">**Nazwa działania**: wybierz nazwę działania.</span><span class="sxs-lookup"><span data-stu-id="8326e-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="8326e-116">**Encja**: Wybierz encję zawierającą dane transakcyjne lub działania.</span><span class="sxs-lookup"><span data-stu-id="8326e-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="8326e-117">**Klucz podstawowy**: Wybierz pole, które jednoznacznie identyfikuje rekord.</span><span class="sxs-lookup"><span data-stu-id="8326e-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="8326e-118">Nie może ono zawierać żadnych powielonych wartości, pustych wartości ani brakujących wartości.</span><span class="sxs-lookup"><span data-stu-id="8326e-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Skonfiguruj dane działań za pomocą nazwy, encji i klucza podstawowego.":::

1. <span data-ttu-id="8326e-120">Wybierz pozycję **Dalej**, aby przejść do następnego kroku.</span><span class="sxs-lookup"><span data-stu-id="8326e-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="8326e-121">W kroku **Relacja** skonfiguruj szczegóły, aby połączyć dane działań z odpowiednim klientem.</span><span class="sxs-lookup"><span data-stu-id="8326e-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="8326e-122">Ten krok obrazuje połączenie między encjami.</span><span class="sxs-lookup"><span data-stu-id="8326e-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="8326e-123">**Pierwszy**: pole obce w encji działania, które będzie używane do ustanowienia relacji z inną encją.</span><span class="sxs-lookup"><span data-stu-id="8326e-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="8326e-124">**Drugi**: odpowiadająca jej encja klienta źródłowego, z którą encja działania będzie w relacji.</span><span class="sxs-lookup"><span data-stu-id="8326e-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="8326e-125">Można utworzyć relację tylko z encjami klienta źródłowego, które są używane w procesie ujednolicania danych.</span><span class="sxs-lookup"><span data-stu-id="8326e-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="8326e-126">**Trzeci**: jeśli relacja między tą encją działania a wybraną encją klienta źródłowego już istnieje, nazwa relacji będzie w trybie tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="8326e-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="8326e-127">Jeśli taka relacja nie istnieje, zostanie utworzona nowa relacja z nazwą podaną w tym polu przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="8326e-127">If there no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definiowanie relacji encji.":::

1. <span data-ttu-id="8326e-129">Wybierz pozycję **Dalej**, aby przejść do następnego kroku.</span><span class="sxs-lookup"><span data-stu-id="8326e-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="8326e-130">W kroku **Ujednolicanie działania** wybierz zdarzenie działania i czas rozpoczęcia działania.</span><span class="sxs-lookup"><span data-stu-id="8326e-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="8326e-131">**Pola wymagane**</span><span class="sxs-lookup"><span data-stu-id="8326e-131">**Required fields**</span></span>
      1. <span data-ttu-id="8326e-132">**Działanie zdarzenia**: pole, które jest zdarzeniem tego działania</span><span class="sxs-lookup"><span data-stu-id="8326e-132">**Event activity**: Field that is the event for this activity</span></span>
      2. <span data-ttu-id="8326e-133">**Sygnatura czasowa**: pole reprezentujące czas rozpoczęcia działania.</span><span class="sxs-lookup"><span data-stu-id="8326e-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="8326e-134">**Pola opcjonalne**</span><span class="sxs-lookup"><span data-stu-id="8326e-134">**Optional fields**</span></span>
      1. <span data-ttu-id="8326e-135">**Dodatkowe szczegóły**: pole z odpowiednimi informacjami dla tego działania.</span><span class="sxs-lookup"><span data-stu-id="8326e-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      2. <span data-ttu-id="8326e-136">**Ikona**: ikona najlepiej reprezentująca ten typ działania.</span><span class="sxs-lookup"><span data-stu-id="8326e-136">**Icon**: Icon that best represents this activity type.</span></span>
      3. <span data-ttu-id="8326e-137">**Adres internetowy**: pole zawierające adres URL z informacjami o tym działaniu.</span><span class="sxs-lookup"><span data-stu-id="8326e-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="8326e-138">Na przykład system transakcyjny, który zawiera źródło tego działania.</span><span class="sxs-lookup"><span data-stu-id="8326e-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="8326e-139">Ten adres URL może być dowolnym polem ze źródła danych lub może być skonstruowany jako nowe pole przy użyciu przekształcenia Power Query.</span><span class="sxs-lookup"><span data-stu-id="8326e-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="8326e-140">Dane adresu URL będą przechowywane w encji *Ujednolicone działanie*, która może być konsumowana w dół przy użyciu [interfejsów API](apis.md).</span><span class="sxs-lookup"><span data-stu-id="8326e-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Określ dane działań klienta w encji Ujednolicone działanie.":::

1. <span data-ttu-id="8326e-142">Wybierz pozycję **Dalej**, aby przejść do następnego kroku.</span><span class="sxs-lookup"><span data-stu-id="8326e-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="8326e-143">Aby zapisać teraz działanie z typem działania ustawionym jako **Inne**, można wybrać opcję **Zakończ i przejrzyj**.</span><span class="sxs-lookup"><span data-stu-id="8326e-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="8326e-144">W kroku **Typ działania** wybierz typ działania i, opcjonalnie, wybierz, czy chcesz etapami mapować niektóre typy działań do użycia w innych obszarach programu Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8326e-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="8326e-145">Obecnie typy działania *Subskrypcja* & *SalesOrderLine* można etapami zamapować po uzgodnieniu mapowania pól.</span><span class="sxs-lookup"><span data-stu-id="8326e-145">Currently, *Subscription* & *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="8326e-146">Jeśli typ działania nie jest odpowiedni dla nowego działania, można wybrać opcję *Inne* lub *Utwórz nowe* dla niestandardowego typu działania.</span><span class="sxs-lookup"><span data-stu-id="8326e-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="8326e-147">Wybierz pozycję **Dalej**, aby przejść do następnego kroku.</span><span class="sxs-lookup"><span data-stu-id="8326e-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="8326e-148">W kroku **Przegląd** sprawdź wybór.</span><span class="sxs-lookup"><span data-stu-id="8326e-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="8326e-149">Należy wrócić do dowolnego z poprzednich kroków i w razie potrzeby zaktualizować te informacje.</span><span class="sxs-lookup"><span data-stu-id="8326e-149">You go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Przeglądanie określonych pól dla działania.":::
   
1. <span data-ttu-id="8326e-151">Wybierz opcję **Zapisz działanie**, aby zastosować zmiany i wybierz opcję **Wykonane**, aby wrócić do **Dane** > **Działania**.</span><span class="sxs-lookup"><span data-stu-id="8326e-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="8326e-152">Tutaj możesz zobaczyć, które działania mają być wyświetlane na osi czasu.</span><span class="sxs-lookup"><span data-stu-id="8326e-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="8326e-153">Na stronie **Działania** wybierz opcję **Uruchom**, aby przetworzyć działanie.</span><span class="sxs-lookup"><span data-stu-id="8326e-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="8326e-154">Istnieje [sześć typów stanu](system.md#status-types) zadań/procesów.</span><span class="sxs-lookup"><span data-stu-id="8326e-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="8326e-155">Ponadto większość procesów [zależy od innych procesów podrzędnych](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="8326e-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="8326e-156">Istnieje możliwość wybrania stanu procesu w celu wyświetlenia szczegółowych informacji o postępie w całym zadaniu.</span><span class="sxs-lookup"><span data-stu-id="8326e-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="8326e-157">Po wybraniu opcji **Zobacz szczegółowe informacje** dla jednego z zadań zadania, można znaleźć więcej informacji: czas przetwarzania, Data ostatniego przetwarzania oraz wszystkie błędy i ostrzeżenia skojarzone z zadaniem.</span><span class="sxs-lookup"><span data-stu-id="8326e-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="8326e-158">Zarządzanie istniejącymi działaniami</span><span class="sxs-lookup"><span data-stu-id="8326e-158">Manage existing activities</span></span>

<span data-ttu-id="8326e-159">W **Dane** > **Działania** można wyświetlić wszystkie zapisane działania i nimi zarządzać.</span><span class="sxs-lookup"><span data-stu-id="8326e-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="8326e-160">Każde działanie jest reprezentowane przez wiersz, który zawiera także szczegółowe informacje o źródle, encji i typie działania.</span><span class="sxs-lookup"><span data-stu-id="8326e-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="8326e-161">Po wybraniu działania są dostępne następujące akcje.</span><span class="sxs-lookup"><span data-stu-id="8326e-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="8326e-162">**Edycja**: powoduje otwarcie konfiguratowa działania w kroku przeglądu.</span><span class="sxs-lookup"><span data-stu-id="8326e-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="8326e-163">W tym kroku można zmienić dowolną lub całą bieżącą konfigurację.</span><span class="sxs-lookup"><span data-stu-id="8326e-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="8326e-164">Po zmianie konfiguracji wybierz opcję **Zapisz działanie**, a następnie wybierz opcję **Uruchom**, aby przetworzyć zmiany.</span><span class="sxs-lookup"><span data-stu-id="8326e-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="8326e-165">**Zmień nazwę**: otwiera okno dialogowe, w którym należy wprowadzić inną nazwę dla wybranego działania.</span><span class="sxs-lookup"><span data-stu-id="8326e-165">**Rename**: Opens a dialog where to enter a different name for the selected activity.</span></span> <span data-ttu-id="8326e-166">Wybierz pozycję **Zapisz**, aby zastosować zmiany.</span><span class="sxs-lookup"><span data-stu-id="8326e-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="8326e-167">**Usuń**: otwiera okno dialogowe w celu potwierdzenia usunięcia wybranego działania.</span><span class="sxs-lookup"><span data-stu-id="8326e-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="8326e-168">Możesz także usunąć wiele działań jednocześnie, zaznaczając działania i wybierając ikonę usuwania.</span><span class="sxs-lookup"><span data-stu-id="8326e-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="8326e-169">Aby potwierdzić usunięcie, wybierz opcję **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="8326e-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
