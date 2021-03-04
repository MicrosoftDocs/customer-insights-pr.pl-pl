---
title: Eksportowanie danych Customer Insights do usługi Autopilot
description: Dowiedz się, jak skonfigurować połączenie z Autopilot.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269251"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="37fcf-103">Łącznik dla usługi Autopilot (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="37fcf-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="37fcf-104">Eksportuj segmenty ujednoliconych profili klientów do Autopilota i używaj ich do marketingu e-mailowego w Autopilocie.</span><span class="sxs-lookup"><span data-stu-id="37fcf-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="37fcf-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="37fcf-105">Prerequisites</span></span>

-   <span data-ttu-id="37fcf-106">Użytkownik ma [konto usługi Autopilot](https://www.autopilothq.com/) i odpowiadające mu poświadczenia administratora.</span><span class="sxs-lookup"><span data-stu-id="37fcf-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="37fcf-107">Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.</span><span class="sxs-lookup"><span data-stu-id="37fcf-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="37fcf-108">Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="37fcf-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="37fcf-109">Połącz z usługą Autopilot</span><span class="sxs-lookup"><span data-stu-id="37fcf-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="37fcf-110">Przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.</span><span class="sxs-lookup"><span data-stu-id="37fcf-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="37fcf-111">W **Autopilot** wybierz **Konfiguruj**.</span><span class="sxs-lookup"><span data-stu-id="37fcf-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="37fcf-112">W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej exportu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="37fcf-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Okienko konfiguracji dla połączenia z Autopilot.":::

1. <span data-ttu-id="37fcf-114">Wprowadź **klucz interfejsu API Autopilot** [klucz interfejsu API Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="37fcf-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="37fcf-115">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.</span><span class="sxs-lookup"><span data-stu-id="37fcf-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="37fcf-116">Wybierz opcję **Połącz**, aby zainicjować połączenie z Autopilot.</span><span class="sxs-lookup"><span data-stu-id="37fcf-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="37fcf-117">Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="37fcf-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="37fcf-118">Wybierz **Dalej**, aby skonfigurować eksport.</span><span class="sxs-lookup"><span data-stu-id="37fcf-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="37fcf-119">Skonfiguruj łącznik</span><span class="sxs-lookup"><span data-stu-id="37fcf-119">Configure the connector</span></span>

1. <span data-ttu-id="37fcf-120">W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta.</span><span class="sxs-lookup"><span data-stu-id="37fcf-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="37fcf-121">Powtórz te kroki dla innych pól opcjonalnych, takich jak **Imię**, **Nazwisko**.</span><span class="sxs-lookup"><span data-stu-id="37fcf-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="37fcf-122">Wybierz segmenty, które chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="37fcf-122">Select the segments you want to export.</span></span> <span data-ttu-id="37fcf-123">Zdecydowanie **zalecamy, aby nie eksportować łącznie ponad 100 000 profili klientów** do Autopilota.</span><span class="sxs-lookup"><span data-stu-id="37fcf-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="37fcf-124">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="37fcf-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="37fcf-125">Eksportowanie danych</span><span class="sxs-lookup"><span data-stu-id="37fcf-125">Export the data</span></span>

<span data-ttu-id="37fcf-126">Możesz [eksportować dane na żądanie](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="37fcf-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="37fcf-127">Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="37fcf-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="37fcf-128">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="37fcf-128">Known limitations</span></span>

- <span data-ttu-id="37fcf-129">Możesz wyeksportować łącznie do 100 000 profili do Autopilota.</span><span class="sxs-lookup"><span data-stu-id="37fcf-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="37fcf-130">Eksport do Autopilot jest ograniczony do segmentów.</span><span class="sxs-lookup"><span data-stu-id="37fcf-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="37fcf-131">Eksportowanie do 100 000 profili do Autopilota może zająć do kilku godzin.</span><span class="sxs-lookup"><span data-stu-id="37fcf-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="37fcf-132">Liczba profilów, które można eksportować do Autopilot, jest zależna od kontraktu i ograniczona jego Autopilot.</span><span class="sxs-lookup"><span data-stu-id="37fcf-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="37fcf-133">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="37fcf-133">Data privacy and compliance</span></span>

<span data-ttu-id="37fcf-134">Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Autopilot można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="37fcf-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="37fcf-135">Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że Autopilot spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="37fcf-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="37fcf-136">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="37fcf-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="37fcf-137">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="37fcf-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]