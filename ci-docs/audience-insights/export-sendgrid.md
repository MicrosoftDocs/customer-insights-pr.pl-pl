---
title: Eksportowanie danych Customer Insights do usługi SendGrid
description: Dowiedz się, jak skonfigurować połączenie z SendGrid.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268745"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="f7ee1-103">Łącznik dla usługi SendGrid (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="f7ee1-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="f7ee1-104">Eksportuj segmenty ujednoliconych profili klientów do list kontaktów SendGrid i używaj ich do kampanii i marketingu e-mailowego w SendGrid.</span><span class="sxs-lookup"><span data-stu-id="f7ee1-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="f7ee1-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="f7ee1-105">Prerequisites</span></span>

-   <span data-ttu-id="f7ee1-106">Użytkownik ma [konto usługi SendGrid](https://sendgrid.com/) i odpowiadające mu poświadczenia administratora.</span><span class="sxs-lookup"><span data-stu-id="f7ee1-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f7ee1-107">Istnieją listy kontaktów w SendGrid i odpowiadające im identyfikatory.</span><span class="sxs-lookup"><span data-stu-id="f7ee1-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="f7ee1-108">Aby uzyskać więcej informacji, zobacz temat [SendGrid — Zarządzanie kontaktami](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="f7ee1-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="f7ee1-109">Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.</span><span class="sxs-lookup"><span data-stu-id="f7ee1-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="f7ee1-110">Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="f7ee1-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="f7ee1-111">Nawiązywanie połączenia z usługą SendGrid</span><span class="sxs-lookup"><span data-stu-id="f7ee1-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="f7ee1-112">Przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.</span><span class="sxs-lookup"><span data-stu-id="f7ee1-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f7ee1-113">W **SendGrid** wybierz **Konfiguruj**.</span><span class="sxs-lookup"><span data-stu-id="f7ee1-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="f7ee1-114">W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej exportu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="f7ee1-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Okienko konfiguracji eksportowania siatki SendGrid.":::

1. <span data-ttu-id="f7ee1-116">Wprowadź **Klucz interfejsu API SendGrid** [Klucz interfejsu API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="f7ee1-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="f7ee1-117">Wprowadź **[Identyfikator listy SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="f7ee1-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="f7ee1-118">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.</span><span class="sxs-lookup"><span data-stu-id="f7ee1-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f7ee1-119">Wybierz opcję **Połącz**, aby zainicjować połączenie z SendGrid.</span><span class="sxs-lookup"><span data-stu-id="f7ee1-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="f7ee1-120">Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f7ee1-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f7ee1-121">Wybierz **Dalej**, aby skonfigurować eksport.</span><span class="sxs-lookup"><span data-stu-id="f7ee1-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="f7ee1-122">Skonfiguruj łącznik</span><span class="sxs-lookup"><span data-stu-id="f7ee1-122">Configure the connector</span></span>

1. <span data-ttu-id="f7ee1-123">W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta.</span><span class="sxs-lookup"><span data-stu-id="f7ee1-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f7ee1-124">Powtórz te kroki dla innych pól opcjonalnych, takich jak **Imię**, **Nazwisko**, **Kraj/Region**, **Stan**, **Miasto** i **Kod pocztowy**.</span><span class="sxs-lookup"><span data-stu-id="f7ee1-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="f7ee1-125">Wybierz segmenty, które chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="f7ee1-125">Select the segments you want to export.</span></span> <span data-ttu-id="f7ee1-126">Zdecydowanie **zalecamy, aby nie eksportować łącznie ponad 100 000 profili klientów** do SendGrid.</span><span class="sxs-lookup"><span data-stu-id="f7ee1-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="f7ee1-127">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f7ee1-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="f7ee1-128">Eksportowanie danych</span><span class="sxs-lookup"><span data-stu-id="f7ee1-128">Export the data</span></span>

<span data-ttu-id="f7ee1-129">Możesz [eksportować dane na żądanie](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f7ee1-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="f7ee1-130">Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f7ee1-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f7ee1-131">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="f7ee1-131">Known limitations</span></span>

- <span data-ttu-id="f7ee1-132">Łącznie do 100'000 profili do SendGrid.</span><span class="sxs-lookup"><span data-stu-id="f7ee1-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="f7ee1-133">Eksport do SendGrid jest ograniczony do segmentów.</span><span class="sxs-lookup"><span data-stu-id="f7ee1-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="f7ee1-134">Eksportowanie do 100 000 profili do SendGrid może zająć do kilku godzin.</span><span class="sxs-lookup"><span data-stu-id="f7ee1-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="f7ee1-135">Liczba profilów, które można eksportować do SendGrid, jest zależna od kontraktu i ograniczona jego SendGrid.</span><span class="sxs-lookup"><span data-stu-id="f7ee1-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f7ee1-136">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="f7ee1-136">Data privacy and compliance</span></span>

<span data-ttu-id="f7ee1-137">Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi SendGrid można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="f7ee1-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f7ee1-138">Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że SendGrid spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="f7ee1-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="f7ee1-139">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f7ee1-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f7ee1-140">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="f7ee1-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]