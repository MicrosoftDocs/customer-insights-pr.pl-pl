---
title: Eksportowanie danych Customer Insights do hostów SFTP
description: Informacje o konfigurowaniu połączenia z hostem SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643516"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="ae22e-103">Łącznik dla SFTP (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="ae22e-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="ae22e-104">Korzystaj z danych klientów w aplikacjach innych firm, eksportując je do hosta Secure File Transfer Protocol (SFTP).</span><span class="sxs-lookup"><span data-stu-id="ae22e-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ae22e-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="ae22e-105">Prerequisites</span></span>

- <span data-ttu-id="ae22e-106">Dostępność hosta SFTP i odpowiednich poświadczeń.</span><span class="sxs-lookup"><span data-stu-id="ae22e-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="ae22e-107">Połącz z SFTP</span><span class="sxs-lookup"><span data-stu-id="ae22e-107">Connect to SFTP</span></span>

1. <span data-ttu-id="ae22e-108">Przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.</span><span class="sxs-lookup"><span data-stu-id="ae22e-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ae22e-109">W **SFTP**, wybierz **Skonfiguruj**.</span><span class="sxs-lookup"><span data-stu-id="ae22e-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="ae22e-110">W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="ae22e-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="ae22e-111">Wprowadź **Nazwę użytkownika**, **Hasło** i **Nazwę hosta** dla konta SFTP.</span><span class="sxs-lookup"><span data-stu-id="ae22e-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="ae22e-112">Przykład: jeśli folder główny serwera SFTP to /root/folder i chcesz, aby dane zostały wyeksportowane do /root/folder/ci_export_destination_folder, hostem powinien być sftp://<server_address>/ci_export_destination_folder".</span><span class="sxs-lookup"><span data-stu-id="ae22e-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="ae22e-113">Wybierz **Zweryfikuj**, aby sprawdzić połączenie.</span><span class="sxs-lookup"><span data-stu-id="ae22e-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="ae22e-114">Po pomyślnej weryfikacji wybierz, czy chcesz eksportować dane **Spakowane** lub **Niespakowane**, i wybierz **ogranicznik pola** dla eksportowanych plików.</span><span class="sxs-lookup"><span data-stu-id="ae22e-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="ae22e-115">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.</span><span class="sxs-lookup"><span data-stu-id="ae22e-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ae22e-116">Wybierz **Dalej**, aby rozpocząć konfigurowanie eksportu.</span><span class="sxs-lookup"><span data-stu-id="ae22e-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="ae22e-117">Konfigurowanie połączenia</span><span class="sxs-lookup"><span data-stu-id="ae22e-117">Configure the connection</span></span>

1. <span data-ttu-id="ae22e-118">Wybierz **atrybuty klienta**, które chcesz eksportować.</span><span class="sxs-lookup"><span data-stu-id="ae22e-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="ae22e-119">Istnieje możliwość wyeksportowania jednego lub wielu atrybutów.</span><span class="sxs-lookup"><span data-stu-id="ae22e-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="ae22e-120">Wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="ae22e-120">Select **Next**.</span></span>

1. <span data-ttu-id="ae22e-121">Wybierz segmenty, które chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="ae22e-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="ae22e-122">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ae22e-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="ae22e-123">Eksportowanie danych</span><span class="sxs-lookup"><span data-stu-id="ae22e-123">Export the data</span></span>

<span data-ttu-id="ae22e-124">Możesz [eksportować dane na żądanie](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="ae22e-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="ae22e-125">Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ae22e-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ae22e-126">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="ae22e-126">Data privacy and compliance</span></span>

<span data-ttu-id="ae22e-127">Po włączeniu Dynamics 365 Customer Insights do transmisji danych za pomocą SFTP można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="ae22e-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ae22e-128">Microsoft przekaże takie dane na Twoje polecenie, ale odpowiadasz za zapewnienie, że miejsce docelowe eksportu spełnia wszelkie Twoje obowiązki w zakresie prywatności lub bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="ae22e-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ae22e-129">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ae22e-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ae22e-130">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="ae22e-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
