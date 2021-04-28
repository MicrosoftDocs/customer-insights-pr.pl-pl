---
title: Scalanie encji w przypadku zjednoczenia danych
description: Scalanie encji w celu utworzenia ujednoliconych profili klientów.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4ad06a0baf57e612fc0e0214dfd23d28e7d2b6be
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896524"
---
# <a name="merge-entities"></a><span data-ttu-id="d8571-103">Scalanie encji</span><span class="sxs-lookup"><span data-stu-id="d8571-103">Merge entities</span></span>

<span data-ttu-id="d8571-104">Faza scalania jest ostatnią fazą procesu unifikacji danych.</span><span class="sxs-lookup"><span data-stu-id="d8571-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="d8571-105">Jego zastosowanie powoduje uzgadnianie danych powodujących konflikty.</span><span class="sxs-lookup"><span data-stu-id="d8571-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="d8571-106">Przykłady danych powodujących konflikty mogą zawierać nazwy klientów znalezione w dwóch zestawach danych, które są wyświetlane w różny sposób w każdym miejscu („Grant Marshall” i „Grant Marshal”) lub numery telefoniczne, który różnią się formatem (617-803-091X a 617803091X).</span><span class="sxs-lookup"><span data-stu-id="d8571-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="d8571-107">Scalanie tych niezgodnych danych jest wykonywane na podstawie poszczególnych atrybutów.</span><span class="sxs-lookup"><span data-stu-id="d8571-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="d8571-108">Po zakończeniu [fazy dopasowania](match-entities.md) można rozpocząć fazę scalenia, zaznaczając kafelek **Scalanie** na stronie **Ujednolicanie**.</span><span class="sxs-lookup"><span data-stu-id="d8571-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="d8571-109">Przejrzyj rekomendacje systemu</span><span class="sxs-lookup"><span data-stu-id="d8571-109">Review system recommendations</span></span>

<span data-ttu-id="d8571-110">Na stronie **Scalanie** można wybrać atrybuty do scalenia w encji ujednoliconego profilu klienta (wynik procesu konfiguracji).</span><span class="sxs-lookup"><span data-stu-id="d8571-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="d8571-111">Niektóre atrybuty są automatycznie scalane przez system.</span><span class="sxs-lookup"><span data-stu-id="d8571-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="d8571-112">Zobacz scalone atrybuty</span><span class="sxs-lookup"><span data-stu-id="d8571-112">View merged attributes</span></span>

<span data-ttu-id="d8571-113">Aby wyświetlić atrybuty, które są uwzględnione w jednym z automatycznie scalanych atrybutów, wybierz atrybut, który ma zostać scalony.</span><span class="sxs-lookup"><span data-stu-id="d8571-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="d8571-114">Dwa atrybuty składające się na ten scalony atrybut są wyświetlane w dwóch nowych wierszach pod atrybutem scalonym.</span><span class="sxs-lookup"><span data-stu-id="d8571-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d8571-115">![Wyszukaj scalony atrybut](media/configure-data-merge-profile-attributes.png "Wyszukaj scalony atrybut")</span><span class="sxs-lookup"><span data-stu-id="d8571-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="d8571-116">Oddziel scalone atrybuty</span><span class="sxs-lookup"><span data-stu-id="d8571-116">Separate merged attributes</span></span>

<span data-ttu-id="d8571-117">Aby wyodrębnić lub rozdzielić każdy z automatycznie scalonych atrybutów, znajdź atrybut w tabeli **Atrybuty profilu**.</span><span class="sxs-lookup"><span data-stu-id="d8571-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="d8571-118">Wybierz przycisk wielokropka (...).</span><span class="sxs-lookup"><span data-stu-id="d8571-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="d8571-119">Z listy rozwijanej wybierz **Rozdziel pola**.</span><span class="sxs-lookup"><span data-stu-id="d8571-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="d8571-120">Usuwanie scalonych atrybutów</span><span class="sxs-lookup"><span data-stu-id="d8571-120">Remove merged attributes</span></span>

<span data-ttu-id="d8571-121">Aby wykluczyć atrybut z ostatecznej encji profilu klienta, należy go znaleźć w tabeli **Atrybuty profilu**.</span><span class="sxs-lookup"><span data-stu-id="d8571-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="d8571-122">Wybierz przycisk wielokropka (...).</span><span class="sxs-lookup"><span data-stu-id="d8571-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="d8571-123">Z listy rozwijanej wybierz **Nie scalaj**.</span><span class="sxs-lookup"><span data-stu-id="d8571-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="d8571-124">Atrybut zostanie przeniesiony do sekcji **Usunięto z rekordu klienta**.</span><span class="sxs-lookup"><span data-stu-id="d8571-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="d8571-125">Ręczne dodanie scalonego atrybutu</span><span class="sxs-lookup"><span data-stu-id="d8571-125">Manually add a merged attribute</span></span>

<span data-ttu-id="d8571-126">Aby dodać scalony atrybut, przejdź na stronę **Scalanie**.</span><span class="sxs-lookup"><span data-stu-id="d8571-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="d8571-127">Wybierz **Dodaj scalony atrybut**.</span><span class="sxs-lookup"><span data-stu-id="d8571-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="d8571-128">Podaj **Nazwę**, która będzie identyfikować go na stronie **Scalenie** później.</span><span class="sxs-lookup"><span data-stu-id="d8571-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="d8571-129">Opcjonalnie wprowadź **Nazwę wyświetlaną**, która będzie widoczna w encji ujednoliconego profilu klienta.</span><span class="sxs-lookup"><span data-stu-id="d8571-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="d8571-130">Konfigurowanie **Wybierz zduplikowane atrybuty** w celu wybrania atrybutów, które mają być scalane z dopasowanych encji.</span><span class="sxs-lookup"><span data-stu-id="d8571-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="d8571-131">Istnieje również możliwość wyszukiwania atrybutów.</span><span class="sxs-lookup"><span data-stu-id="d8571-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="d8571-132">Ustaw **Klasyfikuj wg ważności**, aby nadać priorytety jednemu atrybutowi nad innym.</span><span class="sxs-lookup"><span data-stu-id="d8571-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="d8571-133">Jeśli na przykład encja *WebAccountCSV* zawiera najbardziej dokładne dane o atrybucie *Pełna nazwa*, można przypisać tę encję ponad *ContactCSV*, wybierając pozycję *WebAccountCSV*.</span><span class="sxs-lookup"><span data-stu-id="d8571-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="d8571-134">W efekcie *WebAccountCSV* przechodzi do pierwszego priorytetu, podczas gdy *ContactCSV* przechodzi do drugiego priorytetu podczas ściągania wartości atrybutu *Pełna nazwa*.</span><span class="sxs-lookup"><span data-stu-id="d8571-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="d8571-135">Uruchamianie scalania</span><span class="sxs-lookup"><span data-stu-id="d8571-135">Run your merge</span></span>

<span data-ttu-id="d8571-136">Niezależnie od tego, czy ręcznie scalono atrybuty, czy pozwolono, aby system je scalił, zawsze można uruchomić scalanie.</span><span class="sxs-lookup"><span data-stu-id="d8571-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="d8571-137">Wybierz **Uruchom** na stronie **Scalanie**, aby zacząć proces.</span><span class="sxs-lookup"><span data-stu-id="d8571-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d8571-138">![Zapis i uruchomienie scalania danych](media/configure-data-merge-save-run.png "Zapis i uruchomienie scalania danych")</span><span class="sxs-lookup"><span data-stu-id="d8571-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="d8571-139">Aby dokonać dodatkowych zmian i ponownie uruchomić krok, można anulować trwający proces scalania.</span><span class="sxs-lookup"><span data-stu-id="d8571-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="d8571-140">Wybierz **Odświeżanie...** i wybierz **Anuluj zadanie**  w pojawiającym się okienku bocznym.</span><span class="sxs-lookup"><span data-stu-id="d8571-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="d8571-141">Gdy tekst **Odświeżanie ...** zostanie zmieniony na **Pomyślne**, scalanie zakończyło się i rozwiązano sprzeczności w danych zgodnie z określonymi zasadami.</span><span class="sxs-lookup"><span data-stu-id="d8571-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="d8571-142">Połączone i niepołączone atrybuty są zawarte w encji ujednolicony profil.</span><span class="sxs-lookup"><span data-stu-id="d8571-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="d8571-143">Wykluczone atrybuty nie są zawarte w encji ujednolicony profil.</span><span class="sxs-lookup"><span data-stu-id="d8571-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="d8571-144">Jeśli nie było to pierwsze pomyślnie uruchomienie scalania, wszystkie procesy podrzędne, w tym wzbogacanie, segmentacja i miary, zostaną automatycznie uruchomione ponownie.</span><span class="sxs-lookup"><span data-stu-id="d8571-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="d8571-145">Po ponownym uruchomieniu wszystkich procesów podrzędnych profile klienta odzwierciedlają wszelkie wprowadzone zmiany.</span><span class="sxs-lookup"><span data-stu-id="d8571-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="d8571-146">Istnieje [sześć typów stanu](system.md#status-types) zadań/procesów.</span><span class="sxs-lookup"><span data-stu-id="d8571-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="d8571-147">Ponadto większość procesów [zależy od innych procesów podrzędnych](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="d8571-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="d8571-148">Istnieje możliwość wybrania stanu procesu w celu wyświetlenia szczegółowych informacji o postępie w całym zadaniu.</span><span class="sxs-lookup"><span data-stu-id="d8571-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="d8571-149">Po wybraniu opcji **Zobacz szczegółowe informacje** dla jednego z zadań zadania, można znaleźć więcej informacji: czas przetwarzania, Data ostatniego przetwarzania oraz wszystkie błędy i ostrzeżenia skojarzone z zadaniem.</span><span class="sxs-lookup"><span data-stu-id="d8571-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="d8571-150">Następny krok</span><span class="sxs-lookup"><span data-stu-id="d8571-150">Next Step</span></span>

<span data-ttu-id="d8571-151">Skonfiguruj [działania](activities.md), [wzbogacenie](enrichment-hub.md) lub [relacje](relationships.md), aby uzyskać dokładniejsze informacje o klientach.</span><span class="sxs-lookup"><span data-stu-id="d8571-151">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="d8571-152">Jeśli zostały już skonfigurowane działania, wzbogacenia lub relacje lub jeśli segmenty są zdefiniowane, zostaną one automatycznie przetworzone w celu korzystania z najnowszych danych klienta.</span><span class="sxs-lookup"><span data-stu-id="d8571-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]