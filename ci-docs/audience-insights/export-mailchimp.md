---
title: Eksportowanie danych Customer Insights do usługi Mailchimp
description: Dowiedz się, jak skonfigurować połączenie i eksport do programu Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 35848998e738c7ecc1642f2b75912ff78d85f79e
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976168"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a><span data-ttu-id="f7987-103">Eksportowanie list segmentów do usługi Mailchimp (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="f7987-103">Export segment lists to Mailchimp (preview)</span></span>

<span data-ttu-id="f7987-104">Wyeksportowane segmenty zunifikowanych profilów klientów umożliwiają MailChimp tworzenie biuletynów i kampanii za pośrednictwem poczty e-mail.</span><span class="sxs-lookup"><span data-stu-id="f7987-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="f7987-105">Wymagania wstępne dla połączenia</span><span class="sxs-lookup"><span data-stu-id="f7987-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="f7987-106">Użytkownik ma [konto usługi Mailchimp](https://mailchimp.com/) i odpowiadające mu poświadczenia administratora.</span><span class="sxs-lookup"><span data-stu-id="f7987-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f7987-107">W Mailchimp istnieją już odbiorcy i odpowiadające im identyfikatory.</span><span class="sxs-lookup"><span data-stu-id="f7987-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="f7987-108">Aby uzyskać więcej informacji, zobacz temat [Odbiorcy Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="f7987-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="f7987-109">Posiadasz [skonfigurowane segmenty](segments.md)</span><span class="sxs-lookup"><span data-stu-id="f7987-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="f7987-110">Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="f7987-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f7987-111">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="f7987-111">Known limitations</span></span>

- <span data-ttu-id="f7987-112">Do 1 miliona profili na eksport do Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="f7987-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="f7987-113">Eksport do Mailchimp jest ograniczony do segmentów.</span><span class="sxs-lookup"><span data-stu-id="f7987-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="f7987-114">Eksportowanie segmentów z 1 milionem profili może potrwać do trzech godzin.</span><span class="sxs-lookup"><span data-stu-id="f7987-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="f7987-115">Liczba profilów, które można eksportować do Mailchimp, jest zależna od kontraktu i ograniczona jego Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="f7987-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="f7987-116">Skonfiguruj połączenie z usługą Mailchimp</span><span class="sxs-lookup"><span data-stu-id="f7987-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="f7987-117">Przejdź do **Admin** > **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="f7987-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f7987-118">Wybierz opcję **Dodaj połączenie** i wybierz opcję **Autopilot**, aby skonfigurować połączenie.</span><span class="sxs-lookup"><span data-stu-id="f7987-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="f7987-119">W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="f7987-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f7987-120">Wyświetlana nazwa i typ połączenia opisują to połączenie.</span><span class="sxs-lookup"><span data-stu-id="f7987-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f7987-121">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.</span><span class="sxs-lookup"><span data-stu-id="f7987-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f7987-122">Określ, kto może używać tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="f7987-122">Choose who can use this connection.</span></span> <span data-ttu-id="f7987-123">Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy.</span><span class="sxs-lookup"><span data-stu-id="f7987-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f7987-124">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f7987-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f7987-125">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.</span><span class="sxs-lookup"><span data-stu-id="f7987-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f7987-126">Wybierz opcję **Połącz**, aby inicjować połączenie z usługą Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="f7987-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="f7987-127">Wybierz **Uwierzytelnianie za pomocą usługi Mailchimp** i przekaż swoje poświadczenia w usłudze Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="f7987-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="f7987-128">Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f7987-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f7987-129">Aby zakończyć połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f7987-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="f7987-130">Skonfiguruj łącznik</span><span class="sxs-lookup"><span data-stu-id="f7987-130">Configure the connector</span></span>

<span data-ttu-id="f7987-131">Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="f7987-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f7987-132">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f7987-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f7987-133">Przejdź do **Dane**> **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="f7987-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="f7987-134">Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="f7987-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f7987-135">W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="f7987-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="f7987-136">Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="f7987-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="f7987-137">Wpisz swój **[Identyfikator odbiorcy usługi MailChimp](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="f7987-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="f7987-138">W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta.</span><span class="sxs-lookup"><span data-stu-id="f7987-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="f7987-139">Opcjonalnie możesz wyeksportować **Imię** i **Nazwisko**, aby utworzyć bardziej spersonalizowane wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="f7987-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="f7987-140">Wybierz opcję **Dodaj atrybut**, aby zamapować te pola.</span><span class="sxs-lookup"><span data-stu-id="f7987-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="f7987-141">Wybierz segmenty, które chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="f7987-141">Select the segments you want to export.</span></span> <span data-ttu-id="f7987-142">W sumie do maksymalnie 1 000 000 profilów klientów można wyeksportować do Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="f7987-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="f7987-143">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f7987-143">Select **Save**.</span></span>

<span data-ttu-id="f7987-144">Zapisanie eksportu nie uruchamia natychmiastowo eksportu.</span><span class="sxs-lookup"><span data-stu-id="f7987-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f7987-145">Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f7987-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f7987-146">Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f7987-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f7987-147">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="f7987-147">Data privacy and compliance</span></span>

<span data-ttu-id="f7987-148">Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Mailchimp można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="f7987-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f7987-149">Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że Mailchimp spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="f7987-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f7987-150">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f7987-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f7987-151">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="f7987-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
