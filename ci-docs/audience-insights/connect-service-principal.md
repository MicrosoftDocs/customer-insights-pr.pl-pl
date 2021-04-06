---
title: Połącz się z kontem Azure Data Lake Storage Gen2 przy użyciu nazwy głównej usługi
description: Użyj głównej usługi Azure, aby uzyskać szczegółowe informacje o odbiorcach, aby połączyć się z własnym data lake podczas dołączania go do szczegółowych informacji o odbiorcach.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c670b0065a2833a6dc311d9e86d2b351140382ce
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596512"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="e3639-103">Połącz analizy odbiorców z kontem Azure Data Lake Storage Gen2 za pomocą głównej usługi platformy Azure</span><span class="sxs-lookup"><span data-stu-id="e3639-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="e3639-104">Zautomatyzowane narzędzia korzystające z usług platformy Azure powinny zawsze mieć ograniczone uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="e3639-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="e3639-105">Zamiast logowania się do aplikacji jako w pełni uprzywilejowany użytkownik, platforma Azure oferuje nazwy głównej usługi.</span><span class="sxs-lookup"><span data-stu-id="e3639-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="e3639-106">Czytaj dalej, aby dowiedzieć się, jak połączyć szczegółowe informacje o odbiorcach z kontem Azure Data Lake Storage Gen2 przy użyciu nazwy głównej usługi usługi platformy Azure zamiast kluczy konta magazynu.</span><span class="sxs-lookup"><span data-stu-id="e3639-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="e3639-107">Możesz użyć nazwy głównej usługi, aby bezpiecznie [dodać lub edytować folder Common Data Model](connect-common-data-model.md) jako źródło danych lub [utworzyć nowe lub zaktualizować istniejące środowisko](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="e3639-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="e3639-108">Konto magazynu Azure Data Lake Gen2, które ma używać jednostki usługi, musi mieć [włączoną funkcję Hierarchiczna przestrzeń nazw (HNS)](/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="e3639-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="e3639-109">Aby utworzyć nazwę główną usługi, trzeba mieć uprawnienia administratora w ramach Twojej subskrypcji platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="e3639-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="e3639-110">Utwórz nazwę głównej usługi Azure do analiz odbiorców</span><span class="sxs-lookup"><span data-stu-id="e3639-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="e3639-111">Przed utworzeniem nowej nazwy głównej usługi na potrzeby statystyk odbiorców sprawdź, czy już istnieje w Twojej organizacji.</span><span class="sxs-lookup"><span data-stu-id="e3639-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="e3639-112">Poszukaj istniejącej nazwy głownej usługi</span><span class="sxs-lookup"><span data-stu-id="e3639-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="e3639-113">W tym celu należy przejść do [portalu administracyjnego Azure](https://portal.azure.com) i zalogować się do organizacji.</span><span class="sxs-lookup"><span data-stu-id="e3639-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="e3639-114">Wybierz **Azure Active Directory** z usług Azure.</span><span class="sxs-lookup"><span data-stu-id="e3639-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="e3639-115">W obszarze **Zarządzanie** wybierz pozycję **Aplikacje korporacyjne**.</span><span class="sxs-lookup"><span data-stu-id="e3639-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="e3639-116">Wyszukaj własny identyfikator aplikacji analizy odbiorców `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` lub nazwę `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="e3639-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="e3639-117">Jeśli znajdziesz pasujący rekord, oznacza to, że istnieje jednostka usługi dla szczegółowych informacji o odbiorcach.</span><span class="sxs-lookup"><span data-stu-id="e3639-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="e3639-118">Nie musisz go ponownie tworzyć.</span><span class="sxs-lookup"><span data-stu-id="e3639-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Zrzut ekranu pokazujący istniejącą nazwę główną usługi.":::
   
6. <span data-ttu-id="e3639-120">Jeśli nie są zwracane żadne wyniki, utwórz nową nazwę główną.</span><span class="sxs-lookup"><span data-stu-id="e3639-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="e3639-121">Utwórz nową nazwę główną usługi</span><span class="sxs-lookup"><span data-stu-id="e3639-121">Create a new service principal</span></span>

1. <span data-ttu-id="e3639-122">Zainstaluj najnowszą wersję **Azure Active Directory PowerShell for Graph**.</span><span class="sxs-lookup"><span data-stu-id="e3639-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="e3639-123">Aby uzyskać więcej informacji, zobacz temat [Instalowanie Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="e3639-123">For more information, see [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="e3639-124">Na komputerze wybierz klawisz Windows na klawiaturze i wyszukaj **Windows PowerShell** i **Uruchom jako administrator**.</span><span class="sxs-lookup"><span data-stu-id="e3639-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="e3639-125">W wyświetlonym oknie PowerShell wprowadź polecenie `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="e3639-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="e3639-126">Utwórz nazwę główną usługi dla analizy odbiorców z modułem Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e3639-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="e3639-127">W oknie PowerShell wprowadź polecenie `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="e3639-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="e3639-128">Zastąp „identyfikator dzierżawy” rzeczywisty identyfikator dzierżawy, w której chcesz utworzyć jednostkę usługi.</span><span class="sxs-lookup"><span data-stu-id="e3639-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="e3639-129">Parametr nazwy środowiska `AzureEnvironmentName` jest opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="e3639-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="e3639-130">Wprowadź `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="e3639-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="e3639-131">To polecenie tworzy nazwę główną usługi dla analiz odbiorcy w wybranej dzierżawie.</span><span class="sxs-lookup"><span data-stu-id="e3639-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="e3639-132">Udziel uprawnień do nazwy głównej usługi, aby uzyskać dostęp do konta magazynu</span><span class="sxs-lookup"><span data-stu-id="e3639-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="e3639-133">Przejdź do obszaru Azure portal, aby przyznać uprawnienia do nazwy głównej usługi dla konta magazynu, którego chcesz użyć w analizach odbiorców.</span><span class="sxs-lookup"><span data-stu-id="e3639-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="e3639-134">W tym celu należy przejść do [portalu administracyjnego Azure](https://portal.azure.com) i zalogować się do organizacji.</span><span class="sxs-lookup"><span data-stu-id="e3639-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="e3639-135">Otwórz konto magazynu, do którego chcesz, aby nazwa główna usługi miała dostęp do szczegółowych informacji o odbiorcach.</span><span class="sxs-lookup"><span data-stu-id="e3639-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="e3639-136">Wybierz pozycję **Kontrola dostępu (IAM)** z okienka nawigacji i wybierz pozycję **Dodaj** > **Dodaj przypisanie roli**.</span><span class="sxs-lookup"><span data-stu-id="e3639-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Zrzut ekranu pokazujący Portal Azure podczas dodawania przypisania roli.":::
   
1. <span data-ttu-id="e3639-138">W okienku **Dodawanie przypisania roli** ustaw następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="e3639-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="e3639-139">Rola: *Współautor danych w usłudze Blob Storage*</span><span class="sxs-lookup"><span data-stu-id="e3639-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="e3639-140">Przypisz dostęp do: *Użytkownik, grupa lub nazwa główna usługi*</span><span class="sxs-lookup"><span data-stu-id="e3639-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="e3639-141">Zaznacz: *Dynamics 365 AI for Customer Insights* ([utworzona nazwa główna usługi](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="e3639-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="e3639-142">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="e3639-142">Select **Save**.</span></span>

<span data-ttu-id="e3639-143">Rozpowszechnienie zmian może zająć do 15 minut.</span><span class="sxs-lookup"><span data-stu-id="e3639-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="e3639-144">Wprowadź identyfikator zasobu platformy Azure lub szczegóły subskrypcji platformy Azure w załączniku konta magazynu do usługi analiz odbiorców.</span><span class="sxs-lookup"><span data-stu-id="e3639-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="e3639-145">Dołącz konto magazynowe Azure Data Lake w analizach odbiorców do [przechowywania danych wyjściowych](manage-environments.md) lub [używania jako źródła danych](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="e3639-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="e3639-146">Wybranie opcji Azure Data Lake umożliwia wybranie podejścia opartego na zasobach lub subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="e3639-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="e3639-147">Wykonaj poniższe czynności, aby podać wymagane informacje na temat wybranego podejścia.</span><span class="sxs-lookup"><span data-stu-id="e3639-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="e3639-148">Połączenie z kontem magazynu oparte na zasobach</span><span class="sxs-lookup"><span data-stu-id="e3639-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="e3639-149">Przejdź do [portalu administrowania Azure](https://portal.azure.com), zaloguj się do subskrypcji i otwórz konto magazynu.</span><span class="sxs-lookup"><span data-stu-id="e3639-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="e3639-150">Wybierz **Ustawienia** > **Właściwości** w okienku nawigacji.</span><span class="sxs-lookup"><span data-stu-id="e3639-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="e3639-151">Skopiuj wartość identyfikatora zasobu konta magazynu.</span><span class="sxs-lookup"><span data-stu-id="e3639-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Skopiuj identyfikator zasobu konta magazynu.":::

1. <span data-ttu-id="e3639-153">W szczegółach dotyczących odbiorców wstaw identyfikator zasobu w polu zasobu wyświetlanym na ekranie połączenia konta magazynu.</span><span class="sxs-lookup"><span data-stu-id="e3639-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Wprowadź informacje o identyfikatorze zasobu konta magazynu.":::   
   
1. <span data-ttu-id="e3639-155">Kontynuuj pozostałe kroki w szczegółach dotyczących odbiorców, aby dołączyć konto magazynu.</span><span class="sxs-lookup"><span data-stu-id="e3639-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="e3639-156">Połączenie z kontem magazynu oparte na subskrypcji</span><span class="sxs-lookup"><span data-stu-id="e3639-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="e3639-157">Przejdź do [portalu administrowania Azure](https://portal.azure.com), zaloguj się do subskrypcji i otwórz konto magazynu.</span><span class="sxs-lookup"><span data-stu-id="e3639-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="e3639-158">Wybierz **Ustawienia** > **Właściwości** w okienku nawigacji.</span><span class="sxs-lookup"><span data-stu-id="e3639-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="e3639-159">Przejrzyj **Subskrypcje**, **Grupa zasobów** i **Nazwa** konta magazynu, aby się upewnić, że wybierasz odpowiednie wartości w analizach odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="e3639-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="e3639-160">W szczegółach dotyczących odbiorców wybierz wartości lub odpowiednie pola podczas dołączania konta magazynu.</span><span class="sxs-lookup"><span data-stu-id="e3639-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="e3639-161">Kontynuuj pozostałe kroki w szczegółach dotyczących odbiorców, aby dołączyć konto magazynu.</span><span class="sxs-lookup"><span data-stu-id="e3639-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]