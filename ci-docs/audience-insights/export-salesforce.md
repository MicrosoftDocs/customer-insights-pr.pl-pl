---
title: Eksportowanie danych rozwiązania Customer Insights do usługi Salesforce Marketing Cloud
description: Dowiedz się, jak skonfigurować połączenie i wyeksportować je do usługi Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314654"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="bdfb1-103">Eksportowanie segmentów i innych danych do usługi Salesforce Marketing Cloud (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="bdfb1-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="bdfb1-104">Wykorzystaj dane swoich klientów w Salesforce Marketing Cloud, eksportując je za pośrednictwem lokalizacji Secure File Transfer Protocol (SFTP).</span><span class="sxs-lookup"><span data-stu-id="bdfb1-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="bdfb1-105">Wymagania wstępne dla połączenia</span><span class="sxs-lookup"><span data-stu-id="bdfb1-105">Prerequisites for connection</span></span>

- <span data-ttu-id="bdfb1-106">Dostępność hosta SFTP i odpowiednich danych uwierzytelniających administratora.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="bdfb1-107">Jak skonfigurować lokalizacje platformy SFTP dla usługi Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="bdfb1-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="bdfb1-108">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="bdfb1-108">Known limitations</span></span>

- <span data-ttu-id="bdfb1-109">Czas wykonania eksportu zależy od wydajności systemu.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="bdfb1-110">Zalecamy dwa rdzenie procesora i 1 GB pamięci jako minimalną konfigurację serwera.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="bdfb1-111">Eksportowanie encji posiadających do 100 milionów profili klientów może zająć 90 minut przy zastosowaniu zalecanej minimalnej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="bdfb1-112">Konfigurowanie połączenia z usługą Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="bdfb1-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="bdfb1-113">Przejdź do **Admin** > **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="bdfb1-114">Wybierz opcję **Dodaj połączenie** i wybierz opcję **Salesforce Marketing Cloud**, aby skonfigurować połączenie.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="bdfb1-115">W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="bdfb1-116">Wyświetlana nazwa i typ połączenia opisują to połączenie.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="bdfb1-117">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="bdfb1-118">Określ, kto może używać tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-118">Choose who can use this connection.</span></span> <span data-ttu-id="bdfb1-119">Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="bdfb1-120">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="bdfb1-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="bdfb1-121">Wprowadź **Nazwę użytkownika**, **Hasło**, **Nazwę hosta** i **Eksportuj folder** dla konta SFTP.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="bdfb1-122">Wybierz **Zweryfikuj**, aby sprawdzić połączenie.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="bdfb1-123">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="bdfb1-124">Aby zakończyć połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="bdfb1-125">Konfigurowanie eksportu</span><span class="sxs-lookup"><span data-stu-id="bdfb1-125">Configure an export</span></span>

<span data-ttu-id="bdfb1-126">Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="bdfb1-127">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="bdfb1-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="bdfb1-128">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="bdfb1-129">Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="bdfb1-130">W polu **Połączenie dla eksportu** wybierz połączenie z sekcji SFTP.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="bdfb1-131">Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="bdfb1-132">Określ, czy dane mają być eksportowane po spakowaniu **Gzip**, czy **Niespakowane**, oraz **ogranicznik pola** dla eksportowanych plików.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="bdfb1-133">Wybierz encje, na przykład segmenty, które chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="bdfb1-134">Po wyeksportowaniu każda wybrana encja zostanie podzielona na maksymalnie pięć plików wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="bdfb1-135">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-135">Select **Save**.</span></span>

<span data-ttu-id="bdfb1-136">Zapisanie eksportu nie uruchamia natychmiastowo eksportu.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="bdfb1-137">Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bdfb1-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bdfb1-138">Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="bdfb1-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="bdfb1-139">Import danych Customer Insights z lokalizacji SFTP do Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="bdfb1-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="bdfb1-140">Utwórz [rozszerzenia danych w Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5), aby zaimportować plik danych Customer Insights z lokalizacji SFTP.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="bdfb1-141">[Import danych z lokalizacji SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) do rozszerzenia danych Salesforce Marketing Cloud.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="bdfb1-142">Skonfiguruj automatyzację do importu danych do rozszerzeń danych.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="bdfb1-143">Dowiedz się więcej o [automatyzacji przesyłania plików i planowanych zadaniach automatyzacji](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="bdfb1-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="bdfb1-144">Zdefiniuj [automatyzację przesyłania plików](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) lub [zaplanowane zadania automatyzacji](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="bdfb1-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="bdfb1-145">Oto przykład [automatyzacji SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="bdfb1-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bdfb1-146">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="bdfb1-146">Data privacy and compliance</span></span>

<span data-ttu-id="bdfb1-147">Po włączeniu Dynamics 365 Customer Insights do transmisji danych za pomocą SFTP można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bdfb1-148">Microsoft przekaże takie dane na Twoje polecenie, ale odpowiadasz za zapewnienie, że miejsce docelowe eksportu spełnia wszelkie Twoje obowiązki w zakresie prywatności lub bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="bdfb1-149">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="bdfb1-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="bdfb1-150">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="bdfb1-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
