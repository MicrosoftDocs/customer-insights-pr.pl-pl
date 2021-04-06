---
title: Tworzenie miar i zarządzanie nimi
description: Zdefiniuj miary do analizy i odzwierciedlenia wyników Twojej firmy.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654745"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="aef2f-103">Definiowanie miar i zarządzanie nimi</span><span class="sxs-lookup"><span data-stu-id="aef2f-103">Define and manage measures</span></span>

<span data-ttu-id="aef2f-104">Miary pomagają lepiej zrozumieć zachowania klientów i wyniki biznesowe poprzez pobieranie odpowiednich wartości z [ujednoliconych profili](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="aef2f-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="aef2f-105">Na przykład firma chce zobaczyć *łączne wydatki na klienta*, aby poznać historię zakupów poszczególnych klientów.</span><span class="sxs-lookup"><span data-stu-id="aef2f-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="aef2f-106">Lub zmierz *całkowitą sprzedaż firmy*, aby poznać łączne przychody z całej firmy.</span><span class="sxs-lookup"><span data-stu-id="aef2f-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="aef2f-107">Miary są tworzone za pomocą konstruktora miar, platformy zapytań o dane z różnymi operatorami i prostymi opcjami mapowania.</span><span class="sxs-lookup"><span data-stu-id="aef2f-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="aef2f-108">Umożliwia filtrowanie danych, grupowanie wyników, wykrywanie [ścieżek relacji między encjami](relationships.md) i wyświetlanie podglądu danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="aef2f-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="aef2f-109">Użyj konstruktora miar, aby zaplanować działania biznesowe, wykonując zapytania dotyczące danych klientów i wyodrębniając szczegółowe informacje.</span><span class="sxs-lookup"><span data-stu-id="aef2f-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="aef2f-110">Na przykład utworzenie miary *całkowitych wydatków na klienta* i *całkowitego zwrotu na klienta* pomaga zidentyfikować grupę klientów z wysokimi wydatkami, ale z wysokim zwrotem.</span><span class="sxs-lookup"><span data-stu-id="aef2f-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="aef2f-111">Możesz utworzyć [segment](segments.md), aby stworzyć najlepsze akcje.</span><span class="sxs-lookup"><span data-stu-id="aef2f-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="aef2f-112">Utwórz miarę</span><span class="sxs-lookup"><span data-stu-id="aef2f-112">Create a measure</span></span>

<span data-ttu-id="aef2f-113">W tej sekcji otworzymy nową miarę od podstaw.</span><span class="sxs-lookup"><span data-stu-id="aef2f-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="aef2f-114">Możesz zbudować miarę z atrybutami danych z jednostek danych, które mają skonfigurowaną relację do łączenia się z encją Klient.</span><span class="sxs-lookup"><span data-stu-id="aef2f-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="aef2f-115">W analizach odbiorców przejdź do **Miary**.</span><span class="sxs-lookup"><span data-stu-id="aef2f-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="aef2f-116">Wybierz **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="aef2f-116">Select **New**.</span></span>

1. <span data-ttu-id="aef2f-117">Wybierz opcję **Edytuj** nazwę i podaj **Nazwa** miary.</span><span class="sxs-lookup"><span data-stu-id="aef2f-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="aef2f-118">Jeśli nowa konfiguracja miary ma tylko dwa pola, na przykład IDklienta i jedno obliczenie, dane wyjściowe zostaną dodane jako nowa kolumna do jednostki wygenerowanej przez system o nazwie Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="aef2f-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="aef2f-119">Będziesz mógł zobaczyć wartość miary w ujednoliconym profilu klienta.</span><span class="sxs-lookup"><span data-stu-id="aef2f-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="aef2f-120">Inne miary będą generować własne encje.</span><span class="sxs-lookup"><span data-stu-id="aef2f-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="aef2f-121">W obszarze konfiguracji wybierz funkcję agregowania z menu rozwijanego **Wybierz funkcję**.</span><span class="sxs-lookup"><span data-stu-id="aef2f-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="aef2f-122">Funkcje agregowania obejmują:</span><span class="sxs-lookup"><span data-stu-id="aef2f-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="aef2f-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="aef2f-123">**Sum**</span></span>
   - <span data-ttu-id="aef2f-124">**Średnia**</span><span class="sxs-lookup"><span data-stu-id="aef2f-124">**Average**</span></span>
   - <span data-ttu-id="aef2f-125">**Licznik**</span><span class="sxs-lookup"><span data-stu-id="aef2f-125">**Count**</span></span>
   - <span data-ttu-id="aef2f-126">**Liczba unikatowych**</span><span class="sxs-lookup"><span data-stu-id="aef2f-126">**Count Unique**</span></span>
   - <span data-ttu-id="aef2f-127">**Maksimum**</span><span class="sxs-lookup"><span data-stu-id="aef2f-127">**Max**</span></span>
   - <span data-ttu-id="aef2f-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="aef2f-128">**Min**</span></span>
   - <span data-ttu-id="aef2f-129">**Pierwszy**: pobiera pierwszą wartość rekordu danych</span><span class="sxs-lookup"><span data-stu-id="aef2f-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="aef2f-130">**Ostatnia**: pobiera ostatnią wartość dodaną do rekordu danych</span><span class="sxs-lookup"><span data-stu-id="aef2f-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operatory do oceny obliczeń.":::

1. <span data-ttu-id="aef2f-132">Wybierz **Dodaj atrybut**, aby wybrać dane potrzebne do utworzenia tej miary.</span><span class="sxs-lookup"><span data-stu-id="aef2f-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="aef2f-133">Wybrane kartę **Atrybuty**.</span><span class="sxs-lookup"><span data-stu-id="aef2f-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="aef2f-134">Encja danych: wybierz encję zawierającą atrybut, który chcesz zmierzyć.</span><span class="sxs-lookup"><span data-stu-id="aef2f-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="aef2f-135">Atrybut danych: wybierz atrybut, którego chcesz użyć w funkcji agregowania, aby obliczyć miarę.</span><span class="sxs-lookup"><span data-stu-id="aef2f-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="aef2f-136">Możesz wybrać tylko jeden atrybut naraz.</span><span class="sxs-lookup"><span data-stu-id="aef2f-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="aef2f-137">Atrybut danych można także wybrać z istniejącej miary, wybierając kartę **Miary**. Można także wyszukać nazwę encji lub miary.</span><span class="sxs-lookup"><span data-stu-id="aef2f-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="aef2f-138">Wybierz opcję **Dodaj**, aby dodać do miary wybrany atrybut.</span><span class="sxs-lookup"><span data-stu-id="aef2f-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Wybierz atrybut, który ma być używany w obliczeniach.":::

1. <span data-ttu-id="aef2f-140">Aby zbudować bardziej złożone miary, możesz dodać więcej atrybutów lub użyć operatorów matematycznych w funkcji miary.</span><span class="sxs-lookup"><span data-stu-id="aef2f-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Utwórz złożoną miarę za pomocą operatorów matematycznych.":::

1. <span data-ttu-id="aef2f-142">Aby dodać filtry, wybierz **Filtr** w obszarze konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="aef2f-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="aef2f-143">W sekcji **Dodawanie atrybutu** w okienku **Filtry** wybierz atrybut, którego chcesz użyć do tworzenia filtrów.</span><span class="sxs-lookup"><span data-stu-id="aef2f-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="aef2f-144">Ustaw operatory filtru, aby zdefiniować filtr dla każdego wybranego atrybutu.</span><span class="sxs-lookup"><span data-stu-id="aef2f-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="aef2f-145">Wybierz opcję **Zastosuj**, aby dodać do miary wybrany filtr.</span><span class="sxs-lookup"><span data-stu-id="aef2f-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="aef2f-146">Aby dodać wymiary, wybierz **Wymiar** w obszarze konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="aef2f-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="aef2f-147">Wymiary będą wyświetlane jako kolumny w encji wyjściowej miary.</span><span class="sxs-lookup"><span data-stu-id="aef2f-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="aef2f-148">Wybierz opcję **Edytuj rozmiary**, aby dodać atrybuty danych, według których chcesz grupować wartości miary.</span><span class="sxs-lookup"><span data-stu-id="aef2f-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="aef2f-149">Na przykład miasto lub płeć.</span><span class="sxs-lookup"><span data-stu-id="aef2f-149">For example, city or gender.</span></span> <span data-ttu-id="aef2f-150">Domyślnie wymiar *CustomerID* jest wybrany do tworzenia *miar na poziomie klienta*.</span><span class="sxs-lookup"><span data-stu-id="aef2f-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="aef2f-151">Do utworzenia *miar na poziomie firmy* można usunąć rozmiar domyślny.</span><span class="sxs-lookup"><span data-stu-id="aef2f-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="aef2f-152">Wybierz opcję **Gotowe**, aby dodać do miary wybrany wymiar.</span><span class="sxs-lookup"><span data-stu-id="aef2f-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="aef2f-153">Jeśli istnieje wiele ścieżek między mapowaną encją danych a encją *Klient*, musisz wybrać jedną ze zidentyfikowanych [ścieżek relacji między encjami](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="aef2f-153">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="aef2f-154">Wyniki mogą się różnić w zależności od wybranej ścieżki.</span><span class="sxs-lookup"><span data-stu-id="aef2f-154">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="aef2f-155">Wybierz **preferencje dotyczące danych** i wybierz ścieżkę encji, która powinna być używana do identyfikacji miary.</span><span class="sxs-lookup"><span data-stu-id="aef2f-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="aef2f-156">Jeśli do encji *Klient* jest dostępna tylko jedna ścieżka, ta kontrolka nie będzie wyświetlana.</span><span class="sxs-lookup"><span data-stu-id="aef2f-156">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="aef2f-157">Wybierz opcję **Gotowe**, aby zastosować wybór.</span><span class="sxs-lookup"><span data-stu-id="aef2f-157">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Wybierz ścieżkę jednostki dla miary.":::

1. <span data-ttu-id="aef2f-159">Aby dodać więcej obliczeń dla miary, wybierz opcję **Nowe obliczenia**.</span><span class="sxs-lookup"><span data-stu-id="aef2f-159">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="aef2f-160">Do nowych obliczeń można używać tylko elementów znajdujących się na tej samej ścieżce encji.</span><span class="sxs-lookup"><span data-stu-id="aef2f-160">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="aef2f-161">Więcej obliczeń zostanie wyświetlonych jako nowe kolumny w jednostce wyniku pomiaru.</span><span class="sxs-lookup"><span data-stu-id="aef2f-161">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="aef2f-162">Wybierz opcję **...** w obliczeniach jako **Duplikat**, **Zmień nazwę** lub **Usuń** obliczenia z miary.</span><span class="sxs-lookup"><span data-stu-id="aef2f-162">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="aef2f-163">W obszarze **Podgląd** jest wyświetlony schemat danych encji wyjściowej miary wraz z filtrami i rozmiarami.</span><span class="sxs-lookup"><span data-stu-id="aef2f-163">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="aef2f-164">Podgląd jest dynamicznie reaktywny na zmiany w konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="aef2f-164">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="aef2f-165">Wybierz opcję **Uruchom**, aby obliczyć wyniki dla skonfigurowanej miary.</span><span class="sxs-lookup"><span data-stu-id="aef2f-165">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="aef2f-166">Wybierz opcję **Zapisz i zamknij**, jeśli chcesz zachować bieżącą konfigurację i uruchomić miarę później.</span><span class="sxs-lookup"><span data-stu-id="aef2f-166">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="aef2f-167">Wybierz **Miary**, aby zobaczyć nowo utworzoną miarę na liście.</span><span class="sxs-lookup"><span data-stu-id="aef2f-167">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="aef2f-168">Zarządzanie miarami</span><span class="sxs-lookup"><span data-stu-id="aef2f-168">Manage your measures</span></span>

<span data-ttu-id="aef2f-169">Po [utworzeniu jednej miary](#create-a-measure) zostanie wyświetlona lista miar na stronie **Miary**.</span><span class="sxs-lookup"><span data-stu-id="aef2f-169">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="aef2f-170">Znajdziesz informacje o rodzaju miary, twórcy, dacie utworzenia, stanie i stanie.</span><span class="sxs-lookup"><span data-stu-id="aef2f-170">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="aef2f-171">Po wybraniu miary z listy można wyświetlić podgląd wyniku i pobrać plik .CSV.</span><span class="sxs-lookup"><span data-stu-id="aef2f-171">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="aef2f-172">Aby odświeżyć wszystkie miary w tym samym czasie, wybierz **Odśwież wszystko** bez wybierania określonej miary.</span><span class="sxs-lookup"><span data-stu-id="aef2f-172">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="aef2f-173">![Akcje służące do zarządzania pojedynczymi miarami](media/measure-actions.png "Akcje służące do zarządzania pojedynczymi miarami")</span><span class="sxs-lookup"><span data-stu-id="aef2f-173">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="aef2f-174">Wybierz z listy miarę dla następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="aef2f-174">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="aef2f-175">Wybierz nazwę miary, aby wyświetlić jej szczegóły.</span><span class="sxs-lookup"><span data-stu-id="aef2f-175">Select the measure name to see its details.</span></span>
- <span data-ttu-id="aef2f-176">**Edytuj** konfigurację miary.</span><span class="sxs-lookup"><span data-stu-id="aef2f-176">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="aef2f-177">**Odśwież** miarę na podstawie najnowszych danych.</span><span class="sxs-lookup"><span data-stu-id="aef2f-177">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="aef2f-178">**Zmień nazwę** miary.</span><span class="sxs-lookup"><span data-stu-id="aef2f-178">**Rename** the measure.</span></span>
- <span data-ttu-id="aef2f-179">**Usuń** miarę.</span><span class="sxs-lookup"><span data-stu-id="aef2f-179">**Delete** the measure.</span></span>
- <span data-ttu-id="aef2f-180">**Aktywuj** lub **Dezaktywuj**.</span><span class="sxs-lookup"><span data-stu-id="aef2f-180">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="aef2f-181">Nieaktywne miary nie będą odświeżane podczas [zaplanowanego odświeżania](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="aef2f-181">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="aef2f-182">Istnieje [sześć typów stanu](system.md#status-types) zadań/procesów.</span><span class="sxs-lookup"><span data-stu-id="aef2f-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="aef2f-183">Ponadto większość procesów [zależy od innych procesów podrzędnych](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="aef2f-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="aef2f-184">Istnieje możliwość wybrania stanu procesu w celu wyświetlenia szczegółowych informacji o postępie w całym zadaniu.</span><span class="sxs-lookup"><span data-stu-id="aef2f-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="aef2f-185">Po wybraniu opcji **Zobacz szczegółowe informacje** dla jednego z zadań zadania, można znaleźć więcej informacji: czas przetwarzania, Data ostatniego przetwarzania oraz wszystkie błędy i ostrzeżenia skojarzone z zadaniem.</span><span class="sxs-lookup"><span data-stu-id="aef2f-185">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="aef2f-186">Następny krok</span><span class="sxs-lookup"><span data-stu-id="aef2f-186">Next step</span></span>

<span data-ttu-id="aef2f-187">Zastosowanie istniejących miar umożliwia utworzenie [segmentu klienta](segments.md).</span><span class="sxs-lookup"><span data-stu-id="aef2f-187">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]