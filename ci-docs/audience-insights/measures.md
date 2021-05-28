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
ms.openlocfilehash: 402e5ef3515bce0e6f56788781b7bd909738aaa6
ms.sourcegitcommit: b833e333745d321edeaf96d3ed14458cbce02ff1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049263"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="1cc6a-103">Definiowanie miar i zarządzanie nimi</span><span class="sxs-lookup"><span data-stu-id="1cc6a-103">Define and manage measures</span></span>

<span data-ttu-id="1cc6a-104">Miary pomagają lepiej poznać zachowania klientów i wydajność biznesową.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="1cc6a-105">Analizują one odpowiednie wartości z [ujednoliconych profilów](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="1cc6a-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="1cc6a-106">Na przykład firma chce wyświetlić *łączny przychód na klienta* w celu zrozumienia historii zakupów poszczególnych klientów lub pomiaru *łącznej sprzedaży firmy* w celu zrozumienia przychodu na poziomie zagregowanym dla całej firmy.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-106">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="1cc6a-107">Miary są tworzone za pomocą konstruktora miar, platformy zapytań o dane z różnymi operatorami i prostymi opcjami mapowania.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="1cc6a-108">Umożliwia filtrowanie danych, grupowanie wyników, wykrywanie [ścieżek relacji między encjami](relationships.md) i wyświetlanie podglądu danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="1cc6a-109">Użyj konstruktora miar, aby zaplanować działania biznesowe, wykonując zapytania dotyczące danych klientów i wyodrębniając szczegółowe informacje.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="1cc6a-110">Na przykład utworzenie miary *całkowitych wydatków na klienta* i *całkowitego zwrotu na klienta* pomaga zidentyfikować grupę klientów z wysokimi wydatkami, ale z wysokim zwrotem.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="1cc6a-111">Możesz utworzyć [segment](segments.md), aby stworzyć najlepsze akcje.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="1cc6a-112">Utwórz własną miarę od podstaw</span><span class="sxs-lookup"><span data-stu-id="1cc6a-112">Build your own measure from scratch</span></span>

<span data-ttu-id="1cc6a-113">W tej sekcji otworzymy nową miarę od podstaw.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="1cc6a-114">Możesz zbudować miarę z atrybutami danych z jednostek danych, które mają skonfigurowaną relację do łączenia się z encją Klient.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="1cc6a-115">W analizach odbiorców przejdź do **Miary**.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="1cc6a-116">Wybierz opcję **Nowa** i wybierz pozycję **Utwórz własną**.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="1cc6a-117">Wybierz opcję **Edytuj** nazwę i podaj **Nazwa** miary.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="1cc6a-118">Jeśli nowa konfiguracja miary ma tylko dwa pola, na przykład CustomerID i jedno wyliczenie, dane wyjściowe zostaną dodane jako nowa kolumna do wygenerowanej przez system encji o nazwie Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-118">If your new measure configuration has only two fields, for example, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="1cc6a-119">Będziesz mógł zobaczyć wartość miary w ujednoliconym profilu klienta.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="1cc6a-120">Inne miary będą generować własne encje.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="1cc6a-121">W obszarze konfiguracji wybierz funkcję agregowania z menu rozwijanego **Wybierz funkcję**.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="1cc6a-122">Funkcje agregowania obejmują:</span><span class="sxs-lookup"><span data-stu-id="1cc6a-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="1cc6a-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="1cc6a-123">**Sum**</span></span>
   - <span data-ttu-id="1cc6a-124">**Średnia**</span><span class="sxs-lookup"><span data-stu-id="1cc6a-124">**Average**</span></span>
   - <span data-ttu-id="1cc6a-125">**Licznik**</span><span class="sxs-lookup"><span data-stu-id="1cc6a-125">**Count**</span></span>
   - <span data-ttu-id="1cc6a-126">**Liczba unikatowych**</span><span class="sxs-lookup"><span data-stu-id="1cc6a-126">**Count Unique**</span></span>
   - <span data-ttu-id="1cc6a-127">**Maksimum**</span><span class="sxs-lookup"><span data-stu-id="1cc6a-127">**Max**</span></span>
   - <span data-ttu-id="1cc6a-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="1cc6a-128">**Min**</span></span>
   - <span data-ttu-id="1cc6a-129">**Pierwszy**: pobiera pierwszą wartość rekordu danych</span><span class="sxs-lookup"><span data-stu-id="1cc6a-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="1cc6a-130">**Ostatnia**: pobiera ostatnią wartość dodaną do rekordu danych</span><span class="sxs-lookup"><span data-stu-id="1cc6a-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operatory do oceny obliczeń.":::

1. <span data-ttu-id="1cc6a-132">Wybierz **Dodaj atrybut**, aby wybrać dane potrzebne do utworzenia tej miary.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="1cc6a-133">Wybrane kartę **Atrybuty**.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="1cc6a-134">Encja danych: wybierz encję zawierającą atrybut, który chcesz zmierzyć.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="1cc6a-135">Atrybut danych: wybierz atrybut, którego chcesz użyć w funkcji agregowania, aby obliczyć miarę.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="1cc6a-136">Możesz wybrać tylko jeden atrybut naraz.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="1cc6a-137">Atrybut danych można także wybrać z istniejącej miary, wybierając kartę **Miary**. Można także wyszukać nazwę encji lub miary.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="1cc6a-138">Wybierz opcję **Dodaj**, aby dodać do miary wybrany atrybut.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Wybierz atrybut, który ma być używany w obliczeniach.":::

1. <span data-ttu-id="1cc6a-140">Aby zbudować bardziej złożone miary, możesz dodać więcej atrybutów lub użyć operatorów matematycznych w funkcji miary.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Utwórz złożoną miarę za pomocą operatorów matematycznych.":::

1. <span data-ttu-id="1cc6a-142">Aby dodać filtry, wybierz **Filtr** w obszarze konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="1cc6a-143">W sekcji **Dodawanie atrybutu** w okienku **Filtry** wybierz atrybut, którego chcesz użyć do tworzenia filtrów.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="1cc6a-144">Ustaw operatory filtru, aby zdefiniować filtr dla każdego wybranego atrybutu.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="1cc6a-145">Wybierz opcję **Zastosuj**, aby dodać do miary wybrany filtr.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="1cc6a-146">Aby dodać wymiary, wybierz **Wymiar** w obszarze konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="1cc6a-147">Wymiary będą wyświetlane jako kolumny w encji wyjściowej miary.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="1cc6a-148">Wybierz opcję **Edytuj rozmiary**, aby dodać atrybuty danych, według których chcesz grupować wartości miary.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="1cc6a-149">Na przykład miasto lub płeć.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-149">For example, city or gender.</span></span> <span data-ttu-id="1cc6a-150">Domyślnie wymiar *CustomerID* jest wybrany do tworzenia *miar na poziomie klienta*.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="1cc6a-151">Do utworzenia *miar na poziomie firmy* można usunąć rozmiar domyślny.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="1cc6a-152">Wybierz opcję **Gotowe**, aby dodać do miary wybrany wymiar.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="1cc6a-153">Jeśli w danych są wartości, które trzeba zastąpić liczbą całkowitą, na przykład zastąp *null* wartością *0*, wybierz opcję **Reguły**.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-153">If there are values in your data that you need to replace with an integer, for example, replace *null* with *0*, select **Rules**.</span></span> <span data-ttu-id="1cc6a-154">Skonfiguruj regułę i upewnij się, że jako zamienniki wybierane są tylko liczby całkowite.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="1cc6a-155">Jeśli istnieje wiele ścieżek między mapowaną encją danych a encją *Klient*, musisz wybrać jedną ze zidentyfikowanych [ścieżek relacji między encjami](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="1cc6a-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="1cc6a-156">Wyniki mogą się różnić w zależności od wybranej ścieżki.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-156">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="1cc6a-157">Wybierz **preferencje dotyczące danych** i wybierz ścieżkę encji, która powinna być używana do identyfikacji miary.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="1cc6a-158">Jeśli do encji *Klient* jest dostępna tylko jedna ścieżka, ta kontrolka nie będzie wyświetlana.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="1cc6a-159">Wybierz opcję **Gotowe**, aby zastosować wybór.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Wybierz ścieżkę jednostki dla miary.":::

1. <span data-ttu-id="1cc6a-161">Aby dodać więcej obliczeń dla miary, wybierz opcję **Nowe obliczenia**.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="1cc6a-162">Do nowych obliczeń można używać tylko elementów znajdujących się na tej samej ścieżce encji.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="1cc6a-163">Więcej obliczeń zostanie wyświetlonych jako nowe kolumny w jednostce wyniku pomiaru.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="1cc6a-164">Wybierz opcję **...** w obliczeniach jako **Duplikat**, **Zmień nazwę** lub **Usuń** obliczenia z miary.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="1cc6a-165">W obszarze **Podgląd** jest wyświetlony schemat danych encji wyjściowej miary wraz z filtrami i rozmiarami.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="1cc6a-166">Podgląd jest dynamicznie reaktywny na zmiany w konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="1cc6a-167">Wybierz opcję **Uruchom**, aby obliczyć wyniki dla skonfigurowanej miary.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="1cc6a-168">Wybierz opcję **Zapisz i zamknij**, jeśli chcesz zachować bieżącą konfigurację i uruchomić miarę później.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="1cc6a-169">Wybierz **Miary**, aby zobaczyć nowo utworzoną miarę na liście.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="1cc6a-170">Tworzenie miary za pomocą szablonu</span><span class="sxs-lookup"><span data-stu-id="1cc6a-170">Use a template to build a measure</span></span>

<span data-ttu-id="1cc6a-171">Do ich utworzenia miar można użyć wstępnie zdefiniowanych szablonów najczęściej stosowanych miar.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="1cc6a-172">Szczegółowe opisy szablonów i działanie z przewodnikiem mogą ułatwić efektywne tworzenie miar.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="1cc6a-173">Szablony są budowane na podstawie zamapowanych danych z encji *Ujednolicone działanie*.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="1cc6a-174">Należy więc upewnić się, że skonfigurowano [działania klientów](activities.md) przed utworzeniem miary na podstawie szablonu.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="1cc6a-175">Dostępne szablony miar:</span><span class="sxs-lookup"><span data-stu-id="1cc6a-175">Available measure templates:</span></span> 
- <span data-ttu-id="1cc6a-176">Średnia wartość transakcji (ATV)</span><span class="sxs-lookup"><span data-stu-id="1cc6a-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="1cc6a-177">Łączna wartość transakcji</span><span class="sxs-lookup"><span data-stu-id="1cc6a-177">Total transaction value</span></span>
- <span data-ttu-id="1cc6a-178">Średni przychód dzienny</span><span class="sxs-lookup"><span data-stu-id="1cc6a-178">Average daily revenue</span></span>
- <span data-ttu-id="1cc6a-179">Średni przychód roczny</span><span class="sxs-lookup"><span data-stu-id="1cc6a-179">Average yearly revenue</span></span>
- <span data-ttu-id="1cc6a-180">Liczba transakcji</span><span class="sxs-lookup"><span data-stu-id="1cc6a-180">Transaction count</span></span>
- <span data-ttu-id="1cc6a-181">Zdobyte punkty lojalnościowe</span><span class="sxs-lookup"><span data-stu-id="1cc6a-181">Loyalty points earned</span></span>
- <span data-ttu-id="1cc6a-182">Zrealizowane punkty lojalnościowe</span><span class="sxs-lookup"><span data-stu-id="1cc6a-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="1cc6a-183">Saldo punktów lojalnościowych</span><span class="sxs-lookup"><span data-stu-id="1cc6a-183">Loyalty points balance</span></span>
- <span data-ttu-id="1cc6a-184">Okres istnienia aktywnego klienta</span><span class="sxs-lookup"><span data-stu-id="1cc6a-184">Active customer lifespan</span></span>
- <span data-ttu-id="1cc6a-185">Czas trwania uczestnictwa w programie lojalnościowym</span><span class="sxs-lookup"><span data-stu-id="1cc6a-185">Loyalty membership duration</span></span>
- <span data-ttu-id="1cc6a-186">Czas od ostatniego zakupu</span><span class="sxs-lookup"><span data-stu-id="1cc6a-186">Time since last purchase</span></span>

<span data-ttu-id="1cc6a-187">W poniższej procedurze przedstawiono w zarysie kroki tworzenia nowej miary za pomocą szablonu.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="1cc6a-188">W analizach odbiorców przejdź do **Miary**.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="1cc6a-189">Wybierz **Nowy** i wybierz **Wybierz szablon**.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Zrzut ekranu menu rozwijanego podczas tworzenia nowej miary z wyróżnieniem szablonu.":::

1. <span data-ttu-id="1cc6a-191">Znajdź szablon odpowiedni do potrzeb i wybierz opcję **Wybierz szablon**.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="1cc6a-192">Przejrzyj wymagane dane i wybierz pozycję **Rozpocznij**, jeśli masz już wszystkie dane.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="1cc6a-193">W okienku **Edycja nazwy** ustaw nazwę miary i encji wyjściowej.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="1cc6a-194">Wybierz pozycję **Gotowe**.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-194">Select **Done**.</span></span>

1. <span data-ttu-id="1cc6a-195">W sekcji **Ustawianie okresu czasu** zdefiniuj horyzont czasowy danych, które mają być użyte.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="1cc6a-196">Określ, czy nowa miara ma obejmować całą zawartość zestawu danych, wybierając opcję **Cały czas**.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-196">Choose if you want the new measure to cover the entire data set by selecting **All time**.</span></span> <span data-ttu-id="1cc6a-197">Można też skupić się na **Określonym okresie czasu**.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-197">Or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Zrzut ekranu przedstawiający sekcję okresu podczas konfigurowania miary z szablonu.":::

1. <span data-ttu-id="1cc6a-199">W następnej sekcji wybierz pozycję **Dodaj dane**, aby wybrać działania i zmapować odpowiednie dane z encji *Ujednolicone działanie*.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-199">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="1cc6a-200">Krok 1 z 2: w obszarze **Typ działania** wybierz typ encji, której chcesz użyć.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-200">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="1cc6a-201">W przypadku **Działań** wybierz encje, które chcesz zamapować.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-201">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="1cc6a-202">Krok 2 z 2: wybierz atrybut z encji *Ujednolicone działanie* dla składnika wymaganego przez formułę.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-202">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="1cc6a-203">Na przykład w przypadku Średniej wartości transakcji jest to atrybut reprezentujący wartość Transakcji.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-203">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="1cc6a-204">W przypadku **Znacznika czasu działania** wybierz atrybut z encji Ujednolicone działanie reprezentujący datę i godzinę działania.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-204">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="1cc6a-205">Po pomyślnym mapowaniu danych można zobaczyć stan jako **Zakończone** oraz nazwę zamapowanych działań i atrybutów.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-205">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Zrzut ekranu przedstawiający zakończoną konfigurację szablonu miary.":::

1. <span data-ttu-id="1cc6a-207">Teraz można wybrać opcję **Uruchom**, aby obliczyć wyniki miary.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-207">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="1cc6a-208">Aby uściślić go później, wybierz opcję **Zapisz kopię roboczą**.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-208">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="1cc6a-209">Zarządzanie miarami</span><span class="sxs-lookup"><span data-stu-id="1cc6a-209">Manage your measures</span></span>

<span data-ttu-id="1cc6a-210">Listę miar można znaleźć na stronie **Miary**.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-210">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="1cc6a-211">Znajdziesz informacje o rodzaju miary, twórcy, dacie utworzenia, stanie i stanie.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-211">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="1cc6a-212">Po wybraniu miary z listy można wyświetlić podgląd wyniku i pobrać plik .CSV.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-212">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="1cc6a-213">Aby odświeżyć wszystkie miary w tym samym czasie, wybierz **Odśwież wszystko** bez wybierania określonej miary.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-213">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1cc6a-214">![Akcje służące do zarządzania pojedynczymi miarami](media/measure-actions.png "Akcje służące do zarządzania pojedynczymi miarami")</span><span class="sxs-lookup"><span data-stu-id="1cc6a-214">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="1cc6a-215">Wybierz z listy miarę dla następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="1cc6a-215">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="1cc6a-216">Wybierz nazwę miary, aby wyświetlić jej szczegóły.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-216">Select the measure name to see its details.</span></span>
- <span data-ttu-id="1cc6a-217">**Edytuj** konfigurację miary.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-217">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="1cc6a-218">**Odśwież** miarę na podstawie najnowszych danych.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-218">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="1cc6a-219">**Zmień nazwę** miary.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-219">**Rename** the measure.</span></span>
- <span data-ttu-id="1cc6a-220">**Usuń** miarę.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-220">**Delete** the measure.</span></span>
- <span data-ttu-id="1cc6a-221">**Aktywuj** lub **Dezaktywuj**.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-221">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="1cc6a-222">Nieaktywne miary nie będą odświeżane podczas [zaplanowanego odświeżania](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1cc6a-222">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="1cc6a-223">Istnieje [sześć typów stanu](system.md#status-types) zadań/procesów.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-223">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="1cc6a-224">Ponadto większość procesów [zależy od innych procesów podrzędnych](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="1cc6a-224">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="1cc6a-225">Istnieje możliwość wybrania stanu procesu w celu wyświetlenia szczegółowych informacji o postępie w całym zadaniu.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-225">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="1cc6a-226">Po wybraniu opcji **Zobacz szczegółowe informacje** dla jednego z zadań zadania, można znaleźć więcej informacji: czas przetwarzania, Data ostatniego przetwarzania oraz wszystkie błędy i ostrzeżenia skojarzone z zadaniem.</span><span class="sxs-lookup"><span data-stu-id="1cc6a-226">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="1cc6a-227">Następny krok</span><span class="sxs-lookup"><span data-stu-id="1cc6a-227">Next step</span></span>

<span data-ttu-id="1cc6a-228">Zastosowanie istniejących miar umożliwia utworzenie [segmentu klienta](segments.md).</span><span class="sxs-lookup"><span data-stu-id="1cc6a-228">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
