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
ms.openlocfilehash: d3dae7f0fef1fc3792c90c8ac0d3b037f5c0923d
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760600"
---
# <a name="export-segment-lists-to-snapchat-preview"></a><span data-ttu-id="17550-103">Eksportowanie list segmentów do usługi Snapchat (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="17550-103">Export segment lists to Snapchat (preview)</span></span>

<span data-ttu-id="17550-104">Wyeksportuj segmenty ujednoliconych profilów klientów do usługi Snapchat i użyj ich w celach reklamowych.</span><span class="sxs-lookup"><span data-stu-id="17550-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="17550-105">Wymagania wstępne dla połączenia</span><span class="sxs-lookup"><span data-stu-id="17550-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="17550-106">Posiadasz konto [konto biznesowe Snapchat](https://business.snapchat.com/), [konto reklamowe Snapchat](https://ads.snapchat.com/) i odpowiednie dane logowania administratora.</span><span class="sxs-lookup"><span data-stu-id="17550-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="17550-107">Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.</span><span class="sxs-lookup"><span data-stu-id="17550-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="17550-108">Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="17550-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="17550-109">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="17550-109">Known limitations</span></span>

- <span data-ttu-id="17550-110">Eksportowanie do usługi Snapchat jest ograniczone do segmentów.</span><span class="sxs-lookup"><span data-stu-id="17550-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="17550-111">Wyeksportowanie do 1 miliona profilów do usługi Snapchat może potrwać do 15 minut.</span><span class="sxs-lookup"><span data-stu-id="17550-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="17550-112">Skonfiguruj połączenie z usługą Snapchat</span><span class="sxs-lookup"><span data-stu-id="17550-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="17550-113">Przejdź do **Admin** > **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="17550-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="17550-114">Wybierz opcję **Dodaj połączenie** i wybierz opcję **Snapchat**, aby skonfigurować połączenie.</span><span class="sxs-lookup"><span data-stu-id="17550-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="17550-115">W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="17550-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="17550-116">Wyświetlana nazwa i typ połączenia opisują to połączenie.</span><span class="sxs-lookup"><span data-stu-id="17550-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="17550-117">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.</span><span class="sxs-lookup"><span data-stu-id="17550-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="17550-118">Określ, kto może używać tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="17550-118">Choose who can use this connection.</span></span> <span data-ttu-id="17550-119">Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy.</span><span class="sxs-lookup"><span data-stu-id="17550-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="17550-120">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="17550-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="17550-121">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.</span><span class="sxs-lookup"><span data-stu-id="17550-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="17550-122">Wybierz opcję **Połącz**, aby inicjować połączenie z usługą Snapchat.</span><span class="sxs-lookup"><span data-stu-id="17550-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="17550-123">Wybierz opcję **Uwierzytelnij za pomocą usługi Snapchat** i podaj swoje poświadczenia administratora dla usługi Snapchat.</span><span class="sxs-lookup"><span data-stu-id="17550-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="17550-124">Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="17550-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="17550-125">Aby zakończyć połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="17550-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="17550-126">Konfigurowanie eksportu</span><span class="sxs-lookup"><span data-stu-id="17550-126">Configure an export</span></span>

<span data-ttu-id="17550-127">Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="17550-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="17550-128">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="17550-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="17550-129">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="17550-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="17550-130">Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="17550-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="17550-131">W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Snapchat.</span><span class="sxs-lookup"><span data-stu-id="17550-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="17550-132">Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="17550-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="17550-133">Wprowadź [**identyfikator odbiorcy usługi Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="17550-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="17550-134">W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta.</span><span class="sxs-lookup"><span data-stu-id="17550-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="17550-135">Wymagane jest wyeksportowanie segmentów do usługi Snapchat.</span><span class="sxs-lookup"><span data-stu-id="17550-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="17550-136">Wybierz segmenty, które chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="17550-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="17550-137">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="17550-137">Select **Save**.</span></span>

<span data-ttu-id="17550-138">Zapisanie eksportu nie uruchamia natychmiastowo eksportu.</span><span class="sxs-lookup"><span data-stu-id="17550-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="17550-139">Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="17550-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="17550-140">Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="17550-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="17550-141">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="17550-141">Data privacy and compliance</span></span>

<span data-ttu-id="17550-142">Włączenie rozwiązania Dynamics 365 Customer Insights do przekazywania danych do usługi Snapchat umożliwia przesyłanie danych poza granicą zgodności z przepisami Dynamics 365 Customer Insights, w tym potencjalnie poufnych danych, takich jak dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="17550-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="17550-143">Microsoft przesyła takie dane zgodnie z instrukcjami użytkownika, ale użytkownik musi zagwarantować, że usługa Snapchat będzie spełniać wszelkie zobowiązania dotyczące prywatności lub bezpieczeństwa, jakie może mieć użytkownik.</span><span class="sxs-lookup"><span data-stu-id="17550-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="17550-144">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="17550-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="17550-145">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="17550-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
