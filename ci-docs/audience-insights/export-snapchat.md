---
title: Eksportowanie danych usługi Customer Insights do usługi Snapchat
description: Dowiedz się, jak skonfigurować połączenie i eksport do programu Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6565ab81599abcc0f94465e1153f08e0bc119839
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124056"
---
# <a name="export-segments-to-snapchat-preview"></a><span data-ttu-id="b3e84-103">Eksportowanie segmentów do usługi Snapchat (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="b3e84-103">Export segments to Snapchat (preview)</span></span>

<span data-ttu-id="b3e84-104">Wyeksportuj segmenty ujednoliconych profilów klientów do usługi Snapchat i użyj ich w celach reklamowych.</span><span class="sxs-lookup"><span data-stu-id="b3e84-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="b3e84-105">Wymagania wstępne dla połączenia</span><span class="sxs-lookup"><span data-stu-id="b3e84-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="b3e84-106">Posiadasz konto [konto biznesowe Snapchat](https://business.snapchat.com/), [konto reklamowe Snapchat](https://ads.snapchat.com/) i odpowiednie dane logowania administratora.</span><span class="sxs-lookup"><span data-stu-id="b3e84-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b3e84-107">Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.</span><span class="sxs-lookup"><span data-stu-id="b3e84-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="b3e84-108">Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="b3e84-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b3e84-109">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="b3e84-109">Known limitations</span></span>

- <span data-ttu-id="b3e84-110">Eksportowanie do usługi Snapchat jest ograniczone do segmentów.</span><span class="sxs-lookup"><span data-stu-id="b3e84-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="b3e84-111">Wyeksportowanie do 1 miliona profilów do usługi Snapchat może potrwać do 15 minut.</span><span class="sxs-lookup"><span data-stu-id="b3e84-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="b3e84-112">Skonfiguruj połączenie z usługą Snapchat</span><span class="sxs-lookup"><span data-stu-id="b3e84-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="b3e84-113">Przejdź do **Admin** > **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="b3e84-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b3e84-114">Wybierz opcję **Dodaj połączenie** i wybierz opcję **Snapchat**, aby skonfigurować połączenie.</span><span class="sxs-lookup"><span data-stu-id="b3e84-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="b3e84-115">W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="b3e84-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b3e84-116">Wyświetlana nazwa i typ połączenia opisują to połączenie.</span><span class="sxs-lookup"><span data-stu-id="b3e84-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b3e84-117">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.</span><span class="sxs-lookup"><span data-stu-id="b3e84-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b3e84-118">Określ, kto może używać tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="b3e84-118">Choose who can use this connection.</span></span> <span data-ttu-id="b3e84-119">Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy.</span><span class="sxs-lookup"><span data-stu-id="b3e84-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b3e84-120">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b3e84-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b3e84-121">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.</span><span class="sxs-lookup"><span data-stu-id="b3e84-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b3e84-122">Wybierz opcję **Połącz**, aby inicjować połączenie z usługą Snapchat.</span><span class="sxs-lookup"><span data-stu-id="b3e84-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="b3e84-123">Wybierz opcję **Uwierzytelnij za pomocą usługi Snapchat** i podaj swoje poświadczenia administratora dla usługi Snapchat.</span><span class="sxs-lookup"><span data-stu-id="b3e84-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="b3e84-124">Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b3e84-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="b3e84-125">Aby zakończyć połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="b3e84-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="b3e84-126">Konfigurowanie eksportu</span><span class="sxs-lookup"><span data-stu-id="b3e84-126">Configure an export</span></span>

<span data-ttu-id="b3e84-127">Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="b3e84-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b3e84-128">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b3e84-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b3e84-129">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="b3e84-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b3e84-130">Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="b3e84-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b3e84-131">W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Snapchat.</span><span class="sxs-lookup"><span data-stu-id="b3e84-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="b3e84-132">Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="b3e84-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b3e84-133">Wprowadź [**identyfikator odbiorcy usługi Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="b3e84-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="b3e84-134">W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta.</span><span class="sxs-lookup"><span data-stu-id="b3e84-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="b3e84-135">Wymagane jest wyeksportowanie segmentów do usługi Snapchat.</span><span class="sxs-lookup"><span data-stu-id="b3e84-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="b3e84-136">Wybierz segmenty, które chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="b3e84-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="b3e84-137">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="b3e84-137">Select **Save**.</span></span>

<span data-ttu-id="b3e84-138">Zapisanie eksportu nie uruchamia natychmiastowo eksportu.</span><span class="sxs-lookup"><span data-stu-id="b3e84-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b3e84-139">Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b3e84-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b3e84-140">Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b3e84-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b3e84-141">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="b3e84-141">Data privacy and compliance</span></span>

<span data-ttu-id="b3e84-142">Włączenie rozwiązania Dynamics 365 Customer Insights do przekazywania danych do usługi Snapchat umożliwia przesyłanie danych poza granicą zgodności z przepisami Dynamics 365 Customer Insights, w tym potencjalnie poufnych danych, takich jak dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="b3e84-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b3e84-143">Microsoft przesyła takie dane zgodnie z instrukcjami użytkownika, ale użytkownik musi zagwarantować, że usługa Snapchat będzie spełniać wszelkie zobowiązania dotyczące prywatności lub bezpieczeństwa, jakie może mieć użytkownik.</span><span class="sxs-lookup"><span data-stu-id="b3e84-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b3e84-144">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b3e84-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="b3e84-145">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="b3e84-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
