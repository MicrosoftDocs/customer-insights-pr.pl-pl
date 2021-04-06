---
title: Eksportowanie danych aplikacji Customer Insights do rozwiązania AdRoll
description: Dowiedz się, jak skonfigurować połączenie z rozwiązaniem AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697087"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="adf37-103">Łącznik dla rozwiązania AdRoll (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="adf37-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="adf37-104">Eksportuj segmenty ujednoliconych profilów klientów do rozwiązania AdRoll i używaj ich w celach reklamowych.</span><span class="sxs-lookup"><span data-stu-id="adf37-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="adf37-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="adf37-105">Prerequisites</span></span>

-   <span data-ttu-id="adf37-106">Masz [konto rozwiązania AdRoll](https://www.adroll.com/) i odpowiadające mu poświadczenia administratora.</span><span class="sxs-lookup"><span data-stu-id="adf37-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="adf37-107">Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.</span><span class="sxs-lookup"><span data-stu-id="adf37-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="adf37-108">Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="adf37-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="adf37-109">Połącz z usługą AdRoll</span><span class="sxs-lookup"><span data-stu-id="adf37-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="adf37-110">Przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.</span><span class="sxs-lookup"><span data-stu-id="adf37-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="adf37-111">W obszarze **AdRoll** wybierz **Konfiguruj**.</span><span class="sxs-lookup"><span data-stu-id="adf37-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="adf37-112">W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej exportu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="adf37-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Okienko konfiguracji dla połączenia z rozwiązaniem AdRoll.":::

1. <span data-ttu-id="adf37-114">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.</span><span class="sxs-lookup"><span data-stu-id="adf37-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="adf37-115">Wybierz opcję **Połącz**, aby zainicjować połączenie z rozwiązaniem AdRoll.</span><span class="sxs-lookup"><span data-stu-id="adf37-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="adf37-116">Wybierz opcję **Uwierzytelnij za pomocą rozwiązania AdRoll** i podaj poświadczenia administratora dla rozwiązania AdRoll.</span><span class="sxs-lookup"><span data-stu-id="adf37-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="adf37-117">Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="adf37-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="adf37-118">Wprowadź swój **identyfikator reklamodawcy w usłudze AdRoll**, [AdRoll — możliwości reklamy](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="adf37-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="adf37-119">Wybierz **Dalej**, aby skonfigurować eksport.</span><span class="sxs-lookup"><span data-stu-id="adf37-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="adf37-120">Skonfiguruj łącznik</span><span class="sxs-lookup"><span data-stu-id="adf37-120">Configure the connector</span></span>

1. <span data-ttu-id="adf37-121">W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta.</span><span class="sxs-lookup"><span data-stu-id="adf37-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="adf37-122">Wyeksportowanie segmentów do rozwiązania AdRoll jest wymagane.</span><span class="sxs-lookup"><span data-stu-id="adf37-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="adf37-123">Wybierz segmenty, które chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="adf37-123">Select the segments you want to export.</span></span> <span data-ttu-id="adf37-124">Wybierz segment obejmujący co najmniej 100 członków.</span><span class="sxs-lookup"><span data-stu-id="adf37-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="adf37-125">Nie można eksportować mniejszych segmentów.</span><span class="sxs-lookup"><span data-stu-id="adf37-125">You can't export smaller segments.</span></span> <span data-ttu-id="adf37-126">Dodatkowo maksymalny rozmiar eksportowanego segmentu wynosi 250 000 członków na operację eksportu.</span><span class="sxs-lookup"><span data-stu-id="adf37-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="adf37-127">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="adf37-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="adf37-128">Eksportowanie danych</span><span class="sxs-lookup"><span data-stu-id="adf37-128">Export the data</span></span>

<span data-ttu-id="adf37-129">Możesz [eksportować dane na żądanie](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="adf37-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="adf37-130">Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="adf37-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="adf37-131">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="adf37-131">Known limitations</span></span>

- <span data-ttu-id="adf37-132">Do rozwiązania AdRoll możesz wyeksportować łącznie do 250 000 profilów na operację eksportu.</span><span class="sxs-lookup"><span data-stu-id="adf37-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="adf37-133">Nie można eksportować segmentów obejmujących mniej niż 100 profilów do rozwiązania AdRoll.</span><span class="sxs-lookup"><span data-stu-id="adf37-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="adf37-134">Eksport do rozwiązania AdRoll jest ograniczony do segmentów.</span><span class="sxs-lookup"><span data-stu-id="adf37-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="adf37-135">Wyeksportowanie do 250 000 profilów do rozwiązania AdRoll może potrwać do 10 minut.</span><span class="sxs-lookup"><span data-stu-id="adf37-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="adf37-136">Liczba profilów, które można eksportować do rozwiązania AdRoll, jest zależna od kontraktu z rozwiązaniem AdRoll i ograniczana na jego podstawie.</span><span class="sxs-lookup"><span data-stu-id="adf37-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="adf37-137">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="adf37-137">Data privacy and compliance</span></span>

<span data-ttu-id="adf37-138">Po włączeniu aplikacji Dynamics 365 Customer Insights w celu transmisji danych do usługi AdRoll można przesyłać dane spoza granicy zgodności dla aplikacji Dynamics 365 Customer Insights, w tym również dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="adf37-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="adf37-139">Microsoft prześle takie dane na Twoje polecenie, ale Ty ponosisz odpowiedzialność za zapewnienie, że usługa AdRoll spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="adf37-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="adf37-140">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="adf37-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="adf37-141">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="adf37-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
