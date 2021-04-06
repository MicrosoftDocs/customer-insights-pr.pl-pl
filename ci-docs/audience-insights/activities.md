---
title: Działania klienta
description: Zdefiniować działania klienta i wyświetlić je na osiach czasu na klientach.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: fbfa9d7e00859cc80c24b98bd2dc806f1fda7803
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596742"
---
# <a name="customer-activities"></a><span data-ttu-id="5f00a-103">Działania klienta</span><span class="sxs-lookup"><span data-stu-id="5f00a-103">Customer activities</span></span>

<span data-ttu-id="5f00a-104">Połącz działania klientów z [różnych źródeł danych](data-sources.md) w Dynamics 365 Customer Insights, aby utworzyć oś czasu klienta, która wymienia działania w porządku chronologicznym.</span><span class="sxs-lookup"><span data-stu-id="5f00a-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="5f00a-105">Można umieścić oś czasu w aplikacjach dotyczących zaangażowania klientów w Dynamics 365 za pośrednictwem [dodatku Karta klienta](customer-card-add-in.md) lub na pulpicie nawigacyjnym Power BI.</span><span class="sxs-lookup"><span data-stu-id="5f00a-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="5f00a-106">Definiuj działanie</span><span class="sxs-lookup"><span data-stu-id="5f00a-106">Define an activity</span></span>

<span data-ttu-id="5f00a-107">Źródła danych zawierają encje z danymi transakcyjnymi i danymi działań z wielu źródeł danych.</span><span class="sxs-lookup"><span data-stu-id="5f00a-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="5f00a-108">Zidentyfikuj te encje i wybierz działania, które mają być wyświetlane na osi czasu klienta.</span><span class="sxs-lookup"><span data-stu-id="5f00a-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="5f00a-109">Wybierz encję zawierającą docelowe działanie lub działania.</span><span class="sxs-lookup"><span data-stu-id="5f00a-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="5f00a-110">W analizach odbiorców przejdź do **Dane** > **Działania**.</span><span class="sxs-lookup"><span data-stu-id="5f00a-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="5f00a-111">Wybierz **Dodaj działanie**.</span><span class="sxs-lookup"><span data-stu-id="5f00a-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5f00a-112">Encja musi zawierać co najmniej jeden atrybut typu **Data**, który ma zostać uwzględniony na osi czasu klienta, i nie można dodawać encji bez pól **Data**.</span><span class="sxs-lookup"><span data-stu-id="5f00a-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="5f00a-113">Formant **Dodaj działanie** jest wyłączany jeśli nie zostanie znaleziona taka encja.</span><span class="sxs-lookup"><span data-stu-id="5f00a-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="5f00a-114">W okienku **Dodaj działanie** ustaw wartości dla następujących pól:</span><span class="sxs-lookup"><span data-stu-id="5f00a-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="5f00a-115">**Encja**: Wybierz encję zawierającą dane transakcyjne lub działania.</span><span class="sxs-lookup"><span data-stu-id="5f00a-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="5f00a-116">**Klucz podstawowy**: Wybierz pole, które jednoznacznie identyfikuje rekord.</span><span class="sxs-lookup"><span data-stu-id="5f00a-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="5f00a-117">Nie może ono zawierać żadnych powielonych wartości, pustych wartości ani brakujących wartości.</span><span class="sxs-lookup"><span data-stu-id="5f00a-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="5f00a-118">**Sygnatura czasowa**: Wybierz pole reprezentujące godzinę rozpoczęcia działania.</span><span class="sxs-lookup"><span data-stu-id="5f00a-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="5f00a-119">**Zdarzenie**: Zaznacz pole, które jest zdarzeniem dla działania.</span><span class="sxs-lookup"><span data-stu-id="5f00a-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="5f00a-120">**Adres sieci Web**: Wybierz pole reprezentujące adres URL zawierający dodatkowe informacje o działaniu.</span><span class="sxs-lookup"><span data-stu-id="5f00a-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="5f00a-121">Na przykład system transakcyjny, który zawiera źródło tego działania.</span><span class="sxs-lookup"><span data-stu-id="5f00a-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="5f00a-122">Ten adres URL może być dowolnym polem ze źródła danych lub może być skonstruowany jako nowe pole przy użyciu przekształcenia Power Query.</span><span class="sxs-lookup"><span data-stu-id="5f00a-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="5f00a-123">Te dane URL będą przechowywane w encji Działanie ujednolicone, która może być używana w programie przy użyciu interfejsów API.</span><span class="sxs-lookup"><span data-stu-id="5f00a-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="5f00a-124">**Szczegóły**: Opcjonalnie wybierz pole, dodawane, aby uzyskać dodatkowe szczegóły.</span><span class="sxs-lookup"><span data-stu-id="5f00a-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="5f00a-125">**Ikona**: Opcjonalnie wybierz ikonę reprezentującą to działanie.</span><span class="sxs-lookup"><span data-stu-id="5f00a-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="5f00a-126">**Typ działania**: Zdefiniuj odwołanie typu działania do Common Data Model, który najlepiej opisuje definicję semantyczną działania.</span><span class="sxs-lookup"><span data-stu-id="5f00a-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="5f00a-127">W sekcji **Konfigurowanie relacji** skonfiguruj szczegóły, aby połączyć dane działania z odpowiednim klientem.</span><span class="sxs-lookup"><span data-stu-id="5f00a-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

    - <span data-ttu-id="5f00a-128">**Pole encji działania**: Wybierz pole w encji działanie, które będzie używane do ustanawiania relacji z inną encją.</span><span class="sxs-lookup"><span data-stu-id="5f00a-128">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="5f00a-129">**Encja klienta**: Wybierz odpowiednią encję źródłową klienta, z którą encja działania będzie w relacji.</span><span class="sxs-lookup"><span data-stu-id="5f00a-129">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="5f00a-130">Relacje można powiązać tylko z encjami źródłowymi klienta używanymi w procesie zjednoczenia danych.</span><span class="sxs-lookup"><span data-stu-id="5f00a-130">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="5f00a-131">**Pole encja klienta**: To pole zawiera klucz podstawowy źródłowej encji klienta wybrany w procesie mapowania.</span><span class="sxs-lookup"><span data-stu-id="5f00a-131">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="5f00a-132">To pole klucz podstawowy w encji źródłowej klienta jest używane do ustanawiania relacji z encją działanie.</span><span class="sxs-lookup"><span data-stu-id="5f00a-132">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="5f00a-133">**Nazwa**: Jeśli relacja między tą encją działania a wybraną encją źródłową klienta już istnieje, nazwa relacji zostanie wyświetlona w trybie tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="5f00a-133">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="5f00a-134">Jeśli taka relacja nie istnieje, zostanie utworzona nowa relacja z nazwą podaną w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="5f00a-134">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5f00a-135">![Definiowanie relacji encji](media/activities-entities-define.png "Definiowanie relacji encji")</span><span class="sxs-lookup"><span data-stu-id="5f00a-135">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

1. <span data-ttu-id="5f00a-136">Wybierz pozycję **Zapisz**, aby zastosować zmiany.</span><span class="sxs-lookup"><span data-stu-id="5f00a-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="5f00a-137">Na stronie **Działania** wybierz **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="5f00a-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="5f00a-138">Istnieje [sześć typów stanu](system.md#status-types) zadań/procesów.</span><span class="sxs-lookup"><span data-stu-id="5f00a-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="5f00a-139">Ponadto większość procesów [zależy od innych procesów podrzędnych](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="5f00a-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="5f00a-140">Istnieje możliwość wybrania stanu procesu w celu wyświetlenia szczegółowych informacji o postępie w całym zadaniu.</span><span class="sxs-lookup"><span data-stu-id="5f00a-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="5f00a-141">Po wybraniu opcji **Zobacz szczegółowe informacje** dla jednego z zadań zadania, można znaleźć więcej informacji: czas przetwarzania, Data ostatniego przetwarzania oraz wszystkie błędy i ostrzeżenia skojarzone z zadaniem.</span><span class="sxs-lookup"><span data-stu-id="5f00a-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="5f00a-142">Edytuj działanie</span><span class="sxs-lookup"><span data-stu-id="5f00a-142">Edit an activity</span></span>

1. <span data-ttu-id="5f00a-143">W analizach odbiorców przejdź do **Dane** > **Działania**.</span><span class="sxs-lookup"><span data-stu-id="5f00a-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="5f00a-144">Wybierz encję działania, którą chcesz edytować i wybierz **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="5f00a-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="5f00a-145">Możesz również umieścić kursor nad wierszem encji i wybrać ikonę **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="5f00a-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="5f00a-146">Kliknij ikonę **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="5f00a-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="5f00a-147">W okienku **Edytuj działanie** zaktualizuj wartości i wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="5f00a-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="5f00a-148">Na stronie **Działania** wybierz **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="5f00a-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="5f00a-149">Usuń działanie</span><span class="sxs-lookup"><span data-stu-id="5f00a-149">Delete an activity</span></span>

1. <span data-ttu-id="5f00a-150">W analizach odbiorców przejdź do **Dane** > **Działania**.</span><span class="sxs-lookup"><span data-stu-id="5f00a-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="5f00a-151">Wybierz encję działania, którą chcesz usunąć i wybierz **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="5f00a-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="5f00a-152">Możesz również umieścić kursor nad wierszem encji i wybrać ikonę **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="5f00a-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="5f00a-153">Oprócz tego można wybrać wiele encji działań, które mają zostać usunięte jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="5f00a-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5f00a-154">![Edytuj lub usuń relację między encjami](media/activities-entities-edit-delete.png "Edytuj lub usuń relację między encjami")</span><span class="sxs-lookup"><span data-stu-id="5f00a-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="5f00a-155">Wybierz ikonę **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="5f00a-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="5f00a-156">Potwierdź usunięcie.</span><span class="sxs-lookup"><span data-stu-id="5f00a-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]