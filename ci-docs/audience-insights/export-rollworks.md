---
title: Eksportowanie danych usługi Customer Insights do usługi RollWorks
description: Dowiedz się, jak skonfigurować połączenie i eksport do programu RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dce5d51ca4587b4d7a0644cc701c1826854882b5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124102"
---
# <a name="export-segments-to-rollworks-preview"></a><span data-ttu-id="e4e97-103">Eksportowanie segmentów do usługi RollWorks (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="e4e97-103">Export segments to RollWorks (preview)</span></span>

<span data-ttu-id="e4e97-104">Wyeksportuj segmenty ujednoliconych profilów klientów do usługi RollWorks i użyj ich w celach reklamowych.</span><span class="sxs-lookup"><span data-stu-id="e4e97-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="e4e97-105">Wymagania wstępne dla połączenia</span><span class="sxs-lookup"><span data-stu-id="e4e97-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="e4e97-106">Użytkownik ma konto [Kontakt administracyjny usługi RollWorks](https://www.rollworks.com/) i odpowiednie dane logowania administratora.</span><span class="sxs-lookup"><span data-stu-id="e4e97-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e4e97-107">Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.</span><span class="sxs-lookup"><span data-stu-id="e4e97-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="e4e97-108">Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="e4e97-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e4e97-109">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="e4e97-109">Known limitations</span></span>

- <span data-ttu-id="e4e97-110">Do usługi RollWorks można wyeksportować do 250 000 profili.</span><span class="sxs-lookup"><span data-stu-id="e4e97-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="e4e97-111">Do usługi RollWorks nie można eksportować segmentów o liczbie mniejszej niż 100 profilów.</span><span class="sxs-lookup"><span data-stu-id="e4e97-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="e4e97-112">Eksportowanie do usługi RollWorks jest ograniczone do segmentów.</span><span class="sxs-lookup"><span data-stu-id="e4e97-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="e4e97-113">Wyeksportowanie do 250 000 profilów do usługi RollWorks może potrwać do 10 minut.</span><span class="sxs-lookup"><span data-stu-id="e4e97-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="e4e97-114">Liczba profilów, które można eksportować usługi RollWorks, jest ograniczona i zależy od kontraktu użytkownika z usługą RollWorks.</span><span class="sxs-lookup"><span data-stu-id="e4e97-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="e4e97-115">Skonfiguruj połączenie z usługą RollWorks</span><span class="sxs-lookup"><span data-stu-id="e4e97-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="e4e97-116">Przejdź do **Admin** > **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="e4e97-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e4e97-117">Wybierz opcję **Dodaj połączenie** i wybierz opcję **RollWorks**, aby skonfigurować połączenie.</span><span class="sxs-lookup"><span data-stu-id="e4e97-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="e4e97-118">W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="e4e97-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e4e97-119">Wyświetlana nazwa i typ połączenia opisują to połączenie.</span><span class="sxs-lookup"><span data-stu-id="e4e97-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e4e97-120">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.</span><span class="sxs-lookup"><span data-stu-id="e4e97-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e4e97-121">Określ, kto może używać tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="e4e97-121">Choose who can use this connection.</span></span> <span data-ttu-id="e4e97-122">Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy.</span><span class="sxs-lookup"><span data-stu-id="e4e97-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e4e97-123">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e4e97-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e4e97-124">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.</span><span class="sxs-lookup"><span data-stu-id="e4e97-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e4e97-125">Wybierz opcję **Połącz**, aby inicjować połączenie z usługą RollWorks.</span><span class="sxs-lookup"><span data-stu-id="e4e97-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="e4e97-126">Wybierz opcję **Uwierzytelnij za pomocą usługi RollWorks** i podaj swoje poświadczenia administratora dla usługi RollWorks.</span><span class="sxs-lookup"><span data-stu-id="e4e97-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="e4e97-127">Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e4e97-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e4e97-128">Aby zakończyć połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="e4e97-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e4e97-129">Konfigurowanie eksportu</span><span class="sxs-lookup"><span data-stu-id="e4e97-129">Configure an export</span></span>

<span data-ttu-id="e4e97-130">Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="e4e97-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e4e97-131">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e4e97-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e4e97-132">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="e4e97-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e4e97-133">Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="e4e97-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e4e97-134">W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi RollWorks.</span><span class="sxs-lookup"><span data-stu-id="e4e97-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="e4e97-135">Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="e4e97-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e4e97-136">Wprowadź **Identyfikator raklamodawcy w usłudze RollWorks** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="e4e97-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="e4e97-137">W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta.</span><span class="sxs-lookup"><span data-stu-id="e4e97-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="e4e97-138">Wymagane jest wyeksportowanie segmentów do usługi RollWorks.</span><span class="sxs-lookup"><span data-stu-id="e4e97-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="e4e97-139">Wybierz segmenty, które chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="e4e97-139">Select the segments you want to export.</span></span> <span data-ttu-id="e4e97-140">Wybierz segment obejmujący co najmniej 100 członków.</span><span class="sxs-lookup"><span data-stu-id="e4e97-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="e4e97-141">Nie można eksportować mniejszych segmentów.</span><span class="sxs-lookup"><span data-stu-id="e4e97-141">You can't export smaller segments.</span></span> <span data-ttu-id="e4e97-142">Dodatkowo maksymalny rozmiar eksportowanego segmentu wynosi 250 000 członków na operację eksportu.</span><span class="sxs-lookup"><span data-stu-id="e4e97-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="e4e97-143">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="e4e97-143">Select **Save**.</span></span>

<span data-ttu-id="e4e97-144">Zapisanie eksportu nie uruchamia natychmiastowo eksportu.</span><span class="sxs-lookup"><span data-stu-id="e4e97-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e4e97-145">Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e4e97-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e4e97-146">Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e4e97-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e4e97-147">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="e4e97-147">Data privacy and compliance</span></span>

<span data-ttu-id="e4e97-148">Włączenie rozwiązania Dynamics 365 Customer Insights do przekazywania danych do usługi RollWorks umożliwia przesyłanie danych poza granicą zgodności z przepisami Dynamics 365 Customer Insights, w tym potencjalnie poufnych danych, takich jak dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="e4e97-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e4e97-149">Microsoft przesyła takie dane zgodnie z instrukcjami użytkownika, ale użytkownik musi zagwarantować, że usługa RollWorks będzie spełniać wszelkie zobowiązania dotyczące prywatności lub bezpieczeństwa, jakie może mieć użytkownik.</span><span class="sxs-lookup"><span data-stu-id="e4e97-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e4e97-150">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e4e97-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="e4e97-151">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="e4e97-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
