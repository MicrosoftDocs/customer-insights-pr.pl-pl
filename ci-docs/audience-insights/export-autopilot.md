---
title: Eksportowanie danych Customer Insights do usługi Autopilot
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760156"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="66d21-103">Eksportowanie segmentów do programu Autopilot (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="66d21-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="66d21-104">Eksportuj segmenty ujednoliconych profili klientów do Autopilota i używaj ich do marketingu e-mailowego w Autopilocie.</span><span class="sxs-lookup"><span data-stu-id="66d21-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="66d21-105">Wymagania wstępne dla połączenia</span><span class="sxs-lookup"><span data-stu-id="66d21-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="66d21-106">Użytkownik ma [konto usługi Autopilot](https://www.autopilothq.com/) i odpowiadające mu poświadczenia administratora.</span><span class="sxs-lookup"><span data-stu-id="66d21-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="66d21-107">Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.</span><span class="sxs-lookup"><span data-stu-id="66d21-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="66d21-108">Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="66d21-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="66d21-109">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="66d21-109">Known limitations</span></span>

- <span data-ttu-id="66d21-110">Możesz wyeksportować łącznie do 100 000 profili do Autopilota.</span><span class="sxs-lookup"><span data-stu-id="66d21-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="66d21-111">Eksport do Autopilot jest ograniczony do segmentów.</span><span class="sxs-lookup"><span data-stu-id="66d21-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="66d21-112">Eksportowanie do 100 000 profili do Autopilota może zająć do kilku godzin.</span><span class="sxs-lookup"><span data-stu-id="66d21-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="66d21-113">Liczba profilów, które można eksportować do Autopilot, jest zależna od kontraktu i ograniczona jego Autopilot.</span><span class="sxs-lookup"><span data-stu-id="66d21-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="66d21-114">Skonfiguruj połączenie z usługą Autopilot</span><span class="sxs-lookup"><span data-stu-id="66d21-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="66d21-115">Przejdź do **Admin** > **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="66d21-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="66d21-116">Wybierz opcję **Dodaj połączenie** i wybierz opcję **Autopilot**, aby skonfigurować połączenie.</span><span class="sxs-lookup"><span data-stu-id="66d21-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="66d21-117">W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="66d21-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="66d21-118">Wyświetlana nazwa i typ połączenia opisują to połączenie.</span><span class="sxs-lookup"><span data-stu-id="66d21-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="66d21-119">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.</span><span class="sxs-lookup"><span data-stu-id="66d21-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="66d21-120">Określ, kto może używać tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="66d21-120">Choose who can use this connection.</span></span> <span data-ttu-id="66d21-121">Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy.</span><span class="sxs-lookup"><span data-stu-id="66d21-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="66d21-122">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="66d21-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="66d21-123">Wprowadź [klucz interfejsu API Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="66d21-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="66d21-124">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.</span><span class="sxs-lookup"><span data-stu-id="66d21-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="66d21-125">Wybierz opcję **Połącz**, aby zainicjować połączenie z Autopilot.</span><span class="sxs-lookup"><span data-stu-id="66d21-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="66d21-126">Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="66d21-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="66d21-127">Aby zakończyć połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="66d21-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="66d21-128">Konfigurowanie eksportu</span><span class="sxs-lookup"><span data-stu-id="66d21-128">Configure an export</span></span>

<span data-ttu-id="66d21-129">Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="66d21-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="66d21-130">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="66d21-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="66d21-131">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="66d21-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="66d21-132">Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="66d21-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="66d21-133">W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Autopilot.</span><span class="sxs-lookup"><span data-stu-id="66d21-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="66d21-134">Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="66d21-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="66d21-135">W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta.</span><span class="sxs-lookup"><span data-stu-id="66d21-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="66d21-136">Powtórz te kroki dla innych pól opcjonalnych, takich jak **Imię**, **Nazwisko**.</span><span class="sxs-lookup"><span data-stu-id="66d21-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="66d21-137">Wybierz segmenty, które chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="66d21-137">Select the segments you want to export.</span></span> <span data-ttu-id="66d21-138">Zdecydowanie **zalecamy, aby nie eksportować łącznie ponad 100 000 profili klientów** do Autopilota.</span><span class="sxs-lookup"><span data-stu-id="66d21-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="66d21-139">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="66d21-139">Select **Save**.</span></span>

<span data-ttu-id="66d21-140">Zapisanie eksportu nie uruchamia natychmiastowo eksportu.</span><span class="sxs-lookup"><span data-stu-id="66d21-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="66d21-141">Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="66d21-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="66d21-142">Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="66d21-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="66d21-143">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="66d21-143">Data privacy and compliance</span></span>

<span data-ttu-id="66d21-144">Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Autopilot można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="66d21-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="66d21-145">Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że Autopilot spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="66d21-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="66d21-146">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="66d21-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="66d21-147">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="66d21-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
