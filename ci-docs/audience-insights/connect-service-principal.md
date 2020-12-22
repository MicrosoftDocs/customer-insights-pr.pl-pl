---
title: Połącz się z kontem Azure Data Lake Storage Gen2 przy użyciu nazwy głównej usługi
description: Użyj głównej usługi Azure, aby uzyskać szczegółowe informacje o odbiorcach, aby połączyć się z własnym data lake podczas dołączania go do szczegółowych informacji o odbiorcach.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644101"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="13b4b-103">Połącz analizy odbiorców z kontem Azure Data Lake Storage Gen2 za pomocą głównej usługi platformy Azure</span><span class="sxs-lookup"><span data-stu-id="13b4b-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="13b4b-104">Zautomatyzowane narzędzia korzystające z usług platformy Azure powinny zawsze mieć ograniczone uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="13b4b-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="13b4b-105">Zamiast logowania się do aplikacji jako w pełni uprzywilejowany użytkownik, platforma Azure oferuje nazwy głównej usługi.</span><span class="sxs-lookup"><span data-stu-id="13b4b-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="13b4b-106">Czytaj dalej, aby dowiedzieć się, jak połączyć szczegółowe informacje o odbiorcach z kontem Azure Data Lake Storage Gen2 przy użyciu nazwy głównej usługi usługi platformy Azure zamiast kluczy konta magazynu.</span><span class="sxs-lookup"><span data-stu-id="13b4b-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="13b4b-107">Możesz użyć nazwy głównej usługi, aby bezpiecznie [dodać lub edytować folder Common Data Model](connect-common-data-model.md) jako źródło danych lub [utworzyć nowe lub zaktualizować istniejące środowisko](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="13b4b-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

<span data-ttu-id="13b4b-108">Aby utworzyć nazwę główną usługi, trzeba mieć uprawnienia administratora w ramach Twojej subskrypcji platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="13b4b-108">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="13b4b-109">Utwórz nazwę głównej usługi Azure do analiz odbiorców</span><span class="sxs-lookup"><span data-stu-id="13b4b-109">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="13b4b-110">Przed utworzeniem nowej nazwy głównej usługi na potrzeby statystyk odbiorców sprawdź, czy już istnieje w Twojej organizacji.</span><span class="sxs-lookup"><span data-stu-id="13b4b-110">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="13b4b-111">Poszukaj istniejącej nazwy głownej usługi</span><span class="sxs-lookup"><span data-stu-id="13b4b-111">Look for an existing service principal</span></span>

1. <span data-ttu-id="13b4b-112">W tym celu należy przejść do [portalu administracyjnego Azure](https://portal.azure.com) i zalogować się do organizacji.</span><span class="sxs-lookup"><span data-stu-id="13b4b-112">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="13b4b-113">Wybierz **Azure Active Directory** z usług Azure.</span><span class="sxs-lookup"><span data-stu-id="13b4b-113">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="13b4b-114">W obszarze **Zarządzanie** wybierz pozycję **Aplikacje korporacyjne**.</span><span class="sxs-lookup"><span data-stu-id="13b4b-114">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="13b4b-115">Wyszukaj własny identyfikator aplikacji analizy odbiorców `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` lub nazwę `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="13b4b-115">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="13b4b-116">Jeśli znajdziesz pasujący rekord, oznacza to, że istnieje jednostka usługi dla szczegółowych informacji o odbiorcach.</span><span class="sxs-lookup"><span data-stu-id="13b4b-116">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="13b4b-117">Nie musisz go ponownie tworzyć.</span><span class="sxs-lookup"><span data-stu-id="13b4b-117">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Zrzut ekranu pokazujący istniejącą nazwę główną usługi.":::
   
6. <span data-ttu-id="13b4b-119">Jeśli nie są zwracane żadne wyniki, utwórz nową nazwę główną.</span><span class="sxs-lookup"><span data-stu-id="13b4b-119">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="13b4b-120">Utwórz nową nazwę główną usługi</span><span class="sxs-lookup"><span data-stu-id="13b4b-120">Create a new service principal</span></span>

1. <span data-ttu-id="13b4b-121">Zainstaluj najnowszą wersję **Azure Active Directory PowerShell for Graph**.</span><span class="sxs-lookup"><span data-stu-id="13b4b-121">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="13b4b-122">Aby uzyskać więcej informacji, zobacz temat [Instalowanie Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="13b4b-122">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="13b4b-123">Na komputerze wybierz klawisz Windows na klawiaturze i wyszukaj **Windows PowerShell** i **Uruchom jako administrator**.</span><span class="sxs-lookup"><span data-stu-id="13b4b-123">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="13b4b-124">W wyświetlonym oknie PowerShell wprowadź polecenie `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="13b4b-124">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="13b4b-125">Utwórz nazwę główną usługi dla analizy odbiorców z modułem Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="13b4b-125">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="13b4b-126">W oknie PowerShell wprowadź polecenie `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="13b4b-126">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="13b4b-127">Zastąp „identyfikator dzierżawy” rzeczywisty identyfikator dzierżawy, w której chcesz utworzyć jednostkę usługi.</span><span class="sxs-lookup"><span data-stu-id="13b4b-127">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="13b4b-128">Parametr nazwy środowiska `AzureEnvironmentName` jest opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="13b4b-128">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="13b4b-129">Wprowadź `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="13b4b-129">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="13b4b-130">To polecenie tworzy nazwę główną usługi dla analiz odbiorcy w wybranej dzierżawie.</span><span class="sxs-lookup"><span data-stu-id="13b4b-130">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="13b4b-131">Udziel uprawnień do nazwy głównej usługi, aby uzyskać dostęp do konta magazynu</span><span class="sxs-lookup"><span data-stu-id="13b4b-131">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="13b4b-132">Przejdź do obszaru Azure portal, aby przyznać uprawnienia do nazwy głównej usługi dla konta magazynu, którego chcesz użyć w analizach odbiorców.</span><span class="sxs-lookup"><span data-stu-id="13b4b-132">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="13b4b-133">W tym celu należy przejść do [portalu administracyjnego Azure](https://portal.azure.com) i zalogować się do organizacji.</span><span class="sxs-lookup"><span data-stu-id="13b4b-133">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="13b4b-134">Otwórz konto magazynu, do którego chcesz, aby nazwa główna usługi miała dostęp do szczegółowych informacji o odbiorcach.</span><span class="sxs-lookup"><span data-stu-id="13b4b-134">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="13b4b-135">Wybierz pozycję **Kontrola dostępu (IAM)** z okienka nawigacji i wybierz pozycję **Dodaj** > **Dodaj przypisanie roli**.</span><span class="sxs-lookup"><span data-stu-id="13b4b-135">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Zrzut ekranu pokazujący Portal Azure podczas dodawania przypisania roli.":::
   
1. <span data-ttu-id="13b4b-137">W okienku **Dodawanie przypisania roli** ustaw następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="13b4b-137">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="13b4b-138">Rola: *Współautor danych w usłudze Blob Storage*</span><span class="sxs-lookup"><span data-stu-id="13b4b-138">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="13b4b-139">Przypisz dostęp do: *Użytkownik, grupa lub nazwa główna usługi*</span><span class="sxs-lookup"><span data-stu-id="13b4b-139">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="13b4b-140">Zaznacz: *Dynamics 365 AI for Customer Insights* ([utworzona nazwa główna usługi](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="13b4b-140">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="13b4b-141">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="13b4b-141">Select **Save**.</span></span>

<span data-ttu-id="13b4b-142">Rozpowszechnienie zmian może zająć do 15 minut.</span><span class="sxs-lookup"><span data-stu-id="13b4b-142">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="13b4b-143">Wprowadź identyfikator zasobu platformy Azure lub szczegóły subskrypcji platformy Azure w załączniku konta magazynu do usługi analiz odbiorców.</span><span class="sxs-lookup"><span data-stu-id="13b4b-143">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="13b4b-144">Dołącz konto magazynowe Azure Data Lake w analizach odbiorców do [przechowywania danych wyjściowych](manage-environments.md) lub [używania jako źródła danych](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="13b4b-144">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="13b4b-145">Wybranie opcji Azure Data Lake umożliwia wybranie podejścia opartego na zasobach lub subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="13b4b-145">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="13b4b-146">Wykonaj poniższe czynności, aby podać wymagane informacje na temat wybranego podejścia.</span><span class="sxs-lookup"><span data-stu-id="13b4b-146">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resounce-based-storage-account-connection"></a><span data-ttu-id="13b4b-147">Połączenie z kontem magazynu oparte na zasobach</span><span class="sxs-lookup"><span data-stu-id="13b4b-147">Resounce-based storage account connection</span></span>

1. <span data-ttu-id="13b4b-148">Przejdź do [portalu administrowania Azure](https://portal.azure.com), zaloguj się do subskrypcji i otwórz konto magazynu.</span><span class="sxs-lookup"><span data-stu-id="13b4b-148">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="13b4b-149">Wybierz **Ustawienia** > **Właściwości** w okienku nawigacji.</span><span class="sxs-lookup"><span data-stu-id="13b4b-149">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="13b4b-150">Skopiuj wartość identyfikatora zasobu konta magazynu.</span><span class="sxs-lookup"><span data-stu-id="13b4b-150">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Skopiuj identyfikator zasobu konta magazynu.":::

1. <span data-ttu-id="13b4b-152">W szczegółach dotyczących odbiorców wstaw identyfikator zasobu w polu zasobu wyświetlanym na ekranie połączenia konta magazynu.</span><span class="sxs-lookup"><span data-stu-id="13b4b-152">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Wprowadź informacje o identyfikatorze zasobu konta magazynu.":::   
   
1. <span data-ttu-id="13b4b-154">Kontynuuj pozostałe kroki w szczegółach dotyczących odbiorców, aby dołączyć konto magazynu.</span><span class="sxs-lookup"><span data-stu-id="13b4b-154">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="13b4b-155">Połączenie z kontem magazynu oparte na subskrypcji</span><span class="sxs-lookup"><span data-stu-id="13b4b-155">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="13b4b-156">Przejdź do [portalu administrowania Azure](https://portal.azure.com), zaloguj się do subskrypcji i otwórz konto magazynu.</span><span class="sxs-lookup"><span data-stu-id="13b4b-156">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="13b4b-157">Wybierz **Ustawienia** > **Właściwości** w okienku nawigacji.</span><span class="sxs-lookup"><span data-stu-id="13b4b-157">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="13b4b-158">Przejrzyj **Subskrypcje**, **Grupa zasobów** i **Nazwa** konta magazynu, aby się upewnić, że wybierasz odpowiednie wartości w analizach odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="13b4b-158">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="13b4b-159">W szczegółach dotyczących odbiorców wybierz wartości lub odpowiednie pola podczas dołączania konta magazynu.</span><span class="sxs-lookup"><span data-stu-id="13b4b-159">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Wprowadź informacje o identyfikatorze zasobu konta magazynu.":::
   
1. <span data-ttu-id="13b4b-161">Kontynuuj pozostałe kroki w szczegółach dotyczących odbiorców, aby dołączyć konto magazynu.</span><span class="sxs-lookup"><span data-stu-id="13b4b-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>
