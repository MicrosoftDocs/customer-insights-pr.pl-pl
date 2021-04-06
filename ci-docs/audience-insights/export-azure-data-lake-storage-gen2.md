---
title: Eksportowanie danych Customer Insights do Azure Data Lake Storage Gen2
description: Dowiedz się, jak skonfigurować połączenie z Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596651"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="69241-103">Łącznik dla usługi  Azure Data Lake Storage Gen2 (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="69241-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="69241-104">Przechowuj dane aplikacji Customer Insights w usłudze Azure Data Lake Storage Gen2 lub korzystaj z niej, aby transferować swoje dane do innych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="69241-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="69241-105">Konfigurowanie łącznika dla Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="69241-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="69241-106">W analizach odbiorców przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.</span><span class="sxs-lookup"><span data-stu-id="69241-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="69241-107">W **Azure Data Lake Storage Gen2** wybierz **Konfiguruj**.</span><span class="sxs-lookup"><span data-stu-id="69241-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="69241-108">W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="69241-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="69241-109">Wprowadź **Nazwę konta**, **Klucz klienta** i **Kontener** dla komputera Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="69241-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="69241-110">Informacje o tworzeniu konta magazynu do używania z Azure Data Lake Storage Gen2 można przeczytać w temacie [Utwórz konto magazynu](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="69241-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="69241-111">Aby dowiedzieć się więcej o tym, jak znaleźć nazwę konta magazynu Azure Data Lake Gen2 i klucz konta, zobacz [Zarządzaj ustawieniami konta magazynu w Azure Portal](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="69241-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="69241-112">Wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="69241-112">Select **Next**.</span></span>

1. <span data-ttu-id="69241-113">Zaznacz pole wyboru obok każdej encji, która ma zostać wyeksportowana do tej lokalizacji docelowej.</span><span class="sxs-lookup"><span data-stu-id="69241-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="69241-114">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="69241-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="69241-115">Eksportowanie danych</span><span class="sxs-lookup"><span data-stu-id="69241-115">Export the data</span></span>

<span data-ttu-id="69241-116">Możesz [eksportować dane na żądanie](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="69241-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="69241-117">Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="69241-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>