---
title: Eksportowanie danych aplikacji Customer Insights do rozwiązania AdRoll
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 67bfa23d56b26ae592efa4d7197713664bb02623
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304846"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="ccb51-103">Eksportowanie segmentów do usługi AdRoll (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="ccb51-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="ccb51-104">Eksportuj segmenty ujednoliconych profilów klientów do rozwiązania AdRoll i używaj ich w celach reklamowych.</span><span class="sxs-lookup"><span data-stu-id="ccb51-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="ccb51-105">Wymagania wstępne dla połączenia</span><span class="sxs-lookup"><span data-stu-id="ccb51-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="ccb51-106">Masz [konto rozwiązania AdRoll](https://www.adroll.com/) i odpowiadające mu poświadczenia administratora.</span><span class="sxs-lookup"><span data-stu-id="ccb51-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ccb51-107">Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.</span><span class="sxs-lookup"><span data-stu-id="ccb51-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ccb51-108">Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="ccb51-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ccb51-109">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="ccb51-109">Known limitations</span></span>

- <span data-ttu-id="ccb51-110">Jednocześnie do AdRoll można eksportować maksymalnie 250 000 profili.</span><span class="sxs-lookup"><span data-stu-id="ccb51-110">You can export up to 250,000 profiles at a time to AdRoll.</span></span>
- <span data-ttu-id="ccb51-111">Nie można eksportować segmentów obejmujących mniej niż 100 profilów do rozwiązania AdRoll.</span><span class="sxs-lookup"><span data-stu-id="ccb51-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="ccb51-112">Eksport do rozwiązania AdRoll jest ograniczony do segmentów.</span><span class="sxs-lookup"><span data-stu-id="ccb51-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="ccb51-113">Wyeksportowanie do 250 000 profili do rozwiązania AdRoll może potrwać do 10 minut.</span><span class="sxs-lookup"><span data-stu-id="ccb51-113">Exporting up to 250,000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="ccb51-114">Liczba profili, które możesz wyeksportować do AdRoll jest zależna od Twojej umowy z AdRoll.</span><span class="sxs-lookup"><span data-stu-id="ccb51-114">The number of profiles that you can export to AdRoll is dependent on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="ccb51-115">Skonfiguruj połączenie z usługą AdRoll</span><span class="sxs-lookup"><span data-stu-id="ccb51-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="ccb51-116">Przejdź do **Admin** > **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="ccb51-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ccb51-117">Wybierz opcję **Dodaj połączenie** i wybierz opcję **AdRoll**, aby skonfigurować połączenie.</span><span class="sxs-lookup"><span data-stu-id="ccb51-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="ccb51-118">W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="ccb51-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ccb51-119">Wyświetlana nazwa i typ połączenia opisują to połączenie.</span><span class="sxs-lookup"><span data-stu-id="ccb51-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ccb51-120">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.</span><span class="sxs-lookup"><span data-stu-id="ccb51-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ccb51-121">Określ, kto może używać tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="ccb51-121">Choose who can use this connection.</span></span> <span data-ttu-id="ccb51-122">Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy.</span><span class="sxs-lookup"><span data-stu-id="ccb51-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ccb51-123">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ccb51-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ccb51-124">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.</span><span class="sxs-lookup"><span data-stu-id="ccb51-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ccb51-125">Wybierz opcję **Połącz**, aby zainicjować połączenie z rozwiązaniem AdRoll.</span><span class="sxs-lookup"><span data-stu-id="ccb51-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="ccb51-126">Wybierz opcję **Uwierzytelnij za pomocą rozwiązania AdRoll** i podaj poświadczenia administratora dla rozwiązania AdRoll.</span><span class="sxs-lookup"><span data-stu-id="ccb51-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="ccb51-127">Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ccb51-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ccb51-128">Aby zakończyć połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ccb51-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ccb51-129">Konfigurowanie eksportu</span><span class="sxs-lookup"><span data-stu-id="ccb51-129">Configure an export</span></span>

<span data-ttu-id="ccb51-130">Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="ccb51-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ccb51-131">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ccb51-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ccb51-132">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="ccb51-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ccb51-133">Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="ccb51-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ccb51-134">W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi AdRoll.</span><span class="sxs-lookup"><span data-stu-id="ccb51-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="ccb51-135">Jeśli nie widzisz tej nazwy sekcji, to znaczy, że nie masz dostępu do żadnych połączeń tego typu.</span><span class="sxs-lookup"><span data-stu-id="ccb51-135">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="ccb51-136">Wprowadź identyfikator **Reklamodawcy AdRoll**.</span><span class="sxs-lookup"><span data-stu-id="ccb51-136">Enter your **AdRoll Advertiser ID**.</span></span> <span data-ttu-id="ccb51-137">Aby uzyskać więcej informacji, zobacz [Profile reklamodawców AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="ccb51-137">For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="ccb51-138">W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta.</span><span class="sxs-lookup"><span data-stu-id="ccb51-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ccb51-139">Wyeksportowanie segmentów do rozwiązania AdRoll jest wymagane.</span><span class="sxs-lookup"><span data-stu-id="ccb51-139">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="ccb51-140">Wybierz segmenty, które chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="ccb51-140">Select the segments you want to export.</span></span> <span data-ttu-id="ccb51-141">Wybierz segment obejmujący co najmniej 100 członków.</span><span class="sxs-lookup"><span data-stu-id="ccb51-141">Select a segment with a least 100 members.</span></span> <span data-ttu-id="ccb51-142">Nie można eksportować mniejszych segmentów.</span><span class="sxs-lookup"><span data-stu-id="ccb51-142">You can't export smaller segments.</span></span> <span data-ttu-id="ccb51-143">Dodatkowo maksymalny rozmiar eksportowanego segmentu wynosi 250 000 członków na operację eksportu.</span><span class="sxs-lookup"><span data-stu-id="ccb51-143">Additionally the maximum size of a segment to export is 250,000 members per export.</span></span> 

1. <span data-ttu-id="ccb51-144">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ccb51-144">Select **Save**.</span></span>

<span data-ttu-id="ccb51-145">Zapisanie eksportu nie uruchamia natychmiastowo eksportu.</span><span class="sxs-lookup"><span data-stu-id="ccb51-145">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ccb51-146">Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ccb51-146">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="ccb51-147">Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ccb51-147">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ccb51-148">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="ccb51-148">Data privacy and compliance</span></span>

<span data-ttu-id="ccb51-149">Po włączeniu aplikacji Dynamics 365 Customer Insights w celu transmisji danych do usługi AdRoll można przesyłać dane spoza granicy zgodności dla aplikacji Dynamics 365 Customer Insights, w tym również dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="ccb51-149">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ccb51-150">Microsoft prześle takie dane na Twoje polecenie, ale Ty ponosisz odpowiedzialność za zapewnienie, że usługa AdRoll spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="ccb51-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ccb51-151">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ccb51-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="ccb51-152">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="ccb51-152">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
