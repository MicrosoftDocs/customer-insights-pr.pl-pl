---
title: Eksportowanie danych Customer Insights do hostów SFTP
description: Dowiedz się, jak skonfigurować połączenie i eksport do lokalizacji SFTP.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3663a48955f0b1db8a96e25403e5f8947bc6a220
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976952"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a><span data-ttu-id="67861-103">Eksportowanie list segmentów i innych danych do SFTP (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="67861-103">Export segment lists and other data to SFTP (preview)</span></span>

<span data-ttu-id="67861-104">Danych klientów można używać w aplikacjach innych firm, eksportując je do lokalizacji bezpiecznego protokołu transferu plików (SFTP).</span><span class="sxs-lookup"><span data-stu-id="67861-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="67861-105">Wymagania wstępne dla połączenia</span><span class="sxs-lookup"><span data-stu-id="67861-105">Prerequisites for connection</span></span>

- <span data-ttu-id="67861-106">Dostępność hosta SFTP i odpowiednie poświadczenia.</span><span class="sxs-lookup"><span data-stu-id="67861-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="67861-107">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="67861-107">Known limitations</span></span>

- <span data-ttu-id="67861-108">Czas wykonania eksportu zależy od wydajności systemu.</span><span class="sxs-lookup"><span data-stu-id="67861-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="67861-109">Zalecamy dwa rdzenie procesora i 1 GB pamięci jako minimalną konfigurację serwera.</span><span class="sxs-lookup"><span data-stu-id="67861-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="67861-110">Eksportowanie jednostek z maksymalnie 100 milionami profili klientów może zająć 90 minut przy użyciu zalecanej minimalnej konfiguracji dwóch rdzeni procesora i 1 Gb pamięci.</span><span class="sxs-lookup"><span data-stu-id="67861-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="67861-111">Konfiguruj połączenie z SFTP</span><span class="sxs-lookup"><span data-stu-id="67861-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="67861-112">Przejdź do **Admin** > **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="67861-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="67861-113">Wybierz opcję **Dodaj połączenie** i wybierz opcję **SFTP**, aby skonfigurować połączenie.</span><span class="sxs-lookup"><span data-stu-id="67861-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="67861-114">W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="67861-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="67861-115">Wyświetlana nazwa i typ połączenia opisują to połączenie.</span><span class="sxs-lookup"><span data-stu-id="67861-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="67861-116">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.</span><span class="sxs-lookup"><span data-stu-id="67861-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="67861-117">Określ, kto może używać tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="67861-117">Choose who can use this connection.</span></span> <span data-ttu-id="67861-118">Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy.</span><span class="sxs-lookup"><span data-stu-id="67861-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="67861-119">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="67861-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="67861-120">Wprowadź **Nazwę użytkownika**, **Hasło**, **Nazwę hosta** i **Eksportuj folder** dla konta SFTP.</span><span class="sxs-lookup"><span data-stu-id="67861-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="67861-121">Wybierz **Zweryfikuj**, aby sprawdzić połączenie.</span><span class="sxs-lookup"><span data-stu-id="67861-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="67861-122">Określ, czy dane mają być eksportowane po spakowaniu **Gzip**, czy **Niespakowane**, oraz **ogranicznik pola** dla eksportowanych plików.</span><span class="sxs-lookup"><span data-stu-id="67861-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="67861-123">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.</span><span class="sxs-lookup"><span data-stu-id="67861-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="67861-124">Aby zakończyć połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="67861-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="67861-125">Konfigurowanie eksportu</span><span class="sxs-lookup"><span data-stu-id="67861-125">Configure an export</span></span>

<span data-ttu-id="67861-126">Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="67861-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="67861-127">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="67861-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="67861-128">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="67861-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="67861-129">Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="67861-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="67861-130">W polu **Połączenie dla eksportu** wybierz połączenie z sekcji SFTP.</span><span class="sxs-lookup"><span data-stu-id="67861-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="67861-131">Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="67861-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="67861-132">Wybierz encje, na przykład segmenty, które chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="67861-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="67861-133">Po wyeksportowaniu każda wybrana encja zostanie podzielona na maksymalnie pięć plików wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="67861-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="67861-134">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="67861-134">Select **Save**.</span></span>

<span data-ttu-id="67861-135">Zapisanie eksportu nie uruchamia natychmiastowo eksportu.</span><span class="sxs-lookup"><span data-stu-id="67861-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="67861-136">Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="67861-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="67861-137">Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="67861-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="67861-138">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="67861-138">Data privacy and compliance</span></span>

<span data-ttu-id="67861-139">Po włączeniu Dynamics 365 Customer Insights do transmisji danych za pomocą SFTP można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="67861-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="67861-140">Microsoft przekaże takie dane na Twoje polecenie, ale odpowiadasz za zapewnienie, że miejsce docelowe eksportu spełnia wszelkie Twoje obowiązki w zakresie prywatności lub bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="67861-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="67861-141">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="67861-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="67861-142">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="67861-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
