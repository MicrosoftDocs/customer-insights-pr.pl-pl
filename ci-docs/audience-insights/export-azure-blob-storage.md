---
title: Eksportowanie Customer Insights do magazynu obiektów Azure Blob Storage
description: Dowiedz się, jak skonfigurować połączenie i eksport do magazynu Blob Storage.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 294feff2f77c3756fbadb36c90aab430454f5967
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760248"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="1e92d-103">Eksportowanie listy segmentów i innych danych do magazynu Azure Blob Storage (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="1e92d-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="1e92d-104">Przechowuj dane aplikacji Customer Insights w usłudze Blob Storage lub korzystaj z niej, aby przenosić swoje dane do innych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1e92d-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="1e92d-105">Skonfiguruj połączenie z usługą Blob Storage</span><span class="sxs-lookup"><span data-stu-id="1e92d-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="1e92d-106">Przejdź do **Admin** > **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="1e92d-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1e92d-107">Wybierz opcję **Dodaj połączenie** i wybierz opcję **Azure Blob Storage**, aby skonfigurować połączenie.</span><span class="sxs-lookup"><span data-stu-id="1e92d-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="1e92d-108">W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="1e92d-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1e92d-109">Wyświetlana nazwa i typ połączenia opisują to połączenie.</span><span class="sxs-lookup"><span data-stu-id="1e92d-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1e92d-110">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.</span><span class="sxs-lookup"><span data-stu-id="1e92d-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1e92d-111">Określ, kto może używać tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="1e92d-111">Choose who can use this connection.</span></span> <span data-ttu-id="1e92d-112">Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy.</span><span class="sxs-lookup"><span data-stu-id="1e92d-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1e92d-113">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1e92d-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1e92d-114">Wprowadź **Nazwę konta**, **Klucz klienta** i **Kontener** dla konta Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="1e92d-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="1e92d-115">Aby dowiedzieć się, jak znaleźć nazwę i klucz klienta konta Blob Storage, zobacz [Zarządzanie ustawieniami konta magazynu w portalu Azure Portal](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="1e92d-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="1e92d-116">Aby dowiedzieć się, jak utworzyć kontener, zobacz [Tworzenie kontenera](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="1e92d-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="1e92d-117">Aby zakończyć połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="1e92d-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="1e92d-118">Konfigurowanie eksportu</span><span class="sxs-lookup"><span data-stu-id="1e92d-118">Configure an export</span></span>

<span data-ttu-id="1e92d-119">Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="1e92d-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1e92d-120">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1e92d-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1e92d-121">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="1e92d-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1e92d-122">Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="1e92d-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1e92d-123">W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="1e92d-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="1e92d-124">Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="1e92d-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1e92d-125">Zaznacz pole wyboru obok każdej encji, która ma zostać wyeksportowana do tej lokalizacji docelowej.</span><span class="sxs-lookup"><span data-stu-id="1e92d-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="1e92d-126">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="1e92d-126">Select **Save**.</span></span>

<span data-ttu-id="1e92d-127">Zapisanie eksportu nie uruchamia natychmiastowo eksportu.</span><span class="sxs-lookup"><span data-stu-id="1e92d-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1e92d-128">Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1e92d-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="1e92d-129">Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1e92d-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="1e92d-130">Wyeksportowane dane są przechowywane w skonfigurowanym kontenerze Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="1e92d-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="1e92d-131">W kontenerze są automatycznie tworzone następujące ścieżki folderów:</span><span class="sxs-lookup"><span data-stu-id="1e92d-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="1e92d-132">Dla encji źródłowych i encji wygenerowanych przez system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="1e92d-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="1e92d-133">Przykład: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="1e92d-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="1e92d-134">Element model.json dla eksportowanych encji będzie na poziomie %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="1e92d-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="1e92d-135">Przykład: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="1e92d-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
