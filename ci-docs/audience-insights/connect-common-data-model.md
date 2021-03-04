---
title: Połącz dane Common Data Model z kontem Azure Data Lake
description: Pracuj z danymi Common Data Model przy użyciu usługi Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 247e4d9c47ff2373065ebf3c6d554323e45a120b
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267873"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="e0526-103">Połącz z folderem Common Data Model za pomocą Azure Data Lake Account</span><span class="sxs-lookup"><span data-stu-id="e0526-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="e0526-104">Ten artykuł zawiera informacje na temat pozyskiwania danych z folderu Common Data Model przy użyciu konta Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="e0526-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="e0526-105">Ważne uwagi</span><span class="sxs-lookup"><span data-stu-id="e0526-105">Important considerations</span></span>

- <span data-ttu-id="e0526-106">Dane w usłudze Azure Data Lake muszą być zgodne ze standardem Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="e0526-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="e0526-107">W tym momencie inne formaty nie są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="e0526-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="e0526-108">Pozyskiwanie danych obsługuje wyłącznie konta magazynu Azure Data Lake *Gen2*.</span><span class="sxs-lookup"><span data-stu-id="e0526-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="e0526-109">Nie można używać kont magazynu Azure Data Lake Gen1 do pozyskiwania danych.</span><span class="sxs-lookup"><span data-stu-id="e0526-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="e0526-110">Aby uwierzytelnić się przy użyciu głównej usługi platformy Azure, upewnij się, że jest ona skonfigurowana w dzierżawie.</span><span class="sxs-lookup"><span data-stu-id="e0526-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="e0526-111">Aby uzyskać więcej informacji, zobacz temat [Połącz analizy odbiorców z kontem Azure Data Lake Storage Gen2 za pomocą głównej usługi platformy Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="e0526-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="e0526-112">Usługa Azure Data Lake, z którą chcesz się łączyć i pozyskiwać dane, musi znajdować się w tym samym regionie Azure, co środowisko Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e0526-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="e0526-113">Połączenia z folderem Common Data Model z data lake w innym regionie świadczenia usługi Azure nie są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="e0526-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="e0526-114">Aby sprawdzić, jaki jest obszar Azure środowiska, przejdź do **Administrator** > **System** > **Informacje** w analizach odbiorców.</span><span class="sxs-lookup"><span data-stu-id="e0526-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="e0526-115">Dane przechowywane w usługach online mogą być przechowywane w innej lokalizacji niż ta, w której dane są przetwarzane lub przechowywane w Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e0526-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="e0526-116"> Importując lub łącząc się z danymi w usługach online, użytkownik zgadza się, że dane mogą być przenoszone do programu Dynamics 365 Customer Insights i przechowywane w nim. [Dowiedz się więcej w Centrum zaufania firmy Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="e0526-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="e0526-117">Połącz z folderem modelu Common Data Model</span><span class="sxs-lookup"><span data-stu-id="e0526-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="e0526-118">W analizach odbiorców przejdź do **Dane** > **Źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="e0526-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="e0526-119">Wybierz **Dodaj źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="e0526-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="e0526-120">Wybierz opcję **Połącz z folderem Common Data Model**, wprowadź **Nazwę** źródła danych i wybierz przycisk **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="e0526-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="e0526-121">Wytyczne dotyczące nazw:</span><span class="sxs-lookup"><span data-stu-id="e0526-121">Name guidelines:</span></span> 
   - <span data-ttu-id="e0526-122">Rozpocznij od litery.</span><span class="sxs-lookup"><span data-stu-id="e0526-122">Start with a letter.</span></span>
   - <span data-ttu-id="e0526-123">Używaj tylko liter i liczb.</span><span class="sxs-lookup"><span data-stu-id="e0526-123">Use letters and numbers only.</span></span> <span data-ttu-id="e0526-124">Spacje i znaki specjalne są niedozwolone.</span><span class="sxs-lookup"><span data-stu-id="e0526-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="e0526-125">Użyj między 3 do 64 znaków.</span><span class="sxs-lookup"><span data-stu-id="e0526-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="e0526-126">Można wybrać między opcją opartą na zasobach a opcją opartą na subskrypcji na potrzeby uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="e0526-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="e0526-127">Aby uzyskać więcej informacji, zobacz temat [Połącz analizy odbiorców z kontem Azure Data Lake Storage Gen2 za pomocą głównej usługi platformy Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="e0526-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="e0526-128">Wprowadź informacje o **Kontenerze** i wybierz opcję **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="e0526-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e0526-129">![Okno dialogowe umożliwiające wprowadzenie nowych szczegółów połączenia dla usługi Azure Data Lake](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="e0526-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="e0526-130">Potrzebujesz jednej z następujących ról do kontenera lub konta magazynu, o którym mowa powyżej, aby móc nawiązać połączenie i utworzyć źródło danych:</span><span class="sxs-lookup"><span data-stu-id="e0526-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="e0526-131">Czytnik danych Storage Blob</span><span class="sxs-lookup"><span data-stu-id="e0526-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="e0526-132">Właściciel danych Storage Blob</span><span class="sxs-lookup"><span data-stu-id="e0526-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="e0526-133">Współautor danych w usłudze Blob Storage</span><span class="sxs-lookup"><span data-stu-id="e0526-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="e0526-134">W oknie dialogowym **Wybierz folder Common Data Model** wybierz plik model.json lub manifest.json w celu zaimportowania danych z programu i wybierz przycisk **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="e0526-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="e0526-135">Żaden plik model.json lub manifest.json powiązany z innym źródłem danych w środowisku nie zostanie wyświetlony na liście.</span><span class="sxs-lookup"><span data-stu-id="e0526-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="e0526-136">Otrzymasz listę dostępnych encji w wybranym pliku model.json lub manifest.json.</span><span class="sxs-lookup"><span data-stu-id="e0526-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="e0526-137">Możesz przeanalizować i wybrać z listy dostępnych encji i wybrać **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="e0526-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="e0526-138">Wszystkie wybrane encje zostaną pozyskane z nowego źródła danych.</span><span class="sxs-lookup"><span data-stu-id="e0526-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e0526-139">![Okno dialogowe pokazujące listę encji z pliku model.json](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="e0526-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="e0526-140">Określ, dla których encji danych chcesz włączyć profilowanie danych i wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="e0526-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="e0526-141">Dzięki profilowaniu danych można korzystać z analiz i innych możliwości.</span><span class="sxs-lookup"><span data-stu-id="e0526-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="e0526-142">Możesz wybrać całą encję, która wybiera wszystkie atrybuty z encji lub wybrane atrybuty.</span><span class="sxs-lookup"><span data-stu-id="e0526-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="e0526-143">Domyślnie żadne encje nie są włączone do profilowania danych.</span><span class="sxs-lookup"><span data-stu-id="e0526-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e0526-144">![Okno dialogowe pokazujące Profilowanie danych](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="e0526-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="e0526-145">Po zapisaniu wybranych opcji zostanie otwarta strona **Źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="e0526-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="e0526-146">Łącze do folderu Common Data Model powinno być teraz widoczne jako źródło danych.</span><span class="sxs-lookup"><span data-stu-id="e0526-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="e0526-147">Plik typu model.json lub manifest.json może mieć skojarzenie tylko jedno źródło danych w tym samym środowisku.</span><span class="sxs-lookup"><span data-stu-id="e0526-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="e0526-148">Jednak ten sam plik model.json lub manifest.json może być używany dla źródeł danych w wielu środowiskach.</span><span class="sxs-lookup"><span data-stu-id="e0526-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="e0526-149">Edytowanie źródła danych folderu Common Data Model</span><span class="sxs-lookup"><span data-stu-id="e0526-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="e0526-150">Możesz zaktualizować klucz dostępu dla konta magazynu zawierającego folder Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="e0526-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="e0526-151">Można również zmienić plik model.json lub manifest.json.</span><span class="sxs-lookup"><span data-stu-id="e0526-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="e0526-152">Aby połączyć się z innym kontenerem z konta magazynu lub zmienić nazwę konta, [utwórz nowe połączenie źródła danych](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="e0526-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="e0526-153">W analizach odbiorców przejdź do **Dane** > **Źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="e0526-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="e0526-154">Kliknij wielokropek obok źródła danych, który chcesz zaktualizować.</span><span class="sxs-lookup"><span data-stu-id="e0526-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="e0526-155">Wybierz opcję **Edytuj** z listy.</span><span class="sxs-lookup"><span data-stu-id="e0526-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="e0526-156">Opcjonalnie zaktualizuj **Klucz dostępu** i wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="e0526-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Dialog pozwalający edytować i aktualizować klucz dostępu dla istniejącego źródła danych](media/edit-access-key.png)

5. <span data-ttu-id="e0526-158">Opcjonalnie można zaktualizować połączenie z klucza konta do połączenia opartego na zasobach lub subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="e0526-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="e0526-159">Aby uzyskać więcej informacji, zobacz temat [Połącz analizy odbiorców z kontem Azure Data Lake Storage Gen2 za pomocą głównej usługi platformy Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="e0526-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="e0526-160">Podczas aktualizowania połączenia nie można zmieniać informacji o **Kontenerze**.</span><span class="sxs-lookup"><span data-stu-id="e0526-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![Okno dialogowe wprowadzania szczegółów połączenia dla danych Azure Data Lake do istniejącego konta magazynu](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="e0526-162">Potrzebujesz jednej z następujących ról do kontenera lub konta magazynu, o którym mowa powyżej, aby móc nawiązać połączenie i utworzyć źródło danych:</span><span class="sxs-lookup"><span data-stu-id="e0526-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="e0526-163">Czytnik danych Storage Blob</span><span class="sxs-lookup"><span data-stu-id="e0526-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="e0526-164">Właściciel danych Storage Blob</span><span class="sxs-lookup"><span data-stu-id="e0526-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="e0526-165">Współautor danych w usłudze Blob Storage</span><span class="sxs-lookup"><span data-stu-id="e0526-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="e0526-166">Opcjonalnie wybierz inny plik model.json lub manifest.json z innym zestawem jednostek z kontenera.</span><span class="sxs-lookup"><span data-stu-id="e0526-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="e0526-167">Można też wybrać dodatkowe encje do pobrania.</span><span class="sxs-lookup"><span data-stu-id="e0526-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="e0526-168">Jeśli nie ma zależności, można również usunąć wszystkie wybrane encje.</span><span class="sxs-lookup"><span data-stu-id="e0526-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="e0526-169">Jeśli istnieją zależności między istniejącym plikiem model.json lub manifest.json a zestawem jednostek, zostanie wyświetlony komunikat o błędzie i nie będzie można wybrać innego pliku model.json lub manifest.json.</span><span class="sxs-lookup"><span data-stu-id="e0526-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="e0526-170">Usuń te zależności przed zmianą pliku model.json lub manifest.json lub utwórz nowe źródło danych z plikiem model.json lub manifest.json, którego chcesz użyć, aby uniknąć usuwania zależności.</span><span class="sxs-lookup"><span data-stu-id="e0526-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="e0526-171">Opcjonalnie możesz wybrać dodatkowe atrybuty lub encje, aby włączyć profilowanie danych lub wyłączyć już wybrane.</span><span class="sxs-lookup"><span data-stu-id="e0526-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]