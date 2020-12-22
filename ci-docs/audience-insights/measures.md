---
title: Tworzenie i edytowanie miar
description: Zdefiniowanie miar związanych z klientami w celu przeanalizowania i odzwierciedlenia wydajności pewnych obszarów biznesowych.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406591"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="1969a-103">Definiowanie miar i zarządzanie nimi</span><span class="sxs-lookup"><span data-stu-id="1969a-103">Define and manage measures</span></span>

<span data-ttu-id="1969a-104">**Miary** reprezentują kluczowe wskaźniki wydajności (KPI), które odzwierciedlają wydajność i kondycję poszczególnych obszarów biznesowych.</span><span class="sxs-lookup"><span data-stu-id="1969a-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="1969a-105">Analiza odbiorców zapewnia intuicyjne środowisko tworzenia różnych typów miar za pomocą konstruktora zapytań, który nie wymaga ręcznego kodowania ani sprawdzania poprawności miar.</span><span class="sxs-lookup"><span data-stu-id="1969a-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="1969a-106">Miary biznesowe można śledzić na **stronie głównej**, zobaczyć miary dotyczące określonych klientów w **Karcie klienta**, a następnie użyć miar w celu zdefiniowania segmentów klientów na stronie **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="1969a-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="1969a-107">Utwórz miarę</span><span class="sxs-lookup"><span data-stu-id="1969a-107">Create a measure</span></span>

<span data-ttu-id="1969a-108">Niniejsza sekcja zawiera instrukcje dotyczące tworzenia miary od podstaw.</span><span class="sxs-lookup"><span data-stu-id="1969a-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="1969a-109">Miarą można zbudować na podstawie danych z wielu źródeł danych połączonych za pośrednictwem encji klienta.</span><span class="sxs-lookup"><span data-stu-id="1969a-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="1969a-110">Niektóre [ograniczenia dotyczące usług](service-limits.md) mają zastosowanie.</span><span class="sxs-lookup"><span data-stu-id="1969a-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="1969a-111">W analizach odbiorców przejdź do **Miary**.</span><span class="sxs-lookup"><span data-stu-id="1969a-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="1969a-112">Wybierz opcję **Nowa miara**.</span><span class="sxs-lookup"><span data-stu-id="1969a-112">Select **New measure**.</span></span>

3. <span data-ttu-id="1969a-113">Wybierz **typ** miary:</span><span class="sxs-lookup"><span data-stu-id="1969a-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="1969a-114">**Atrybut klienta**: jedno pole na klienta, które odzwierciedla wyniki, wartość lub stan dla klienta.</span><span class="sxs-lookup"><span data-stu-id="1969a-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="1969a-115">Atrybuty klienta są tworzone jako atrybuty w nowym obiekcie wygenerowanym przez system o nazwie **Customer_Measure**.</span><span class="sxs-lookup"><span data-stu-id="1969a-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="1969a-116">**Miara klienta**: wgląd w informacje dotyczące zachowania klienta z podziałem według wybranych wymiarów.</span><span class="sxs-lookup"><span data-stu-id="1969a-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="1969a-117">Dla każdej miary zostanie wygenerowana nowa encja, prawdopodobnie z wieloma rekordami na klienta.</span><span class="sxs-lookup"><span data-stu-id="1969a-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="1969a-118">**Miary biznesowe**: pozwala śledzić wyniki działalności i kondycję prowadzonej działalności.</span><span class="sxs-lookup"><span data-stu-id="1969a-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="1969a-119">Miary biznesowe mogą mieć dwie różne wyjścia: liczbowe wyniki, które są wyświetlane na **stronie głównej** lub w nowej encji, która znajduje się na stronie **Encje** .</span><span class="sxs-lookup"><span data-stu-id="1969a-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="1969a-120">Wpisz **nazwę** i opcjonalnie **wyświetlaną nazwę**, a następnie wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="1969a-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="1969a-121">W sekcji **Encje** wybierz pierwszą encję z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="1969a-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="1969a-122">W tym momencie należy określić, czy w ramach definicji miary są potrzebne dodatkowe encje.</span><span class="sxs-lookup"><span data-stu-id="1969a-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1969a-123">![Definicja miary](media/measure-definition.png "Definicja miary")</span><span class="sxs-lookup"><span data-stu-id="1969a-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="1969a-124">Aby dodać więcej encji, wybierz pozycję **Dodaj encję** i wybierz encje, które mają być używane dla miary.</span><span class="sxs-lookup"><span data-stu-id="1969a-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1969a-125">Możesz wybrać tylko encje, które mają powiązania z encją początkową.</span><span class="sxs-lookup"><span data-stu-id="1969a-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="1969a-126">Aby uzyskać więcej informacji dotyczących definiowania relacji, zobacz [Relacje](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="1969a-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="1969a-127">Opcjonalnie można skonfigurować zmienne.</span><span class="sxs-lookup"><span data-stu-id="1969a-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="1969a-128">W sekcji **Zmienne** wybierz pozycję **Nowa zmienna**.</span><span class="sxs-lookup"><span data-stu-id="1969a-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="1969a-129">Zmienne są obliczeniami dokonywanymi w poszczególnych zaznaczonych rekordach.</span><span class="sxs-lookup"><span data-stu-id="1969a-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="1969a-130">Na przykład: sumowanie punktów sprzedaży (POS) i sprzedaży online w przypadku poszczególnych rekordów klientów.</span><span class="sxs-lookup"><span data-stu-id="1969a-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="1969a-131">W polu **Nazwa** podaj nazwę zmiennej.</span><span class="sxs-lookup"><span data-stu-id="1969a-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="1969a-132">W obszarze **Wyrażenia** wybierz pole, od którego chcesz rozpocząć obliczenia.</span><span class="sxs-lookup"><span data-stu-id="1969a-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="1969a-133">Umożliwia wpisanie wyrażenia w obszarze **Wyrażenia** podczas wybierania większej liczby pól, które mają zostać uwzględnione w obliczeniu.</span><span class="sxs-lookup"><span data-stu-id="1969a-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1969a-134">Obecnie obsługiwane są tylko wyrażenia arytmetyczne.</span><span class="sxs-lookup"><span data-stu-id="1969a-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="1969a-135">Ponadto, obliczanie zmiennych nie jest obsługiwane w przypadku encjipochodzących z różnych [ścieżek encji](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="1969a-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="1969a-136">Wybierz **Gotowe**.</span><span class="sxs-lookup"><span data-stu-id="1969a-136">Select **Done**.</span></span>

11. <span data-ttu-id="1969a-137">W sekcji **Definicja miary** zdefiniujesz, jak wybrane encje i obliczane zmienne są agregowane w nowych encjach lub atrybutach miary.</span><span class="sxs-lookup"><span data-stu-id="1969a-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="1969a-138">Wybierz **Nowy wymiar**.</span><span class="sxs-lookup"><span data-stu-id="1969a-138">Select **New dimension**.</span></span> <span data-ttu-id="1969a-139">Wymiar może być postrzegany jako funkcja *Grupuj według*.</span><span class="sxs-lookup"><span data-stu-id="1969a-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="1969a-140">Dane wyjściowe encji lub atrybutu miary zostaną pogrupowane według wszystkich zdefiniowanych wymiarów.</span><span class="sxs-lookup"><span data-stu-id="1969a-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1969a-141">![Wybieranie cyklu agregacji](media/measures-businessreport-measure-definition2.png "Wybieranie cyklu agregacji")</span><span class="sxs-lookup"><span data-stu-id="1969a-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="1969a-142">Wybierz lub wprowadź następujące informacje jako część definicji danego wymiaru:</span><span class="sxs-lookup"><span data-stu-id="1969a-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="1969a-143">**Encja**: po zdefiniowaniu miary encji powinna ona zawierać co najmniej jeden atrybut.</span><span class="sxs-lookup"><span data-stu-id="1969a-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="1969a-144">W przypadku zdefiniowania atrybutu miary będzie w nim domyślnie uwzględniony tylko jeden atrybut.</span><span class="sxs-lookup"><span data-stu-id="1969a-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="1969a-145">Ta opcja służy do wybierania encji zawierającej dany atrybut.</span><span class="sxs-lookup"><span data-stu-id="1969a-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="1969a-146">**Pole**: wybierz konkretny atrybut, który ma zostać uwzględniony w encji lub atrybucie miary.</span><span class="sxs-lookup"><span data-stu-id="1969a-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="1969a-147">**Zasobnik**: należy wybrać, czy dane mają być agregowane codzienne, comiesięczne czy roczne.</span><span class="sxs-lookup"><span data-stu-id="1969a-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="1969a-148">Jest to wymagane tylko w przypadku wybrania atrybutu typu Data.</span><span class="sxs-lookup"><span data-stu-id="1969a-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="1969a-149">**Jako**: definiuje nazwę nowego pola.</span><span class="sxs-lookup"><span data-stu-id="1969a-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="1969a-150">**Wyświetlana nazwa**: definiuje wyświetlaną nazwę pola.</span><span class="sxs-lookup"><span data-stu-id="1969a-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1969a-151">Miara biznesowa zostanie zapisana jako encja z jednym numerem i będzie widoczna na **stronie głównej**, chyba że dodasz więcej wymiarów do miary.</span><span class="sxs-lookup"><span data-stu-id="1969a-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="1969a-152">Po dodaniu dodatkowych wymiarów miara *nie* zostanie wyświetlona na **stronie głównej**.</span><span class="sxs-lookup"><span data-stu-id="1969a-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="1969a-153">Opcjonalnie dodaj funkcje agregowania.</span><span class="sxs-lookup"><span data-stu-id="1969a-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="1969a-154">Każda utworzona wartość zagregowana powoduje utworzenie nowej wartości w encji lub atrybucie miary.</span><span class="sxs-lookup"><span data-stu-id="1969a-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="1969a-155">Obsługiwane są następujące funkcje agregujące: **Min.**, **Max.**, **Średnia**, **Mediana**, **Suma**, **Liczba unikatowych**, **Pierwsze** (pobiera pierwszy rekord wartości wymiaru) i **ostatnia** (pobiera ostatni rekord dodany do wartości wymiaru).</span><span class="sxs-lookup"><span data-stu-id="1969a-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="1969a-156">Wybierz pozycję **Zapisz**, aby zapisać zmiany wprowadzone w miarze.</span><span class="sxs-lookup"><span data-stu-id="1969a-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="1969a-157">Zarządzanie miarami</span><span class="sxs-lookup"><span data-stu-id="1969a-157">Manage your measures</span></span>

<span data-ttu-id="1969a-158">Po utworzeniu co najmniej jednej miary zostanie wyświetlona lista miar na stronie **Miary**.</span><span class="sxs-lookup"><span data-stu-id="1969a-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="1969a-159">Znajdują się na niej informacje o typie miary, autorze, dacie i godzinie utworzenia, daty i godziny ostatniej edycji, stanie (bez względu na to, czy miara jest aktywna, nieaktywna lub błędna) oraz data i godzina ostatniego odświeżenia.</span><span class="sxs-lookup"><span data-stu-id="1969a-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="1969a-160">Po wybraniu miary z listy można wyświetlić podgląd jej wyników.</span><span class="sxs-lookup"><span data-stu-id="1969a-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="1969a-161">Aby odświeżyć wszystkie miary w tym samym czasie, wybierz **Odśwież wszystko** bez wybierania określonej miary.</span><span class="sxs-lookup"><span data-stu-id="1969a-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1969a-162">![Akcje służące do zarządzania pojedynczymi miarami](media/measure-actions.png "Akcje służące do zarządzania pojedynczymi miarami")</span><span class="sxs-lookup"><span data-stu-id="1969a-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="1969a-163">Można też wybrać miarę z listy, a następnie wykonać jedną z następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="1969a-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="1969a-164">Wybierz nazwę miary, aby wyświetlić jej szczegóły.</span><span class="sxs-lookup"><span data-stu-id="1969a-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="1969a-165">**Edytuj** konfigurację miary.</span><span class="sxs-lookup"><span data-stu-id="1969a-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="1969a-166">**Zmień nazwę** miary.</span><span class="sxs-lookup"><span data-stu-id="1969a-166">**Rename** the measure.</span></span>
- <span data-ttu-id="1969a-167">**Usuń** miarę.</span><span class="sxs-lookup"><span data-stu-id="1969a-167">**Delete** the measure.</span></span>
- <span data-ttu-id="1969a-168">Wybierz wielokropek (...), a następnie **Odśwież**, aby rozpocząć proces odświeżania miary.</span><span class="sxs-lookup"><span data-stu-id="1969a-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="1969a-169">Wybierz wielokropek (...), a następnie **Pobierz**, aby uzyskać plik .CSV miary.</span><span class="sxs-lookup"><span data-stu-id="1969a-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="1969a-170">Istnieje [sześć typów stanu](system.md#status-types) zadań/procesów.</span><span class="sxs-lookup"><span data-stu-id="1969a-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="1969a-171">Ponadto większość procesów [zależy od innych procesów podrzędnych](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="1969a-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="1969a-172">Istnieje możliwość wybrania stanu procesu w celu wyświetlenia szczegółowych informacji o postępie w całym zadaniu.</span><span class="sxs-lookup"><span data-stu-id="1969a-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="1969a-173">Po wybraniu opcji **Zobacz szczegółowe informacje** dla jednego z zadań zadania, można znaleźć więcej informacji: czas przetwarzania, Data ostatniego przetwarzania oraz wszystkie błędy i ostrzeżenia skojarzone z zadaniem.</span><span class="sxs-lookup"><span data-stu-id="1969a-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="1969a-174">Następny krok</span><span class="sxs-lookup"><span data-stu-id="1969a-174">Next step</span></span>

<span data-ttu-id="1969a-175">W tym celu należy skorzystać z istniejących miar w celu utworzenia pierwszego segmentu klienta na stronie **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="1969a-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="1969a-176">Aby uzyskać więcej informacji, zobacz [Segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="1969a-176">For more information, see [Segments](segments.md).</span></span>
