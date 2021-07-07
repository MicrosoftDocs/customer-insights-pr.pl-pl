---
title: Scalanie encji w przypadku zjednoczenia danych
description: Scalanie encji w celu utworzenia ujednoliconych profili klientów.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305664"
---
# <a name="merge-entities"></a><span data-ttu-id="b5593-103">Scalanie encji</span><span class="sxs-lookup"><span data-stu-id="b5593-103">Merge entities</span></span>

<span data-ttu-id="b5593-104">Faza scalania jest ostatnią fazą procesu unifikacji danych.</span><span class="sxs-lookup"><span data-stu-id="b5593-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="b5593-105">Jego zastosowanie powoduje uzgadnianie danych powodujących konflikty.</span><span class="sxs-lookup"><span data-stu-id="b5593-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="b5593-106">Przykłady danych powodujących konflikty mogą zawierać nazwy klientów znalezione w dwóch zestawach danych, które są wyświetlane w różny sposób w każdym miejscu („Grant Marshall” i „Grant Marshal”) lub numery telefoniczne, który różnią się formatem (617-803-091X a 617803091X).</span><span class="sxs-lookup"><span data-stu-id="b5593-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="b5593-107">Scalanie tych niezgodnych danych jest wykonywane na podstawie poszczególnych atrybutów.</span><span class="sxs-lookup"><span data-stu-id="b5593-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Strona scalania w procesie ujednolicania danych pokazująca tabelę z połączonymi polami definiującymi ujednolicony profil klienta.":::

<span data-ttu-id="b5593-109">Po zakończeniu [fazy dopasowania](match-entities.md) można rozpocząć fazę scalenia, zaznaczając kafelek **Scalanie** na stronie **Ujednolicanie**.</span><span class="sxs-lookup"><span data-stu-id="b5593-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="b5593-110">Przejrzyj rekomendacje systemu</span><span class="sxs-lookup"><span data-stu-id="b5593-110">Review system recommendations</span></span>

<span data-ttu-id="b5593-111">W **Dane** > **Ujednolić** > **Scal** wybierasz i wykluczasz atrybuty do połączenia w ramach ujednoliconej jednostki profilu klienta.</span><span class="sxs-lookup"><span data-stu-id="b5593-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="b5593-112">Ujednolicony profil klienta jest wynikiem procesu unifikacji danych.</span><span class="sxs-lookup"><span data-stu-id="b5593-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="b5593-113">Niektóre atrybuty są automatycznie scalane przez system.</span><span class="sxs-lookup"><span data-stu-id="b5593-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="b5593-114">Aby zobaczyć atrybuty, które są zawarte w jednym z twoich automatycznie połączonych atrybutów, wybierz ten połączony atrybut **Pola klienta** na zakładce tabeli.</span><span class="sxs-lookup"><span data-stu-id="b5593-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="b5593-115">Dwa nowe wiersze tworzące scalony atrybut będą wyświetlane w dwóch nowych wierszach pod atrybutem scalonym.</span><span class="sxs-lookup"><span data-stu-id="b5593-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="b5593-116">Rozdzielanie, zmienianie nazw, wykluczanie i edytowanie pól scalonych</span><span class="sxs-lookup"><span data-stu-id="b5593-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="b5593-117">W celu wygenerowania ujednoliconego profilu klienta można zmienić sposób przetwarzania przez system scalonych atrybutów.</span><span class="sxs-lookup"><span data-stu-id="b5593-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="b5593-118">Wybierz opcję **Pokaż więcej** i wybierz, co chcesz zmienić.</span><span class="sxs-lookup"><span data-stu-id="b5593-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Opcje w menu rozwijanym Pokaż więcej, aby zarządzać połączonymi atrybutami.":::

<span data-ttu-id="b5593-120">Aby uzyskać więcej informacji, zobacz następną sekcję.</span><span class="sxs-lookup"><span data-stu-id="b5593-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="b5593-121">Oddzielenie połączonych pól</span><span class="sxs-lookup"><span data-stu-id="b5593-121">Separate merged fields</span></span>

<span data-ttu-id="b5593-122">Aby oddzielić połączone pola, znajdź atrybut w tabeli.</span><span class="sxs-lookup"><span data-stu-id="b5593-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="b5593-123">Oddzielone pola są wyświetlane jako pojedyncze punkty danych na jednolitym profilu klienta.</span><span class="sxs-lookup"><span data-stu-id="b5593-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="b5593-124">Zaznacz scalone pole.</span><span class="sxs-lookup"><span data-stu-id="b5593-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="b5593-125">Wybierz opcję **Pokaż więcej** i wybierz pozycję **Rozdziel pola**.</span><span class="sxs-lookup"><span data-stu-id="b5593-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="b5593-126">Potwierdź rozdział.</span><span class="sxs-lookup"><span data-stu-id="b5593-126">Confirm the separation.</span></span>

1. <span data-ttu-id="b5593-127">Wybierz opcję **Zapisz** i **Uruchom**, aby przetworzyć zmiany.</span><span class="sxs-lookup"><span data-stu-id="b5593-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="b5593-128">Zmienianie nazw pól scalonych</span><span class="sxs-lookup"><span data-stu-id="b5593-128">Rename merged fields</span></span>

<span data-ttu-id="b5593-129">Zmień wyświetlaną nazwę scalonych atrybutów.</span><span class="sxs-lookup"><span data-stu-id="b5593-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="b5593-130">Nie można zmienić nazwy elementu wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="b5593-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="b5593-131">Zaznacz scalone pole.</span><span class="sxs-lookup"><span data-stu-id="b5593-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="b5593-132">Wybierz opcję **Pokaż więcej** i wybierz pozycję **Zmień nazwę**.</span><span class="sxs-lookup"><span data-stu-id="b5593-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="b5593-133">Potwierdź zmienioną nazwę wyświetlania.</span><span class="sxs-lookup"><span data-stu-id="b5593-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="b5593-134">Wybierz opcję **Zapisz** i **Uruchom**, aby przetworzyć zmiany.</span><span class="sxs-lookup"><span data-stu-id="b5593-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="b5593-135">Wykluczanie pól połączonych</span><span class="sxs-lookup"><span data-stu-id="b5593-135">Exclude merged fields</span></span>

<span data-ttu-id="b5593-136">Wykluczenie atrybutu z ujednoliconego profilu klienta.</span><span class="sxs-lookup"><span data-stu-id="b5593-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="b5593-137">Jeśli pole jest wykorzystywane w innych procesach, np. w segmencie, usuń je z tych procesów, zanim wykluczysz je z profilu klienta.</span><span class="sxs-lookup"><span data-stu-id="b5593-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="b5593-138">Zaznacz scalone pole.</span><span class="sxs-lookup"><span data-stu-id="b5593-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="b5593-139">Wybierz opcję **Pokaż więcej** i wybierz pozycję **Wyklucz**.</span><span class="sxs-lookup"><span data-stu-id="b5593-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="b5593-140">Potwierdź wykluczenie.</span><span class="sxs-lookup"><span data-stu-id="b5593-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="b5593-141">Wybierz opcję **Zapisz** i **Uruchom**, aby przetworzyć zmiany.</span><span class="sxs-lookup"><span data-stu-id="b5593-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="b5593-142">Na stronie **Scalanie** wybierz pozycję **Wykluczone pola**, aby wyświetlić listę wszystkich pól wykluczonych.</span><span class="sxs-lookup"><span data-stu-id="b5593-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="b5593-143">To okienko umożliwia dodawanie z powrotem wykluczonych pól.</span><span class="sxs-lookup"><span data-stu-id="b5593-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="b5593-144">Ręczne łączenie pól</span><span class="sxs-lookup"><span data-stu-id="b5593-144">Manually combine fields</span></span>

<span data-ttu-id="b5593-145">Określ ręcznie łączony atrybut.</span><span class="sxs-lookup"><span data-stu-id="b5593-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="b5593-146">Na stronie **Scalanie** wybierz opcję **Połącz pola**.</span><span class="sxs-lookup"><span data-stu-id="b5593-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="b5593-147">Podaj **nazwę** i **nazwę pola wyjściowego**.</span><span class="sxs-lookup"><span data-stu-id="b5593-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="b5593-148">Wybierz pole, które chcesz dodać.</span><span class="sxs-lookup"><span data-stu-id="b5593-148">Choose a field to add.</span></span> <span data-ttu-id="b5593-149">Wybierz **Dodaj pola**, aby połączyć więcej pól.</span><span class="sxs-lookup"><span data-stu-id="b5593-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="b5593-150">Potwierdź wykluczenie.</span><span class="sxs-lookup"><span data-stu-id="b5593-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="b5593-151">Wybierz opcję **Zapisz** i **Uruchom**, aby przetworzyć zmiany.</span><span class="sxs-lookup"><span data-stu-id="b5593-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="b5593-152">Zmiana kolejności pól</span><span class="sxs-lookup"><span data-stu-id="b5593-152">Change the order of fields</span></span>

<span data-ttu-id="b5593-153">Niektóre encje zawierają więcej szczegółów niż inne.</span><span class="sxs-lookup"><span data-stu-id="b5593-153">Some entities contain more details than others.</span></span> <span data-ttu-id="b5593-154">Jeśli encja zawiera najnowsze dane o polu, możesz nadać jej priorytet nad innymi encjami podczas łączenia wartości.</span><span class="sxs-lookup"><span data-stu-id="b5593-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="b5593-155">Zaznacz scalone pole.</span><span class="sxs-lookup"><span data-stu-id="b5593-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="b5593-156">Wybierz opcję **Pokaż więcej** i wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="b5593-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="b5593-157">W okienku **Łączenie pól** wybierz opcję **Przenieś w górę/w dół**, aby ustawić kolejność lub przeciągnij je i upuść w żądanym miejscu.</span><span class="sxs-lookup"><span data-stu-id="b5593-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="b5593-158">Potwierdź zmianę.</span><span class="sxs-lookup"><span data-stu-id="b5593-158">Confirm the change.</span></span>

1. <span data-ttu-id="b5593-159">Wybierz opcję **Zapisz** i **Uruchom**, aby przetworzyć zmiany.</span><span class="sxs-lookup"><span data-stu-id="b5593-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="b5593-160">Uruchamianie scalania</span><span class="sxs-lookup"><span data-stu-id="b5593-160">Run your merge</span></span>

<span data-ttu-id="b5593-161">Niezależnie od tego, czy ręcznie scalono atrybuty, czy pozwolono, aby system je scalił, zawsze można uruchomić scalanie.</span><span class="sxs-lookup"><span data-stu-id="b5593-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="b5593-162">Wybierz **Uruchom** na stronie **Scalanie**, aby zacząć proces.</span><span class="sxs-lookup"><span data-stu-id="b5593-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b5593-163">![Zapis i uruchomienie scalania danych](media/configure-data-merge-save-run.png "Zapis i uruchomienie scalania danych")</span><span class="sxs-lookup"><span data-stu-id="b5593-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="b5593-164">Wybierz opcję **Uruchom tylko scalanie**, jeśli chcesz, aby wyniki pracy zostały odzwierciedlone w ujednoliconej encji klienta.</span><span class="sxs-lookup"><span data-stu-id="b5593-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="b5593-165">Procesy niższego szczebla zostaną odświeżone zgodnie [z definicją w harmonogramie odświeżania](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b5593-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="b5593-166">Wybierz **Uruchom procesy scalania i procesy niższego rzędu**, aby odświeżyć system przy użyciu zmian.</span><span class="sxs-lookup"><span data-stu-id="b5593-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="b5593-167">Wszystkie procesy, w tym wzbogacenie, segmenty i miary, zostaną automatycznie ponownie uruchomione.</span><span class="sxs-lookup"><span data-stu-id="b5593-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="b5593-168">Po zakończeniu wszystkich dalszych procesów, profile klientów odzwierciedlają wszystkie wprowadzone zmiany.</span><span class="sxs-lookup"><span data-stu-id="b5593-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="b5593-169">Aby wprowadzić więcej zmian i ponownie uruchomić krok, można anulować trwające scalanie.</span><span class="sxs-lookup"><span data-stu-id="b5593-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="b5593-170">Wybierz **Odświeżanie...** i wybierz **Anuluj zadanie**  w pojawiającym się okienku bocznym.</span><span class="sxs-lookup"><span data-stu-id="b5593-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="b5593-171">Istnieje [sześć typów stanu](system.md#status-types) zadań/procesów.</span><span class="sxs-lookup"><span data-stu-id="b5593-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="b5593-172">Ponadto większość procesów [zależy od innych procesów podrzędnych](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="b5593-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="b5593-173">Istnieje możliwość wybrania stanu procesu w celu wyświetlenia szczegółowych informacji o postępie w całym zadaniu.</span><span class="sxs-lookup"><span data-stu-id="b5593-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="b5593-174">Po wybraniu opcji **Zobacz szczegółowe informacje** dla jednego z zadań zadania, można znaleźć więcej informacji: czas przetwarzania, Data ostatniego przetwarzania oraz wszystkie błędy i ostrzeżenia skojarzone z zadaniem.</span><span class="sxs-lookup"><span data-stu-id="b5593-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="b5593-175">Następny krok</span><span class="sxs-lookup"><span data-stu-id="b5593-175">Next Step</span></span>

<span data-ttu-id="b5593-176">Skonfiguruj [działania](activities.md), [wzbogacenie](enrichment-hub.md) lub [relacje](relationships.md), aby uzyskać dokładniejsze informacje o klientach.</span><span class="sxs-lookup"><span data-stu-id="b5593-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="b5593-177">Jeśli już skonfigurowałeś działania, wzbogacenia lub segmenty, zostaną one przetworzone automatycznie, aby wykorzystać najnowsze dane o klientach.</span><span class="sxs-lookup"><span data-stu-id="b5593-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
