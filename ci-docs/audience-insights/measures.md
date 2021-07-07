---
title: Tworzenie miar i zarządzanie nimi
description: Zdefiniuj miary do analizy i odzwierciedlenia wyników Twojej firmy.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a83caf2428f3dbd9791b9f746d00d370362a508c
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304815"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="bb627-103">Definiowanie miar i zarządzanie nimi</span><span class="sxs-lookup"><span data-stu-id="bb627-103">Define and manage measures</span></span>

<span data-ttu-id="bb627-104">Miary pomagają lepiej poznać zachowania klientów i wydajność biznesową.</span><span class="sxs-lookup"><span data-stu-id="bb627-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="bb627-105">Analizują one odpowiednie wartości z [ujednoliconych profilów](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="bb627-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="bb627-106">Na przykład, firma chce zobaczyć *całkowite wydatki na klienta*, aby zrozumieć historię zakupów poszczególnych klientów lub zmierzyć *całkowitą sprzedaż firmy*, aby zrozumieć zagregowany poziom przychodów w całej firmie.</span><span class="sxs-lookup"><span data-stu-id="bb627-106">For example, a business wants to see the *total spend per customer* to understand an individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="bb627-107">Miary są tworzone za pomocą konstruktora miar, platformy zapytań o dane z różnymi operatorami i prostymi opcjami mapowania.</span><span class="sxs-lookup"><span data-stu-id="bb627-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="bb627-108">Umożliwia filtrowanie danych, grupowanie wyników, wykrywanie [ścieżek relacji między encjami](relationships.md) i wyświetlanie podglądu danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="bb627-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="bb627-109">Użyj konstruktora miar, aby zaplanować działania biznesowe, wykonując zapytania dotyczące danych klientów i wyodrębniając szczegółowe informacje.</span><span class="sxs-lookup"><span data-stu-id="bb627-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="bb627-110">Na przykład utworzenie miary *całkowitych wydatków na klienta* i *całkowitego zwrotu na klienta* pomaga zidentyfikować grupę klientów z wysokimi wydatkami, ale z wysokim zwrotem.</span><span class="sxs-lookup"><span data-stu-id="bb627-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="bb627-111">Możesz utworzyć [segment](segments.md), aby stworzyć najlepsze akcje.</span><span class="sxs-lookup"><span data-stu-id="bb627-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="bb627-112">Utwórz własną miarę od podstaw</span><span class="sxs-lookup"><span data-stu-id="bb627-112">Build your own measure from scratch</span></span>

<span data-ttu-id="bb627-113">W tej sekcji otworzymy nową miarę od podstaw.</span><span class="sxs-lookup"><span data-stu-id="bb627-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="bb627-114">Możesz zbudować miarę z atrybutami danych z jednostek danych, które mają skonfigurowaną relację do łączenia się z encją Klient.</span><span class="sxs-lookup"><span data-stu-id="bb627-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="bb627-115">W analizach odbiorców przejdź do **Miary**.</span><span class="sxs-lookup"><span data-stu-id="bb627-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="bb627-116">Wybierz opcję **Nowa** i wybierz pozycję **Utwórz własną**.</span><span class="sxs-lookup"><span data-stu-id="bb627-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="bb627-117">Wybierz opcję **Edytuj** nazwę i podaj **Nazwa** miary.</span><span class="sxs-lookup"><span data-stu-id="bb627-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="bb627-118">Jeśli nowa konfiguracja miary ma tylko dwa pola, na przykład CustomerID i jedno wyliczenie, dane wyjściowe zostaną dodane jako nowa kolumna do wygenerowanej przez system encji o nazwie Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="bb627-118">If your new measure configuration has only two fields—for example, CustomerID and one calculation—the output will be added as a new column to the system-generated entity called Customer_Measure.</span></span> <span data-ttu-id="bb627-119">Będziesz mógł zobaczyć wartość miary w ujednoliconym profilu klienta.</span><span class="sxs-lookup"><span data-stu-id="bb627-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="bb627-120">Inne miary będą generować własne encje.</span><span class="sxs-lookup"><span data-stu-id="bb627-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="bb627-121">W obszarze konfiguracji wybierz funkcję agregowania z menu rozwijanego **Wybierz funkcję**.</span><span class="sxs-lookup"><span data-stu-id="bb627-121">In the configuration area, choose the aggregation function from the **Select Function** dropdown menu.</span></span> <span data-ttu-id="bb627-122">Funkcje agregowania obejmują:</span><span class="sxs-lookup"><span data-stu-id="bb627-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="bb627-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="bb627-123">**Sum**</span></span>
   - <span data-ttu-id="bb627-124">**Średnia**</span><span class="sxs-lookup"><span data-stu-id="bb627-124">**Average**</span></span>
   - <span data-ttu-id="bb627-125">**Licznik**</span><span class="sxs-lookup"><span data-stu-id="bb627-125">**Count**</span></span>
   - <span data-ttu-id="bb627-126">**Liczba unikatowych**</span><span class="sxs-lookup"><span data-stu-id="bb627-126">**Count Unique**</span></span>
   - <span data-ttu-id="bb627-127">**Maksimum**</span><span class="sxs-lookup"><span data-stu-id="bb627-127">**Max**</span></span>
   - <span data-ttu-id="bb627-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="bb627-128">**Min**</span></span>
   - <span data-ttu-id="bb627-129">**Pierwszy**: pobiera pierwszą wartość rekordu danych</span><span class="sxs-lookup"><span data-stu-id="bb627-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="bb627-130">**Ostatnia**: pobiera ostatnią wartość dodaną do rekordu danych</span><span class="sxs-lookup"><span data-stu-id="bb627-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operatory do oceny obliczeń.":::

1. <span data-ttu-id="bb627-132">Wybierz **Dodaj atrybut**, aby wybrać dane potrzebne do utworzenia tej miary.</span><span class="sxs-lookup"><span data-stu-id="bb627-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="bb627-133">Wybrane kartę **Atrybuty**.</span><span class="sxs-lookup"><span data-stu-id="bb627-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="bb627-134">Encja danych: wybierz encję zawierającą atrybut, który chcesz zmierzyć.</span><span class="sxs-lookup"><span data-stu-id="bb627-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="bb627-135">Atrybut danych: wybierz atrybut, którego chcesz użyć w funkcji agregowania, aby obliczyć miarę.</span><span class="sxs-lookup"><span data-stu-id="bb627-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="bb627-136">Możesz wybrać tylko jeden atrybut naraz.</span><span class="sxs-lookup"><span data-stu-id="bb627-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="bb627-137">Atrybut danych można także wybrać z istniejącej miary, wybierając kartę **Miary**. Można także wyszukać nazwę encji lub miary.</span><span class="sxs-lookup"><span data-stu-id="bb627-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="bb627-138">Wybierz opcję **Dodaj**, aby dodać do miary wybrany atrybut.</span><span class="sxs-lookup"><span data-stu-id="bb627-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Wybierz atrybut, który ma być używany w obliczeniach.":::

1. <span data-ttu-id="bb627-140">Aby zbudować bardziej złożone miary, możesz dodać więcej atrybutów lub użyć operatorów matematycznych w funkcji miary.</span><span class="sxs-lookup"><span data-stu-id="bb627-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Utwórz złożoną miarę za pomocą operatorów matematycznych.":::

1. <span data-ttu-id="bb627-142">Aby dodać filtry, wybierz **Filtr** w obszarze konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="bb627-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="bb627-143">W sekcji **Dodawanie atrybutu** okienka **Filtry** wybierz atrybut, którego chcesz użyć do tworzenia filtrów.</span><span class="sxs-lookup"><span data-stu-id="bb627-143">In the **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="bb627-144">Ustaw operatory filtru, aby zdefiniować filtr dla każdego wybranego atrybutu.</span><span class="sxs-lookup"><span data-stu-id="bb627-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="bb627-145">Wybierz opcję **Zastosuj**, aby dodać do miary wybrany filtr.</span><span class="sxs-lookup"><span data-stu-id="bb627-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="bb627-146">Aby dodać wymiary, wybierz **Wymiar** w obszarze konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="bb627-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="bb627-147">Wymiary będą wyświetlane jako kolumny w encji wyjściowej miary.</span><span class="sxs-lookup"><span data-stu-id="bb627-147">Dimensions will show as columns in the measure output entity.</span></span>
 
   1. <span data-ttu-id="bb627-148">Wybierz opcję **Edytuj rozmiary**, aby dodać atrybuty danych, według których chcesz grupować wartości miary.</span><span class="sxs-lookup"><span data-stu-id="bb627-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="bb627-149">Na przykład miasto lub płeć.</span><span class="sxs-lookup"><span data-stu-id="bb627-149">For example, city or gender.</span></span> <span data-ttu-id="bb627-150">Domyślnie wymiar *CustomerID* jest wybrany do tworzenia *miar na poziomie klienta*.</span><span class="sxs-lookup"><span data-stu-id="bb627-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="bb627-151">Do utworzenia *miar na poziomie firmy* można usunąć rozmiar domyślny.</span><span class="sxs-lookup"><span data-stu-id="bb627-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="bb627-152">Wybierz opcję **Gotowe**, aby dodać do miary wybrany wymiar.</span><span class="sxs-lookup"><span data-stu-id="bb627-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="bb627-153">Jeśli w danych są wartości, które trzeba zastąpić liczbą całkowitą, na przykład zastąp *null* wartością *0*, wybierz opcję **Reguły**.</span><span class="sxs-lookup"><span data-stu-id="bb627-153">If there are values in your data that you need to replace with an integer—for example, replace *null* with *0*—select **Rules**.</span></span> <span data-ttu-id="bb627-154">Skonfiguruj regułę i upewnij się, że jako zamienniki wybierane są tylko liczby całkowite.</span><span class="sxs-lookup"><span data-stu-id="bb627-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="bb627-155">Jeśli istnieje wiele ścieżek między mapowaną encją danych a encją *Klient*, musisz wybrać jedną ze zidentyfikowanych [ścieżek relacji między encjami](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="bb627-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="bb627-156">Wyniki mogą się różnić w zależności od wybranej ścieżki.</span><span class="sxs-lookup"><span data-stu-id="bb627-156">Measure results can vary depending on the selected path.</span></span> 
   
   1. <span data-ttu-id="bb627-157">Wybierz **preferencje dotyczące danych** i wybierz ścieżkę encji, która powinna być używana do identyfikacji miary.</span><span class="sxs-lookup"><span data-stu-id="bb627-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="bb627-158">Jeśli do encji *Klient* jest dostępna tylko jedna ścieżka, ta kontrolka nie będzie wyświetlana.</span><span class="sxs-lookup"><span data-stu-id="bb627-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="bb627-159">Wybierz opcję **Gotowe**, aby zastosować wybór.</span><span class="sxs-lookup"><span data-stu-id="bb627-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Wybierz ścieżkę jednostki dla miary.":::

1. <span data-ttu-id="bb627-161">Aby dodać więcej obliczeń dla miary, wybierz opcję **Nowe obliczenia**.</span><span class="sxs-lookup"><span data-stu-id="bb627-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="bb627-162">Do nowych obliczeń można używać tylko elementów znajdujących się na tej samej ścieżce encji.</span><span class="sxs-lookup"><span data-stu-id="bb627-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="bb627-163">Więcej obliczeń zostanie wyświetlonych jako nowe kolumny w jednostce wyniku pomiaru.</span><span class="sxs-lookup"><span data-stu-id="bb627-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="bb627-164">Wybierz opcję **...** w obliczeniach jako **Duplikat**, **Zmień nazwę** lub **Usuń** obliczenia z miary.</span><span class="sxs-lookup"><span data-stu-id="bb627-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="bb627-165">W obszarze **Podgląd** jest wyświetlony schemat danych encji wyjściowej miary wraz z filtrami i rozmiarami.</span><span class="sxs-lookup"><span data-stu-id="bb627-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="bb627-166">Podgląd jest dynamicznie reaktywny na zmiany w konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="bb627-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="bb627-167">Wybierz opcję **Uruchom**, aby obliczyć wyniki dla skonfigurowanej miary.</span><span class="sxs-lookup"><span data-stu-id="bb627-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="bb627-168">Wybierz opcję **Zapisz i zamknij**, jeśli chcesz zachować bieżącą konfigurację i uruchomić miarę później.</span><span class="sxs-lookup"><span data-stu-id="bb627-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="bb627-169">Wybierz **Miary**, aby zobaczyć nowo utworzoną miarę na liście.</span><span class="sxs-lookup"><span data-stu-id="bb627-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="bb627-170">Tworzenie miary za pomocą szablonu</span><span class="sxs-lookup"><span data-stu-id="bb627-170">Use a template to build a measure</span></span>

<span data-ttu-id="bb627-171">Do ich utworzenia miar można użyć wstępnie zdefiniowanych szablonów najczęściej stosowanych miar.</span><span class="sxs-lookup"><span data-stu-id="bb627-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="bb627-172">Szczegółowe opisy szablonów i działanie z przewodnikiem mogą ułatwić efektywne tworzenie miar.</span><span class="sxs-lookup"><span data-stu-id="bb627-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="bb627-173">Szablony są budowane na podstawie zamapowanych danych z encji *Ujednolicone działanie*.</span><span class="sxs-lookup"><span data-stu-id="bb627-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="bb627-174">Należy więc upewnić się, że skonfigurowano [działania klientów](activities.md) przed utworzeniem miary na podstawie szablonu.</span><span class="sxs-lookup"><span data-stu-id="bb627-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="bb627-175">Dostępne szablony miar:</span><span class="sxs-lookup"><span data-stu-id="bb627-175">Available measure templates:</span></span> 
- <span data-ttu-id="bb627-176">Średnia wartość transakcji (ATV)</span><span class="sxs-lookup"><span data-stu-id="bb627-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="bb627-177">Łączna wartość transakcji</span><span class="sxs-lookup"><span data-stu-id="bb627-177">Total transaction value</span></span>
- <span data-ttu-id="bb627-178">Średni przychód dzienny</span><span class="sxs-lookup"><span data-stu-id="bb627-178">Average daily revenue</span></span>
- <span data-ttu-id="bb627-179">Średni przychód roczny</span><span class="sxs-lookup"><span data-stu-id="bb627-179">Average yearly revenue</span></span>
- <span data-ttu-id="bb627-180">Liczba transakcji</span><span class="sxs-lookup"><span data-stu-id="bb627-180">Transaction count</span></span>
- <span data-ttu-id="bb627-181">Zdobyte punkty lojalnościowe</span><span class="sxs-lookup"><span data-stu-id="bb627-181">Loyalty points earned</span></span>
- <span data-ttu-id="bb627-182">Zrealizowane punkty lojalnościowe</span><span class="sxs-lookup"><span data-stu-id="bb627-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="bb627-183">Saldo punktów lojalnościowych</span><span class="sxs-lookup"><span data-stu-id="bb627-183">Loyalty points balance</span></span>
- <span data-ttu-id="bb627-184">Okres istnienia aktywnego klienta</span><span class="sxs-lookup"><span data-stu-id="bb627-184">Active customer lifespan</span></span>
- <span data-ttu-id="bb627-185">Czas trwania uczestnictwa w programie lojalnościowym</span><span class="sxs-lookup"><span data-stu-id="bb627-185">Loyalty membership duration</span></span>
- <span data-ttu-id="bb627-186">Czas od ostatniego zakupu</span><span class="sxs-lookup"><span data-stu-id="bb627-186">Time since last purchase</span></span>

<span data-ttu-id="bb627-187">W poniższej procedurze przedstawiono w zarysie kroki tworzenia nowej miary za pomocą szablonu.</span><span class="sxs-lookup"><span data-stu-id="bb627-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="bb627-188">W analizach odbiorców przejdź do **Miary**.</span><span class="sxs-lookup"><span data-stu-id="bb627-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="bb627-189">Wybierz **Nowy** i wybierz **Wybierz szablon**.</span><span class="sxs-lookup"><span data-stu-id="bb627-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Zrzut ekranu menu rozwijanego podczas tworzenia nowej miary z wyróżnieniem szablonu.":::

1. <span data-ttu-id="bb627-191">Znajdź szablon odpowiedni do potrzeb i wybierz opcję **Wybierz szablon**.</span><span class="sxs-lookup"><span data-stu-id="bb627-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="bb627-192">Przejrzyj wymagane dane i wybierz pozycję **Rozpocznij**, jeśli masz już wszystkie dane.</span><span class="sxs-lookup"><span data-stu-id="bb627-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="bb627-193">W okienku **Edycja nazwy** ustaw nazwę miary i encji wyjściowej.</span><span class="sxs-lookup"><span data-stu-id="bb627-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="bb627-194">Wybierz pozycję **Gotowe**.</span><span class="sxs-lookup"><span data-stu-id="bb627-194">Select **Done**.</span></span>

1. <span data-ttu-id="bb627-195">W sekcji **Ustawianie okresu czasu** zdefiniuj horyzont czasowy danych, które mają być użyte.</span><span class="sxs-lookup"><span data-stu-id="bb627-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="bb627-196">Określ, czy nowa miara ma obejmować cały zestaw danych, wybierając opcję **Ogółem** lub jeśli chcesz skupić się na **określonym okresie**.</span><span class="sxs-lookup"><span data-stu-id="bb627-196">Choose if you want the new measure to cover the entire dataset by selecting **All time**, or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Zrzut ekranu przedstawiający sekcję okresu podczas konfigurowania miary z szablonu.":::

1. <span data-ttu-id="bb627-198">W następnej sekcji wybierz pozycję **Dodaj dane**, aby wybrać działania i zmapować odpowiednie dane z encji *Ujednolicone działanie*.</span><span class="sxs-lookup"><span data-stu-id="bb627-198">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="bb627-199">Krok 1 z 2: w obszarze **Typ działania** wybierz typ encji, której chcesz użyć.</span><span class="sxs-lookup"><span data-stu-id="bb627-199">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="bb627-200">W przypadku **Działań** wybierz encje, które chcesz zamapować.</span><span class="sxs-lookup"><span data-stu-id="bb627-200">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="bb627-201">Krok 2 z 2: wybierz atrybut z encji *Ujednolicone działanie* dla składnika wymaganego przez formułę.</span><span class="sxs-lookup"><span data-stu-id="bb627-201">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="bb627-202">Na przykład w przypadku Średniej wartości transakcji jest to atrybut reprezentujący wartość Transakcji.</span><span class="sxs-lookup"><span data-stu-id="bb627-202">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="bb627-203">W przypadku **Znacznika czasu działania** wybierz atrybut z encji Ujednolicone działanie reprezentujący datę i godzinę działania.</span><span class="sxs-lookup"><span data-stu-id="bb627-203">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="bb627-204">Po pomyślnym mapowaniu danych można zobaczyć stan jako **Zakończone** oraz nazwę zamapowanych działań i atrybutów.</span><span class="sxs-lookup"><span data-stu-id="bb627-204">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Zrzut ekranu przedstawiający zakończoną konfigurację szablonu miary.":::

1. <span data-ttu-id="bb627-206">Teraz można wybrać opcję **Uruchom**, aby obliczyć wyniki miary.</span><span class="sxs-lookup"><span data-stu-id="bb627-206">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="bb627-207">Aby uściślić go później, wybierz opcję **Zapisz kopię roboczą**.</span><span class="sxs-lookup"><span data-stu-id="bb627-207">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="bb627-208">Zarządzanie miarami</span><span class="sxs-lookup"><span data-stu-id="bb627-208">Manage your measures</span></span>

<span data-ttu-id="bb627-209">Listę miar można znaleźć na stronie **Miary**.</span><span class="sxs-lookup"><span data-stu-id="bb627-209">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="bb627-210">Znajdziesz informacje o rodzaju miary, twórcy, dacie utworzenia, stanie i stanie.</span><span class="sxs-lookup"><span data-stu-id="bb627-210">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="bb627-211">Po wybraniu miary z listy można wyświetlić podgląd danych wyjściowych i pobrać plik CSV.</span><span class="sxs-lookup"><span data-stu-id="bb627-211">When you select a measure from the list, you can preview the output and download a CSV file.</span></span>

<span data-ttu-id="bb627-212">Aby odświeżyć wszystkie miary w tym samym czasie, wybierz **Odśwież wszystko** bez wybierania określonej miary.</span><span class="sxs-lookup"><span data-stu-id="bb627-212">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bb627-213">![Akcje służące do zarządzania pojedynczymi miarami.](media/measure-actions.png "Akcje służące do zarządzania pojedynczymi miarami.")</span><span class="sxs-lookup"><span data-stu-id="bb627-213">![Actions to manage single measures.](media/measure-actions.png "Actions to manage single measures.")</span></span>

<span data-ttu-id="bb627-214">Wybierz z listy miarę dla następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="bb627-214">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="bb627-215">Wybierz nazwę miary, aby wyświetlić jej szczegóły.</span><span class="sxs-lookup"><span data-stu-id="bb627-215">Select the measure name to see its details.</span></span>
- <span data-ttu-id="bb627-216">**Edytuj** konfigurację miary.</span><span class="sxs-lookup"><span data-stu-id="bb627-216">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="bb627-217">**Odśwież** miarę na podstawie najnowszych danych.</span><span class="sxs-lookup"><span data-stu-id="bb627-217">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="bb627-218">**Zmień nazwę** miary.</span><span class="sxs-lookup"><span data-stu-id="bb627-218">**Rename** the measure.</span></span>
- <span data-ttu-id="bb627-219">**Usuń** miarę.</span><span class="sxs-lookup"><span data-stu-id="bb627-219">**Delete** the measure.</span></span>
- <span data-ttu-id="bb627-220">**Aktywuj** lub **Dezaktywuj**.</span><span class="sxs-lookup"><span data-stu-id="bb627-220">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="bb627-221">Nieaktywne miary nie będą odświeżane podczas [zaplanowanego odświeżania](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bb627-221">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="bb627-222">Istnieje [sześć typów stanu](system.md#status-types) zadań/procesów.</span><span class="sxs-lookup"><span data-stu-id="bb627-222">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="bb627-223">Ponadto większość procesów [zależy od innych procesów podrzędnych](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="bb627-223">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="bb627-224">Istnieje możliwość wybrania stanu procesu w celu wyświetlenia szczegółowych informacji o postępie w całym zadaniu.</span><span class="sxs-lookup"><span data-stu-id="bb627-224">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="bb627-225">Po wybraniu opcji **Zobacz szczegóły** dla jednego z zadań, zobaczysz dodatkowe informacje: czas przetwarzania, data ostatniego przetwarzania i wszystkie błędy i ostrzeżenia związane z zadaniem.</span><span class="sxs-lookup"><span data-stu-id="bb627-225">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="bb627-226">Następny krok</span><span class="sxs-lookup"><span data-stu-id="bb627-226">Next step</span></span>

<span data-ttu-id="bb627-227">Istniejące miary można wykorzystać do utworzenia [segmentu klienta](segments.md).</span><span class="sxs-lookup"><span data-stu-id="bb627-227">You can use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
