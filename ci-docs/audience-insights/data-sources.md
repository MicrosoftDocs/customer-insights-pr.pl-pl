---
title: Użyj źródeł danych do pozyskiwania danych
description: Informacje na temat importowania danych z różnych źródeł.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54dd7b629d4b4e7f640b932b0f9246e0602f46bd
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304709"
---
# <a name="data-sources-overview"></a><span data-ttu-id="b322e-103">Omówienie źródeł danych</span><span class="sxs-lookup"><span data-stu-id="b322e-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="b322e-104">Funkcja wglądu w odbiorców w Dynamics 365 Customer Insights łączy się z danymi z szerokiego zestawu źródeł.</span><span class="sxs-lookup"><span data-stu-id="b322e-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="b322e-105">Łączenie się ze źródłem danych jest często określane jako proces *pozyskiwania danych*.</span><span class="sxs-lookup"><span data-stu-id="b322e-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="b322e-106">Po pozyskaniu danych można je [ujednolicić](data-unification.md) i podejmować na nich akcje.</span><span class="sxs-lookup"><span data-stu-id="b322e-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="b322e-107">Dodaj źródło danych</span><span class="sxs-lookup"><span data-stu-id="b322e-107">Add a data source</span></span>

<span data-ttu-id="b322e-108">Zapoznaj się ze szczegółowymi artykułami dotyczącymi sposobu dodawania źródła danych w zależności od wybranej opcji.</span><span class="sxs-lookup"><span data-stu-id="b322e-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="b322e-109">Źródło danych można dodać na trzy podstawowe sposoby:</span><span class="sxs-lookup"><span data-stu-id="b322e-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="b322e-110">Za pomocą licznych łączników Power Query</span><span class="sxs-lookup"><span data-stu-id="b322e-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="b322e-111">Z folderu Common Data Model</span><span class="sxs-lookup"><span data-stu-id="b322e-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="b322e-112">Z własnego repozytorium tylu lake Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="b322e-112">From your own Microsoft Dataverse lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="b322e-113">Dodawanie danych z lokalnych źródeł danych</span><span class="sxs-lookup"><span data-stu-id="b322e-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="b322e-114">Przetwarzanie danych z lokalnych źródeł danych w programie Wynikach analiz odbiorców jest obsługiwane na podstawie przepływów danych Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="b322e-114">Ingesting data from on-premises data sources in audience insights is supported based on Microsoft Power Platform dataflows.</span></span> <span data-ttu-id="b322e-115">Przepływy danych można włączyć w funkcji Customer Insights, [podając adres URL środowiska Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) podczas konfigurowania środowiska.</span><span class="sxs-lookup"><span data-stu-id="b322e-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="b322e-116">Źródła danych tworzone po skojarzeniu środowiska Dataverse z usługą Customer Insights domyślnie będą korzystać z [przepływów danych Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365).</span><span class="sxs-lookup"><span data-stu-id="b322e-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="b322e-117">Przepływy danych obsługują lokalną łączność przy użyciu bramy danych.</span><span class="sxs-lookup"><span data-stu-id="b322e-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="b322e-118">Należy usunąć i ponownie utworzyć źródła danych, które istniały, zanim środowisko Dataverse zostało skojarzone do użycia [lokalnych bram danych](/data-integration/gateway/service-gateway-app.md).</span><span class="sxs-lookup"><span data-stu-id="b322e-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/data-integration/gateway/service-gateway-app.md).</span></span>

<span data-ttu-id="b322e-119">Brama danych z istniejącego lub środowiska Power BI lub Power Apps będzie widoczna i można jej użyć ponownie w usłudze Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b322e-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="b322e-120">Na stronie źródeł danych znajdują się łącza umożliwiające przejście do środowiska Microsoft Power Platform, w którym można wyświetlić i skonfigurować lokalne bramy danych.</span><span class="sxs-lookup"><span data-stu-id="b322e-120">The data sources page shows links to go to the Microsoft Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="b322e-121">Przeglądanie pobranych danych</span><span class="sxs-lookup"><span data-stu-id="b322e-121">Review ingested data</span></span>

<span data-ttu-id="b322e-122">Zostanie wyświetlona nazwa każdego pozyskanego źródła danych, jego stan i data ostatniego odświeżenia danych dla tego źródła.</span><span class="sxs-lookup"><span data-stu-id="b322e-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="b322e-123">Listę źródeł danych można posortować według każdej kolumny.</span><span class="sxs-lookup"><span data-stu-id="b322e-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b322e-124">![Dodano źródło danych](media/configure-data-datasource-added.png "Dodano źródło danych")</span><span class="sxs-lookup"><span data-stu-id="b322e-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="b322e-125">Status</span><span class="sxs-lookup"><span data-stu-id="b322e-125">Status</span></span>  |<span data-ttu-id="b322e-126">Opis</span><span class="sxs-lookup"><span data-stu-id="b322e-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="b322e-127">Pomyślnie</span><span class="sxs-lookup"><span data-stu-id="b322e-127">Successful</span></span>   |<span data-ttu-id="b322e-128">Źródło danych zostało pomyślnie przetworzone, jeśli w kolumnie **Odświeżono** podano godzinę.</span><span class="sxs-lookup"><span data-stu-id="b322e-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="b322e-129">Nie rozpoczęto</span><span class="sxs-lookup"><span data-stu-id="b322e-129">Not started</span></span>   |<span data-ttu-id="b322e-130">Źródło danych nie ma jeszcze pozyskanych danych lub nadal jest w trybie roboczym.</span><span class="sxs-lookup"><span data-stu-id="b322e-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="b322e-131">Odświeżanie</span><span class="sxs-lookup"><span data-stu-id="b322e-131">Refreshing</span></span>    |<span data-ttu-id="b322e-132">Pobieranie danych jest w toku.</span><span class="sxs-lookup"><span data-stu-id="b322e-132">Data ingestion is in progress.</span></span> <span data-ttu-id="b322e-133">Aby anulować operację, można wybrać opcję **Zatrzymaj odświeżanie** w kolumnie **Czynności**.</span><span class="sxs-lookup"><span data-stu-id="b322e-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="b322e-134">Zatrzymanie odświeżania źródła danych spowoduje przywrócenie jego ostatniego stanu odświeżania.</span><span class="sxs-lookup"><span data-stu-id="b322e-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="b322e-135">Zakończone niepowodzeniem</span><span class="sxs-lookup"><span data-stu-id="b322e-135">Failed</span></span>     |<span data-ttu-id="b322e-136">Pobieranie danych zostało napotkało błędy.</span><span class="sxs-lookup"><span data-stu-id="b322e-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="b322e-137">Wybierz wartość w kolumnie **Stan** dowolnego pola źródło danych, aby przejrzeć więcej szczegółów.</span><span class="sxs-lookup"><span data-stu-id="b322e-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="b322e-138">W okienku **Szczegółów postępu** rozwiń pozycję **Źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="b322e-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="b322e-139">Wybierz opcję **Zobacz szczegółowe informacje**, aby uzyskać więcej informacji na temat stanu odświeżania, w tym szczegóły błędów i aktualizacje procesów podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="b322e-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="b322e-140">Ładowanie danych może zająć czas.</span><span class="sxs-lookup"><span data-stu-id="b322e-140">Loading data can take time.</span></span> <span data-ttu-id="b322e-141">Po pomyślnym odświeżeniu dane z pobierania można przejrzeć na stronie **Encji**.</span><span class="sxs-lookup"><span data-stu-id="b322e-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="b322e-142">Aby uzyskać więcej informacji, zobacz [Encje](entities.md).</span><span class="sxs-lookup"><span data-stu-id="b322e-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="b322e-143">Odśwież źródło danych</span><span class="sxs-lookup"><span data-stu-id="b322e-143">Refresh a data source</span></span>

<span data-ttu-id="b322e-144">Źródła danych mogą być odświeżane w harmonogramie automatycznym lub ręcznie odświeżane na żądanie.</span><span class="sxs-lookup"><span data-stu-id="b322e-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="b322e-145">Przejdź do **Administrator** > **System** > [**Harmonogram**](system.md#schedule-tab), aby skonfigurować zaplanowane odświeżanie wszystkich spożywanych źródeł danych.</span><span class="sxs-lookup"><span data-stu-id="b322e-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="b322e-146">Aby odświeżyć źródło danych na żądanie, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="b322e-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="b322e-147">W analizach odbiorców przejdź do **Dane** > **Źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="b322e-147">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="b322e-148">Wybierz wielokropek pionowy obok źródła danych, które chcesz odświeżyć, i z menu rozwijanego wybierz pozycję **Odśwież**.</span><span class="sxs-lookup"><span data-stu-id="b322e-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the dropdown list.</span></span>

3. <span data-ttu-id="b322e-149">Źródło danych jest teraz wyzwalane w celu ręcznego odświeżenia.</span><span class="sxs-lookup"><span data-stu-id="b322e-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="b322e-150">Odświeżenie źródła danych spowoduje zaktualizowanie schematu encji i danych dla wszystkich encji określonych w źródle danych.</span><span class="sxs-lookup"><span data-stu-id="b322e-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="b322e-151">Wybierz **Zatrzymaj odświeżanie**, aby anulować istniejące odświeżanie, a źródło danych przywróci do ostatniego stanu odświeżania.</span><span class="sxs-lookup"><span data-stu-id="b322e-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="b322e-152">Usuń źródło danych</span><span class="sxs-lookup"><span data-stu-id="b322e-152">Delete a data source</span></span>

1. <span data-ttu-id="b322e-153">W analizach odbiorców przejdź do **Dane** > **Źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="b322e-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="b322e-154">Wybierz wielokropek pionowy obok źródła danych, które chcesz usunąć, i z menu rozwijanego wybierz pozycję **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="b322e-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the dropdown menu.</span></span>

3. <span data-ttu-id="b322e-155">Potwierdź usunięcie.</span><span class="sxs-lookup"><span data-stu-id="b322e-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
