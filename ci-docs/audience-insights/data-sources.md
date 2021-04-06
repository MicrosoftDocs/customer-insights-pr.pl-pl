---
title: Użyj źródeł danych do pozyskiwania danych
description: Informacje na temat importowania danych z różnych źródeł.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 780dc61a82d6ed9856a37dc8f164fa946d982bbe
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595960"
---
# <a name="data-sources-overview"></a><span data-ttu-id="17636-103">Omówienie źródeł danych</span><span class="sxs-lookup"><span data-stu-id="17636-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="17636-104">Funkcja wglądu w odbiorców w Dynamics 365 Customer Insights łączy się z danymi z szerokiego zestawu źródeł.</span><span class="sxs-lookup"><span data-stu-id="17636-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="17636-105">Łączenie się ze źródłem danych jest często określane jako proces *pozyskiwania danych*.</span><span class="sxs-lookup"><span data-stu-id="17636-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="17636-106">Po pozyskaniu danych można je [ujednolicić](data-unification.md) i podejmować na nich akcje.</span><span class="sxs-lookup"><span data-stu-id="17636-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="17636-107">Dodaj źródło danych</span><span class="sxs-lookup"><span data-stu-id="17636-107">Add a data source</span></span>

<span data-ttu-id="17636-108">Zapoznaj się ze szczegółowymi artykułami dotyczącymi sposobu dodawania źródła danych w zależności od wybranej opcji.</span><span class="sxs-lookup"><span data-stu-id="17636-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="17636-109">Źródło danych można dodać na trzy podstawowe sposoby:</span><span class="sxs-lookup"><span data-stu-id="17636-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="17636-110">Za pomocą licznych łączników Power Query</span><span class="sxs-lookup"><span data-stu-id="17636-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="17636-111">Z folderu Common Data Model</span><span class="sxs-lookup"><span data-stu-id="17636-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="17636-112">Z własnego repozytorium tylu lake Common Data Service</span><span class="sxs-lookup"><span data-stu-id="17636-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="17636-113">Nie można jeszcze dodawać danych z lokalny źródeł danych.</span><span class="sxs-lookup"><span data-stu-id="17636-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="17636-114">Przeglądanie pobranych danych</span><span class="sxs-lookup"><span data-stu-id="17636-114">Review ingested data</span></span>

<span data-ttu-id="17636-115">Zostanie wyświetlona nazwa każdego pozyskanego źródła danych, jego stan i data ostatniego odświeżenia danych dla tego źródła.</span><span class="sxs-lookup"><span data-stu-id="17636-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="17636-116">Listę źródeł danych można posortować według każdej kolumny.</span><span class="sxs-lookup"><span data-stu-id="17636-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="17636-117">![Dodano źródło danych](media/configure-data-datasource-added.png "Dodano źródło danych")</span><span class="sxs-lookup"><span data-stu-id="17636-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="17636-118">Status</span><span class="sxs-lookup"><span data-stu-id="17636-118">Status</span></span>  |<span data-ttu-id="17636-119">Opis</span><span class="sxs-lookup"><span data-stu-id="17636-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="17636-120">Pomyślnie</span><span class="sxs-lookup"><span data-stu-id="17636-120">Successful</span></span>   |<span data-ttu-id="17636-121">Źródło danych zostało pomyślnie przetworzone, jeśli w kolumnie **Odświeżono** podano godzinę.</span><span class="sxs-lookup"><span data-stu-id="17636-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="17636-122">Nie rozpoczęto</span><span class="sxs-lookup"><span data-stu-id="17636-122">Not started</span></span>   |<span data-ttu-id="17636-123">Źródło danych nie ma jeszcze pozyskanych danych lub nadal jest w trybie roboczym.</span><span class="sxs-lookup"><span data-stu-id="17636-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="17636-124">Odświeżanie</span><span class="sxs-lookup"><span data-stu-id="17636-124">Refreshing</span></span>    |<span data-ttu-id="17636-125">Pobieranie danych jest w toku.</span><span class="sxs-lookup"><span data-stu-id="17636-125">Data ingestion is in progress.</span></span> <span data-ttu-id="17636-126">Aby anulować operację, można wybrać opcję **Zatrzymaj odświeżanie** w kolumnie **Czynności**.</span><span class="sxs-lookup"><span data-stu-id="17636-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="17636-127">Zatrzymanie odświeżania źródła danych spowoduje przywrócenie jego ostatniego stanu odświeżania.</span><span class="sxs-lookup"><span data-stu-id="17636-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="17636-128">Zakończone niepowodzeniem</span><span class="sxs-lookup"><span data-stu-id="17636-128">Failed</span></span>     |<span data-ttu-id="17636-129">Pobieranie danych zostało napotkało błędy.</span><span class="sxs-lookup"><span data-stu-id="17636-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="17636-130">Wybierz wartość w kolumnie **Stan** dowolnego pola źródło danych, aby przejrzeć więcej szczegółów.</span><span class="sxs-lookup"><span data-stu-id="17636-130">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="17636-131">W okienku **Szczegółów postępu** rozwiń pozycję **Źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="17636-131">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="17636-132">Wybierz opcję **Zobacz szczegółowe informacje**, aby uzyskać więcej informacji na temat stanu odświeżania, w tym szczegóły błędów i aktualizacje procesów podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="17636-132">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="17636-133">Ładowanie danych może potrwać trochę czasu.</span><span class="sxs-lookup"><span data-stu-id="17636-133">Loading data can take some time.</span></span> <span data-ttu-id="17636-134">Po pomyślnym odświeżeniu dane z pobierania można przejrzeć na stronie **Encji**.</span><span class="sxs-lookup"><span data-stu-id="17636-134">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="17636-135">Aby uzyskać więcej informacji, zobacz [Encje](entities.md).</span><span class="sxs-lookup"><span data-stu-id="17636-135">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="17636-136">Odśwież źródło danych</span><span class="sxs-lookup"><span data-stu-id="17636-136">Refresh a data source</span></span>

<span data-ttu-id="17636-137">Źródła danych mogą być odświeżane w harmonogramie automatycznym lub ręcznie odświeżane na żądanie.</span><span class="sxs-lookup"><span data-stu-id="17636-137">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="17636-138">Przejdź do **Administrator** > **System** > [**Harmonogram**](system.md#schedule-tab), aby skonfigurować zaplanowane odświeżanie wszystkich spożywanych źródeł danych.</span><span class="sxs-lookup"><span data-stu-id="17636-138">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="17636-139">Aby odświeżyć źródło danych na żądanie, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="17636-139">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="17636-140">W analizach odbiorców przejdź do **Dane** > **Źródła danych**</span><span class="sxs-lookup"><span data-stu-id="17636-140">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="17636-141">Zaznacz pionowy wielokropek obok źródło danych, który chcesz odświeżyć, i wybierz opcję **Odśwież** z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="17636-141">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="17636-142">Źródło danych jest teraz wyzwalane w celu ręcznego odświeżenia.</span><span class="sxs-lookup"><span data-stu-id="17636-142">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="17636-143">Odświeżenie źródła danych spowoduje zaktualizowanie zarówno schematu jednostki, jak i danych dla wszystkich jednostek określonych w źródle danych.</span><span class="sxs-lookup"><span data-stu-id="17636-143">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="17636-144">Wybierz **Zatrzymaj odświeżanie**, aby anulować istniejące odświeżanie, a źródło danych przywróci do ostatniego stanu odświeżania.</span><span class="sxs-lookup"><span data-stu-id="17636-144">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="17636-145">Usuń źródło danych</span><span class="sxs-lookup"><span data-stu-id="17636-145">Delete a data source</span></span>

1. <span data-ttu-id="17636-146">W analizach odbiorców przejdź do **Dane** > **Źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="17636-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="17636-147">Zaznacz pionowy wielokropek obok źródła danych, które chcesz usunąć, i wybierz **Usuń** z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="17636-147">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="17636-148">Potwierdź usunięcie.</span><span class="sxs-lookup"><span data-stu-id="17636-148">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]