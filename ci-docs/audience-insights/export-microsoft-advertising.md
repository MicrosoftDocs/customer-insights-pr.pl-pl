---
title: Eksportowanie Customer Insights do magazynu obiektów Microsoft Advertising
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124531"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="6df3c-103">Eksportowanie segmentów do programu Microsoft Advertising (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="6df3c-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="6df3c-104">Eksport segmentów Customer Insights do Microsoft Advertising w celu stworzenia grup odbiorców Customer Match.</span><span class="sxs-lookup"><span data-stu-id="6df3c-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="6df3c-105">Grupy odbiorców mogą być wykorzystania w kampaniach reklamowych.</span><span class="sxs-lookup"><span data-stu-id="6df3c-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6df3c-106">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="6df3c-106">Prerequisites</span></span>

-   <span data-ttu-id="6df3c-107">Użytkownik ma [konto Microsoft Advertising](https://ads.microsoft.com/) i odpowiednie dane logowania administratora.</span><span class="sxs-lookup"><span data-stu-id="6df3c-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="6df3c-108">Zaakceptowałeś warunki korzystania z Customer Match.</span><span class="sxs-lookup"><span data-stu-id="6df3c-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="6df3c-109">[Segmenty skonfigurowane](segments.md) w wynikach analizy danych odbiorców.</span><span class="sxs-lookup"><span data-stu-id="6df3c-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="6df3c-110">Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole z adresem e-mail.</span><span class="sxs-lookup"><span data-stu-id="6df3c-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="6df3c-111">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="6df3c-111">Known limitations</span></span>

- <span data-ttu-id="6df3c-112">Do programu Microsoft Advertising można wyeksportować maksymalnie 500 tysięcy profili.</span><span class="sxs-lookup"><span data-stu-id="6df3c-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="6df3c-113">Eksportowanie do usługi Microsoft Advertising jest ograniczone do segmentów.</span><span class="sxs-lookup"><span data-stu-id="6df3c-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="6df3c-114">Wyeksportowanie do 500 tysięcy profilów do usługi Microsoft Advertising może potrwać do 10 minut.</span><span class="sxs-lookup"><span data-stu-id="6df3c-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="6df3c-115">Skonfiguruj połączenie z usługą Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="6df3c-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="6df3c-116">Przejdź do **Admin** > **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="6df3c-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="6df3c-117">Wybierz opcję **Dodaj połączenie** i wybierz opcję **Microsoft Advertising**, aby skonfigurować połączenie.</span><span class="sxs-lookup"><span data-stu-id="6df3c-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="6df3c-118">W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="6df3c-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="6df3c-119">Wyświetlana nazwa i typ połączenia opisują to połączenie.</span><span class="sxs-lookup"><span data-stu-id="6df3c-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="6df3c-120">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.</span><span class="sxs-lookup"><span data-stu-id="6df3c-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="6df3c-121">Określ, kto może używać tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="6df3c-121">Choose who can use this connection.</span></span> <span data-ttu-id="6df3c-122">Wartość domyślna to administratorzy.</span><span class="sxs-lookup"><span data-stu-id="6df3c-122">The default is administrators.</span></span> <span data-ttu-id="6df3c-123">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="6df3c-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="6df3c-124">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.</span><span class="sxs-lookup"><span data-stu-id="6df3c-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="6df3c-125">Wybierz opcję **Połącz**, aby inicjować połączenie z usługą Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="6df3c-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="6df3c-126">Wybierz opcję **Uwierzytelnij z usługą Microsoft Advertising** i podaj swoje poświadczenia administratora dla usługi Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="6df3c-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="6df3c-127">Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6df3c-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="6df3c-128">Aby zakończyć połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="6df3c-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="6df3c-129">Konfigurowanie eksportu</span><span class="sxs-lookup"><span data-stu-id="6df3c-129">Configure an export</span></span>

<span data-ttu-id="6df3c-130">Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="6df3c-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="6df3c-131">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="6df3c-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="6df3c-132">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="6df3c-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6df3c-133">Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="6df3c-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="6df3c-134">W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="6df3c-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="6df3c-135">Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="6df3c-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="6df3c-136">Wybierz segmenty do eksportu.</span><span class="sxs-lookup"><span data-stu-id="6df3c-136">Select the segments to export.</span></span> <span data-ttu-id="6df3c-137">Odbiorcy Customer Match w Microsoft Advertising są automatycznie tworzeni z nazwą segmentów wybranych do eksportu.</span><span class="sxs-lookup"><span data-stu-id="6df3c-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="6df3c-138">W przypadku każdego z segmentów będzie to Customer Match odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="6df3c-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="6df3c-139">Wprowadź swój **Identyfikator klienta i konta Microsoft Advertising**.</span><span class="sxs-lookup"><span data-stu-id="6df3c-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="6df3c-140">Możesz znaleźć ID klienta (`cid`) i ID konta (`aid`) w parametrach adresu URL po zalogowaniu w Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="6df3c-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="6df3c-141">W sekcji **Dopasowywanie danych** w polu **E-mail** wybierz pole w ujednoliconym profilu klienta z adresem e-mail klienta.</span><span class="sxs-lookup"><span data-stu-id="6df3c-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="6df3c-142">Wymagane jest wyeksportowanie segmentów do usługi Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="6df3c-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="6df3c-143">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="6df3c-143">Select **Save**.</span></span>

<span data-ttu-id="6df3c-144">Zapisanie eksportu nie uruchamia natychmiastowo eksportu.</span><span class="sxs-lookup"><span data-stu-id="6df3c-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="6df3c-145">Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6df3c-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6df3c-146">Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="6df3c-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6df3c-147">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="6df3c-147">Data privacy and compliance</span></span>

<span data-ttu-id="6df3c-148">Włączenie rozwiązania Dynamics 365 Customer Insights do przekazywania danych do usługi Microsoft Advertising umożliwia przesyłanie danych poza granicą zgodności z przepisami Dynamics 365 Customer Insights, w tym potencjalnie poufnych danych, takich jak dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="6df3c-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6df3c-149">Microsoft przesyła takie dane zgodnie z instrukcjami użytkownika, ale użytkownik musi zagwarantować, że usługa Microsoft Advertising będzie spełniać wszelkie zobowiązania dotyczące prywatności lub bezpieczeństwa, jakie może mieć użytkownik.</span><span class="sxs-lookup"><span data-stu-id="6df3c-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="6df3c-150">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6df3c-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="6df3c-151">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="6df3c-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
