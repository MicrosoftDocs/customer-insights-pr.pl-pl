---
title: Utwórz środowisko i zarządzaj nim.
description: Dowiedz się, jak zapisać się w usłudze i zarządzać środowiskami.
ms.date: 03/26/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8cc1401251ed7c45c598bd4a8fb33a9709fabbc8
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887999"
---
# <a name="manage-environments"></a><span data-ttu-id="9e827-103">Zarządzaj środowiskami</span><span class="sxs-lookup"><span data-stu-id="9e827-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="9e827-104">W tym artykule wyjaśniono, jak utworzyć nową organizację i zastrzec bezpieczeństwo środowiska.</span><span class="sxs-lookup"><span data-stu-id="9e827-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="9e827-105">Tworzenie konta i organizacja</span><span class="sxs-lookup"><span data-stu-id="9e827-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="9e827-106">Przejdź do witryny internetowej [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="9e827-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="9e827-107">Wybierz **Rozpocznij**.</span><span class="sxs-lookup"><span data-stu-id="9e827-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="9e827-108">Wybierz preferowany scenariusz zapisywania i wybierz odpowiednie łącze.</span><span class="sxs-lookup"><span data-stu-id="9e827-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="9e827-109">Zaakceptuj warunki, a następnie wybierz **Dalej**, aby rozpocząć tworzenie organizacji.</span><span class="sxs-lookup"><span data-stu-id="9e827-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="9e827-110">Po utworzeniu środowiska nastąpi przekierowanie do [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="9e827-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="9e827-111">Użyj środowiska pokazowego, aby eksplorować aplikację, lub utwórz nowe środowisko, wykonując kroki opisane w następnej sekcji.</span><span class="sxs-lookup"><span data-stu-id="9e827-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="9e827-112">Po określeniu ustawień środowiska wybierz **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="9e827-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="9e827-113">Po pomyślnym utworzeniu środowiska użytkownik zostanie zalogowany.</span><span class="sxs-lookup"><span data-stu-id="9e827-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="9e827-114">Tworzenie środowiska w istniejącej organizacji</span><span class="sxs-lookup"><span data-stu-id="9e827-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="9e827-115">Istnieją dwa sposoby utworzenia nowego środowiska.</span><span class="sxs-lookup"><span data-stu-id="9e827-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="9e827-116">Można określić zupełnie nową konfigurację lub skopiować niektóre ustawienia konfiguracji z istniejącego środowiska.</span><span class="sxs-lookup"><span data-stu-id="9e827-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

> [!NOTE]
> <span data-ttu-id="9e827-117">Organizacje mogą utworzyć *dwa* środowiska dla każdej licencji usługi Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9e827-117">Organizations can create *two* environments for every Customer Insights license.</span></span> <span data-ttu-id="9e827-118">Jeśli organizacja kupuje więcej niż jedną licencję, [skontaktuj się z zespołem pomocy technicznej](https://go.microsoft.com/fwlink/?linkid=2079641) w celu zwiększenia liczby dostępnych środowisk.</span><span class="sxs-lookup"><span data-stu-id="9e827-118">If your organization purchases more than once license, please [contact our support team](https://go.microsoft.com/fwlink/?linkid=2079641) to increase the number of available environments.</span></span> <span data-ttu-id="9e827-119">Aby uzyskać więcej informacji dotyczących pojemności i wydajności dodatku, pobierz [Przewodnik licencjonowania usługi Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).</span><span class="sxs-lookup"><span data-stu-id="9e827-119">For more information about capacity and add-on capacity, download [Dynamics 365 licensing guide](https://go.microsoft.com/fwlink/?LinkId=866544).</span></span>

<span data-ttu-id="9e827-120">Aby utworzyć nowe środowisko:</span><span class="sxs-lookup"><span data-stu-id="9e827-120">To create an environment:</span></span>

1. <span data-ttu-id="9e827-121">Wybierz selektor **Środowiska** w nagłówku aplikacji.</span><span class="sxs-lookup"><span data-stu-id="9e827-121">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="9e827-122">Wybierz **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="9e827-122">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9e827-123">![Ustawienia środowiska](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="9e827-123">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="9e827-124">W oknie dialogowym **Tworzenie nowego środowiska** wybierz **Nowe środowisko**.</span><span class="sxs-lookup"><span data-stu-id="9e827-124">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="9e827-125">Jeśli chcesz [kopiować dane z bieżącego środowiska](#considerations-for-copy-configuration-preview), wybierz **Kopiowanie z istniejącego środowiska**.</span><span class="sxs-lookup"><span data-stu-id="9e827-125">If you want to [copy data from the current environment](#considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="9e827-126">Zobaczysz listę wszystkich dostępnych środowisk w organizacji, z których można kopiować dane.</span><span class="sxs-lookup"><span data-stu-id="9e827-126">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="9e827-127">Podaj następujące szczegóły:</span><span class="sxs-lookup"><span data-stu-id="9e827-127">Provide the following details:</span></span>
   - <span data-ttu-id="9e827-128">**Nazwa**: Nazwa tego środowiska.</span><span class="sxs-lookup"><span data-stu-id="9e827-128">**Name**: The name for this environment.</span></span> <span data-ttu-id="9e827-129">To pole jest już wypełnione, jeśli skopiowano istniejące środowisko, ale można to zmienić.</span><span class="sxs-lookup"><span data-stu-id="9e827-129">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="9e827-130">**Region**: Region, w którym usługa jest wdrażana i hostowana.</span><span class="sxs-lookup"><span data-stu-id="9e827-130">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="9e827-131">**Wpisz**: Wybierz, czy chcesz utworzyć środowisko produkcyjne, czy też piaskownicę.</span><span class="sxs-lookup"><span data-stu-id="9e827-131">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

1. <span data-ttu-id="9e827-132">Opcjonalnie możesz wybrać **Ustawienia zaawansowane**:</span><span class="sxs-lookup"><span data-stu-id="9e827-132">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="9e827-133">**Zapisz wszystkie dane do**: Określa miejsce, w którym mają być przechowywane dane wyjściowe uzyskane na podstawie danych dotyczących klienta.</span><span class="sxs-lookup"><span data-stu-id="9e827-133">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="9e827-134">Dostępne będą dwie opcje: **Magazyn Customer Insights** (usługa Azure Data Lake zarządzana przez zespół Customer Insights) i **Azure Data Lake Storage Gen2** (Twój własny Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="9e827-134">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="9e827-135">Domyślnie jest zaznaczona opcja magazyn Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9e827-135">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9e827-136">Zapisując dane w usłudze Azure Data Lake Storage, zgadzasz się na przenoszenie danych do lokalizacji geograficznej odpowiedniej dla danego konta usługi Azure Storage i przechowywanie ich w tej lokalizacji, która może być inna niż lokalizacja, w której są przechowywane dane w Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9e827-136">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="9e827-137">Więcej informacji znajduje się w centrum zaufania Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9e827-137">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="9e827-138">Obecnie pozyskiwane encje są zawsze przechowywane w data lake obsługiwanym przez Customer Insights..</span><span class="sxs-lookup"><span data-stu-id="9e827-138">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="9e827-139">Obsługujemy tylko konta magazynu Azure Data Lake Gen2 z tego samego regionu Azure, który został wybrany podczas tworzenia środowiska.</span><span class="sxs-lookup"><span data-stu-id="9e827-139">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="9e827-140">Obsługujemy tylko konta magazynów włączone przez Hierarchiczny Obszar Nazw (HNS) Azure Data Lake Gen2.</span><span class="sxs-lookup"><span data-stu-id="9e827-140">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="9e827-141">W przypadku opcji Azure Data Lake Storage Gen2 można wybrać między opcją opartą na zasobach a opcją opartą na subskrypcji na potrzeby uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="9e827-141">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="9e827-142">Aby uzyskać więcej informacji, zobacz temat [Połącz analizy odbiorców z kontem Azure Data Lake Storage Gen2 za pomocą głównej usługi platformy Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="9e827-142">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="9e827-143">Nazwa **Kontenera** nie może zostać zmieniona i będzie mieć wartość „customerinsights”.</span><span class="sxs-lookup"><span data-stu-id="9e827-143">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="9e827-144">Jeśli chcesz używać [przewidywań](predictions.md), skonfiguruj udostępnianie danych w aplikacjach i rozwiązaniach na podstawie funkcji Microsoft Dataverse lub włącz pozyskiwanie danych z lokalnych źródeł danych, podaj adres URL środowiska Microsoft Dataverse w obszarze **Konfigurowanie udostępniania danych funkcji Microsoft Dataverse i włączanie dodatkowych funkcji**.</span><span class="sxs-lookup"><span data-stu-id="9e827-144">If you want to use [predictions](predictions.md), configure data sharing with applications and solutions based on Microsoft Dataverse, or enable data ingestion from on-premises data sources, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="9e827-145">Wybierz opcję **Włącz udostępnianie danych**, aby udostępnić dane wyjściowe usługi Customer Insights daneom wyjściowym z zarządzanego Data Lake Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="9e827-145">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="9e827-146">Udostępnianie danych za pomocą usługi Microsoft Dataverse Zarządzanego Data Lake nie jest obecnie obsługiwane w przypadku zapisywania wszystkich danych we własnym Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="9e827-146">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="9e827-147">[Przewidywanie brakujących wartości w encji](predictions.md) nie są obecnie obsługiwane, jeśli w przypadku włączenia udostępniania danych w Microsoft Dataverse zarządzane są Data Lake.</span><span class="sxs-lookup"><span data-stu-id="9e827-147">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="9e827-148">![Opcje konfiguracji umożliwiające udostępnianie danych z Microsoft Dataverse](media/datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="9e827-148">![Configuration options to enable data sharing with Microsoft Dataverse](media/datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="9e827-149">Podczas uruchamiania procesów, takich jak pozyskiwanie danych lub tworzenie segmentów, odpowiednie foldery zostaną utworzone na koncie magazynu określonym powyżej.</span><span class="sxs-lookup"><span data-stu-id="9e827-149">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="9e827-150">Pliki danych i pliki model.json zostaną utworzone i dodane do odpowiednich podfolderów na podstawie uruchamianego procesu.</span><span class="sxs-lookup"><span data-stu-id="9e827-150">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="9e827-151">Jeśli utworzysz wiele środowisk Customer Insights i zdecydujesz się zapisać encje wyjściowe z tych środowisk na koncie magazynu, dla każdego środowiska zostaną utworzone osobne foldery z ci_<environmentid> w kontenerze.</span><span class="sxs-lookup"><span data-stu-id="9e827-151">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="considerations-for-copy-configuration-preview"></a><span data-ttu-id="9e827-152">Rozważania dotyczące konfiguracji kopiowania (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="9e827-152">Considerations for copy configuration (preview)</span></span>

<span data-ttu-id="9e827-153">Kopiowane są następujące ustawienia konfiguracji:</span><span class="sxs-lookup"><span data-stu-id="9e827-153">The following configuration settings are copied:</span></span>

- <span data-ttu-id="9e827-154">Konfiguracja funkcji</span><span class="sxs-lookup"><span data-stu-id="9e827-154">Feature configurations</span></span>
- <span data-ttu-id="9e827-155">Importowanie/importowanie źródeł danych</span><span class="sxs-lookup"><span data-stu-id="9e827-155">Ingested/imported data sources</span></span>
- <span data-ttu-id="9e827-156">Konfiguracja ujednolicania danych (mapowanie, dopasowywanie, scalanie)</span><span class="sxs-lookup"><span data-stu-id="9e827-156">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="9e827-157">Segmenty</span><span class="sxs-lookup"><span data-stu-id="9e827-157">Segments</span></span>
- <span data-ttu-id="9e827-158">Miary</span><span class="sxs-lookup"><span data-stu-id="9e827-158">Measures</span></span>
- <span data-ttu-id="9e827-159">Relacje</span><span class="sxs-lookup"><span data-stu-id="9e827-159">Relationships</span></span>
- <span data-ttu-id="9e827-160">Działania</span><span class="sxs-lookup"><span data-stu-id="9e827-160">Activities</span></span>
- <span data-ttu-id="9e827-161">Wyszukiwanie i indeks filtrów</span><span class="sxs-lookup"><span data-stu-id="9e827-161">Search & filter Index</span></span>
- <span data-ttu-id="9e827-162">Lokalizacje docelowe eksportu</span><span class="sxs-lookup"><span data-stu-id="9e827-162">Export destinations</span></span>
- <span data-ttu-id="9e827-163">Zaplanowane odświeżanie</span><span class="sxs-lookup"><span data-stu-id="9e827-163">Scheduled refresh</span></span>
- <span data-ttu-id="9e827-164">Wzbogacenia</span><span class="sxs-lookup"><span data-stu-id="9e827-164">Enrichments</span></span>
- <span data-ttu-id="9e827-165">Zarządzanie modelem</span><span class="sxs-lookup"><span data-stu-id="9e827-165">Model management</span></span>
- <span data-ttu-id="9e827-166">Przypisania ról</span><span class="sxs-lookup"><span data-stu-id="9e827-166">Role assignments</span></span>

<span data-ttu-id="9e827-167">Poniższe ustawienia *nie są* kopiowane:</span><span class="sxs-lookup"><span data-stu-id="9e827-167">The following settings are *not* copied:</span></span>

- <span data-ttu-id="9e827-168">Profile klientów.</span><span class="sxs-lookup"><span data-stu-id="9e827-168">Customer profiles.</span></span>
- <span data-ttu-id="9e827-169">Poświadczenia źródła danych.</span><span class="sxs-lookup"><span data-stu-id="9e827-169">Data source credentials.</span></span> <span data-ttu-id="9e827-170">Konieczne będzie podanie poświadczeń dla każdego źródła danych i ręczne odświeżenie źródeł danych.</span><span class="sxs-lookup"><span data-stu-id="9e827-170">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="9e827-171">Źródła danych z folderu Common Data Model i zarządzanego repozytorium danych typu lake Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="9e827-171">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="9e827-172">Konieczne będzie ręczne utworzenie tych źródeł danych pod tą samą nazwą jak w środowisku źródłowym.</span><span class="sxs-lookup"><span data-stu-id="9e827-172">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="9e827-173">Podczas kopiowania środowiska zostanie wyświetlony komunikat z potwierdzeniem, że utworzono nowe środowisko.</span><span class="sxs-lookup"><span data-stu-id="9e827-173">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="9e827-174">Wybierz **Przejdź do źródeł danych**, aby wyświetlić listę źródeł danych.</span><span class="sxs-lookup"><span data-stu-id="9e827-174">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="9e827-175">Wszystkie źródła danych ukażą stan **Wymagane poświadczenia**.</span><span class="sxs-lookup"><span data-stu-id="9e827-175">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="9e827-176">Dokonaj edycji źródeł danych i wprowadź poświadczenia, aby je odświeżyć.</span><span class="sxs-lookup"><span data-stu-id="9e827-176">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9e827-177">![Skopiowane źródła danych](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="9e827-177">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="9e827-178">Po odświeżeniu źródeł danych przejdź do **Dane** > **Ujednolicanie**.</span><span class="sxs-lookup"><span data-stu-id="9e827-178">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="9e827-179">W tym miejscu można znaleźć ustawienia z poziomu środowiska źródłowego.</span><span class="sxs-lookup"><span data-stu-id="9e827-179">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="9e827-180">Edytuj je zgodnie z wymaganiami lub wybierz **Uruchom**, aby rozpocząć proces ujednolicania danych i utworzyć zunifikowaną encję klienta.</span><span class="sxs-lookup"><span data-stu-id="9e827-180">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="9e827-181">Po zakończeniu ujednolicania danych należy przejść do **Miary** i **Segmenty**, aby je również odświeżyć.</span><span class="sxs-lookup"><span data-stu-id="9e827-181">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="9e827-182">Edytuj istniejące środowisko</span><span class="sxs-lookup"><span data-stu-id="9e827-182">Edit an existing environment</span></span>

<span data-ttu-id="9e827-183">Użytkownik może edytować niektóre szczegóły istniejących środowisk.</span><span class="sxs-lookup"><span data-stu-id="9e827-183">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="9e827-184">Wybierz selektor **Środowiska** w nagłówku aplikacji.</span><span class="sxs-lookup"><span data-stu-id="9e827-184">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="9e827-185">Wybierz ikonę **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="9e827-185">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="9e827-186">W polu **Edytuj środowisko** można zaktualizować pole **Wyświetlana nazwa**, ale nie można zmienić **Regionu** lub **Typu**.</span><span class="sxs-lookup"><span data-stu-id="9e827-186">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="9e827-187">Jeśli środowisko jest skonfigurowane do przechowywania danych w Azure Data Lake Storage Gen2, można zaktualizować **Klucz konta**.</span><span class="sxs-lookup"><span data-stu-id="9e827-187">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="9e827-188">Nie można jednak zmienić **Nazwy konta** lub nazwy **Kontener**.</span><span class="sxs-lookup"><span data-stu-id="9e827-188">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="9e827-189">Opcjonalnie można zaktualizować połączenie oparte na kluczu konta do połączenia opartego na zasobach lub subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="9e827-189">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="9e827-190">Po uaktualnieniu nie można powrócić do klucza konta po aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="9e827-190">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="9e827-191">Aby uzyskać więcej informacji, zobacz temat [Połącz analizy odbiorców z kontem Azure Data Lake Storage Gen2 za pomocą głównej usługi platformy Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="9e827-191">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="9e827-192">Podczas aktualizowania połączenia nie można zmieniać informacji o **Kontenerze**.</span><span class="sxs-lookup"><span data-stu-id="9e827-192">You can't change **Container** information when updating the connection.</span></span>

6. <span data-ttu-id="9e827-193">Opcjonalnie można podać adres URL środowiska Microsoft Dataverse w obszarze **Konfigurowanie udostępniania danych funkcji Microsoft Dataverse i włączanie dodatkowych możliwości**.</span><span class="sxs-lookup"><span data-stu-id="9e827-193">Optionally, you can provide a Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="9e827-194">Funkcje te zawierają udostępnianie danych aplikacjom i rozwiązań opartych na Microsoft Dataverse, pozyskiwanie danych z lokalnych źródeł danych lub używanie [przewidywać](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="9e827-194">These capabilities inlcude data sharing with applications and solutions based on Microsoft Dataverse, data ingestion from on-premises data sources, or the use [predictions](predictions.md).</span></span> <span data-ttu-id="9e827-195">Wybierz opcję **Włącz udostępnianie danych**, aby udostępnić dane wyjściowe usługi Customer Insights daneom wyjściowym z zarządzanego Data Lake Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="9e827-195">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data lake.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="9e827-196">Udostępnianie danych za pomocą usługi Microsoft Dataverse Zarządzanego Data Lake nie jest obecnie obsługiwane w przypadku zapisywania wszystkich danych we własnym Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="9e827-196">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
   > - <span data-ttu-id="9e827-197">[Przewidywanie brakujących wartości w encji](predictions.md) nie jest obecnie obsługiwane, jeśli włączone zostało udostępnianie danych zarządzanemu Data Lake Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="9e827-197">[Prediction of missing values in an entity](predictions.md) is currently not supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

   <span data-ttu-id="9e827-198">Po włączeniu udostępniania danych funkcji Microsoft Dataverse zostanie wyzwolone pełne odświeżanie źródeł danych i innych procesów.</span><span class="sxs-lookup"><span data-stu-id="9e827-198">Once you enable data sharing with Microsoft Dataverse, a full refresh of your data sources and other processes will be triggered.</span></span> <span data-ttu-id="9e827-199">Jeśli procesy są obecnie uruchomione i są w kolejce, nie będzie dostępna opcja włączenia udostępniania danych funkcji Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="9e827-199">If processes are currently running and queued, you will not see the option to enable data sharing with Microsoft Dataverse.</span></span> <span data-ttu-id="9e827-200">Można poczekać na zakończenie tych procesów lub je anulować, aby włączyć udostępnianie danych.</span><span class="sxs-lookup"><span data-stu-id="9e827-200">You can wait for those processes to complete or cancel them to enable data sharing.</span></span> 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Opcje konfiguracji umożliwiające udostępnianie danych funkcji Microsoft Dataverse.":::
   
   <span data-ttu-id="9e827-202">Podczas uruchamiania procesów, takich jak pozyskiwanie danych lub tworzenie segmentów, odpowiednie foldery zostaną utworzone na koncie magazynu określonym powyżej.</span><span class="sxs-lookup"><span data-stu-id="9e827-202">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="9e827-203">W zależności od uruchomionego procesu pliki danych i pliki model.json zostaną utworzone i dodane do odpowiednich podfolderów.</span><span class="sxs-lookup"><span data-stu-id="9e827-203">Data files and model.json files will be created and added to the respective subfolders, depending on the process you run.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="9e827-204">Zresetuj istniejące środowisko</span><span class="sxs-lookup"><span data-stu-id="9e827-204">Reset an existing environment</span></span>

<span data-ttu-id="9e827-205">Jako administrator jeśli chcesz usunąć wszystkie konfiguracje i przetworzone dane, możesz zresetować środowisko do stanu pustego.</span><span class="sxs-lookup"><span data-stu-id="9e827-205">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="9e827-206">Wybierz selektor **Środowiska** w nagłówku aplikacji.</span><span class="sxs-lookup"><span data-stu-id="9e827-206">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="9e827-207">Wybierz środowisko, które chcesz zresetować, i wybierz wielokropek **...**.</span><span class="sxs-lookup"><span data-stu-id="9e827-207">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="9e827-208">Wybierz opcję **Reset**.</span><span class="sxs-lookup"><span data-stu-id="9e827-208">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="9e827-209">Aby potwierdzić usunięcie, wprowadź nazwę środowiska i wybierz pozycję **Zresetuj**.</span><span class="sxs-lookup"><span data-stu-id="9e827-209">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="9e827-210">Usuwanie istniejącego środowiska (dostępnego tylko dla administratorów)</span><span class="sxs-lookup"><span data-stu-id="9e827-210">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="9e827-211">Jako Administrator użytkownik możesz usunąć administrowane środowisko.</span><span class="sxs-lookup"><span data-stu-id="9e827-211">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="9e827-212">Wybierz selektor **Środowiska** w nagłówku aplikacji.</span><span class="sxs-lookup"><span data-stu-id="9e827-212">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="9e827-213">Wybierz środowisko, które chcesz zresetować, i wybierz wielokropek **...**.</span><span class="sxs-lookup"><span data-stu-id="9e827-213">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="9e827-214">Wybierz opcję **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="9e827-214">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="9e827-215">Aby potwierdzić usunięcie, wprowadź nazwę środowiska i wybierz **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="9e827-215">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
