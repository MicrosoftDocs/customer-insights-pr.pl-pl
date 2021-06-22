---
title: Segmenty w analizie odbiorców
description: Omówienie segmentów oraz sposobu ich tworzenia i zarządzania nimi.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6cb7bd62bf0f61e6dc5811b20e5011e4a086c743
ms.sourcegitcommit: 84283d523a891298fca8aaf629d9f9ab2a1bc067
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/27/2021
ms.locfileid: "6111400"
---
# <a name="segments-overview"></a><span data-ttu-id="89a3f-103">Omówienie segmentów</span><span class="sxs-lookup"><span data-stu-id="89a3f-103">Segments overview</span></span>

<span data-ttu-id="89a3f-104">Segmenty umożliwiają grupowanie klientów na podstawie atrybutów demograficznych, transakcyjnych i behawioralnych.</span><span class="sxs-lookup"><span data-stu-id="89a3f-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="89a3f-105">W celu realizacji celów biznesowych można korzystać z segmentów w celu ukierunkowania kampanii promocyjnych, działań sprzedaży i akcji obsługi klienta.</span><span class="sxs-lookup"><span data-stu-id="89a3f-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="89a3f-106">Profile klientów zgodne z filtrami definicji segmentu są określane mianem *członków* segmentu.</span><span class="sxs-lookup"><span data-stu-id="89a3f-106">Customer profiles that match the filters of a segment definition are referred as *members* of a segment.</span></span> <span data-ttu-id="89a3f-107">Niektóre [ograniczenia dotyczące usług](service-limits.md) mają zastosowanie.</span><span class="sxs-lookup"><span data-stu-id="89a3f-107">Some [service limits](service-limits.md) apply.</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="89a3f-108">Utwórz nowy segment</span><span class="sxs-lookup"><span data-stu-id="89a3f-108">Create a new segment</span></span>

<span data-ttu-id="89a3f-109">Istnieje wiele sposobów utworzenia nowego segmentu:</span><span class="sxs-lookup"><span data-stu-id="89a3f-109">There are multiple ways to create a new segment:</span></span> 

- <span data-ttu-id="89a3f-110">Złożony segment z konstruktorem segmentów: [pusty segment](segment-builder.md#create-a-new-segment)</span><span class="sxs-lookup"><span data-stu-id="89a3f-110">Complex segment with segment builder: [Blank segment](segment-builder.md#create-a-new-segment)</span></span>
- <span data-ttu-id="89a3f-111">Proste segmenty z jednym operatorem: [szybki segment](segment-builder.md#quick-segments)</span><span class="sxs-lookup"><span data-stu-id="89a3f-111">Simple segments with one operator: [Quick segment](segment-builder.md#quick-segments)</span></span>
- <span data-ttu-id="89a3f-112">Oparty na sztucznej inteligencji sposób na znalezienie podobnych klientów: [podobni klienci](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="89a3f-112">AI-powered way to find similar customers: [Similar Customers](find-similar-customer-segments.md)</span></span>
- <span data-ttu-id="89a3f-113">Sugestie oparte na SI, bazujące na miarach lub atrybutach: [sugerowane segmenty w celu usprawnienia działań](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="89a3f-113">AI-powered suggestions based on measures or attributes: [Suggested segments to improve measures](suggested-segments.md)</span></span>
- <span data-ttu-id="89a3f-114">Sugestie na bazie działań: [sugerowane segmenty oparte na działaniach klienta](suggested-segments-activity.md)</span><span class="sxs-lookup"><span data-stu-id="89a3f-114">Suggestions based on activities: [Suggested segments based on customer activity](suggested-segments-activity.md)</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="89a3f-115">Zarządzanie istniejącymi segmentami</span><span class="sxs-lookup"><span data-stu-id="89a3f-115">Manage existing segments</span></span>

<span data-ttu-id="89a3f-116">Przejdź na stronę **Segmenty**, aby wyświetlić wszystkie zapisane segmenty i zarządzać nimi.</span><span class="sxs-lookup"><span data-stu-id="89a3f-116">Go to the **Segments** page, to view all your saved segments and manage them.</span></span>

<span data-ttu-id="89a3f-117">Każdy segment jest reprezentowany przez wiersz zawierający dodatkowe informacje o segmencie.</span><span class="sxs-lookup"><span data-stu-id="89a3f-117">Each segment is represented by a row that includes additional information about the segment.</span></span>

:::image type="content" source="media/segments-selected-segment.png" alt-text="Wybrany segment z listą rozwijaną opcji i dostępnymi opcjami.":::

<span data-ttu-id="89a3f-119">Po wybraniu segmentu są dostępne następujące akcje:</span><span class="sxs-lookup"><span data-stu-id="89a3f-119">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="89a3f-120">**Wyświetlanie** szczegółowych informacji o segmencie, w tym trendu liczby członków podgląd składników segmentu.</span><span class="sxs-lookup"><span data-stu-id="89a3f-120">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="89a3f-121">**Edytuj** segment, aby zmienić jego właściwości.</span><span class="sxs-lookup"><span data-stu-id="89a3f-121">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="89a3f-122">**Utwórz duplikat** segmentu.</span><span class="sxs-lookup"><span data-stu-id="89a3f-122">**Create duplicate** of a segment.</span></span> <span data-ttu-id="89a3f-123">Można od razu edytować jego właściwości lub po prostu zapisać duplikat.</span><span class="sxs-lookup"><span data-stu-id="89a3f-123">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="89a3f-124">**Odśwież** segment, aby uwzględnić najnowsze dane.</span><span class="sxs-lookup"><span data-stu-id="89a3f-124">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="89a3f-125">**Aktywuj** lub **Dezaktywuj** segment.</span><span class="sxs-lookup"><span data-stu-id="89a3f-125">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="89a3f-126">Segmenty mogą być w dwóch stanach — aktywnym lub nieaktywnym.</span><span class="sxs-lookup"><span data-stu-id="89a3f-126">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="89a3f-127">Te stany są przydatne przy edytowaniu segmentu.</span><span class="sxs-lookup"><span data-stu-id="89a3f-127">These states come in handy when editing a segment.</span></span> <span data-ttu-id="89a3f-128">W przypadku nieaktywnych segmentów definicja segmentu istnieje, ale nie zawiera jeszcze żadnych klientów.</span><span class="sxs-lookup"><span data-stu-id="89a3f-128">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="89a3f-129">W przypadku aktywowania segmentu jego stan zmieni się z "nieaktywny" na "aktywny" i rozpocznie wyszukiwanie klientów zgodnych z definicją segmentu.</span><span class="sxs-lookup"><span data-stu-id="89a3f-129">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="89a3f-130">Jeśli skonfigurowano [zaplanowane odświeżanie](system.md#schedule-tab), segment nieaktywne mają **Stan** wyświetlany jako **Pominięty**, co oznacza, że nie wystąpiła jeszcze próba odświeżenia.</span><span class="sxs-lookup"><span data-stu-id="89a3f-130">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="89a3f-131">W przypadku aktywowania nieaktywnego segmentu zostanie on odświeżony i będzie uwzględniony w zaplanowanych odświeżeniach.</span><span class="sxs-lookup"><span data-stu-id="89a3f-131">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="89a3f-132">Alternatywnie można użyć funkcji **Zaplanuj później** na liście rozwijanej **Aktywuj/Zdezaktywuj**, aby określić przyszłą datę i godzinę aktywacji i dezaktywacji konkretnego segmentu.</span><span class="sxs-lookup"><span data-stu-id="89a3f-132">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="89a3f-133">**Zmień nazwę** segmentu.</span><span class="sxs-lookup"><span data-stu-id="89a3f-133">**Rename** the segment.</span></span>
- <span data-ttu-id="89a3f-134">**Pobierz** listę członków jako plik .CSV.</span><span class="sxs-lookup"><span data-stu-id="89a3f-134">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="89a3f-135">**Zarządzanie eksportami**, aby zobaczyć segmenty związane z eksportem i zarządzać nimi.</span><span class="sxs-lookup"><span data-stu-id="89a3f-135">**Manage exports** to see exports related segment and manage them.</span></span> [<span data-ttu-id="89a3f-136">Dowiedz się więcej o eksportach.</span><span class="sxs-lookup"><span data-stu-id="89a3f-136">Learn more about exports.</span></span>](export-destinations.md)
- <span data-ttu-id="89a3f-137">**Usuń** segment.</span><span class="sxs-lookup"><span data-stu-id="89a3f-137">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="89a3f-138">Odśwież segmenty</span><span class="sxs-lookup"><span data-stu-id="89a3f-138">Refresh segments</span></span>

<span data-ttu-id="89a3f-139">Można odświeżyć wszystkie segmenty naraz, wybierając **Odśwież wszystko** na stronie **Segmenty** lub odświeżyć jeden lub wiele segmentów po ich zaznaczeniu i wybraniu **Odśwież** z opcji.</span><span class="sxs-lookup"><span data-stu-id="89a3f-139">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="89a3f-140">Alternatywnie można skonfigurować cykliczne odświeżanie w **Administracja** > **System** > **Harmonogram**.</span><span class="sxs-lookup"><span data-stu-id="89a3f-140">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="89a3f-141">Istnieje [sześć typów stanu](system.md#status-types) zadań/procesów.</span><span class="sxs-lookup"><span data-stu-id="89a3f-141">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="89a3f-142">Ponadto większość procesów [zależy od innych procesów podrzędnych](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="89a3f-142">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="89a3f-143">Istnieje możliwość wybrania stanu procesu w celu wyświetlenia szczegółowych informacji o postępie w całym zadaniu.</span><span class="sxs-lookup"><span data-stu-id="89a3f-143">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="89a3f-144">Po wybraniu opcji **Zobacz szczegółowe informacje** dla jednego z zadań zadania, można znaleźć więcej informacji: czas przetwarzania, Data ostatniego przetwarzania oraz wszystkie błędy i ostrzeżenia skojarzone z zadaniem.</span><span class="sxs-lookup"><span data-stu-id="89a3f-144">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="export-segments"></a><span data-ttu-id="89a3f-145">Eksportowanie segmentów</span><span class="sxs-lookup"><span data-stu-id="89a3f-145">Export segments</span></span>

<span data-ttu-id="89a3f-146">Segment można wyeksportować ze strony segmentów lub ze [strony eksportowania](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="89a3f-146">You can export a segment from the segments page or the [exports page](export-destinations.md).</span></span> 

1. <span data-ttu-id="89a3f-147">Przejdź do strony **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="89a3f-147">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="89a3f-148">Wybierz **Pokaż więcej [...]** dla segmentu, który chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="89a3f-148">Select **Show more [...]** for the segment you want to export.</span></span>

1. <span data-ttu-id="89a3f-149">Wybierz **Zarządzaj eksportami** z listy rozwijanej akacji.</span><span class="sxs-lookup"><span data-stu-id="89a3f-149">Select **Manage exports** from the actions drop-down list.</span></span>

1. <span data-ttu-id="89a3f-150">Zostanie otwarta strona **Eksportty (wersja zapoznawcza) dla segmentu**.</span><span class="sxs-lookup"><span data-stu-id="89a3f-150">The page **Exports (preview) for segment** opens.</span></span> <span data-ttu-id="89a3f-151">Możesz zobaczyć wszystkie skonfigurowane eksporty pogrupowane według eksportów, które zawierają bieżący segment lub go nie zawierają.</span><span class="sxs-lookup"><span data-stu-id="89a3f-151">You can see all configured exports grouped by by exports that contain the current segment or don't contain it.</span></span>

   1. <span data-ttu-id="89a3f-152">Aby dodać wybrany segment do eksportu, wybierz eksport z listy i wybierz opcję **Dodaj segment**.</span><span class="sxs-lookup"><span data-stu-id="89a3f-152">To add the selected segment to an export, select the export in the list and select **Add segment**.</span></span>

   1. <span data-ttu-id="89a3f-153">Aby utworzyć nowy eksport dla wybranego segmentu, wybierz opcję **Dodaj eksport**.</span><span class="sxs-lookup"><span data-stu-id="89a3f-153">To create a new export with the selected segment, select **Add export**.</span></span> <span data-ttu-id="89a3f-154">Aby uzyskać więcej informacji o tworzeniu eksportów, zobacz [Konfiguracja nowego eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="89a3f-154">For more information about creating exports, see [Set up a new export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="89a3f-155">Wybierz opcję **Wstecz**, aby powrócić do strony głównej segmentów.</span><span class="sxs-lookup"><span data-stu-id="89a3f-155">Select **Back** to return to the main page for segments.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="89a3f-156">Wyświetlanie historii przetwarzania i członków segmentu</span><span class="sxs-lookup"><span data-stu-id="89a3f-156">View processing history and segment members</span></span>

<span data-ttu-id="89a3f-157">Istnieje możliwość wyświetlenia skonsolidowanych danych o segmencie dzięki przejrzeniu jego szczegółów.</span><span class="sxs-lookup"><span data-stu-id="89a3f-157">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="89a3f-158">Na stronie **Segmenty** zaznacz segment, który chcesz przejrzeć.</span><span class="sxs-lookup"><span data-stu-id="89a3f-158">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="89a3f-159">W górnej części strony znajduje się wykres trendów zawierający wizualizacje zmian w licznikach członków.</span><span class="sxs-lookup"><span data-stu-id="89a3f-159">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="89a3f-160">Umieść wskaźnik myszy nad punktami danych, aby wyświetlić liczbę członków w określonym dniu.</span><span class="sxs-lookup"><span data-stu-id="89a3f-160">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="89a3f-161">Użytkownik może aktualizować horyzont czasowy wizualizacji.</span><span class="sxs-lookup"><span data-stu-id="89a3f-161">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="89a3f-162">![Zakres czasu segmentu](media/segment-time-range.png "Zakres czasu segmentu")</span><span class="sxs-lookup"><span data-stu-id="89a3f-162">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="89a3f-163">W dolnej części znajduje się lista członków segmentu.</span><span class="sxs-lookup"><span data-stu-id="89a3f-163">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="89a3f-164">Pola wyświetlane na tej liście są oparte na atrybutach encji segmentu.</span><span class="sxs-lookup"><span data-stu-id="89a3f-164">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="89a3f-165">Lista jest podglądem pasujących składników segmentu i zawiera pierwsze 100 rekordów segmentu, dzięki czemu można szybko oceniać i przejrzeć w razie potrzeby jego definicje.</span><span class="sxs-lookup"><span data-stu-id="89a3f-165">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="89a3f-166">Aby wyświetlić wszystkie pasujące rekordy, należy [wyeksportować segment](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="89a3f-166">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
