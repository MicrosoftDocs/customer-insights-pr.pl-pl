---
title: Praca z API
description: Korzystanie z interfejsów API i zrozumienie ograniczeń.
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 966db1a22e7dece1bcd89733880bce059151157f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267537"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="e432e-103">Pracuj z interfejsami API Customer Insights</span><span class="sxs-lookup"><span data-stu-id="e432e-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="e432e-104">Dynamics 365 Customer Insights udostępnia interfejsy API umożliwiające konstruowanie własnych aplikacji na podstawie danych z Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e432e-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e432e-105">Szczegółowe informacje o tych interfejsach API są wymienione w [Kompendium interfejsów API Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="e432e-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="e432e-106">Zawierają one dodatkowe informacje na temat operacji i parametrów oraz odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="e432e-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="e432e-107">Ten artykuł zawiera instrukcje dotyczące dostępu do interfejsów API usługi Customer Insights, tworzenia rejestracji aplikacji platformy Azure i rozpoczynania pracy z dostępnymi bibliotekami klienckimi.</span><span class="sxs-lookup"><span data-stu-id="e432e-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="e432e-108">Rozpoczynanie korzystania z interfejsów API Customer Insights</span><span class="sxs-lookup"><span data-stu-id="e432e-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="e432e-109">[Zaloguj się](https://home.ci.ai.dynamics.com) do aplikacji Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e432e-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="e432e-110">Jeśli nie dysponujesz jeszcze subskrypcją, [Załóż konto w celu rozpoczęcia wersji próbnej Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="e432e-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="e432e-111">Aby włączyć interfejsy API w środowisku Customer Insights, przejdź do **Administrator** > **Uprawnienia**.</span><span class="sxs-lookup"><span data-stu-id="e432e-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="e432e-112">Konieczne są więc uprawnienia administratora.</span><span class="sxs-lookup"><span data-stu-id="e432e-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="e432e-113">Przejdź do **karty interfejsy API** i wybierz przycisk **Włącz**.</span><span class="sxs-lookup"><span data-stu-id="e432e-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="e432e-114">Włączenie interfejsów API powoduje utworzenie podstawowego i dodatkowego klucza subskrypcji dla Twojej instancji, który jest używany w żądaniach API.</span><span class="sxs-lookup"><span data-stu-id="e432e-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="e432e-115">Klucze można wygenerować ponownie, wybierając z listy ponowne **Wygeneruj ponownie podstawowy** lub **Wygeneruj ponownie pomocniczy** w **Administrator** > **Uprawnienia** > **Interfejsy API**.</span><span class="sxs-lookup"><span data-stu-id="e432e-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Włącz interfejsy API Customer Insights":::

1. <span data-ttu-id="e432e-117">Zaznacz opcję **Poznaj nasze interfejsy API** w celu wypróbowania interfejsów API.</span><span class="sxs-lookup"><span data-stu-id="e432e-117">Select **Explore our APIs** to try out the APIs.</span></span>

1. <span data-ttu-id="e432e-118">Wybierz operację interfejsu API i wybierz opcję **Wypróbuj tę funkcję**.</span><span class="sxs-lookup"><span data-stu-id="e432e-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="e432e-119">W okienku bocznym ustaw wartość w menu rozwijanym **Autoryzacja** na **domniemany**.</span><span class="sxs-lookup"><span data-stu-id="e432e-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="e432e-120">Nagłówek `Authorization` jest dodawany wraz z dodanym tokenem okaziciela.</span><span class="sxs-lookup"><span data-stu-id="e432e-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="e432e-121">Klucz subskrypcji zostanie wypełniony automatycznie.</span><span class="sxs-lookup"><span data-stu-id="e432e-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="e432e-122">Można też dodać wszystkie wymagane parametry zapytania.</span><span class="sxs-lookup"><span data-stu-id="e432e-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="e432e-123">Przewiń w dół do końca okienka bocznego i wybierz opcję **Wyślij**.</span><span class="sxs-lookup"><span data-stu-id="e432e-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="e432e-124">Odpowiedź HTTP będzie wkrótce widoczna poniżej.</span><span class="sxs-lookup"><span data-stu-id="e432e-124">The HTTP response will soon appear below.</span></span>

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="e432e-125">Utwórz nową rejestrację aplikacji w witrynie Azure Portal</span><span class="sxs-lookup"><span data-stu-id="e432e-125">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="e432e-126">Te kroki ułatwiają rozpoczęcie korzystania z interfejsów API usługi Customer Insights w aplikacji platformy Azure przy użyciu uprawnień delegowanych.</span><span class="sxs-lookup"><span data-stu-id="e432e-126">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="e432e-127">W pierwszej kolejności upewnij się, że [sekcją Rozpocznij pracę](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="e432e-127">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="e432e-128">Zaloguj się w [witrynie Azure Portal](https://portal.azure.com), korzystając z konta, które może mieć dostęp do danych Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e432e-128">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="e432e-129">W lewym okienku wybierz pozycję **Rejestracja aplikacji**.</span><span class="sxs-lookup"><span data-stu-id="e432e-129">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="e432e-130">Wybierz **Nowa rejestracja**, podaj nazwę aplikacji i wybierz typ konta.</span><span class="sxs-lookup"><span data-stu-id="e432e-130">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="e432e-131">Opcjonalnie dodaj przekierowanie.</span><span class="sxs-lookup"><span data-stu-id="e432e-131">Optionally, add a redirect URL.</span></span> <span data-ttu-id="e432e-132">http://localhost jest wystarczający do projektowania aplikacji na komputerze lokalnym.</span><span class="sxs-lookup"><span data-stu-id="e432e-132">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="e432e-133">W nowej rejestracji aplikacji przejdź do **uprawnienia interfejsu API**.</span><span class="sxs-lookup"><span data-stu-id="e432e-133">On your new App registration, go to **API permissions**.</span></span>

1. <span data-ttu-id="e432e-134">Zaznacz pole wyboru **Dodaj uprawnienie** i w okienku bocznym wybierz pozycję **Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="e432e-134">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="e432e-135">W przypadku **Typu uprawnienia** Wybierz opcję **Uprawnienia delegowane** i wybierz uprawnienie **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="e432e-135">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="e432e-136">Wybierz **Przyznaj uprawnienia**.</span><span class="sxs-lookup"><span data-stu-id="e432e-136">Select **Add permissions**.</span></span> <span data-ttu-id="e432e-137">Jeśli chcesz uzyskać dostęp do interfejsu API bez logowania się użytkownika, zapoznaj się z sekcją [Uprawnienia aplikacji serwer-serwer](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="e432e-137">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="e432e-138">Wybierz opcję **Udziel administratorowi zgodę na...**, aby zakończyć rejestrację aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e432e-138">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="e432e-139">Możesz użyć identyfikatora aplikacji/klienta do rejestracji tej aplikacji z biblioteką uwierzytelniania firmy Microsoft (MSAL), aby uzyskać token okaziciela do wysłania z żądaniem do interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="e432e-139">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

<span data-ttu-id="e432e-140">Aby uzyskać więcej informacji na temat MSAL, zobacz [Omówienie biblioteki uwierzytelniania Microsoft (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="e432e-140">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="e432e-141">Aby uzyskać więcej informacji na temat rejestracji aplikacji w Azure, zobacz [Nowy interfejs usługi Azure Portal App Registration](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="e432e-141">For more information about app registration in Azure, see [The new Azure portal app registration experience](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="e432e-142">Informacje o korzystaniu z interfejsów API naszych bibliotek klientów znajduje się w artykule [Biblioteki klienta usługi Customer Insights](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="e432e-142">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="e432e-143">Uprawnienia dotyczące aplikacji serwera do serwera</span><span class="sxs-lookup"><span data-stu-id="e432e-143">Server-to-server application permissions</span></span>

<span data-ttu-id="e432e-144">[Sekcja rejestracji aplikacji](#create-a-new-app-registration-in-the-azure-portal) zawiera informacje na temat sposobu zarejestrowania aplikacji, która wymaga zalogowania się użytkownika w celu uwierzytelnienia.</span><span class="sxs-lookup"><span data-stu-id="e432e-144">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="e432e-145">Dowiedz się, jak utworzyć rejestrację aplikacji, która nie wymaga interakcji użytkownika i może być uruchamiana na serwerze.</span><span class="sxs-lookup"><span data-stu-id="e432e-145">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="e432e-146">W rejestracji aplikacji w portalu Azure Portal wybierz opcję **uprawnienia interfejsu API**.</span><span class="sxs-lookup"><span data-stu-id="e432e-146">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="e432e-147">Zaznacz pole wyboru **Dodaj uprawnienie** i w okienku bocznym wybierz pozycję **Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="e432e-147">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="e432e-148">W przypadku **Typu uprawnienia** Wybierz opcję **Uprawnienia do aplikacji** i wybierz uprawnienie **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="e432e-148">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="e432e-149">Wybierz **Przyznaj uprawnienia**.</span><span class="sxs-lookup"><span data-stu-id="e432e-149">Select **Add permissions**.</span></span>

1. <span data-ttu-id="e432e-150">Aby przyznać administratorowi uprawnienie zgody na tę aplikację, należy dodać nazwę główną usługi.</span><span class="sxs-lookup"><span data-stu-id="e432e-150">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="e432e-151">Zainstaluj moduł Azure Active Directory (AD) PowerShell: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="e432e-151">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="e432e-152">Nawiąż połączenie ze swoim kontem AD: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="e432e-152">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="e432e-153">Identyfikator dzierżawy można znaleźć na ekranie **Omówienie** > **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="e432e-153">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="e432e-154">Aby dodać nazwę główną usługi, należy uruchomić następujące polecenie Azure AD: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` parametr AppID jest związany z interfejsem API aplikacji Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e432e-154">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Przykład głównej nazwy usługi":::

1. <span data-ttu-id="e432e-156">Aby zobaczyć rejestrację aplikacji wróć do **uprawnienia interfejsu API**.</span><span class="sxs-lookup"><span data-stu-id="e432e-156">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="e432e-157">Wybierz opcję **Udziel administratorowi zgodę na...**, aby zakończyć rejestrację aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e432e-157">Select **Grant admin consent for...** to complete the app registration.</span></span>

1. <span data-ttu-id="e432e-158">Na koniec musimy dodać nazwę rejestracji aplikacji jako użytkownika w Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e432e-158">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="e432e-159">Otwórz Customer Insights, przejdź do **Administrator** > **Uprawnienia** i wybierz **Dodaj użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="e432e-159">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="e432e-160">Wyszukaj nazwę rejestracji swojej aplikacji, wybierz ją z listy wyników wyszukiwania i wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="e432e-160">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="e432e-161">Biblioteki klientów Customer Insights</span><span class="sxs-lookup"><span data-stu-id="e432e-161">Customer Insights client libraries</span></span>

<span data-ttu-id="e432e-162">Ta sekcja ułatwia rozpoczęcie korzystania z bibliotek klienta dostępnych dla interfejsów API usługi Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e432e-162">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span>

### <a name="c-nuget"></a><span data-ttu-id="e432e-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="e432e-163">C# NuGet</span></span>

<span data-ttu-id="e432e-164">Dowiedz się jak rozpocząć pracę za pomocą klienta C# bibliotek z NuGet.org. Aby uzyskać więcej informacji o pakiecie NuGet, zobacz [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="e432e-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="e432e-165">Obecnie ten pakiet jest przeznaczony dla struktur netstandard2.0 i netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="e432e-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="e432e-166">Dodawanie biblioteki klienta C# do projektu C#</span><span class="sxs-lookup"><span data-stu-id="e432e-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="e432e-167">W Visual Studio otwórz **Menedżera pakietów NuGet** dla swojego projektu.</span><span class="sxs-lookup"><span data-stu-id="e432e-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="e432e-168">Wyszukaj **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="e432e-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="e432e-169">Wybierz **Zainstaluj**, aby dodać pakiet do projektu.</span><span class="sxs-lookup"><span data-stu-id="e432e-169">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="e432e-170">Można też uruchomić to polecenie w **konsoli Menedżer pakietów NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="e432e-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Dodawanie pakietu NuGet do projektu Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="e432e-172">Korzystanie z biblioteki klienta C#</span><span class="sxs-lookup"><span data-stu-id="e432e-172">Use the C# client library</span></span>

1. <span data-ttu-id="e432e-173">Użyj [biblioteki uwierzytelniania firmy Microsoft (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview), aby uzyskać możliwość `AccessToken` za pomocą istniejącej [rejestracji aplikacji Azure](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="e432e-173">Use the [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="e432e-174">Po pomyślnym uwierzytelnieniu i uzyskaniu tokena utwórz nowy lub użyj istniejącego `HttpClient` z dodatkowym **DefaultRequestHeaders "Authorization"** ustawionym na **Element nośny <access token>** i **Ocp-Apim-Subscription-Key** ustawiony na [**klucz subskrypcji** ze środowiska Customer Insights](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="e432e-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="e432e-175">Nagłówek **Autoryzacji** jest resetowany w zależności od potrzeb.</span><span class="sxs-lookup"><span data-stu-id="e432e-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="e432e-176">Na przykład ważność tokenu wygasła.</span><span class="sxs-lookup"><span data-stu-id="e432e-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="e432e-177">Przekaż `HttpClient` do konstrukcji klienta `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="e432e-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Przykład httpclient":::

1. <span data-ttu-id="e432e-179">Wywołaj z klientem „metody rozszerzające”, na przykład `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="e432e-179">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="e432e-180">Jeśli preferowany jest dostęp do bazowego `Microsoft.Rest.HttpOperationResponse`, użyj „metod wiadomości http”, na przykład `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="e432e-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="e432e-181">Odpowiedź będzie prawdopodobnie typu `object`, ponieważ metoda może zwracać wiele typów (na przykład `IList<InstanceInfo>` i `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="e432e-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="e432e-182">Aby sprawdzić zwracany typ, można bezpiecznie rzutować obiekty do typów odpowiedzi określonych na [stronie szczegółów interfejsu API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) dla tej operacji.</span><span class="sxs-lookup"><span data-stu-id="e432e-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="e432e-183">Jeśli potrzeba więcej informacji na temat żądania, użyj **metod wiadomości http**, aby uzyskać dostęp do surowego obiektu odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="e432e-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]