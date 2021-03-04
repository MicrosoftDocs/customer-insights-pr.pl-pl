---
title: Eksportowanie danych Customer Insights do hostów SFTP
description: Informacje o konfigurowaniu połączenia z hostem SFTP.
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268011"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="4a98f-103">Łącznik dla SFTP (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="4a98f-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="4a98f-104">Korzystaj z danych klientów w aplikacjach innych firm, eksportując je do hosta Secure File Transfer Protocol (SFTP).</span><span class="sxs-lookup"><span data-stu-id="4a98f-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4a98f-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="4a98f-105">Prerequisites</span></span>

- <span data-ttu-id="4a98f-106">Dostępność hosta SFTP i odpowiednie poświadczenia.</span><span class="sxs-lookup"><span data-stu-id="4a98f-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="4a98f-107">Połącz z usługą SFTP</span><span class="sxs-lookup"><span data-stu-id="4a98f-107">Connect to SFTP</span></span>

1. <span data-ttu-id="4a98f-108">Przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.</span><span class="sxs-lookup"><span data-stu-id="4a98f-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="4a98f-109">W **SFTP**, wybierz **Skonfiguruj**.</span><span class="sxs-lookup"><span data-stu-id="4a98f-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="4a98f-110">W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="4a98f-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="4a98f-111">Wprowadź **Nazwę użytkownika**, **Hasło**, **Nazwę hosta** i **Eksportuj folder** dla konta SFTP.</span><span class="sxs-lookup"><span data-stu-id="4a98f-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="4a98f-112">Wybierz **Zweryfikuj**, aby sprawdzić połączenie.</span><span class="sxs-lookup"><span data-stu-id="4a98f-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="4a98f-113">Po pomyślnej weryfikacji wybierz, czy chcesz wyeksportować dane **spakowane**, czy **rozpakowane**, i wybierz **ogranicznik pól** dla eksportowanych plików.</span><span class="sxs-lookup"><span data-stu-id="4a98f-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="4a98f-114">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.</span><span class="sxs-lookup"><span data-stu-id="4a98f-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="4a98f-115">Wybierz **Dalej**, aby rozpocząć konfigurowanie eksportu.</span><span class="sxs-lookup"><span data-stu-id="4a98f-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="4a98f-116">Skonfiguruj eksport</span><span class="sxs-lookup"><span data-stu-id="4a98f-116">Configure the export</span></span>

1. <span data-ttu-id="4a98f-117">Wybierz encje, na przykład segmenty, które chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="4a98f-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4a98f-118">Każda wybrana encja będzie miała do pięciu plików wyjściowych po wyeksportowaniu.</span><span class="sxs-lookup"><span data-stu-id="4a98f-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="4a98f-119">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="4a98f-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="4a98f-120">Eksportowanie danych</span><span class="sxs-lookup"><span data-stu-id="4a98f-120">Export the data</span></span>

<span data-ttu-id="4a98f-121">Możesz [eksportować dane na żądanie](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="4a98f-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="4a98f-122">Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4a98f-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="4a98f-123">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="4a98f-123">Known limitations</span></span>

- <span data-ttu-id="4a98f-124">Czas wykonania eksportu zależy od wydajności systemu.</span><span class="sxs-lookup"><span data-stu-id="4a98f-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="4a98f-125">Zalecamy dwa rdzenie procesora i 1 GB pamięci jako minimalną konfigurację serwera.</span><span class="sxs-lookup"><span data-stu-id="4a98f-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="4a98f-126">Eksportowanie jednostek z maksymalnie 100 milionami profili klientów może zająć 90 minut przy użyciu zalecanej minimalnej konfiguracji dwóch rdzeni procesora i 1 Gb pamięci.</span><span class="sxs-lookup"><span data-stu-id="4a98f-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4a98f-127">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="4a98f-127">Data privacy and compliance</span></span>

<span data-ttu-id="4a98f-128">Po włączeniu Dynamics 365 Customer Insights do transmisji danych za pomocą SFTP można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="4a98f-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4a98f-129">Microsoft przekaże takie dane na Twoje polecenie, ale odpowiadasz za zapewnienie, że miejsce docelowe eksportu spełnia wszelkie Twoje obowiązki w zakresie prywatności lub bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="4a98f-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="4a98f-130">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="4a98f-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="4a98f-131">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="4a98f-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]