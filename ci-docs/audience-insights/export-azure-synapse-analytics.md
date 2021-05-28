---
title: Eksportowanie danych usługi Customer Insights do usługi Azure Synapse Analytics
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977390"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="dc484-103">Eksportuj dane do Azure Synapse Analytics</span><span class="sxs-lookup"><span data-stu-id="dc484-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="dc484-104">Azure Synapse to usługa analityczna, która przyspiesza czas uzyskania wglądu w magazyny danych i systemy big data.</span><span class="sxs-lookup"><span data-stu-id="dc484-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="dc484-105">Możesz pobierać dane Customer Insights i wykorzystywać je w [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="dc484-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dc484-106">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="dc484-106">Prerequisites</span></span>

<span data-ttu-id="dc484-107">Aby skonfigurować połączenie Customer Insights z Azure Synapse należy spełnić następujące wymagania wstępne.</span><span class="sxs-lookup"><span data-stu-id="dc484-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="dc484-108">Upewnij się, że zostały ustawione wszystkie **przypisania ról** w odpowiedni sposób.</span><span class="sxs-lookup"><span data-stu-id="dc484-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="dc484-109">Wymagania Customer Insights</span><span class="sxs-lookup"><span data-stu-id="dc484-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="dc484-110">Masz rolę użytkownika **Administrator** w rozwiązaniu analiza odbiorców.</span><span class="sxs-lookup"><span data-stu-id="dc484-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="dc484-111">Więcej informacji o [ustawianiu uprawnień użytkowników w analizie odbiorców](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="dc484-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="dc484-112">W Azure:</span><span class="sxs-lookup"><span data-stu-id="dc484-112">In Azure:</span></span> 

- <span data-ttu-id="dc484-113">Aktywna subskrypcja platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="dc484-113">An active Azure subscription.</span></span>

- <span data-ttu-id="dc484-114">Jeśli jest potrzebne nowe konto Azure Data Lake Storage Gen2, *nazwa główna usługi analizy odbiorców* potrzebuje uprawnień **Współautor danych w usłudze Blob Storage**.</span><span class="sxs-lookup"><span data-stu-id="dc484-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="dc484-115">Dowiedz się więcej o [łączeniu się z kontem Azure Data Lake Storage Gen2 za pomocą nazwy głównej usługi Azure w analizie odbiorców](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="dc484-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="dc484-116">Data Lake Storage Gen2 **musi posiadać** uruchomiony [hierarchiczny obszar nazw](/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="dc484-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="dc484-117">W grupie zasobów, w której znajduje się obszar roboczy Azure Synapse, *nazwa główna usługi* i *użytkownik w analizie odbiorców* muszą posiadać uprawnienia na poziomie co najmniej **Odczyt**.</span><span class="sxs-lookup"><span data-stu-id="dc484-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="dc484-118">Aby uzyskać więcej informacji, zobacz [przypisywanie ról Azure za pomocą portalu Azure](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="dc484-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="dc484-119">*Użytkownik* musi mieć uprawnienia **Współautor danych w usłudze Blob Storage** na koncie Azure Data Lake Storage Gen2, na którym zlokalizowane są dane i połączone z obszarem roboczym Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="dc484-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="dc484-120">Więcej informacji na temat [używania portalu Azure w celu przydzielania roli Azure, aby uzyskać dostęp do danych kolejki i danych blob](/azure/storage/common/storage-auth-aad-rbac-portal) oraz [Współautor danych w usłudze Blob Storage — uprawnienia](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="dc484-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="dc484-121">*[Tożsamość zarządzanego obszaru roboczego Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* musi mieć uprawnienia **Współautor danych w usłudze Blob Storage** na koncie Azure Data Lake Storage Gen2, na którym zlokalizowane są dane i połączone z obszarem roboczym Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="dc484-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="dc484-122">Więcej informacji na temat [używania portalu Azure w celu przydzielania roli Azure, aby uzyskać dostęp do danych kolejki i danych blob](/azure/storage/common/storage-auth-aad-rbac-portal) oraz [Współautor danych w usłudze Blob Storage — uprawnienia](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="dc484-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="dc484-123">W obszarze roboczym Azure Synapse jest rola *nazwa główna usługi analizy odbiorców* musi posiadać przypisaną rolę **Administrator Synapse**.</span><span class="sxs-lookup"><span data-stu-id="dc484-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="dc484-124">Aby uzyskać więcej informacji, zobacz temat [Jak skonfigurować formant dostępu dla obszaru roboczego Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="dc484-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="dc484-125">Skonfiguruj połączenie i eksport do Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="dc484-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="dc484-126">Konfigurowanie połączenia</span><span class="sxs-lookup"><span data-stu-id="dc484-126">Configure a connection</span></span>

1. <span data-ttu-id="dc484-127">Przejdź do **Admin** > **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="dc484-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="dc484-128">Wybierz opcję **Dodaj połączenie** i wybierz opcję **Azure Synapse Analytics**, aby skonfigurować połączenie, lub wybierz opcję **Konfiguruj** w kafelku **Azure Synapse Analytics**, aby skonfigurować połączenie.</span><span class="sxs-lookup"><span data-stu-id="dc484-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="dc484-129">W polu Wyświetlana nazwa nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="dc484-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="dc484-130">Wyświetlana nazwa i typ połączenia opisują to połączenie.</span><span class="sxs-lookup"><span data-stu-id="dc484-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="dc484-131">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.</span><span class="sxs-lookup"><span data-stu-id="dc484-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="dc484-132">Określ, kto może używać tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="dc484-132">Choose who can use this connection.</span></span> <span data-ttu-id="dc484-133">Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy.</span><span class="sxs-lookup"><span data-stu-id="dc484-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="dc484-134">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="dc484-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="dc484-135">Wybierz lub wyszukaj subskrypcję, w której chcesz korzystać z danych funkcji Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="dc484-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="dc484-136">Po wybraniu subskrypcji można również wybrać opcję **Obszar roboczy**, **Konto magazynu** i **Kontener**.</span><span class="sxs-lookup"><span data-stu-id="dc484-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="dc484-137">Aby zapisać połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="dc484-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="dc484-138">Konfigurowanie eksportu</span><span class="sxs-lookup"><span data-stu-id="dc484-138">Configure an export</span></span>

<span data-ttu-id="dc484-139">Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="dc484-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="dc484-140">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="dc484-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="dc484-141">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="dc484-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="dc484-142">Wybierz **Dodaj eksport**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="dc484-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="dc484-143">W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi **Azure Synapse Analytics**.</span><span class="sxs-lookup"><span data-stu-id="dc484-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="dc484-144">Jeśli nie widać nazwy tej sekcji, nie ma dostępnych [połączeń](connections.md) tego typu dla tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="dc484-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="dc484-145">Podaj rozpoznawalną **wyświetlaną nazwę** eksportowi i **nazwę bazy danych**.</span><span class="sxs-lookup"><span data-stu-id="dc484-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="dc484-146">Wybierz encje do wyeksportowania do Azure Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="dc484-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="dc484-147">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="dc484-147">Select **Save**.</span></span>

<span data-ttu-id="dc484-148">Zapisanie eksportu nie uruchamia natychmiastowo eksportu.</span><span class="sxs-lookup"><span data-stu-id="dc484-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="dc484-149">Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dc484-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="dc484-150">Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="dc484-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="dc484-151">Aktualizowanie eksportu</span><span class="sxs-lookup"><span data-stu-id="dc484-151">Update an export</span></span>

1. <span data-ttu-id="dc484-152">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="dc484-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="dc484-153">Wybierz pozycję **Edytuj** dla eksportu, który chcesz zaktualizować.</span><span class="sxs-lookup"><span data-stu-id="dc484-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="dc484-154">**Dodawanie** encji do wyboru i **usuwanie** ich.</span><span class="sxs-lookup"><span data-stu-id="dc484-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="dc484-155">Jeśli encje zostaną usunięte z wybranej bazy danych, nie zostaną usunięte z bazy danych Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="dc484-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="dc484-156">Jednak odświeżenie przyszłych danych nie spowoduje zaktualizowania usuniętych encji z tej bazy danych.</span><span class="sxs-lookup"><span data-stu-id="dc484-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="dc484-157">**Zmiana nazwy bazy danych** spowoduje utworzenie nowej bazy danych Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="dc484-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="dc484-158">Baza danych o nazwie, która została wcześniej skonfigurowana, nie będzie otrzymywać żadnych aktualizacji w kolejnych odświeżeniach.</span><span class="sxs-lookup"><span data-stu-id="dc484-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
