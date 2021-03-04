---
title: Eksportowanie danych Customer Insights do usługi Google ads
description: Dowiedz się, jak skonfigurować połączenie z reklamą usługi Google ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ba7c82e643ea0dc1897e0954e78646932cafffa3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268975"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="4168b-103">Łącznik dla usługi Google Ads (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="4168b-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="4168b-104">Eksportuj segmenty ujednoliconych profili klientów na listę odbiorców Google Ads i używaj ich do reklamowania się w wyszukiwarce Google, Gmailu, YouTube i sieci reklamowej Google.</span><span class="sxs-lookup"><span data-stu-id="4168b-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="4168b-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="4168b-105">Prerequisites</span></span>

-   <span data-ttu-id="4168b-106">Użytkownik ma [konto usługi Google Ads](https://ads.google.com/) i odpowiadające mu poświadczenia administratora.</span><span class="sxs-lookup"><span data-stu-id="4168b-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="4168b-107">W Google Ads istnieją już odbiorcy i odpowiadające im identyfikatory.</span><span class="sxs-lookup"><span data-stu-id="4168b-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="4168b-108">Aby uzyskać więcej informacji, zobacz temat [Odbiorcy Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="4168b-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="4168b-109">Posiadasz [skonfigurowane segmenty](segments.md)</span><span class="sxs-lookup"><span data-stu-id="4168b-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="4168b-110">Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pola reprezentujące adresy e-mail, imię i nazwisko</span><span class="sxs-lookup"><span data-stu-id="4168b-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="4168b-111">Połącz z usługą Google Ads</span><span class="sxs-lookup"><span data-stu-id="4168b-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="4168b-112">Przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.</span><span class="sxs-lookup"><span data-stu-id="4168b-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="4168b-113">W **Google Ads** wybierz **Konfiguruj**.</span><span class="sxs-lookup"><span data-stu-id="4168b-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="4168b-114">W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej exportu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="4168b-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="4168b-115">Wpisz **[Identyfikator klienta usługi Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="4168b-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="4168b-116">Wprowadź **[zatwierdzony token dewelopera usługi Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="4168b-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="4168b-117">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.</span><span class="sxs-lookup"><span data-stu-id="4168b-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="4168b-118">Wprowadź **[identyfikator odbiorcy usługi Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** i wybierz pozycję **Połącz**, aby zainicjować połączenie z usługą Google Ads.</span><span class="sxs-lookup"><span data-stu-id="4168b-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="4168b-119">Wybierz **Uwierzytelnianie za pomocą usługi Google Ads** i przekaż swoje poświadczenia w usłudze Google AD.</span><span class="sxs-lookup"><span data-stu-id="4168b-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="4168b-120">Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4168b-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Eksportuj zrzut ekranu dla połączenia z Google Ads":::

1. <span data-ttu-id="4168b-122">Wybierz **Dalej**, aby skonfigurować eksport.</span><span class="sxs-lookup"><span data-stu-id="4168b-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="4168b-123">Skonfiguruj łącznik</span><span class="sxs-lookup"><span data-stu-id="4168b-123">Configure the connector</span></span>

1. <span data-ttu-id="4168b-124">W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta.</span><span class="sxs-lookup"><span data-stu-id="4168b-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="4168b-125">Powtórz te same kroki dla pól **Imię** i **Nazwisko**.</span><span class="sxs-lookup"><span data-stu-id="4168b-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="4168b-126">Wybierz segmenty, które chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="4168b-126">Select the segments you want to export.</span></span> <span data-ttu-id="4168b-127">W sumie do maksymalnie 1 000 000 profilów klientów można wyeksportować do Google Ads.</span><span class="sxs-lookup"><span data-stu-id="4168b-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="4168b-128">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="4168b-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="4168b-129">Eksportowanie danych</span><span class="sxs-lookup"><span data-stu-id="4168b-129">Export the data</span></span>

<span data-ttu-id="4168b-130">Możesz [eksportować dane na żądanie](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="4168b-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="4168b-131">Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4168b-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4168b-132">W usłudze Google Ads można teraz znaleźć segmenty w [Odbiorcy Google ads](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="4168b-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="4168b-133">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="4168b-133">Known limitations</span></span>

- <span data-ttu-id="4168b-134">Do 1 miliona profili na eksport do Google Ads.</span><span class="sxs-lookup"><span data-stu-id="4168b-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="4168b-135">Eksport do Google Ads jest ograniczony do segmentów.</span><span class="sxs-lookup"><span data-stu-id="4168b-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="4168b-136">Eksportowanie segmentów zawierających łącznie 1 milion profili może zająć do 5 minut ze względu na ograniczenia po stronie dostawcy.</span><span class="sxs-lookup"><span data-stu-id="4168b-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="4168b-137">Dopasowanie w usłudze Google Ads może potrwać do 48 godzin.</span><span class="sxs-lookup"><span data-stu-id="4168b-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4168b-138">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="4168b-138">Data privacy and compliance</span></span>

<span data-ttu-id="4168b-139">Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Google Ads można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="4168b-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4168b-140">Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że Google Ads spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="4168b-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="4168b-141">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="4168b-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="4168b-142">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="4168b-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]