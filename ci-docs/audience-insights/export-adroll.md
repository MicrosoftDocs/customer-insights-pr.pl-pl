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
ms.openlocfilehash: e8f4d4ee6b2c6cdec513b700641db568fa16076d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895972"
---
# <a name="export-segment-lists-to-adroll-preview"></a><span data-ttu-id="23060-103">Eksportowanie list segmentów do usługi AdRoll (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="23060-103">Export segment lists to AdRoll (preview)</span></span>

<span data-ttu-id="23060-104">Eksportuj segmenty ujednoliconych profilów klientów do rozwiązania AdRoll i używaj ich w celach reklamowych.</span><span class="sxs-lookup"><span data-stu-id="23060-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="23060-105">Wymagania wstępne dla połączenia</span><span class="sxs-lookup"><span data-stu-id="23060-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="23060-106">Masz [konto rozwiązania AdRoll](https://www.adroll.com/) i odpowiadające mu poświadczenia administratora.</span><span class="sxs-lookup"><span data-stu-id="23060-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="23060-107">Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.</span><span class="sxs-lookup"><span data-stu-id="23060-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="23060-108">Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="23060-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="23060-109">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="23060-109">Known limitations</span></span>

- <span data-ttu-id="23060-110">Do rozwiązania AdRoll możesz wyeksportować łącznie do 250 000 profilów na operację eksportu.</span><span class="sxs-lookup"><span data-stu-id="23060-110">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="23060-111">Nie można eksportować segmentów obejmujących mniej niż 100 profilów do rozwiązania AdRoll.</span><span class="sxs-lookup"><span data-stu-id="23060-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="23060-112">Eksport do rozwiązania AdRoll jest ograniczony do segmentów.</span><span class="sxs-lookup"><span data-stu-id="23060-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="23060-113">Wyeksportowanie do 250 000 profilów do rozwiązania AdRoll może potrwać do 10 minut.</span><span class="sxs-lookup"><span data-stu-id="23060-113">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="23060-114">Liczba profilów, które można eksportować do rozwiązania AdRoll, jest zależna od kontraktu z rozwiązaniem AdRoll i ograniczana na jego podstawie.</span><span class="sxs-lookup"><span data-stu-id="23060-114">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="23060-115">Skonfiguruj połączenie z usługą AdRoll</span><span class="sxs-lookup"><span data-stu-id="23060-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="23060-116">Przejdź do **Admin** > **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="23060-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="23060-117">Wybierz opcję **Dodaj połączenie** i wybierz opcję **AdRoll**, aby skonfigurować połączenie.</span><span class="sxs-lookup"><span data-stu-id="23060-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="23060-118">W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="23060-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="23060-119">Wyświetlana nazwa i typ połączenia opisują to połączenie.</span><span class="sxs-lookup"><span data-stu-id="23060-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="23060-120">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.</span><span class="sxs-lookup"><span data-stu-id="23060-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="23060-121">Określ, kto może używać tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="23060-121">Choose who can use this connection.</span></span> <span data-ttu-id="23060-122">Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy.</span><span class="sxs-lookup"><span data-stu-id="23060-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="23060-123">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="23060-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="23060-124">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.</span><span class="sxs-lookup"><span data-stu-id="23060-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="23060-125">Wybierz opcję **Połącz**, aby zainicjować połączenie z rozwiązaniem AdRoll.</span><span class="sxs-lookup"><span data-stu-id="23060-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="23060-126">Wybierz opcję **Uwierzytelnij za pomocą rozwiązania AdRoll** i podaj poświadczenia administratora dla rozwiązania AdRoll.</span><span class="sxs-lookup"><span data-stu-id="23060-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="23060-127">Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="23060-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="23060-128">Aby zakończyć połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="23060-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="23060-129">Konfigurowanie eksportu</span><span class="sxs-lookup"><span data-stu-id="23060-129">Configure an export</span></span>

<span data-ttu-id="23060-130">Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="23060-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="23060-131">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="23060-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="23060-132">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="23060-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="23060-133">Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="23060-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="23060-134">W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi AdRoll.</span><span class="sxs-lookup"><span data-stu-id="23060-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="23060-135">Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="23060-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="23060-136">Aby uzyskać więcej informacji, wprowadź **identyfikator reklamodawcy AdRoll**. Więcej informacji znajdziesz w [profilach reklamodawcy AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="23060-136">Enter your **AdRoll Advertiser ID** For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="23060-137">W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta.</span><span class="sxs-lookup"><span data-stu-id="23060-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="23060-138">Wyeksportowanie segmentów do rozwiązania AdRoll jest wymagane.</span><span class="sxs-lookup"><span data-stu-id="23060-138">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="23060-139">Wybierz segmenty, które chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="23060-139">Select the segments you want to export.</span></span> <span data-ttu-id="23060-140">Wybierz segment obejmujący co najmniej 100 członków.</span><span class="sxs-lookup"><span data-stu-id="23060-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="23060-141">Nie można eksportować mniejszych segmentów.</span><span class="sxs-lookup"><span data-stu-id="23060-141">You can't export smaller segments.</span></span> <span data-ttu-id="23060-142">Dodatkowo maksymalny rozmiar eksportowanego segmentu wynosi 250 000 członków na operację eksportu.</span><span class="sxs-lookup"><span data-stu-id="23060-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="23060-143">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="23060-143">Select **Save**.</span></span>

<span data-ttu-id="23060-144">Zapisanie eksportu nie uruchamia natychmiastowo eksportu.</span><span class="sxs-lookup"><span data-stu-id="23060-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="23060-145">Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="23060-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="23060-146">Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="23060-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="23060-147">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="23060-147">Data privacy and compliance</span></span>

<span data-ttu-id="23060-148">Po włączeniu aplikacji Dynamics 365 Customer Insights w celu transmisji danych do usługi AdRoll można przesyłać dane spoza granicy zgodności dla aplikacji Dynamics 365 Customer Insights, w tym również dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="23060-148">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="23060-149">Microsoft prześle takie dane na Twoje polecenie, ale Ty ponosisz odpowiedzialność za zapewnienie, że usługa AdRoll spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="23060-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="23060-150">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="23060-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="23060-151">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="23060-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
