---
title: Informacje o segmencie w istniejących segmentach
description: Uzyskiwanie wglądu w istniejące segmenty w celu wyświetlenia różnic i cech wspólnych.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: article
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 92e1b05dd08588a5da446af5b17b2d6ce57490ce
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406593"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="53b15-103">Informacje o segmentach (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="53b15-103">Segment insights (preview)</span></span>

<span data-ttu-id="53b15-104">Odkryj dodatkowe informacje i spostrzeżenia o istniejących segmentach.</span><span class="sxs-lookup"><span data-stu-id="53b15-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="53b15-105">Dowiedz się, co odróżnia dwa segmenty lub co mają ze sobą wspólnego.</span><span class="sxs-lookup"><span data-stu-id="53b15-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="53b15-106">Nakładanie się na siebie segmentów</span><span class="sxs-lookup"><span data-stu-id="53b15-106">Segment overlap</span></span>

<span data-ttu-id="53b15-107">Analiza nakładania się na siebie segmentów wskazuje, ilu klientów i którzy są wspólni dla dwóch lub więcej segmentów.</span><span class="sxs-lookup"><span data-stu-id="53b15-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="53b15-108">Na przykład, jak segment często występujących klientów pokrywa się z segmentem, który zawiera klientów, którzy są zadowoleni z usługi lub produktu.</span><span class="sxs-lookup"><span data-stu-id="53b15-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="53b15-109">Można również przeanalizować sposób zmiany nakładania się dla poszczególnych atrybutów.</span><span class="sxs-lookup"><span data-stu-id="53b15-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="53b15-110">Uruchamianie analizy nakładania się</span><span class="sxs-lookup"><span data-stu-id="53b15-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="53b15-111">Przejdź do **Segmenty**, a następnie wybierz kartę **Insights (wersja zapoznawcza)**.</span><span class="sxs-lookup"><span data-stu-id="53b15-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="53b15-112">Wybierz **Nowy**, i wybierz opcję **Nakładanie się** w okienku **Wybierz typ szczegółowych informacji**.</span><span class="sxs-lookup"><span data-stu-id="53b15-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="53b15-113">Wybierz segmenty i wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="53b15-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="53b15-114">Można też wybrać jedno lub kilka pól, aby analizować nakładanie się dla każdej możliwej wartości pola i wybrać **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="53b15-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="53b15-115">W tym celu należy określić nazwę analizy nakładania się, opcjonalną nazwę wyświetlaną, oraz opis.</span><span class="sxs-lookup"><span data-stu-id="53b15-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="53b15-116">Wybierz **Zapisz**, aby uruchomić analizę.</span><span class="sxs-lookup"><span data-stu-id="53b15-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="53b15-117">Analiza nakładania się jest gotowa, gdy stan zmieni się z Odświeżanie na Sukces.</span><span class="sxs-lookup"><span data-stu-id="53b15-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="53b15-118">Wyświetlanie i optymalizowanie analizy nakładania się</span><span class="sxs-lookup"><span data-stu-id="53b15-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="53b15-119">Po zakończeniu analizy znajdź szczegółowe informacje w **Segmenty** > **Insights (wersja zapoznawcza)**.</span><span class="sxs-lookup"><span data-stu-id="53b15-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Informacje szczegółowe dotyczące nakładania się na siebie segmentów":::

<span data-ttu-id="53b15-121">Aby wyświetlić wyniki analizy, należy wybrać szczegółowe informacje:</span><span class="sxs-lookup"><span data-stu-id="53b15-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="53b15-122">Liczba członków nakładających się na segmenty wybrane do analizy.</span><span class="sxs-lookup"><span data-stu-id="53b15-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="53b15-123">Liczba członków zawartych w jednym z segmentów, ale nie w pozostałych segmentach.</span><span class="sxs-lookup"><span data-stu-id="53b15-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="53b15-124">Jeśli podczas konfigurowania analizy nakładania się wybrano pola, pozostaną one na odpowiednich kartach.</span><span class="sxs-lookup"><span data-stu-id="53b15-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="53b15-125">Można użyć listy rozwijanej filtrów w celu wybrania dowolnego poziomu atrybutów, a w tabeli znajdującej się u dołu zostaną wyświetlone odpowiednie dane.</span><span class="sxs-lookup"><span data-stu-id="53b15-125">You can use the filter drop-down to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="53b15-126">Wyróżniki segmentów</span><span class="sxs-lookup"><span data-stu-id="53b15-126">Segment differentiators</span></span>

<span data-ttu-id="53b15-127">Elementy odróżniające segmenty pomagają dowiedzieć się, co odróżnia segment od pozostałej części klientów lub innego segmentu.</span><span class="sxs-lookup"><span data-stu-id="53b15-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="53b15-128">Wystarczy wybrać segment, a system zidentyfikuje atrybuty profilu i miary odróżniające wybrany segment.</span><span class="sxs-lookup"><span data-stu-id="53b15-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="53b15-129">Uruchamianie analizy elementów odróżniających</span><span class="sxs-lookup"><span data-stu-id="53b15-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="53b15-130">Przejdź do **Segmenty**, a następnie wybierz kartę **Insights (wersja zapoznawcza)**.</span><span class="sxs-lookup"><span data-stu-id="53b15-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="53b15-131">Wybierz **Nowy**, i wybierz opcję **Nakładanie się** w okienku **Wybierz typ szczegółowych informacji**.</span><span class="sxs-lookup"><span data-stu-id="53b15-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="53b15-132">Wybierz segment, który chcesz przeanalizować jako **Segment podstawowy**, i wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="53b15-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="53b15-133">Wybierz **Wszyscy klienci** lub **Segment pomocniczy**, aby porównać z nim segment podstawowy i wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="53b15-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="53b15-134">Lub wybierz co najmniej jedno pole, aby skoncentrować analizę na określonych atrybutach i wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="53b15-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="53b15-135">W tym celu należy określić nazwę analizy nakładania się, opcjonalną nazwę wyświetlaną, oraz opis.</span><span class="sxs-lookup"><span data-stu-id="53b15-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="53b15-136">Wybierz **Zapisz**, aby uruchomić analizę.</span><span class="sxs-lookup"><span data-stu-id="53b15-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="53b15-137">Analiza nakładania się jest gotowa, gdy stan zmieni się z Odświeżanie na Sukces.</span><span class="sxs-lookup"><span data-stu-id="53b15-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="53b15-138">Wyświetlanie i optymalizowanie analizy elementów odróżniających</span><span class="sxs-lookup"><span data-stu-id="53b15-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="53b15-139">Po zakończeniu analizy znajdź szczegółowe informacje w **Segmenty** > **Insights (wersja zapoznawcza)**.</span><span class="sxs-lookup"><span data-stu-id="53b15-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Informacje szczegółowe dotyczące elementów odróżniających segmenty":::

<span data-ttu-id="53b15-141">Aby wyświetlić wyniki analizy, należy wybrać szczegółowe informacje.</span><span class="sxs-lookup"><span data-stu-id="53b15-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="53b15-142">Analiza elementów odróżniających zawiera dwie karty.</span><span class="sxs-lookup"><span data-stu-id="53b15-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="53b15-143">Karta **Atrybuty** wyświetla atrybuty profilu, które są uważane za elementy odróżniające.</span><span class="sxs-lookup"><span data-stu-id="53b15-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="53b15-144">Karta **Miary** wyświetla elementy odróżniające.</span><span class="sxs-lookup"><span data-stu-id="53b15-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="53b15-145">Na każdej karcie znajdują się następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="53b15-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="53b15-146">Uporządkowana lista elementów odróżniających, uporządkowana według wyniku różnicy.</span><span class="sxs-lookup"><span data-stu-id="53b15-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="53b15-147">**Wynik różnicy** dla każdego elementu odróżniającego.</span><span class="sxs-lookup"><span data-stu-id="53b15-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="53b15-148">Wynik różnicy reprezentuje stopień zróżnicowania atrybutów między dwoma segmentami.</span><span class="sxs-lookup"><span data-stu-id="53b15-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="53b15-149">Im wyższy jest wynik różnicy, tym większe są różnice atrybutów między dwoma segmentami.</span><span class="sxs-lookup"><span data-stu-id="53b15-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="53b15-150">Wybierz wynik, aby otworzyć okienko **Wynik różnicy** wraz z rozkładami wartości dla tego atrybutu.</span><span class="sxs-lookup"><span data-stu-id="53b15-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="53b15-151">Zarządzanie szczegółowymi informacjami dotyczącymi segmentów</span><span class="sxs-lookup"><span data-stu-id="53b15-151">Manage segment insights</span></span>

<span data-ttu-id="53b15-152">Na pasku poleceń można korzystać z następujących opcji szczegółowych informacji:</span><span class="sxs-lookup"><span data-stu-id="53b15-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="53b15-153">**Wstecz**, aby wrócić do listy szczegółowych informacji</span><span class="sxs-lookup"><span data-stu-id="53b15-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="53b15-154">**Odśwież**, aby ponownie uruchomić analizę</span><span class="sxs-lookup"><span data-stu-id="53b15-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="53b15-155">**Usuń**, aby usunąć te szczegółowe informacje</span><span class="sxs-lookup"><span data-stu-id="53b15-155">**Delete** to remove this insight</span></span>
