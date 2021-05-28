---
title: Tworzenie segmentów i zarządzanie nimi
description: W celu pogrupowania klientów na podstawie różnych atrybutów można utworzyć ich segmenty.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064950"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="a8df5-103">Tworzenie segmentów i zarządzanie nimi</span><span class="sxs-lookup"><span data-stu-id="a8df5-103">Create and manage segments</span></span>

<span data-ttu-id="a8df5-104">Zdefiniować złożone filtry dla ujednoliconej encji klienta i jej encji pokrewnych.</span><span class="sxs-lookup"><span data-stu-id="a8df5-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="a8df5-105">Każdy segment, po przetworzeniu, tworzy zestaw rekordów klientów, który można eksportować i na którym można podejmować akcje.</span><span class="sxs-lookup"><span data-stu-id="a8df5-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="a8df5-106">Segmenty są zarządzane na stronie **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="a8df5-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="a8df5-107">Poniższy przykład ilustruje możliwości segmentacji.</span><span class="sxs-lookup"><span data-stu-id="a8df5-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="a8df5-108">Zdefiniowano segment dla klientów, którzy zamówili towary za przynajmniej 500 USD w ciągu ostatnich 90 dni *i* którzy uczestniczyli w rozmowie telefonicznej z obsługą klienta, która eskalowała.</span><span class="sxs-lookup"><span data-stu-id="a8df5-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Zrzut ekranu interfejsu użytkownika segmentu konstruktora z dwiema grupami określającymi segment klientów.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="a8df5-110">Utwórz nowy segment</span><span class="sxs-lookup"><span data-stu-id="a8df5-110">Create a new segment</span></span>

<span data-ttu-id="a8df5-111">Istnieje wiele sposobów utworzenia nowego segmentu.</span><span class="sxs-lookup"><span data-stu-id="a8df5-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="a8df5-112">W tej sekcji opisano sposób tworzenia *pustego segmentu* od podstaw.</span><span class="sxs-lookup"><span data-stu-id="a8df5-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="a8df5-113">Można również utworzyć *krótki segment* na podstawie istniejących obiektów lub skorzystać z uczenia maszynowego, aby uzyskać *sugerowane segmenty*.</span><span class="sxs-lookup"><span data-stu-id="a8df5-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="a8df5-114">Więcej informacji: [Omówienie segmentów](segments.md).</span><span class="sxs-lookup"><span data-stu-id="a8df5-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="a8df5-115">Podczas tworzenia segmentu można zapisać jego wersje robocze.</span><span class="sxs-lookup"><span data-stu-id="a8df5-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="a8df5-116">Zostanie on zapisany jako nieaktywny segment i nie można go aktywować w ramach prawidłowej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="a8df5-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="a8df5-117">Przejdź do strony **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="a8df5-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="a8df5-118">Wybierz **Nowy** > **Pusty segment**.</span><span class="sxs-lookup"><span data-stu-id="a8df5-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="a8df5-119">W okienku **Nowy segment** wybierz typ segmentu:</span><span class="sxs-lookup"><span data-stu-id="a8df5-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="a8df5-120">**Dynamiczne segmenty** są [odświeżane](segments.md#refresh-segments) w harmonogramie cyklicznym.</span><span class="sxs-lookup"><span data-stu-id="a8df5-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="a8df5-121">**Segmenty statyczne** są uruchamiane jeden raz podczas ich tworzenia.</span><span class="sxs-lookup"><span data-stu-id="a8df5-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="a8df5-122">Podaj **nazwę encji wyjściowej** dla segmentu.</span><span class="sxs-lookup"><span data-stu-id="a8df5-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="a8df5-123">Opcjonalnie można podać wyświetlaną nazwę i opis ułatwiający identyfikację segmentu.</span><span class="sxs-lookup"><span data-stu-id="a8df5-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="a8df5-124">Wybierz **Dalej**, aby połączyć się ze stroną **Konstruktor segmentu**, na której jest definiowana grupa.</span><span class="sxs-lookup"><span data-stu-id="a8df5-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="a8df5-125">Grupa jest zbiorem klientów.</span><span class="sxs-lookup"><span data-stu-id="a8df5-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="a8df5-126">Wybierz encję zawierającą atrybut, według którego chcesz segmentować.</span><span class="sxs-lookup"><span data-stu-id="a8df5-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="a8df5-127">Wybierz atrybut, według którego ma zostać przeprowadzona segmentacja.</span><span class="sxs-lookup"><span data-stu-id="a8df5-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="a8df5-128">Ten atrybut może mieć jeden z czterech typów wartości: numeryczny, ciąg, data lub wartość logiczna.</span><span class="sxs-lookup"><span data-stu-id="a8df5-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="a8df5-129">Wybierz operatora i wartość dla zaznaczonego atrybutu.</span><span class="sxs-lookup"><span data-stu-id="a8df5-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a8df5-130">![Niestandardowy filtr grup](media/customer-group-numbers.png "Filtr grupy klienta")</span><span class="sxs-lookup"><span data-stu-id="a8df5-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="a8df5-131">Liczba</span><span class="sxs-lookup"><span data-stu-id="a8df5-131">Number</span></span> |<span data-ttu-id="a8df5-132">Definicja</span><span class="sxs-lookup"><span data-stu-id="a8df5-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="a8df5-133">1</span><span class="sxs-lookup"><span data-stu-id="a8df5-133">1</span></span>     |<span data-ttu-id="a8df5-134">Entity</span><span class="sxs-lookup"><span data-stu-id="a8df5-134">Entity</span></span>          |
   |<span data-ttu-id="a8df5-135">2</span><span class="sxs-lookup"><span data-stu-id="a8df5-135">2</span></span>     |<span data-ttu-id="a8df5-136">Atrybut</span><span class="sxs-lookup"><span data-stu-id="a8df5-136">Attribute</span></span>          |
   |<span data-ttu-id="a8df5-137">3</span><span class="sxs-lookup"><span data-stu-id="a8df5-137">3</span></span>    |<span data-ttu-id="a8df5-138">Operator</span><span class="sxs-lookup"><span data-stu-id="a8df5-138">Operator</span></span>         |
   |<span data-ttu-id="a8df5-139">4</span><span class="sxs-lookup"><span data-stu-id="a8df5-139">4</span></span>    |<span data-ttu-id="a8df5-140">Wartość</span><span class="sxs-lookup"><span data-stu-id="a8df5-140">Value</span></span>         |

   1. <span data-ttu-id="a8df5-141">Aby dodać do grupy więcej warunków, można użyć dwóch operatorów logicznych:</span><span class="sxs-lookup"><span data-stu-id="a8df5-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="a8df5-142">**AND** operator: oba warunki muszą być spełnione w procesie segmentacji.</span><span class="sxs-lookup"><span data-stu-id="a8df5-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="a8df5-143">Ta opcja jest najbardziej przydatna podczas definiowania warunków między różnymi encjami.</span><span class="sxs-lookup"><span data-stu-id="a8df5-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="a8df5-144">**OR** operator: jeden z warunków musi zostać osiągnięty jako część procesu segmentacji.</span><span class="sxs-lookup"><span data-stu-id="a8df5-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="a8df5-145">Ta opcja jest najbardziej przydatna podczas definiowania wielu warunków dla tej samej encji.</span><span class="sxs-lookup"><span data-stu-id="a8df5-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="a8df5-146">![OR operator, w którym oba warunki muszą zostać spełnione](media/segmentation-either-condition.png "OR operator, w którym oba warunki muszą zostać spełnione")</span><span class="sxs-lookup"><span data-stu-id="a8df5-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="a8df5-147">Obecnie istnieje możliwość zawinięcia operatora **OR** pod operatorem **AND**, ale nie na odwrót.</span><span class="sxs-lookup"><span data-stu-id="a8df5-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="a8df5-148">Każda grupa odpowiada grupie klientów.</span><span class="sxs-lookup"><span data-stu-id="a8df5-148">Each group matches set of customers.</span></span> <span data-ttu-id="a8df5-149">Można łączyć grupy w celu uwzględnienia klientów wymaganych dla danego przypadku biznesowego.</span><span class="sxs-lookup"><span data-stu-id="a8df5-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="a8df5-150">Wybierz **Dodaj grupę**.</span><span class="sxs-lookup"><span data-stu-id="a8df5-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="a8df5-151">![Grupa klientów, Dodawanie grupy](media/customer-group-add-group.png "Grupa klientów, Dodawanie grupy")</span><span class="sxs-lookup"><span data-stu-id="a8df5-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="a8df5-152">Wybierz jeden z operatorów: **Związek**, **Część wspólna** lub **Z wyjątkiem**.</span><span class="sxs-lookup"><span data-stu-id="a8df5-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a8df5-153">![Grupa klientów, Dodawanie związku](media/customer-group-union.png "Grupa klientów, Dodawanie związku")</span><span class="sxs-lookup"><span data-stu-id="a8df5-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="a8df5-154">**Związek** łączy dwie grupy.</span><span class="sxs-lookup"><span data-stu-id="a8df5-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="a8df5-155">**Część wspólna** pokrywa się z dwiema grupami.</span><span class="sxs-lookup"><span data-stu-id="a8df5-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="a8df5-156">Tylko dane, które *są wspólne* dla obu grup, są zachowywane w ujednoliconej grupie.</span><span class="sxs-lookup"><span data-stu-id="a8df5-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="a8df5-157">**Z wyjątkiem** łączy dwie grupy.</span><span class="sxs-lookup"><span data-stu-id="a8df5-157">**Except** combines the two groups.</span></span> <span data-ttu-id="a8df5-158">Tylko dane w grupie A, które *nie są wspólne* dla grupy B, są zachowywane w ujednoliconej grupie.</span><span class="sxs-lookup"><span data-stu-id="a8df5-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="a8df5-159">Jeśli encja jest połączona z zunifikowaną encją klient za pośrednictwem [relacji](relationships.md), należy zdefiniować ścieżkę relacji, aby utworzyć prawidłowy segment.</span><span class="sxs-lookup"><span data-stu-id="a8df5-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="a8df5-160">Dodaj encje ze ścieżki relacji, aż będzie można wybrać encję **Klient : CustomerInsights** z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="a8df5-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="a8df5-161">Następnie dla każdego kroku wybierz opcję **Wszystkie rekordy**.</span><span class="sxs-lookup"><span data-stu-id="a8df5-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a8df5-162">![Ścieżka relacji podczas tworzenia segmentu](media/segments-multiple-relationships.png "Ścieżka relacji podczas tworzenia segmentu")</span><span class="sxs-lookup"><span data-stu-id="a8df5-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="a8df5-163">Domyślnie segmenty generują encję wyjściową zawierającą wszystkie atrybuty profilów klientów zgodne ze zdefiniowanymi filtrami.</span><span class="sxs-lookup"><span data-stu-id="a8df5-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="a8df5-164">Jeśli segment jest oparty na encjach innych niż encja *Klient*, do encji wyjściowej można dodać więcej atrybutów z tych encji.</span><span class="sxs-lookup"><span data-stu-id="a8df5-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="a8df5-165">Wybierz pozycję **Atrybuty projektu**, aby wybrać atrybuty, które będą dołączane do encji wyjściowej.</span><span class="sxs-lookup"><span data-stu-id="a8df5-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="a8df5-166">Przykład: segment jest oparty na encji zawierającej dane działań klienta powiązane z encją *Klient*.</span><span class="sxs-lookup"><span data-stu-id="a8df5-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="a8df5-167">Segment wyszukuje wszystkich klientów, którzy w ciągu ostatnich 60 dni dzwonili do działu pomocy technicznej.</span><span class="sxs-lookup"><span data-stu-id="a8df5-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="a8df5-168">Można dodać czas trwania rozmowy oraz liczbę rozmów telefonicznych do wszystkich pasujących rekordów klientów w encji wyjściowej.</span><span class="sxs-lookup"><span data-stu-id="a8df5-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="a8df5-169">Te informacje mogą być przydatne podczas wysyłania wiadomości e-mail z pomocnymi linków do artykułów pomocy online i często zadawanych pytań do klientów, którzy często dzwonili do działu pomocy.</span><span class="sxs-lookup"><span data-stu-id="a8df5-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="a8df5-170">Atrybuty projektu działają tylko w przypadku encji, które mają relację jeden do wielu z encją klienta.</span><span class="sxs-lookup"><span data-stu-id="a8df5-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="a8df5-171">Na przykład jeden klient może mieć wiele subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="a8df5-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="a8df5-172">Możesz rzutować tylko te atrybuty z encji, które są używane w każdej grupie segmentów, które budujesz.</span><span class="sxs-lookup"><span data-stu-id="a8df5-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="a8df5-173">Atrybuty rzutowane są uwzględniane podczas używania operatorów zestawów.</span><span class="sxs-lookup"><span data-stu-id="a8df5-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="a8df5-174">Wybierz **Zapisz**, aby zapisać segment.</span><span class="sxs-lookup"><span data-stu-id="a8df5-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="a8df5-175">Segment zostanie zapisany i przetworzony po sprawdzeniu poprawności wszystkich wymagań.</span><span class="sxs-lookup"><span data-stu-id="a8df5-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="a8df5-176">W przeciwnym razie zostanie zapisany jako wersja robocza.</span><span class="sxs-lookup"><span data-stu-id="a8df5-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="a8df5-177">Wybierz **Wróć do segmentów**, aby wrócić do strony **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="a8df5-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="a8df5-178">Szybkie segmenty</span><span class="sxs-lookup"><span data-stu-id="a8df5-178">Quick segments</span></span>

<span data-ttu-id="a8df5-179">Szybkie segmenty umożliwiają tworzenie prostych segmentów z jednym operatorem w celu szybszego wglądu w dane.</span><span class="sxs-lookup"><span data-stu-id="a8df5-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="a8df5-180">Na stronie **Segmentów** wybierz opcję **Nowy** > **Utwórz za pomocą**.</span><span class="sxs-lookup"><span data-stu-id="a8df5-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="a8df5-181">Wybierz opcję **profile**, aby zbudować segment utworzony na podstawie *ujednoliconej encji klienta*.</span><span class="sxs-lookup"><span data-stu-id="a8df5-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="a8df5-182">Wybierz opcję **Miary**, aby utworzyć segment na podstawie miar utworzonych wcześniej.</span><span class="sxs-lookup"><span data-stu-id="a8df5-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="a8df5-183">Wybierz opcję **Analizy**, aby utworzyć segment wokół jednej z encji wyjściowych wygenerowanych przy użyciu funkcji **Przewidywania** lub **Modele niestandardowe**.</span><span class="sxs-lookup"><span data-stu-id="a8df5-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="a8df5-184">W oknie dialogowym **Nowy szybki segment** wybierz atrybut z listy rozwijanej **Pole**.</span><span class="sxs-lookup"><span data-stu-id="a8df5-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="a8df5-185">W ramach systemu będzie dostępne kilka dodatkowych informacji ułatwiających stworzenie lepszych segmentów klientów.</span><span class="sxs-lookup"><span data-stu-id="a8df5-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="a8df5-186">W przypadku pól kategorii pokażemy 10 największych klientów.</span><span class="sxs-lookup"><span data-stu-id="a8df5-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="a8df5-187">Wybierz **Wartość** i wybierz **Przejrzyj**.</span><span class="sxs-lookup"><span data-stu-id="a8df5-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="a8df5-188">W przypadku atrybutu numerycznego system pokaże, jaka wartość atrybutu mieści się w percentylu każdego klienta</span><span class="sxs-lookup"><span data-stu-id="a8df5-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="a8df5-189">Wybierz **Operator** i **Wartość**, a następnie wybierz pozycję **Przeglądaj**.</span><span class="sxs-lookup"><span data-stu-id="a8df5-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="a8df5-190">System zaproponuje opcje **Szacowany rozmiar segmentu**.</span><span class="sxs-lookup"><span data-stu-id="a8df5-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="a8df5-191">Użytkownik może wybrać, czy ma zostać wyświetlona definicja segmentu, czy też najpierw ją ponownie przejrzeć w celu uzyskania innego rozmiaru segmentu.</span><span class="sxs-lookup"><span data-stu-id="a8df5-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a8df5-192">![Nazwa i oszacowanie szybkiego segmentu](media/quick-segment-name.png "Nazwa i oszacowanie szybkiego segmentu")</span><span class="sxs-lookup"><span data-stu-id="a8df5-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="a8df5-193">Podaj **Nazwę** segmentu.</span><span class="sxs-lookup"><span data-stu-id="a8df5-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="a8df5-194">Opcjonalnie, podaj **Nazwę wyświetlaną**.</span><span class="sxs-lookup"><span data-stu-id="a8df5-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="a8df5-195">Wybierz opcję **Zapisz**, aby utworzyć segment.</span><span class="sxs-lookup"><span data-stu-id="a8df5-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="a8df5-196">Po zakończeniu przetwarzania segmentu można go wyświetlić tak samo, jak każdy inny segment utworzony przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="a8df5-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a8df5-197">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="a8df5-197">Next steps</span></span>

<span data-ttu-id="a8df5-198">[Wyeksportuj segment](export-destinations.md) i zapoznaj się z [kartą klienta](customer-card-add-in.md) i [łącznikami](export-power-bi.md), aby zdobyć informacje na poziomie klienta.</span><span class="sxs-lookup"><span data-stu-id="a8df5-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
