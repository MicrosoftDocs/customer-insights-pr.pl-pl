---
title: Eksportowanie danych usługi Customer Insights do usługi Campaign Monitor
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 091a3197dc0c19ff78f0419fb4e88868e0f78359
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124194"
---
# <a name="export-segments-to-campaign-monitor-preview"></a><span data-ttu-id="c75f5-103">Eksportowanie segmentów do usługi Campaign Monitor (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="c75f5-103">Export segments to Campaign Monitor (preview)</span></span>

<span data-ttu-id="c75f5-104">Wyeksportuj segmenty ujednoliconych profilów klientów do usługi Campaign Monitor i użyj ich w działaniach marketingowych.</span><span class="sxs-lookup"><span data-stu-id="c75f5-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c75f5-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="c75f5-105">Prerequisites</span></span>

-   <span data-ttu-id="c75f5-106">Użytkownik ma konto [Kontakt administracyjny usługi Campaign Monitor](https://www.campaignmonitor.com/) i odpowiednie dane logowania administratora.</span><span class="sxs-lookup"><span data-stu-id="c75f5-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c75f5-107">Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.</span><span class="sxs-lookup"><span data-stu-id="c75f5-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="c75f5-108">Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="c75f5-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c75f5-109">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="c75f5-109">Known limitations</span></span>

- <span data-ttu-id="c75f5-110">Do usługi Campaign Monitor można wyeksportować do 1 miliona profili.</span><span class="sxs-lookup"><span data-stu-id="c75f5-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="c75f5-111">Eksportowanie do usługi Campaign Monitor jest ograniczone do segmentów.</span><span class="sxs-lookup"><span data-stu-id="c75f5-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="c75f5-112">Wyeksportowanie do 1 miliona profilów do usługi Campaign Monitor może potrwać do 20 minut.</span><span class="sxs-lookup"><span data-stu-id="c75f5-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="c75f5-113">Liczba profilów, które można eksportować usługi Campaign Monitor, jest ograniczona i zależy od kontraktu użytkownika z usługą Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="c75f5-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="c75f5-114">Konfiguracja połączenia z usługą Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="c75f5-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="c75f5-115">Przejdź do **Admin** > **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="c75f5-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c75f5-116">Wybierz opcję **Dodaj połączenie** i wybierz opcję **Campaign Monitor**, aby skonfigurować połączenie.</span><span class="sxs-lookup"><span data-stu-id="c75f5-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="c75f5-117">W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="c75f5-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="c75f5-118">Wyświetlana nazwa i typ połączenia opisują to połączenie.</span><span class="sxs-lookup"><span data-stu-id="c75f5-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="c75f5-119">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.</span><span class="sxs-lookup"><span data-stu-id="c75f5-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c75f5-120">Określ, kto może używać tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="c75f5-120">Choose who can use this connection.</span></span> <span data-ttu-id="c75f5-121">Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy.</span><span class="sxs-lookup"><span data-stu-id="c75f5-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="c75f5-122">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c75f5-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c75f5-123">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.</span><span class="sxs-lookup"><span data-stu-id="c75f5-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c75f5-124">Wybierz opcję **Połącz**, aby inicjować połączenie z usługą Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="c75f5-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="c75f5-125">Wybierz opcję **Uwierzytelnij z usługą Campaign Monitor** i podaj swoje poświadczenia administratora dla usługi Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="c75f5-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="c75f5-126">Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c75f5-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="c75f5-127">Aby zakończyć połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="c75f5-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="c75f5-128">Konfigurowanie eksportu</span><span class="sxs-lookup"><span data-stu-id="c75f5-128">Configure an export</span></span>

<span data-ttu-id="c75f5-129">Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="c75f5-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c75f5-130">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c75f5-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c75f5-131">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="c75f5-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c75f5-132">Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="c75f5-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="c75f5-133">W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="c75f5-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="c75f5-134">Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="c75f5-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="c75f5-135">Wprowadź swój [**Identyfikator listy usługi Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span><span class="sxs-lookup"><span data-stu-id="c75f5-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="c75f5-136">Najpierw [Wygeneruj klucz interfejsu API](https://www.campaignmonitor.com/api/getting-started/) na podstawie **Ustawień klienta** w usłudze Campaign Monitor, aby wyświetlić identyfikator listy interfejsów API.</span><span class="sxs-lookup"><span data-stu-id="c75f5-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="c75f5-137">W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta.</span><span class="sxs-lookup"><span data-stu-id="c75f5-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="c75f5-138">Wymagane jest wyeksportowanie segmentów do usługi Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="c75f5-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="c75f5-139">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="c75f5-139">Select **Save**.</span></span>

<span data-ttu-id="c75f5-140">Zapisanie eksportu nie uruchamia natychmiastowo eksportu.</span><span class="sxs-lookup"><span data-stu-id="c75f5-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="c75f5-141">Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c75f5-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c75f5-142">Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c75f5-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c75f5-143">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="c75f5-143">Data privacy and compliance</span></span>

<span data-ttu-id="c75f5-144">Włączenie rozwiązania Dynamics 365 Customer Insights do przekazywania danych do usługi Campaign Monitor umożliwia przesyłanie danych poza granicą zgodności z przepisami Dynamics 365 Customer Insights, w tym potencjalnie poufnych danych, takich jak dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="c75f5-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c75f5-145">Microsoft przesyła takie dane zgodnie z instrukcjami użytkownika, ale użytkownik musi zagwarantować, że usługa Campaign Monitor będzie spełniać wszelkie zobowiązania dotyczące prywatności lub bezpieczeństwa, jakie może mieć użytkownik.</span><span class="sxs-lookup"><span data-stu-id="c75f5-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c75f5-146">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c75f5-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="c75f5-147">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="c75f5-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
