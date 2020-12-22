---
title: Połącz dane Common Data Model z kontem Azure Data Lake
description: Pracuj z danymi Common Data Model przy użyciu usługi Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643471"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="89d68-103">Połącz z folderem Common Data Model za pomocą Azure Data Lake Account</span><span class="sxs-lookup"><span data-stu-id="89d68-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="89d68-104">Ten artykuł zawiera informacje na temat pozyskiwania danych z folderu Common Data Model przy użyciu konta Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="89d68-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="89d68-105">Ważne uwagi</span><span class="sxs-lookup"><span data-stu-id="89d68-105">Important considerations</span></span>

- <span data-ttu-id="89d68-106">Dane w usłudze Azure Data Lake muszą być zgodne ze standardem Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="89d68-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="89d68-107">W tym momencie inne formaty nie są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="89d68-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="89d68-108">Pozyskiwanie danych obsługuje wyłącznie konta magazynu Azure Data Lake *Gen2*.</span><span class="sxs-lookup"><span data-stu-id="89d68-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="89d68-109">Nie można używać kont magazynu Azure Data Lake Gen1 do pozyskiwania danych.</span><span class="sxs-lookup"><span data-stu-id="89d68-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="89d68-110">Aby uwierzytelnić się przy użyciu głównej usługi platformy Azure, upewnij się, że jest ona skonfigurowana w dzierżawie.</span><span class="sxs-lookup"><span data-stu-id="89d68-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="89d68-111">Aby uzyskać więcej informacji, zobacz temat [Połącz analizy odbiorców z kontem Azure Data Lake Storage Gen2 za pomocą głównej usługi platformy Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="89d68-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="89d68-112">Usługa Azure Data Lake, z którą chcesz się łączyć i pozyskiwać dane, musi znajdować się w tym samym regionie Azure, co środowisko Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="89d68-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="89d68-113">Połączenia z folderem Common Data Model z data lake w innym regionie świadczenia usługi Azure nie są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="89d68-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="89d68-114">Aby sprawdzić, jaki jest obszar Azure środowiska, przejdź do **Administrator** > **System** > **Informacje** w analizach odbiorców.</span><span class="sxs-lookup"><span data-stu-id="89d68-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="89d68-115">Dane przechowywane w usługach online mogą być przechowywane w innej lokalizacji niż ta, w której dane są przetwarzane lub przechowywane w Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="89d68-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="89d68-116"> Importując lub łącząc się z danymi w usługach online, użytkownik zgadza się, że dane mogą być przenoszone do programu Dynamics 365 Customer Insights i przechowywane w nim. [Dowiedz się więcej w Centrum zaufania firmy Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="89d68-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="89d68-117">Połącz z folderem modelu Common Data Model</span><span class="sxs-lookup"><span data-stu-id="89d68-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="89d68-118">W analizach odbiorców przejdź do **Dane** > **Źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="89d68-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="89d68-119">Wybierz **Dodaj źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="89d68-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="89d68-120">Wybierz opcję **Połącz z folderem Common Data Model**, wprowadź **Nazwę** źródła danych i wybierz przycisk **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="89d68-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span>

1. <span data-ttu-id="89d68-121">Można wybrać między opcją opartą na zasobach a opcją opartą na subskrypcji na potrzeby uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="89d68-121">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="89d68-122">Aby uzyskać więcej informacji, zobacz temat [Połącz analizy odbiorców z kontem Azure Data Lake Storage Gen2 za pomocą głównej usługi platformy Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="89d68-122">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="89d68-123">Wprowadź informacje o **Kontenerze** i wybierz opcję **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="89d68-123">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="89d68-124">![Okno dialogowe, w którym można wprowadzić szczegółowe dane dotyczące połączenia z Azure Data Lake](media/enter-new-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="89d68-124">![Dialog box to enter connection details for Azure Data Lake](media/enter-new-storage-details.png)</span></span>

1. <span data-ttu-id="89d68-125">W oknie dialogowym **Wybierz folder Common Data Model** wybierz plik model.json w celu zaimportowania danych z programu i wybierz przycisk **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="89d68-125">In the **Select a Common Data Model folder** dialog, select the model.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="89d68-126">Żaden plik model.json powiązany z innym źródłem danych w środowisku nie zostanie wyświetlony na liście.</span><span class="sxs-lookup"><span data-stu-id="89d68-126">Any model.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="89d68-127">Otrzymasz listę dostępnych encji w wybranym pliku model.json.</span><span class="sxs-lookup"><span data-stu-id="89d68-127">You'll get a list of available entities in the selected model.json file.</span></span> <span data-ttu-id="89d68-128">Możesz przeanalizować i wybrać z listy dostępnych encji i wybrać **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="89d68-128">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="89d68-129">Wszystkie wybrane encje zostaną pozyskane z nowego źródła danych.</span><span class="sxs-lookup"><span data-stu-id="89d68-129">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="89d68-130">![Okno dialogowe pokazujące listę encji z pliku model.json](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="89d68-130">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="89d68-131">Określ, dla których encji danych chcesz włączyć profilowanie danych i wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="89d68-131">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="89d68-132">Dzięki profilowaniu danych można korzystać z analiz i innych możliwości.</span><span class="sxs-lookup"><span data-stu-id="89d68-132">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="89d68-133">Możesz wybrać całą encję, która wybiera wszystkie atrybuty z encji lub wybrane atrybuty.</span><span class="sxs-lookup"><span data-stu-id="89d68-133">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="89d68-134">Domyślnie żadne encje nie są włączone do profilowania danych.</span><span class="sxs-lookup"><span data-stu-id="89d68-134">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="89d68-135">![Okno dialogowe pokazujące Profilowanie danych](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="89d68-135">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="89d68-136">Po zapisaniu wybranych opcji zostanie otwarta strona **Źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="89d68-136">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="89d68-137">Łącze do folderu Common Data Model powinno być teraz widoczne jako źródło danych.</span><span class="sxs-lookup"><span data-stu-id="89d68-137">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="89d68-138">Plik typu model.json może mieć skojarzenie tylko jedno źródło danych w tym samym środowisku.</span><span class="sxs-lookup"><span data-stu-id="89d68-138">A model.json file can only associate with one data source in the same environment.</span></span> <span data-ttu-id="89d68-139">Jednak ten sam plik model.json może być używany dla źródeł danych w wielu środowiskach.</span><span class="sxs-lookup"><span data-stu-id="89d68-139">However, the same model.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="89d68-140">Edytowanie źródła danych folderu Common Data Model</span><span class="sxs-lookup"><span data-stu-id="89d68-140">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="89d68-141">Możesz zaktualizować klucz dostępu dla konta magazynu zawierającego folder Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="89d68-141">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="89d68-142">Użytkownik może również zmienić plik model.json.</span><span class="sxs-lookup"><span data-stu-id="89d68-142">You may also change the model.json file.</span></span> <span data-ttu-id="89d68-143">Aby połączyć się z innym kontenerem z konta magazynu lub zmienić nazwę konta, [utwórz nowe połączenie źródła danych](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="89d68-143">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="89d68-144">W analizach odbiorców przejdź do **Dane** > **Źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="89d68-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="89d68-145">Kliknij wielokropek obok źródła danych, który chcesz zaktualizować.</span><span class="sxs-lookup"><span data-stu-id="89d68-145">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="89d68-146">Wybierz opcję **Edytuj** z listy.</span><span class="sxs-lookup"><span data-stu-id="89d68-146">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="89d68-147">Opcjonalnie zaktualizuj **Klucz dostępu** i wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="89d68-147">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Dialog pozwalający edytować i aktualizować klucz dostępu dla istniejącego źródła danych](media/edit-access-key.png)

5. <span data-ttu-id="89d68-149">Opcjonalnie można zaktualizować połączenie z klucza konta do połączenia opartego na zasobach lub subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="89d68-149">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="89d68-150">Aby uzyskać więcej informacji, zobacz temat [Połącz analizy odbiorców z kontem Azure Data Lake Storage Gen2 za pomocą głównej usługi platformy Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="89d68-150">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="89d68-151">Podczas aktualizowania połączenia nie można zmieniać informacji o **Kontenerze**.</span><span class="sxs-lookup"><span data-stu-id="89d68-151">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="89d68-152">![Okno dialogowe, w którym można wprowadzić szczegółowe dane dotyczące połączenia z Azure Data Lake](media/enter-existing-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="89d68-152">![Dialog box to enter connection details for Azure Data Lake](media/enter-existing-storage-details.png)</span></span>

6. <span data-ttu-id="89d68-153">Opcjonalnie wybierz inny plik model.json z innym zestawem encji z kontenera.</span><span class="sxs-lookup"><span data-stu-id="89d68-153">Optionally, choose a different model.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="89d68-154">Można też wybrać dodatkowe encje do pobrania.</span><span class="sxs-lookup"><span data-stu-id="89d68-154">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="89d68-155">Jeśli nie ma zależności, można również usunąć wszystkie wybrane encje.</span><span class="sxs-lookup"><span data-stu-id="89d68-155">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="89d68-156">Jeśli istnieją zależności między istniejącym plikiem model.json a zestawem encji, zostanie wyświetlony komunikat o błędzie i nie będzie można wybrać innego pliku model.json.</span><span class="sxs-lookup"><span data-stu-id="89d68-156">If there are dependencies on the existing model.json file and the set of entities, you'll see an error message and can't select a different model.json file.</span></span> <span data-ttu-id="89d68-157">Usuń te zależności przed zmodyfikowaniem pliku model.json lub utwórz nowe źródło danych za pomocą pliku typu model.json, którego chcesz użyć, aby zapobiec usuwaniu zależności.</span><span class="sxs-lookup"><span data-stu-id="89d68-157">Remove those dependencies before changing the model.json file or create a new data source with the model.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="89d68-158">Opcjonalnie możesz wybrać dodatkowe atrybuty lub encje, aby włączyć profilowanie danych lub wyłączyć już wybrane.</span><span class="sxs-lookup"><span data-stu-id="89d68-158">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   
