---
title: Utwórz środowisko i zarządzaj nim.
description: Dowiedz się, jak zapisać się w usłudze i zarządzać środowiskami.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644146"
---
# <a name="manage-environments"></a><span data-ttu-id="8d1aa-103">Zarządzaj środowiskami</span><span class="sxs-lookup"><span data-stu-id="8d1aa-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="8d1aa-104">W tym artykule wyjaśniono, jak utworzyć nową organizację i zastrzec bezpieczeństwo środowiska.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="8d1aa-105">Tworzenie konta i organizacja</span><span class="sxs-lookup"><span data-stu-id="8d1aa-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="8d1aa-106">Przejdź do witryny internetowej [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="8d1aa-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="8d1aa-107">Wybierz **Rozpocznij**.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="8d1aa-108">Wybierz preferowany scenariusz zapisywania i wybierz odpowiednie łącze.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="8d1aa-109">Zaakceptuj warunki, a następnie wybierz **Dalej**, aby rozpocząć tworzenie organizacji.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="8d1aa-110">Po utworzeniu środowiska nastąpi przekierowanie do [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="8d1aa-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="8d1aa-111">Użyj środowiska pokazowego, aby eksplorować aplikację, lub utwórz nowe środowisko, wykonując kroki opisane w następnej sekcji.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="8d1aa-112">Po określeniu ustawień środowiska wybierz **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="8d1aa-113">Po pomyślnym utworzeniu środowiska użytkownik zostanie zalogowany.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="8d1aa-114">Tworzenie środowiska w istniejącej organizacji</span><span class="sxs-lookup"><span data-stu-id="8d1aa-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="8d1aa-115">Istnieją dwa sposoby utworzenia nowego środowiska.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="8d1aa-116">Można określić zupełnie nową konfigurację lub skopiować niektóre ustawienia konfiguracji z istniejącego środowiska.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="8d1aa-117">Aby utworzyć nowe środowisko:</span><span class="sxs-lookup"><span data-stu-id="8d1aa-117">To create an environment:</span></span>

1. <span data-ttu-id="8d1aa-118">Wybierz symbol **Ustawienia** w nagłówku aplikacji.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-118">Select the **Settings** symbol in the header of the app.</span></span>

1. <span data-ttu-id="8d1aa-119">Wybierz **Nowe środowisko**.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-119">Select **New environment**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8d1aa-120">![Ustawienia środowiska](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="8d1aa-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="8d1aa-121">W oknie dialogowym **Tworzenie nowego środowiska** wybierz **Nowe środowisko**.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="8d1aa-122">Jeśli chcesz [kopiować dane z bieżącego środowiska](#additional-considerations-for-copy-configuration-preview), wybierz **Kopiowanie z istniejącego środowiska**.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="8d1aa-123">Zobaczysz listę wszystkich dostępnych środowisk w organizacji, z których można kopiować dane.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="8d1aa-124">Podaj następujące szczegóły:</span><span class="sxs-lookup"><span data-stu-id="8d1aa-124">Provide the following details:</span></span>
   - <span data-ttu-id="8d1aa-125">**Nazwa**: Nazwa tego środowiska.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="8d1aa-126">To pole jest już wypełnione, jeśli skopiowano istniejące środowisko, ale można to zmienić.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="8d1aa-127">**Region**: Region, w którym usługa jest wdrażana i hostowana.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="8d1aa-128">**Wpisz**: Wybierz, czy chcesz utworzyć środowisko produkcyjne, czy też piaskownicę.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="8d1aa-129">Opcjonalnie możesz wybrać **Ustawienia zaawansowane**:</span><span class="sxs-lookup"><span data-stu-id="8d1aa-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="8d1aa-130">**Zapisz wszystkie dane do**: Określa miejsce, w którym mają być przechowywane dane wyjściowe uzyskane na podstawie danych dotyczących klienta.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="8d1aa-131">Dostępne będą dwie opcje: **Magazyn Customer Insights** (usługa Azure Data Lake zarządzana przez zespół Customer Insights) i **Azure Data Lake Storage Gen2** (Twój własny Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="8d1aa-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="8d1aa-132">Domyślnie jest zaznaczona opcja magazyn Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8d1aa-133">Zapisując dane w usłudze Azure Data Lake Storage, zgadzasz się na przenoszenie danych do lokalizacji geograficznej odpowiedniej dla danego konta usługi Azure Storage i przechowywanie ich w tej lokalizacji, która może być inna niż lokalizacja, w której są przechowywane dane w Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="8d1aa-134">Więcej informacji znajduje się w centrum zaufania Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="8d1aa-135">Obecnie pozyskiwane encje są zawsze przechowywane w data lake obsługiwanym przez Customer Insights..</span><span class="sxs-lookup"><span data-stu-id="8d1aa-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="8d1aa-136">Obsługujemy tylko konta magazynu Azure Data Lake Gen2 z tego samego regionu Azure, który został wybrany podczas tworzenia środowiska.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="8d1aa-137">Obsługujemy tylko konta magazynów włączone przez Hierarchiczny Obszar Nazw (HNS) Azure Data Lake Gen2.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="8d1aa-138">W przypadku opcji Azure Data Lake Storage Gen2 można wybrać między opcją opartą na zasobach a opcją opartą na subskrypcji na potrzeby uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="8d1aa-139">Aby uzyskać więcej informacji, zobacz temat [Połącz analizy odbiorców z kontem Azure Data Lake Storage Gen2 za pomocą głównej usługi platformy Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="8d1aa-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="8d1aa-140">Nazwa **Kontenera** nie może zostać zmieniona i będzie mieć wartość „customerinsights”.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="8d1aa-141">Aby użyć [przewidywania](predictions.md), wprowadź adres URL wystąpienia Common Data Service w polu **Adres serwera** w obszarze **Korzystanie z przewidywania**.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-141">If you want to use [predictions](predictions.md), enter the Common Data Service instance URL in the **Server address** field under **Use predictions**.</span></span>

   <span data-ttu-id="8d1aa-142">Podczas uruchamiania procesów, takich jak pozyskiwanie danych lub tworzenie segmentów, odpowiednie foldery zostaną utworzone na koncie magazynu określonym powyżej.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-142">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="8d1aa-143">Pliki danych i pliki model.json zostaną utworzone i dodane do odpowiednich podfolderów na podstawie uruchamianego procesu.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-143">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="8d1aa-144">Jeśli utworzysz wiele środowisk Customer Insights i zdecydujesz się zapisać encje wyjściowe z tych środowisk na koncie magazynu, dla każdego środowiska zostaną utworzone osobne foldery z ci_<environmentid> w kontenerze.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-144">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="8d1aa-145">Uwagi dodatkowe dotyczące konfiguracji kopiowania (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="8d1aa-145">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="8d1aa-146">Kopiowane są następujące ustawienia konfiguracji:</span><span class="sxs-lookup"><span data-stu-id="8d1aa-146">The following configuration settings are copied:</span></span>

- <span data-ttu-id="8d1aa-147">Konfiguracja funkcji</span><span class="sxs-lookup"><span data-stu-id="8d1aa-147">Feature configurations</span></span>
- <span data-ttu-id="8d1aa-148">Pobrane/zaimportowane źródła danych</span><span class="sxs-lookup"><span data-stu-id="8d1aa-148">Inegsted/imported data sources</span></span>
- <span data-ttu-id="8d1aa-149">Konfiguracja ujednolicania danych (mapowanie, dopasowywanie, scalanie)</span><span class="sxs-lookup"><span data-stu-id="8d1aa-149">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="8d1aa-150">Segmenty</span><span class="sxs-lookup"><span data-stu-id="8d1aa-150">Segments</span></span>
- <span data-ttu-id="8d1aa-151">Miary</span><span class="sxs-lookup"><span data-stu-id="8d1aa-151">Measures</span></span>
- <span data-ttu-id="8d1aa-152">Relacje</span><span class="sxs-lookup"><span data-stu-id="8d1aa-152">Relationships</span></span>
- <span data-ttu-id="8d1aa-153">Działania</span><span class="sxs-lookup"><span data-stu-id="8d1aa-153">Activities</span></span>
- <span data-ttu-id="8d1aa-154">Wyszukiwanie i indeks filtrów</span><span class="sxs-lookup"><span data-stu-id="8d1aa-154">Search & filter Index</span></span>
- <span data-ttu-id="8d1aa-155">Lokalizacje docelowe eksportu</span><span class="sxs-lookup"><span data-stu-id="8d1aa-155">Export destinations</span></span>
- <span data-ttu-id="8d1aa-156">Zaplanowane odświeżanie</span><span class="sxs-lookup"><span data-stu-id="8d1aa-156">Scheduled refresh</span></span>
- <span data-ttu-id="8d1aa-157">Wzbogacenia</span><span class="sxs-lookup"><span data-stu-id="8d1aa-157">Enrichments</span></span>
- <span data-ttu-id="8d1aa-158">Zarządzanie modelem</span><span class="sxs-lookup"><span data-stu-id="8d1aa-158">Model management</span></span>
- <span data-ttu-id="8d1aa-159">Przypisania ról</span><span class="sxs-lookup"><span data-stu-id="8d1aa-159">Role assignments</span></span>

<span data-ttu-id="8d1aa-160">Poniższe ustawienia *nie są* kopiowane:</span><span class="sxs-lookup"><span data-stu-id="8d1aa-160">The following settings are *not* copied:</span></span>

- <span data-ttu-id="8d1aa-161">Profile klientów.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-161">Customer profiles.</span></span>
- <span data-ttu-id="8d1aa-162">Poświadczenia źródła danych.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-162">Data source credentials.</span></span> <span data-ttu-id="8d1aa-163">Konieczne będzie podanie poświadczeń dla każdego źródła danych i ręczne odświeżenie źródeł danych.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-163">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="8d1aa-164">Źródła danych z folderu Common Data Model i zarządzanego repozytorium danych typu lake Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-164">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="8d1aa-165">Konieczne będzie ręczne utworzenie tych źródeł danych pod tą samą nazwą jak w środowisku źródłowym.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-165">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="8d1aa-166">Podczas kopiowania środowiska zostanie wyświetlony komunikat z potwierdzeniem, że utworzono nowe środowisko.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-166">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="8d1aa-167">Wybierz **Przejdź do źródeł danych**, aby wyświetlić listę źródeł danych.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-167">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="8d1aa-168">Wszystkie źródła danych ukażą stan **Wymagane poświadczenia**.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-168">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="8d1aa-169">Dokonaj edycji źródeł danych i wprowadź poświadczenia, aby je odświeżyć.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-169">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8d1aa-170">![Skopiowane źródła danych](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="8d1aa-170">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="8d1aa-171">Po odświeżeniu źródeł danych przejdź do **Dane** > **Ujednolicanie**.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-171">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="8d1aa-172">W tym miejscu można znaleźć ustawienia z poziomu środowiska źródłowego.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-172">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="8d1aa-173">Edytuj je zgodnie z wymaganiami lub wybierz **Uruchom**, aby rozpocząć proces ujednolicania danych i utworzyć zunifikowaną encję klienta.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-173">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="8d1aa-174">Po zakończeniu ujednolicania danych należy przejść do **Miary** i **Segmenty**, aby je również odświeżyć.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-174">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="8d1aa-175">Edytuj istniejące środowisko</span><span class="sxs-lookup"><span data-stu-id="8d1aa-175">Edit an existing environment</span></span>

<span data-ttu-id="8d1aa-176">Użytkownik może edytować niektóre szczegóły istniejących środowisk.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-176">You can edit some of the details of existing environments.</span></span>

1. <span data-ttu-id="8d1aa-177">Przejdź do **Administracja** > **System** > **Informacje**.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-177">Go to **Admin** > **System** > **About**.</span></span>

2. <span data-ttu-id="8d1aa-178">Zaznacz **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-178">Select **Edit**.</span></span>

3. <span data-ttu-id="8d1aa-179">Użytkownik może aktualizować **Wyświetlaną nazwę** środowiska, ale nie może zmienić **Regionu** ani **Typu**.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-179">You can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="8d1aa-180">Jeśli środowisko jest skonfigurowane do przechowywania danych w Azure Data Lake Storage Gen2, można zaktualizować **Klucz konta**.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-180">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="8d1aa-181">Nie można jednak zmienić **Nazwy konta** lub nazwy **Kontener**.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-181">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="8d1aa-182">Opcjonalnie można zaktualizować połączenie oparte na kluczu konta do połączenia opartego na zasobach lub subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-182">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="8d1aa-183">Po uaktualnieniu nie można powrócić do klucza konta po aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-183">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="8d1aa-184">Aby uzyskać więcej informacji, zobacz temat [Połącz analizy odbiorców z kontem Azure Data Lake Storage Gen2 za pomocą głównej usługi platformy Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="8d1aa-184">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="8d1aa-185">Podczas aktualizowania połączenia nie można zmieniać informacji o **Kontenerze**.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-185">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="8d1aa-186">Zresetuj istniejące środowisko</span><span class="sxs-lookup"><span data-stu-id="8d1aa-186">Reset an existing environment</span></span>

<span data-ttu-id="8d1aa-187">Jeśli chcesz usunąć wszystkie konfiguracje i przetworzone dane, możesz zresetować środowisko do stanu pustego.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-187">You can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="8d1aa-188">Przejdź do **Administracja** > **System** > **Informacje**.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-188">Go to **Admin** > **System** > **About**.</span></span>

2.  <span data-ttu-id="8d1aa-189">Wybierz **Resetuj**.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-189">Select **Reset**.</span></span> 

3.  <span data-ttu-id="8d1aa-190">Aby potwierdzić usunięcie, wprowadź nazwę środowiska i wybierz pozycję **Zresetuj**.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-190">To confirm the deletion, enter the environment name and select **Reset**.</span></span>


## <a name="delete-an-existing-environment"></a><span data-ttu-id="8d1aa-191">Usuń istniejące środowisko</span><span class="sxs-lookup"><span data-stu-id="8d1aa-191">Delete an existing environment</span></span>

1. <span data-ttu-id="8d1aa-192">Przejdź do **Administracja** > **System** > **Informacje**.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-192">Go to **Admin** > **System** > **About**.</span></span>

1. <span data-ttu-id="8d1aa-193">Wybierz **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-193">Select **Delete**.</span></span>

1. <span data-ttu-id="8d1aa-194">Aby potwierdzić usunięcie, wprowadź nazwę środowiska i wybierz **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="8d1aa-194">To confirm the deletion, enter the environment name and select **Delete**.</span></span>
