---
title: Spożycie danych za pośrednictwem łącznika Power Query
description: Łączniki źródeł danych oparte na Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406572"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="a7a06-103">Nawiązywanie połączenia ze źródłem danych Power Query</span><span class="sxs-lookup"><span data-stu-id="a7a06-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="a7a06-104">Power Query oferuje szeroki zestaw łączników do pozyskiwania danych.</span><span class="sxs-lookup"><span data-stu-id="a7a06-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="a7a06-105">Większość z tych łączników jest obsługiwana przez Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a7a06-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="a7a06-106">Dodawanie źródeł danych na podstawie łączników Power Query zazwyczaj przebiega zgodnie z krokami opisanymi w następnej sekcji.</span><span class="sxs-lookup"><span data-stu-id="a7a06-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="a7a06-107">W zależności od używanego łącznika wymagane są jednak różne informacje.</span><span class="sxs-lookup"><span data-stu-id="a7a06-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="a7a06-108">Aby uzyskać więcej informacji, zobacz dokumentację dla poszczególnych łączników w [Informacje na temat łączników Power Query](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="a7a06-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="a7a06-109">Utwórz nowe źródło danych</span><span class="sxs-lookup"><span data-stu-id="a7a06-109">Create a new data source</span></span>

1. <span data-ttu-id="a7a06-110">W analizach odbiorców przejdź do **Dane** > **Źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="a7a06-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="a7a06-111">Wybierz **Dodaj źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="a7a06-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="a7a06-112">Wybierz metodę **importu danych** i wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="a7a06-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="a7a06-113">Wprowadź **Nazwę** źródła danych i wybierz **Dalej**, aby utworzyć źródło danych.</span><span class="sxs-lookup"><span data-stu-id="a7a06-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span>

1. <span data-ttu-id="a7a06-114">Wybierz jeden z [dostępnych łączników](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="a7a06-114">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="a7a06-115">W tym przykładzie wybraliśmy łącznik **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="a7a06-115">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="a7a06-116">Wprowadź wymagane informacje szczegółowe w **Ustawienia połączenia** dla wybranego łącznika i wybierz **Dalej**, aby wyświetlić podgląd danych.</span><span class="sxs-lookup"><span data-stu-id="a7a06-116">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="a7a06-117">Wybierz **Przekształć dane**.</span><span class="sxs-lookup"><span data-stu-id="a7a06-117">Select **Transform data**.</span></span> <span data-ttu-id="a7a06-118">W tym kroku encje zostaną dodane do źródła danych.</span><span class="sxs-lookup"><span data-stu-id="a7a06-118">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="a7a06-119">Encje są zestawami danych.</span><span class="sxs-lookup"><span data-stu-id="a7a06-119">Entities are datasets.</span></span> <span data-ttu-id="a7a06-120">Jeśli istnieje baza danych zawierająca wiele zestawów danych, każdy zestaw danych jest swoją własną encją.</span><span class="sxs-lookup"><span data-stu-id="a7a06-120">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="a7a06-121">Dialog **Power Query — edytuj zapytania** pozwala na przejrzenie i uściślenie danych.</span><span class="sxs-lookup"><span data-stu-id="a7a06-121">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="a7a06-122">Encje, które zostały określone przez systemy w wybranych źródłach danych, są wyświetlane w lewym okienku.</span><span class="sxs-lookup"><span data-stu-id="a7a06-122">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a7a06-123">![Okno dialogowe Edytuj zapytania](media/data-manager-configure-edit-queries.png "Okno dialogowe Edytuj zapytania")</span><span class="sxs-lookup"><span data-stu-id="a7a06-123">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="a7a06-124">Dane można również przekształcać.</span><span class="sxs-lookup"><span data-stu-id="a7a06-124">You can also transform your data.</span></span> <span data-ttu-id="a7a06-125">Wybierz encję do edycji lub przekształcenia.</span><span class="sxs-lookup"><span data-stu-id="a7a06-125">Select an entity to edit or transform.</span></span> <span data-ttu-id="a7a06-126">Korzystając z opcji dostępnych w oknie Power Query, można stosować przekształcenia.</span><span class="sxs-lookup"><span data-stu-id="a7a06-126">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="a7a06-127">Każde przekształcenie jest wyświetlane w obszarze **Zastosowane kroki**.</span><span class="sxs-lookup"><span data-stu-id="a7a06-127">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="a7a06-128">Power Query oferuje wiele wstępnie wbudowanych opcji transformacji.</span><span class="sxs-lookup"><span data-stu-id="a7a06-128">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="a7a06-129">Aby uzyskać więcej informacji, zobacz [Transformacje Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="a7a06-129">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="a7a06-130">Kolejne encje można dodać do źródła danych, wybierając polecenie **Pobierz dane** w oknie dialogowym **Edytuj zapytania**.</span><span class="sxs-lookup"><span data-stu-id="a7a06-130">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="a7a06-131">Te przekształcenia są zdecydowanie zalecane:</span><span class="sxs-lookup"><span data-stu-id="a7a06-131">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="a7a06-132">Jeśli pozyskujesz dane z pliku CSV, pierwszy wiersz często zawiera nagłówki.</span><span class="sxs-lookup"><span data-stu-id="a7a06-132">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="a7a06-133">Przejdź do **Przekształć tabelę** i wybierz **Użyj nagłówków jako pierwszego wiersza**.</span><span class="sxs-lookup"><span data-stu-id="a7a06-133">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="a7a06-134">Upewnij się, że typ danych jest odpowiednio ustawiony.</span><span class="sxs-lookup"><span data-stu-id="a7a06-134">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="a7a06-135">Wybierz **Zapisz** u dołu okna Power Query, aby zapisać przekształcenia.</span><span class="sxs-lookup"><span data-stu-id="a7a06-135">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="a7a06-136">Po zapisaniu źródło danych będzie znajdować się w **Dane** > **Źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="a7a06-136">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="a7a06-137">Na stronie **Źródła danych** zobaczysz, że nowe źródło danych jest w stanie **Odświeżanie**.</span><span class="sxs-lookup"><span data-stu-id="a7a06-137">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="a7a06-138">Dostępne źródła danych Power Query</span><span class="sxs-lookup"><span data-stu-id="a7a06-138">Available Power Query data sources</span></span>

<span data-ttu-id="a7a06-139">Sprawdź [Informacje na temat łączników Power Query](https://docs.microsoft.com/power-query/connectors/), aby otrzymać aktualną listę łączników, które można wybrać w celu zaimportowania danych do usługi Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a7a06-139">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="a7a06-140">Łączniki ze znacznikiem wyboru w kolumnie **Customer Insights (Przepływy danych)** są dostępne w celu utworzenia nowych źródeł danych na podstawie Power Query.</span><span class="sxs-lookup"><span data-stu-id="a7a06-140">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="a7a06-141">Przejrzyj dokumentację określonego łącznika, aby dowiedzieć się więcej o jego wymaganiach wstępnych, ograniczeniach i innych szczegółach.</span><span class="sxs-lookup"><span data-stu-id="a7a06-141">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="a7a06-142">Edytuj źródła danych Power Query</span><span class="sxs-lookup"><span data-stu-id="a7a06-142">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="a7a06-143">Wprowadzenie zmian w źródłach danych, które są obecnie używane w jednym z procesów aplikacji (na przykład *segmentacja*, *dopasowywanie* lub *scalanie*) może być niemożliwe.</span><span class="sxs-lookup"><span data-stu-id="a7a06-143">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="a7a06-144">Przy użyciu strony **Ustawienia** można śledzić postępy wszystkich aktywnych procesów.</span><span class="sxs-lookup"><span data-stu-id="a7a06-144">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="a7a06-145">Po zakończeniu procesu można powrócić do strony **Źródła danych** i wprowadzić zmiany.</span><span class="sxs-lookup"><span data-stu-id="a7a06-145">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="a7a06-146">W analizach odbiorców przejdź do **Dane** > **Źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="a7a06-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="a7a06-147">Zaznacz pionowy wielokropek obok źródła danych, które chcesz zmienić, i wybierz **Edytuj** z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="a7a06-147">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a7a06-148">![Opcja Edytuj](media/edit-option-data-sources.png "Opcja Edytuj")</span><span class="sxs-lookup"><span data-stu-id="a7a06-148">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="a7a06-149">Zastosuj zmiany i przekształcenia w oknie dialogowym **Power Query - edytuj zapytania**, jak to opisano w sekcji [Tworzenie nowego źródła danych](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="a7a06-149">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="a7a06-150">Wybierz **Zapisz** w Power Query po zakończeniu edycji, aby zapisać zmiany.</span><span class="sxs-lookup"><span data-stu-id="a7a06-150">Select **Save** in Power Query after completing your edits to save your changes.</span></span>
