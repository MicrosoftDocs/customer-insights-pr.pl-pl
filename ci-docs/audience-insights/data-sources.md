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
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887907"
---
# <a name="data-sources-overview"></a><span data-ttu-id="309bd-103">Omówienie źródeł danych</span><span class="sxs-lookup"><span data-stu-id="309bd-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="309bd-104">Funkcja wglądu w odbiorców w Dynamics 365 Customer Insights łączy się z danymi z szerokiego zestawu źródeł.</span><span class="sxs-lookup"><span data-stu-id="309bd-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="309bd-105">Łączenie się ze źródłem danych jest często określane jako proces *pozyskiwania danych*.</span><span class="sxs-lookup"><span data-stu-id="309bd-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="309bd-106">Po pozyskaniu danych można je [ujednolicić](data-unification.md) i podejmować na nich akcje.</span><span class="sxs-lookup"><span data-stu-id="309bd-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="309bd-107">Dodaj źródło danych</span><span class="sxs-lookup"><span data-stu-id="309bd-107">Add a data source</span></span>

<span data-ttu-id="309bd-108">Zapoznaj się ze szczegółowymi artykułami dotyczącymi sposobu dodawania źródła danych w zależności od wybranej opcji.</span><span class="sxs-lookup"><span data-stu-id="309bd-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="309bd-109">Źródło danych można dodać na trzy podstawowe sposoby:</span><span class="sxs-lookup"><span data-stu-id="309bd-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="309bd-110">Za pomocą licznych łączników Power Query</span><span class="sxs-lookup"><span data-stu-id="309bd-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="309bd-111">Z folderu Common Data Model</span><span class="sxs-lookup"><span data-stu-id="309bd-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="309bd-112">Z własnego repozytorium tylu lake Common Data Service</span><span class="sxs-lookup"><span data-stu-id="309bd-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="309bd-113">Dodawanie danych z lokalnych źródeł danych</span><span class="sxs-lookup"><span data-stu-id="309bd-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="309bd-114">Przetwarzanie danych z lokalnych źródeł danych w programie Wynikach analiz odbiorców jest obsługiwane na podstawie przepływów danych Power Platform.</span><span class="sxs-lookup"><span data-stu-id="309bd-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="309bd-115">Przepływy danych można włączyć w funkcji Customer Insights, [podając adres URL środowiska Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) podczas konfigurowania środowiska.</span><span class="sxs-lookup"><span data-stu-id="309bd-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="309bd-116">Źródła danych tworzone po skojarzeniu środowiska Dataverse z usługą Customer Insights domyślnie będą korzystać z [przepływów danych Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365).</span><span class="sxs-lookup"><span data-stu-id="309bd-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="309bd-117">Przepływy danych obsługują lokalną łączność przy użyciu bram danych.</span><span class="sxs-lookup"><span data-stu-id="309bd-117">Dataflows support on-prem connectivity using the data gateways.</span></span> <span data-ttu-id="309bd-118">Należy usunąć i ponownie utworzyć źródła danych, które istniały, zanim środowisko Dataverse zostało skojarzone do użycia lokalnych bram danych.</span><span class="sxs-lookup"><span data-stu-id="309bd-118">Remove and recreate data sources that existed before a Dataverse environment was associated to use the on-premises data gateways.</span></span>

<span data-ttu-id="309bd-119">Brama danych z istniejącego lub środowiska Power BI lub Power Apps będzie widoczna i można jej użyć ponownie w usłudze Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="309bd-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="309bd-120">Strona źródła danych pokazuje łącza do środowiska Power Platform, w którym można wyświetlać i konfigurować lokalne bramy danych.</span><span class="sxs-lookup"><span data-stu-id="309bd-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text="Zrzut ekranu strony źródeł danych przedstawiający łącza do środowiska Power Platform.":::

## <a name="review-ingested-data"></a><span data-ttu-id="309bd-122">Przeglądanie pobranych danych</span><span class="sxs-lookup"><span data-stu-id="309bd-122">Review ingested data</span></span>

<span data-ttu-id="309bd-123">Zostanie wyświetlona nazwa każdego pozyskanego źródła danych, jego stan i data ostatniego odświeżenia danych dla tego źródła.</span><span class="sxs-lookup"><span data-stu-id="309bd-123">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="309bd-124">Listę źródeł danych można posortować według każdej kolumny.</span><span class="sxs-lookup"><span data-stu-id="309bd-124">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="309bd-125">![Dodano źródło danych](media/configure-data-datasource-added.png "Dodano źródło danych")</span><span class="sxs-lookup"><span data-stu-id="309bd-125">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="309bd-126">Status</span><span class="sxs-lookup"><span data-stu-id="309bd-126">Status</span></span>  |<span data-ttu-id="309bd-127">Opis</span><span class="sxs-lookup"><span data-stu-id="309bd-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="309bd-128">Pomyślnie</span><span class="sxs-lookup"><span data-stu-id="309bd-128">Successful</span></span>   |<span data-ttu-id="309bd-129">Źródło danych zostało pomyślnie przetworzone, jeśli w kolumnie **Odświeżono** podano godzinę.</span><span class="sxs-lookup"><span data-stu-id="309bd-129">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="309bd-130">Nie rozpoczęto</span><span class="sxs-lookup"><span data-stu-id="309bd-130">Not started</span></span>   |<span data-ttu-id="309bd-131">Źródło danych nie ma jeszcze pozyskanych danych lub nadal jest w trybie roboczym.</span><span class="sxs-lookup"><span data-stu-id="309bd-131">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="309bd-132">Odświeżanie</span><span class="sxs-lookup"><span data-stu-id="309bd-132">Refreshing</span></span>    |<span data-ttu-id="309bd-133">Pobieranie danych jest w toku.</span><span class="sxs-lookup"><span data-stu-id="309bd-133">Data ingestion is in progress.</span></span> <span data-ttu-id="309bd-134">Aby anulować operację, można wybrać opcję **Zatrzymaj odświeżanie** w kolumnie **Czynności**.</span><span class="sxs-lookup"><span data-stu-id="309bd-134">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="309bd-135">Zatrzymanie odświeżania źródła danych spowoduje przywrócenie jego ostatniego stanu odświeżania.</span><span class="sxs-lookup"><span data-stu-id="309bd-135">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="309bd-136">Zakończone niepowodzeniem</span><span class="sxs-lookup"><span data-stu-id="309bd-136">Failed</span></span>     |<span data-ttu-id="309bd-137">Pobieranie danych zostało napotkało błędy.</span><span class="sxs-lookup"><span data-stu-id="309bd-137">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="309bd-138">Wybierz wartość w kolumnie **Stan** dowolnego pola źródło danych, aby przejrzeć więcej szczegółów.</span><span class="sxs-lookup"><span data-stu-id="309bd-138">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="309bd-139">W okienku **Szczegółów postępu** rozwiń pozycję **Źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="309bd-139">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="309bd-140">Wybierz opcję **Zobacz szczegółowe informacje**, aby uzyskać więcej informacji na temat stanu odświeżania, w tym szczegóły błędów i aktualizacje procesów podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="309bd-140">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="309bd-141">Ładowanie danych może potrwać trochę czasu.</span><span class="sxs-lookup"><span data-stu-id="309bd-141">Loading data can take some time.</span></span> <span data-ttu-id="309bd-142">Po pomyślnym odświeżeniu dane z pobierania można przejrzeć na stronie **Encji**.</span><span class="sxs-lookup"><span data-stu-id="309bd-142">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="309bd-143">Aby uzyskać więcej informacji, zobacz [Encje](entities.md).</span><span class="sxs-lookup"><span data-stu-id="309bd-143">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="309bd-144">Odśwież źródło danych</span><span class="sxs-lookup"><span data-stu-id="309bd-144">Refresh a data source</span></span>

<span data-ttu-id="309bd-145">Źródła danych mogą być odświeżane w harmonogramie automatycznym lub ręcznie odświeżane na żądanie.</span><span class="sxs-lookup"><span data-stu-id="309bd-145">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="309bd-146">Przejdź do **Administrator** > **System** > [**Harmonogram**](system.md#schedule-tab), aby skonfigurować zaplanowane odświeżanie wszystkich spożywanych źródeł danych.</span><span class="sxs-lookup"><span data-stu-id="309bd-146">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="309bd-147">Aby odświeżyć źródło danych na żądanie, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="309bd-147">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="309bd-148">W analizach odbiorców przejdź do **Dane** > **Źródła danych**</span><span class="sxs-lookup"><span data-stu-id="309bd-148">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="309bd-149">Zaznacz pionowy wielokropek obok źródło danych, który chcesz odświeżyć, i wybierz opcję **Odśwież** z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="309bd-149">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="309bd-150">Źródło danych jest teraz wyzwalane w celu ręcznego odświeżenia.</span><span class="sxs-lookup"><span data-stu-id="309bd-150">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="309bd-151">Odświeżenie źródła danych spowoduje zaktualizowanie schematu encji i danych dla wszystkich encji określonych w źródle danych.</span><span class="sxs-lookup"><span data-stu-id="309bd-151">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="309bd-152">Wybierz **Zatrzymaj odświeżanie**, aby anulować istniejące odświeżanie, a źródło danych przywróci do ostatniego stanu odświeżania.</span><span class="sxs-lookup"><span data-stu-id="309bd-152">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="309bd-153">Usuń źródło danych</span><span class="sxs-lookup"><span data-stu-id="309bd-153">Delete a data source</span></span>

1. <span data-ttu-id="309bd-154">W analizach odbiorców przejdź do **Dane** > **Źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="309bd-154">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="309bd-155">Zaznacz pionowy wielokropek obok źródła danych, które chcesz usunąć, i wybierz **Usuń** z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="309bd-155">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="309bd-156">Potwierdź usunięcie.</span><span class="sxs-lookup"><span data-stu-id="309bd-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
