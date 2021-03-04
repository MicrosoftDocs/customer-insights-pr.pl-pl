---
title: Eksportowanie danych Customer Insights do usługi Marketo
description: Dowiedz się, jak skonfigurować połączenie z Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e0245f2d01aabc86f43532822c056965ff7ae67a
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267094"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="b87aa-103">Łącznik dla usługi Marketo (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="b87aa-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="b87aa-104">Eksportuj segmenty ujednoliconych profili klientów w celu generowania kampanii, prowadzenia marketingu e-mailowego i korzystania z określonych grup klientów w Marketo.</span><span class="sxs-lookup"><span data-stu-id="b87aa-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b87aa-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="b87aa-105">Prerequisites</span></span>

-   <span data-ttu-id="b87aa-106">Użytkownik ma [konto usługi Marketo](https://login.marketo.com/) i odpowiadające mu poświadczenia administratora.</span><span class="sxs-lookup"><span data-stu-id="b87aa-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b87aa-107">W Marketo istnieją już listy i odpowiadające im identyfikatory.</span><span class="sxs-lookup"><span data-stu-id="b87aa-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="b87aa-108">Aby uzyskać więcej informacji, zobacz [listy Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="b87aa-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="b87aa-109">Posiadasz [skonfigurowane segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="b87aa-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="b87aa-110">Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="b87aa-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="b87aa-111">Nawiązywanie połączenia z usługą Marketo</span><span class="sxs-lookup"><span data-stu-id="b87aa-111">Connect to Marketo</span></span>

1. <span data-ttu-id="b87aa-112">Przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.</span><span class="sxs-lookup"><span data-stu-id="b87aa-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b87aa-113">W **Marketo** wybierz **Konfiguruj**.</span><span class="sxs-lookup"><span data-stu-id="b87aa-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="b87aa-114">W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej exportu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="b87aa-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="b87aa-115">Wprowadź **[Identyfikator klienta Marketo, klucz tajny klienta i nazwa hosta punktu końcowego REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="b87aa-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="b87aa-116">Wprowadź **[Identyfikator listy Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="b87aa-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="b87aa-117">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność**, a następnie wybierz **Połącz**, aby zainicjować połączenie z Marketo.</span><span class="sxs-lookup"><span data-stu-id="b87aa-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="b87aa-118">Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b87aa-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Eksportuj zrzut ekranu dla połączenia z Marketo":::

1. <span data-ttu-id="b87aa-120">Wybierz **Dalej**, aby skonfigurować eksport.</span><span class="sxs-lookup"><span data-stu-id="b87aa-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="b87aa-121">Skonfiguruj łącznik</span><span class="sxs-lookup"><span data-stu-id="b87aa-121">Configure the connector</span></span>

1. <span data-ttu-id="b87aa-122">W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta.</span><span class="sxs-lookup"><span data-stu-id="b87aa-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="b87aa-123">Można też eksportować **imię**, **Nazwisko**, **Miasto**, **Stan** i **Kraj/region** jako dodatkowe pola, aby utworzyć bardziej spersonalizowane wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="b87aa-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="b87aa-124">Wybierz opcję **Dodaj atrybut**, aby zamapować te pola.</span><span class="sxs-lookup"><span data-stu-id="b87aa-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="b87aa-125">Wybierz segmenty, które chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="b87aa-125">Select the segments you want to export.</span></span> <span data-ttu-id="b87aa-126">W sumie do maksymalnie 1 000 000 profilów klientów można wyeksportować do Marketo.</span><span class="sxs-lookup"><span data-stu-id="b87aa-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Wybieranie pól i segmentów do wyeksportowania do Marketo":::

1. <span data-ttu-id="b87aa-128">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="b87aa-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="b87aa-129">Eksportowanie danych</span><span class="sxs-lookup"><span data-stu-id="b87aa-129">Export the data</span></span>

<span data-ttu-id="b87aa-130">Możesz [eksportować dane na żądanie](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="b87aa-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="b87aa-131">Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b87aa-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b87aa-132">W programie Marketo można znaleźć segmenty na [listach Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="b87aa-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b87aa-133">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="b87aa-133">Known limitations</span></span>

- <span data-ttu-id="b87aa-134">Do 1 miliona profili na eksport do Marketo.</span><span class="sxs-lookup"><span data-stu-id="b87aa-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="b87aa-135">Eksport do Marketo jest ograniczony do segmentów.</span><span class="sxs-lookup"><span data-stu-id="b87aa-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="b87aa-136">Eksportowanie segmentów razem z profilem 1 000 000 może potrwać do 3 godzin.</span><span class="sxs-lookup"><span data-stu-id="b87aa-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="b87aa-137">Liczba profilów, które można eksportować do Marketo, jest zależna od kontraktu i ograniczona jego Marketo.</span><span class="sxs-lookup"><span data-stu-id="b87aa-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b87aa-138">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="b87aa-138">Data privacy and compliance</span></span>

<span data-ttu-id="b87aa-139">Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Marketo można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="b87aa-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b87aa-140">Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że Marketo spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="b87aa-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b87aa-141">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b87aa-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b87aa-142">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="b87aa-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]