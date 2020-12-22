---
title: Eksportowanie danych Customer Insights do usługi Mailchimp
description: Dowiedz się, jak skonfigurować połączenie z Mailchimp.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: edff494f6edf26a8b641cb1d788a715389ddb346
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406554"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="8325e-103">Łącznik dla usługi Mailchimp (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="8325e-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="8325e-104">Wyeksportowane segmenty zunifikowanych profilów klientów umożliwiają MailChimp tworzenie biuletynów i kampanii za pośrednictwem poczty e-mail.</span><span class="sxs-lookup"><span data-stu-id="8325e-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8325e-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="8325e-105">Prerequisites</span></span>

-   <span data-ttu-id="8325e-106">Użytkownik ma [konto usługi Mailchimp](https://mailchimp.com/) i odpowiadające mu poświadczenia administratora.</span><span class="sxs-lookup"><span data-stu-id="8325e-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="8325e-107">W Mailchimp istnieją już odbiorcy i odpowiadające im identyfikatory.</span><span class="sxs-lookup"><span data-stu-id="8325e-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="8325e-108">Aby uzyskać więcej informacji, zobacz temat [Odbiorcy Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="8325e-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="8325e-109">Posiadasz [skonfigurowane segmenty](segments.md)</span><span class="sxs-lookup"><span data-stu-id="8325e-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="8325e-110">Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="8325e-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="8325e-111">Połącz z usługą Mailchimp</span><span class="sxs-lookup"><span data-stu-id="8325e-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="8325e-112">Przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.</span><span class="sxs-lookup"><span data-stu-id="8325e-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="8325e-113">W **Mailchimp** wybierz **Konfiguruj**.</span><span class="sxs-lookup"><span data-stu-id="8325e-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="8325e-114">W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej exportu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="8325e-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="8325e-115">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.</span><span class="sxs-lookup"><span data-stu-id="8325e-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8325e-116">Wprowadź **[identyfikator odbiorcy usługi Mailchimp](https://mailchimp.com/help/find-audience-id/)** i wybierz pozycję **Połącz**, aby zainicjować połączenie z usługą Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="8325e-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="8325e-117">Wybierz **Uwierzytelnianie za pomocą usługi Mailchimp** i przekaż swoje poświadczenia w usłudze Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="8325e-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="8325e-118">Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8325e-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Eksportuj zrzut ekranu dla połączenia z Mailchimp":::

1. <span data-ttu-id="8325e-120">Wybierz **Dalej**, aby skonfigurować eksport.</span><span class="sxs-lookup"><span data-stu-id="8325e-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="8325e-121">Skonfiguruj łącznik</span><span class="sxs-lookup"><span data-stu-id="8325e-121">Configure the connector</span></span>

1. <span data-ttu-id="8325e-122">W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta.</span><span class="sxs-lookup"><span data-stu-id="8325e-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="8325e-123">Można też eksportować **imię** i **Nazwisko** jako dodatkowe pola, aby utworzyć bardziej spersonalizowane wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="8325e-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="8325e-124">Wybierz opcję **Dodaj atrybut**, aby zamapować te pola.</span><span class="sxs-lookup"><span data-stu-id="8325e-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="8325e-125">Wybierz segmenty, które chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="8325e-125">Select the segments you want to export.</span></span> <span data-ttu-id="8325e-126">W sumie do maksymalnie 1 000 000 profilów klientów można wyeksportować do Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="8325e-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Wybieranie pól i segmentów do wyeksportowania do Mailchimp":::

1. <span data-ttu-id="8325e-128">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="8325e-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="8325e-129">Eksportowanie danych</span><span class="sxs-lookup"><span data-stu-id="8325e-129">Export the data</span></span>

<span data-ttu-id="8325e-130">Możesz [eksportować dane na żądanie](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="8325e-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="8325e-131">Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8325e-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8325e-132">W Mailchimp można znaleźć segmenty na [odbiorcy Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="8325e-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8325e-133">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="8325e-133">Known limitations</span></span>

- <span data-ttu-id="8325e-134">Do 1 miliona profili na eksport do Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="8325e-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="8325e-135">Eksport do Mailchimp jest ograniczony do segmentów.</span><span class="sxs-lookup"><span data-stu-id="8325e-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="8325e-136">Eksportowanie segmentów zawierających łącznie 1 milion profili może zająć do trzech godzin ze względu na ograniczenia po stronie dostawcy.</span><span class="sxs-lookup"><span data-stu-id="8325e-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="8325e-137">Liczba profilów, które można eksportować do Mailchimp, jest zależna od kontraktu i ograniczona jego Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="8325e-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8325e-138">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="8325e-138">Data privacy and compliance</span></span>

<span data-ttu-id="8325e-139">Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Mailchimp można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="8325e-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8325e-140">Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że Mailchimp spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="8325e-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8325e-141">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8325e-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8325e-142">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="8325e-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
