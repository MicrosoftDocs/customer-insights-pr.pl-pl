---
title: Tworzenie segmentów i zarządzanie nimi
description: W celu pogrupowania klientów na podstawie różnych atrybutów można utworzyć ich segmenty.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 6931110c2ae93cd2792d319aa5a34f0df3088552
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406600"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="0ccff-103">Tworzenie segmentów i zarządzanie nimi</span><span class="sxs-lookup"><span data-stu-id="0ccff-103">Create and manage segments</span></span>

<span data-ttu-id="0ccff-104">Segmenty umożliwiają grupowanie klientów na podstawie atrybutów demograficznych, transakcyjnych i behawioralnych.</span><span class="sxs-lookup"><span data-stu-id="0ccff-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="0ccff-105">W celu realizacji celów biznesowych można korzystać z segmentów w celu ukierunkowania kampanii promocyjnych, działań sprzedaży i akcji obsługi klienta.</span><span class="sxs-lookup"><span data-stu-id="0ccff-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="0ccff-106">Istnieje możliwość zdefiniowania złożonych filtrów wokół encji profil klienta i encji pokrewnych.</span><span class="sxs-lookup"><span data-stu-id="0ccff-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="0ccff-107">Każdy segment, po przetworzeniu, tworzy zestaw rekordów klientów, który można eksportować i na którym można podejmować akcje.</span><span class="sxs-lookup"><span data-stu-id="0ccff-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="0ccff-108">Niektóre [ograniczenia dotyczące usług](service-limits.md) mają zastosowanie.</span><span class="sxs-lookup"><span data-stu-id="0ccff-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="0ccff-109">O ile nie zaznaczono inaczej, wszystkie segmenty są **Segmentami dynamicznymi**, które są odświeżane w harmonogramie cyklicznym.</span><span class="sxs-lookup"><span data-stu-id="0ccff-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="0ccff-110">Poniższy przykład ilustruje możliwości segmentacji.</span><span class="sxs-lookup"><span data-stu-id="0ccff-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="0ccff-111">Zdefiniowano segment dla klientów, którzy zamówili towary za przynajmniej 500 USD w ciągu ostatnich 90 dni *i* którzy uczestniczyli w rozmowie telefonicznej z obsługą klienta, która eskalowała.</span><span class="sxs-lookup"><span data-stu-id="0ccff-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0ccff-112">![Wiele grup](media/segmentation-group1-2.png "Wiele grup")</span><span class="sxs-lookup"><span data-stu-id="0ccff-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="0ccff-113">Utwórz nowy segment</span><span class="sxs-lookup"><span data-stu-id="0ccff-113">Create a new segment</span></span>

<span data-ttu-id="0ccff-114">Segmenty są zarządzane na stronie **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="0ccff-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="0ccff-115">W analizach odbiorców przejdź do strony **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="0ccff-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="0ccff-116">Wybierz **Nowy** > **Pusty segment**.</span><span class="sxs-lookup"><span data-stu-id="0ccff-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="0ccff-117">W okienku **nowy segment** wybierz typ segmentu i podaj jego **nazwę**.</span><span class="sxs-lookup"><span data-stu-id="0ccff-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="0ccff-118">Opcjonalnie można podać wyświetlaną nazwę i opis ułatwiający identyfikację segmentu.</span><span class="sxs-lookup"><span data-stu-id="0ccff-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="0ccff-119">Wybierz **Dalej**, aby połączyć się ze stroną **Konstruktor segmentu**, na której jest definiowana grupa.</span><span class="sxs-lookup"><span data-stu-id="0ccff-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="0ccff-120">Grupa jest zbiorem klientów.</span><span class="sxs-lookup"><span data-stu-id="0ccff-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="0ccff-121">Wybierz encję zawierającą atrybut, według którego chcesz segmentować.</span><span class="sxs-lookup"><span data-stu-id="0ccff-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="0ccff-122">Wybierz atrybut, według którego ma zostać przeprowadzona segmentacja.</span><span class="sxs-lookup"><span data-stu-id="0ccff-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="0ccff-123">Ten atrybut może mieć jeden z czterech typów wartości: numeryczny, ciąg, data lub wartość logiczna.</span><span class="sxs-lookup"><span data-stu-id="0ccff-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="0ccff-124">Wybierz operatora i wartość dla zaznaczonego atrybutu.</span><span class="sxs-lookup"><span data-stu-id="0ccff-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0ccff-125">![Niestandardowy filtr grup](media/customer-group-numbers.png "Filtr grupy klienta")</span><span class="sxs-lookup"><span data-stu-id="0ccff-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="0ccff-126">Numer</span><span class="sxs-lookup"><span data-stu-id="0ccff-126">Number</span></span> |<span data-ttu-id="0ccff-127">Definicja</span><span class="sxs-lookup"><span data-stu-id="0ccff-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="0ccff-128">1</span><span class="sxs-lookup"><span data-stu-id="0ccff-128">1</span></span>     |<span data-ttu-id="0ccff-129">Entity</span><span class="sxs-lookup"><span data-stu-id="0ccff-129">Entity</span></span>          |
   |<span data-ttu-id="0ccff-130">2</span><span class="sxs-lookup"><span data-stu-id="0ccff-130">2</span></span>     |<span data-ttu-id="0ccff-131">Atrybut</span><span class="sxs-lookup"><span data-stu-id="0ccff-131">Attribute</span></span>          |
   |<span data-ttu-id="0ccff-132">3</span><span class="sxs-lookup"><span data-stu-id="0ccff-132">3</span></span>    |<span data-ttu-id="0ccff-133">Operator</span><span class="sxs-lookup"><span data-stu-id="0ccff-133">Operator</span></span>         |
   |<span data-ttu-id="0ccff-134">100</span><span class="sxs-lookup"><span data-stu-id="0ccff-134">4</span></span>    |<span data-ttu-id="0ccff-135">Wartość</span><span class="sxs-lookup"><span data-stu-id="0ccff-135">Value</span></span>         |

8. <span data-ttu-id="0ccff-136">Jeśli encja jest połączona z zunifikowaną encją klient za pośrednictwem [relacji](relationships.md), należy zdefiniować ścieżkę relacji, aby utworzyć prawidłowy segment.</span><span class="sxs-lookup"><span data-stu-id="0ccff-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="0ccff-137">Dodaj encje ze ścieżki relacji, aż będzie można wybrać encję **Klient : CustomerInsights** z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="0ccff-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="0ccff-138">Następnie wybierz **Wszystkie rekordy** dla każdego warunku.</span><span class="sxs-lookup"><span data-stu-id="0ccff-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0ccff-139">![Ścieżka relacji podczas tworzenia segmentu](media/segments-multiple-relationships.png "Ścieżka relacji podczas tworzenia segmentu")</span><span class="sxs-lookup"><span data-stu-id="0ccff-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="0ccff-140">Wybierz **Zapisz**, aby zapisać segment.</span><span class="sxs-lookup"><span data-stu-id="0ccff-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="0ccff-141">Segment zostanie zapisany i przetworzony po sprawdzeniu poprawności wszystkich wymagań.</span><span class="sxs-lookup"><span data-stu-id="0ccff-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="0ccff-142">W przeciwnym razie zostanie zapisany jako wersja robocza.</span><span class="sxs-lookup"><span data-stu-id="0ccff-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="0ccff-143">Wybierz **Wróć do segmentów**, aby wrócić do strony **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="0ccff-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="0ccff-144">Zarządzanie istniejącymi segmentami</span><span class="sxs-lookup"><span data-stu-id="0ccff-144">Manage existing segments</span></span>

<span data-ttu-id="0ccff-145">Na stronie **Segmenty** można wyświetlić wszystkie zapamiętane segmenty i zarządzać nimi.</span><span class="sxs-lookup"><span data-stu-id="0ccff-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="0ccff-146">Każdy segment jest reprezentowany przez wiersz zawierający dodatkowe informacje o segmencie.</span><span class="sxs-lookup"><span data-stu-id="0ccff-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="0ccff-147">Aby posortować segmenty w kolumnie, należy wybrać nagłówek kolumny.</span><span class="sxs-lookup"><span data-stu-id="0ccff-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="0ccff-148">Użyj pola **Wyszukaj**, które znajduje się w prawym górnym rogu, aby filtrować segmenty.</span><span class="sxs-lookup"><span data-stu-id="0ccff-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0ccff-149">![Opcje zarządzania istniejącym segmentem](media/segments-selected-segment.png "Opcje zarządzania istniejącym segmentem")</span><span class="sxs-lookup"><span data-stu-id="0ccff-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="0ccff-150">Po wybraniu segmentu są dostępne następujące akcje:</span><span class="sxs-lookup"><span data-stu-id="0ccff-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="0ccff-151">**Wyświetlanie** szczegółowych informacji o segmencie, w tym trendu liczby członków podgląd składników segmentu.</span><span class="sxs-lookup"><span data-stu-id="0ccff-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="0ccff-152">**Edytuj** segment, aby zmienić jego właściwości.</span><span class="sxs-lookup"><span data-stu-id="0ccff-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="0ccff-153">**Odśwież** segment, aby uwzględnić najnowsze dane.</span><span class="sxs-lookup"><span data-stu-id="0ccff-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="0ccff-154">**Aktywuj** lub **Dezaktywuj** segment.</span><span class="sxs-lookup"><span data-stu-id="0ccff-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="0ccff-155">Segmenty mogą być w dwóch stanach — aktywnym lub nieaktywnym.</span><span class="sxs-lookup"><span data-stu-id="0ccff-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="0ccff-156">Te stany są przydatne przy edytowaniu segmentu.</span><span class="sxs-lookup"><span data-stu-id="0ccff-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="0ccff-157">W przypadku nieaktywnych segmentów definicja segmentu istnieje, ale nie zawiera jeszcze żadnych klientów.</span><span class="sxs-lookup"><span data-stu-id="0ccff-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="0ccff-158">W przypadku aktywowania segmentu jego stan zmieni się z "nieaktywny" na "aktywny" i rozpocznie wyszukiwanie klientów zgodnych z definicją segmentu.</span><span class="sxs-lookup"><span data-stu-id="0ccff-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="0ccff-159">Jeśli skonfigurowano [zaplanowane odświeżanie](system.md#schedule-tab), segment nieaktywne mają **Stan** wyświetlany jako **Pominięty**, co oznacza, że nie wystąpiła jeszcze próba odświeżenia.</span><span class="sxs-lookup"><span data-stu-id="0ccff-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="0ccff-160">W przypadku aktywowania nieaktywnego segmentu zostanie on odświeżony i będzie uwzględniony w zaplanowanych odświeżeniach.</span><span class="sxs-lookup"><span data-stu-id="0ccff-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="0ccff-161">Alternatywnie można użyć funkcji **Zaplanuj później** na liście rozwijanej **Aktywuj/Zdezaktywuj**, aby określić przyszłą datę i godzinę aktywacji i dezaktywacji konkretnego segmentu.</span><span class="sxs-lookup"><span data-stu-id="0ccff-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="0ccff-162">**Zmień nazwę** segmentu.</span><span class="sxs-lookup"><span data-stu-id="0ccff-162">**Rename** the segment.</span></span>
- <span data-ttu-id="0ccff-163">**Pobierz** listę członków jako plik .CSV.</span><span class="sxs-lookup"><span data-stu-id="0ccff-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="0ccff-164">Opcja **Dodaj do** wysyła listę identyfikatorów klientów w segmencie w celu ich przetworzenia w innej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="0ccff-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="0ccff-165">**Usuń** segment.</span><span class="sxs-lookup"><span data-stu-id="0ccff-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="0ccff-166">Odśwież segmenty</span><span class="sxs-lookup"><span data-stu-id="0ccff-166">Refresh segments</span></span>

<span data-ttu-id="0ccff-167">Można odświeżyć wszystkie segmenty naraz, wybierając **Odśwież wszystko** na stronie **Segmenty** lub odświeżyć jeden lub wiele segmentów po ich zaznaczeniu i wybraniu **Odśwież** z opcji.</span><span class="sxs-lookup"><span data-stu-id="0ccff-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="0ccff-168">Alternatywnie można skonfigurować cykliczne odświeżanie w **Administracja** > **System** > **Harmonogram**.</span><span class="sxs-lookup"><span data-stu-id="0ccff-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="0ccff-169">Istnieje [sześć typów stanu](system.md#status-types) zadań/procesów.</span><span class="sxs-lookup"><span data-stu-id="0ccff-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="0ccff-170">Ponadto większość procesów [zależy od innych procesów podrzędnych](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="0ccff-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="0ccff-171">Istnieje możliwość wybrania stanu procesu w celu wyświetlenia szczegółowych informacji o postępie w całym zadaniu.</span><span class="sxs-lookup"><span data-stu-id="0ccff-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="0ccff-172">Po wybraniu opcji **Zobacz szczegółowe informacje** dla jednego z zadań zadania, można znaleźć więcej informacji: czas przetwarzania, Data ostatniego przetwarzania oraz wszystkie błędy i ostrzeżenia skojarzone z zadaniem.</span><span class="sxs-lookup"><span data-stu-id="0ccff-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="0ccff-173">Pobieranie i eksportowanie segmentów</span><span class="sxs-lookup"><span data-stu-id="0ccff-173">Download and export segments</span></span>

<span data-ttu-id="0ccff-174">Segmenty można pobrać do pliku CSV lub wyeksportować je do Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="0ccff-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="0ccff-175">Pobierz segmenty do pliku CSV</span><span class="sxs-lookup"><span data-stu-id="0ccff-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="0ccff-176">W analizach odbiorców przejdź do strony **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="0ccff-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="0ccff-177">Wybierz wielokropek na kafelku konkretnego segmentu.</span><span class="sxs-lookup"><span data-stu-id="0ccff-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="0ccff-178">Z listy rozwijanej akcje wybierz polecenie **Pobierz jako CSV**.</span><span class="sxs-lookup"><span data-stu-id="0ccff-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="0ccff-179">Eksportuj segmenty do Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="0ccff-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="0ccff-180">Przed wyeksportowaniem segmentów do Dynamics 365 Sales, administrator musi [utworzyć miejsce docelowe eksportu](export-destinations.md) dla Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="0ccff-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="0ccff-181">W analizach odbiorców przejdź do strony **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="0ccff-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="0ccff-182">Wybierz wielokropek na kafelku konkretnego segmentu.</span><span class="sxs-lookup"><span data-stu-id="0ccff-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="0ccff-183">Z listy rozwijanej akcji wybierz **Dodaj do** i wybierz miejsce docelowe eksportu, do którego chcesz wysłać dane.</span><span class="sxs-lookup"><span data-stu-id="0ccff-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="0ccff-184">Tryb roboczy dla segmentów</span><span class="sxs-lookup"><span data-stu-id="0ccff-184">Draft mode for segments</span></span>

<span data-ttu-id="0ccff-185">Jeśli nie wszystkie wymagania dotyczące przetwarzania segmentu są spełnione, można zapisać dany segment jako wersję roboczą i uzyskać do niego dostęp z poziomu strony **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="0ccff-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="0ccff-186">Zostanie on zapisany w nieaktywnym segmencie i nie będzie można go aktywować, dopóki nie będzie prawidłowy.</span><span class="sxs-lookup"><span data-stu-id="0ccff-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="0ccff-187">Dodawanie warunków do grupy</span><span class="sxs-lookup"><span data-stu-id="0ccff-187">Add more conditions to a group</span></span>

<span data-ttu-id="0ccff-188">Aby dodać do grupy więcej warunków, można użyć dwóch operatorów logicznych:</span><span class="sxs-lookup"><span data-stu-id="0ccff-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="0ccff-189">**AND** operator: oba warunki muszą być spełnione w procesie segmentacji.</span><span class="sxs-lookup"><span data-stu-id="0ccff-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="0ccff-190">Ta opcja jest najbardziej przydatna podczas definiowania warunków między różnymi encjami.</span><span class="sxs-lookup"><span data-stu-id="0ccff-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="0ccff-191">**OR** operator: jeden z warunków musi zostać osiągnięty jako część procesu segmentacji.</span><span class="sxs-lookup"><span data-stu-id="0ccff-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="0ccff-192">Ta opcja jest najbardziej przydatna podczas definiowania wielu warunków dla tej samej encji.</span><span class="sxs-lookup"><span data-stu-id="0ccff-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0ccff-193">![OR operator, w którym oba warunki muszą zostać spełnione](media/segmentation-either-condition.png "OR operator, w którym oba warunki muszą zostać spełnione")</span><span class="sxs-lookup"><span data-stu-id="0ccff-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="0ccff-194">Obecnie istnieje możliwość zawinięcia operatora **OR** pod operatorem **AND**, ale nie na odwrót.</span><span class="sxs-lookup"><span data-stu-id="0ccff-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="0ccff-195">Łączenie wielu grup</span><span class="sxs-lookup"><span data-stu-id="0ccff-195">Combine multiple groups</span></span>

<span data-ttu-id="0ccff-196">Każda grupa dostarcza określony zbiór klientów.</span><span class="sxs-lookup"><span data-stu-id="0ccff-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="0ccff-197">Te grupy można połączyć w celu dołączenia klientów niezbędnych do pracy z sprawą biznesową.</span><span class="sxs-lookup"><span data-stu-id="0ccff-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="0ccff-198">W analizach odbiorców przejdź na stronę **Segmenty** i wybierz segment.</span><span class="sxs-lookup"><span data-stu-id="0ccff-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="0ccff-199">Wybierz **Dodaj grupę**.</span><span class="sxs-lookup"><span data-stu-id="0ccff-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0ccff-200">![Grupa klientów, Dodawanie grupy](media/customer-group-add-group.png "Grupa klientów, Dodawanie grupy")</span><span class="sxs-lookup"><span data-stu-id="0ccff-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="0ccff-201">Wybierz jeden z następujących operatorów zestawu: **Związek**, **Część wspólna** lub **Z wyjątkiem**.</span><span class="sxs-lookup"><span data-stu-id="0ccff-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0ccff-202">![Grupa klientów, Dodawanie związku](media/customer-group-union.png "Grupa klientów, Dodawanie związku")</span><span class="sxs-lookup"><span data-stu-id="0ccff-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="0ccff-203">Wybierz operator zestawu, aby zdefiniować nową grupę.</span><span class="sxs-lookup"><span data-stu-id="0ccff-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="0ccff-204">Zapisz różne grupy, aby określić, jakie dane mają zostać zachowane:</span><span class="sxs-lookup"><span data-stu-id="0ccff-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="0ccff-205">**Związek** łączy dwie grupy.</span><span class="sxs-lookup"><span data-stu-id="0ccff-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="0ccff-206">**Część wspólna** pokrywa się z dwiema grupami.</span><span class="sxs-lookup"><span data-stu-id="0ccff-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="0ccff-207">Tylko dane, które *są wspólne* dla obu grup, są zachowywane w ujednoliconej grupie.</span><span class="sxs-lookup"><span data-stu-id="0ccff-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="0ccff-208">**Z wyjątkiem** łączy dwie grupy.</span><span class="sxs-lookup"><span data-stu-id="0ccff-208">**Except** combines the two groups.</span></span> <span data-ttu-id="0ccff-209">Tylko dane w grupie A, które *nie są wspólne* dla grupy B, są zachowywane w ujednoliconej grupie.</span><span class="sxs-lookup"><span data-stu-id="0ccff-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="0ccff-210">Wyświetlanie historii przetwarzania i członków segmentu</span><span class="sxs-lookup"><span data-stu-id="0ccff-210">View processing history and segment members</span></span>

<span data-ttu-id="0ccff-211">Istnieje możliwość wyświetlenia skonsolidowanych danych o segmencie dzięki przejrzeniu jego szczegółów.</span><span class="sxs-lookup"><span data-stu-id="0ccff-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="0ccff-212">Na stronie **Segmenty** zaznacz segment, który chcesz przejrzeć.</span><span class="sxs-lookup"><span data-stu-id="0ccff-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="0ccff-213">W górnej części strony znajduje się wykres trendów zawierający wizualizacje zmian w licznikach członków.</span><span class="sxs-lookup"><span data-stu-id="0ccff-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="0ccff-214">Umieść wskaźnik myszy nad punktami danych, aby wyświetlić liczbę członków w określonym dniu.</span><span class="sxs-lookup"><span data-stu-id="0ccff-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="0ccff-215">Użytkownik może aktualizować horyzont czasowy wizualizacji.</span><span class="sxs-lookup"><span data-stu-id="0ccff-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0ccff-216">![Zakres czasu segmentu](media/segment-time-range.png "Zakres czasu segmentu")</span><span class="sxs-lookup"><span data-stu-id="0ccff-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="0ccff-217">W dolnej części znajduje się lista członków segmentu.</span><span class="sxs-lookup"><span data-stu-id="0ccff-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="0ccff-218">Pola wyświetlane na tej liście są oparte na atrybutach encji segmentu.</span><span class="sxs-lookup"><span data-stu-id="0ccff-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="0ccff-219">Lista jest podglądem pasujących składników segmentu i zawiera pierwsze 100 rekordów segmentu, dzięki czemu można szybko oceniać i przejrzeć w razie potrzeby jego definicje.</span><span class="sxs-lookup"><span data-stu-id="0ccff-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="0ccff-220">Aby wyświetlić wszystkie pasujące rekordy, należy [wyeksportować segment](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="0ccff-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="0ccff-221">Szybkie segmenty</span><span class="sxs-lookup"><span data-stu-id="0ccff-221">Quick segments</span></span>

<span data-ttu-id="0ccff-222">Poza konstruktorem segmentu istnieje też inna ścieżka do tworzenia segmentów.</span><span class="sxs-lookup"><span data-stu-id="0ccff-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="0ccff-223">Szybkie segmenty umożliwiają tworzenie prostych segmentów z jednym operatorem szybko i z natychmiastowymi wynikami analiz.</span><span class="sxs-lookup"><span data-stu-id="0ccff-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="0ccff-224">Na stronie **Segmenty** wybierz **Nowe** > **Szybko utwórz z**.</span><span class="sxs-lookup"><span data-stu-id="0ccff-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="0ccff-225">Wybierz opcję **profile**, aby zbudować segment utworzony na podstawie ujednoliconej encji klienta.</span><span class="sxs-lookup"><span data-stu-id="0ccff-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="0ccff-226">Wybierz opcję **miary**, aby zbudować segment dla każdego typu atrybutu klienta, który został uprzednio utworzony na stronie **miary**.</span><span class="sxs-lookup"><span data-stu-id="0ccff-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="0ccff-227">Wybierz opcję **Analizy**, aby utworzyć segment wokół jednej z encji wyjściowych wygenerowanych przy użyciu funkcji **Przewidywania** lub **Modele niestandardowe**.</span><span class="sxs-lookup"><span data-stu-id="0ccff-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="0ccff-228">W oknie dialogowym **Nowy szybki segment** wybierz atrybut z listy rozwijanej **Pole**.</span><span class="sxs-lookup"><span data-stu-id="0ccff-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="0ccff-229">W ramach systemu będzie dostępne kilka dodatkowych informacji ułatwiających stworzenie lepszych segmentów klientów.</span><span class="sxs-lookup"><span data-stu-id="0ccff-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="0ccff-230">W przypadku pól kategorii pokażemy 10 największych klientów.</span><span class="sxs-lookup"><span data-stu-id="0ccff-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="0ccff-231">Wybierz **Wartość** i wybierz **Przejrzyj**.</span><span class="sxs-lookup"><span data-stu-id="0ccff-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="0ccff-232">W przypadku atrybutu numerycznego system pokaże, jaka wartość atrybutu mieści się w percentylu każdego klienta</span><span class="sxs-lookup"><span data-stu-id="0ccff-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="0ccff-233">Wybierz **Operator** i **Wartość**, a następnie wybierz pozycję **Przeglądaj**.</span><span class="sxs-lookup"><span data-stu-id="0ccff-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="0ccff-234">System zaproponuje opcje **Szacowany rozmiar segmentu**.</span><span class="sxs-lookup"><span data-stu-id="0ccff-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="0ccff-235">Użytkownik może wybrać, czy ma zostać wyświetlona definicja segmentu, czy też najpierw ją ponownie przejrzeć w celu uzyskania innego rozmiaru segmentu.</span><span class="sxs-lookup"><span data-stu-id="0ccff-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0ccff-236">![Nazwa i oszacowanie szybkiego segmentu](media/quick-segment-name.png "Nazwa i oszacowanie szybkiego segmentu")</span><span class="sxs-lookup"><span data-stu-id="0ccff-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="0ccff-237">Podaj **Nazwę** segmentu.</span><span class="sxs-lookup"><span data-stu-id="0ccff-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="0ccff-238">Opcjonalnie, podaj **Nazwę wyświetlaną**.</span><span class="sxs-lookup"><span data-stu-id="0ccff-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="0ccff-239">Wybierz opcję **Zapisz**, aby utworzyć segment.</span><span class="sxs-lookup"><span data-stu-id="0ccff-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="0ccff-240">Po zakończeniu przetwarzania segmentu można go wyświetlić tak samo, jak każdy inny segment utworzony przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="0ccff-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="0ccff-241">W poniższych scenariuszach zaleca się użycie konstruktora segment zamiast możliwości zalecanego segmentu:</span><span class="sxs-lookup"><span data-stu-id="0ccff-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="0ccff-242">Tworzenie segmentów z filtrami na polach jakościowych, w których operator jest inny niż operator **Is**.</span><span class="sxs-lookup"><span data-stu-id="0ccff-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="0ccff-243">Tworzenie segmentów z filtrami na polach numerycznych, w których operator jest inny niż operatory **Między**, **Większe niż** i **Mniejsze niż**.</span><span class="sxs-lookup"><span data-stu-id="0ccff-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="0ccff-244">Tworzenie segmentów z filtrami w polach typu Data</span><span class="sxs-lookup"><span data-stu-id="0ccff-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="0ccff-245">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="0ccff-245">Next steps</span></span>

<span data-ttu-id="0ccff-246">[Wyeksportuj segment](export-destinations.md) i zapoznaj się z [kartą klienta](customer-card-add-in.md) i [łącznikami](export-power-bi.md), aby zdobyć informacje na poziomie klienta.</span><span class="sxs-lookup"><span data-stu-id="0ccff-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>
