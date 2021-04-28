---
title: Eksportowanie danych Customer Insights do Azure Data Lake Storage Gen2
description: Dowiedz się, jak skonfigurować połączenie z Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760064"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="ad312-103">Skonfiguruj połączenie z usługą Azure Data Lake Storage Gen2 (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="ad312-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="ad312-104">Przejdź do **Admin** > **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="ad312-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ad312-105">Wybierz opcję **Dodaj połączenie** i wybierz opcję **Azure Data Lake Gen 2**, aby skonfigurować połączenie.</span><span class="sxs-lookup"><span data-stu-id="ad312-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="ad312-106">W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="ad312-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ad312-107">Wyświetlana nazwa i typ połączenia opisują to połączenie.</span><span class="sxs-lookup"><span data-stu-id="ad312-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ad312-108">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.</span><span class="sxs-lookup"><span data-stu-id="ad312-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ad312-109">Określ, kto może używać tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="ad312-109">Choose who can use this connection.</span></span> <span data-ttu-id="ad312-110">Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy.</span><span class="sxs-lookup"><span data-stu-id="ad312-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ad312-111">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ad312-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ad312-112">Wprowadź **Nazwę konta**, **Klucz klienta** i **Kontener** dla komputera Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="ad312-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="ad312-113">Informacje o tworzeniu konta magazynu do używania z Azure Data Lake Storage Gen2 można przeczytać w temacie [Utwórz konto magazynu](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="ad312-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="ad312-114">Aby dowiedzieć się, jak znaleźć nazwę i klucz klienta konta magazynu Azure Data Lake Gen 2, zobacz [Zarządzanie ustawieniami konta magazynu w portalu Azure Portal](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="ad312-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="ad312-115">Aby zakończyć połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ad312-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="ad312-116">Konfigurowanie eksportu</span><span class="sxs-lookup"><span data-stu-id="ad312-116">Configure an export</span></span>

<span data-ttu-id="ad312-117">Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="ad312-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ad312-118">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ad312-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ad312-119">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="ad312-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ad312-120">Wybierz **Dodaj eksport**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="ad312-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="ad312-121">W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi **Azure Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="ad312-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="ad312-122">Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="ad312-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ad312-123">Zaznacz pole wyboru obok każdej encji, która ma zostać wyeksportowana do tej lokalizacji docelowej.</span><span class="sxs-lookup"><span data-stu-id="ad312-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="ad312-124">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ad312-124">Select **Save**.</span></span>

<span data-ttu-id="ad312-125">Zapisanie eksportu nie uruchamia natychmiastowo eksportu.</span><span class="sxs-lookup"><span data-stu-id="ad312-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ad312-126">Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ad312-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ad312-127">Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ad312-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="ad312-128">Wyeksportowane dane są przechowywane w skonfigurowanym kontenerze magazynu Azure Data Lake Gen 2.</span><span class="sxs-lookup"><span data-stu-id="ad312-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
