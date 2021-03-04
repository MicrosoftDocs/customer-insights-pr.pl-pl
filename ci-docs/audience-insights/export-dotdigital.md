---
title: Eksportowanie danych Customer Insights do usługi DotDigital
description: Dowiedz się, jak skonfigurować połączenie z DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 573a22e24f84c65fc4d21faf823cace801cc7ea3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269113"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="c6f94-103">Łącznik dla usługi DotDigital (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="c6f94-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="c6f94-104">Eksportuj segmenty ujednoliconych profili klientów do książek adresowych DotDigital i wykorzystuj je do prowadzenia kampanii, marketingu e-mailowego i budowania segmentów klientów za pomocą DotDigital.</span><span class="sxs-lookup"><span data-stu-id="c6f94-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="c6f94-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="c6f94-105">Prerequisites</span></span>

-   <span data-ttu-id="c6f94-106">Użytkownik ma [konto usługi DotDigital](https://dotdigital.com/) i odpowiadające mu poświadczenia administratora.</span><span class="sxs-lookup"><span data-stu-id="c6f94-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c6f94-107">Istnieją książki adresowe w DotDigital i odpowiadające im identyfikatory.</span><span class="sxs-lookup"><span data-stu-id="c6f94-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="c6f94-108">Identyfikator można znaleźć w adresie URL podczas wybierania i otwierania książki adresowej.</span><span class="sxs-lookup"><span data-stu-id="c6f94-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="c6f94-109">Aby uzyskać więcej informacji, zobacz temat [Książka adresowa DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="c6f94-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="c6f94-110">Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.</span><span class="sxs-lookup"><span data-stu-id="c6f94-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="c6f94-111">Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="c6f94-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="c6f94-112">Nawiązywanie połączenia z DotDigital</span><span class="sxs-lookup"><span data-stu-id="c6f94-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="c6f94-113">Przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.</span><span class="sxs-lookup"><span data-stu-id="c6f94-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c6f94-114">W **DotDigital** wybierz **Konfiguruj**.</span><span class="sxs-lookup"><span data-stu-id="c6f94-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="c6f94-115">W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej exportu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="c6f94-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Okienko konfiguracji dla eksportu DotDigital.":::

1. <span data-ttu-id="c6f94-117">Wprowadź **Nazwę użytkownika i hasło DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="c6f94-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="c6f94-118">Wprowadź **[Identyfikator książki adresowej DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="c6f94-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="c6f94-119">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.</span><span class="sxs-lookup"><span data-stu-id="c6f94-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c6f94-120">Wybierz opcję **Połącz**, aby zainicjować połączenie z DotDigital.</span><span class="sxs-lookup"><span data-stu-id="c6f94-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="c6f94-121">Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c6f94-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="c6f94-122">Wybierz **Dalej**, aby skonfigurować eksport.</span><span class="sxs-lookup"><span data-stu-id="c6f94-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="c6f94-123">Skonfiguruj łącznik</span><span class="sxs-lookup"><span data-stu-id="c6f94-123">Configure the connector</span></span>

1. <span data-ttu-id="c6f94-124">W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta.</span><span class="sxs-lookup"><span data-stu-id="c6f94-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="c6f94-125">Powtórz te kroki dla innych pól opcjonalnych, takich jak **Imię**, **Nazwisko**, **Imię i nazwisko**, **Płeć** i **Kod pocztowy**.</span><span class="sxs-lookup"><span data-stu-id="c6f94-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="c6f94-126">Wybierz segmenty, które chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="c6f94-126">Select the segments you want to export.</span></span> <span data-ttu-id="c6f94-127">W sumie do maksymalnie 1 000 000 profilów klientów można wyeksportować do DotDigital.</span><span class="sxs-lookup"><span data-stu-id="c6f94-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="c6f94-128">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="c6f94-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c6f94-129">Eksportowanie danych</span><span class="sxs-lookup"><span data-stu-id="c6f94-129">Export the data</span></span>

<span data-ttu-id="c6f94-130">Możesz [eksportować dane na żądanie](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c6f94-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="c6f94-131">Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c6f94-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c6f94-132">W DotDigital można teraz znaleźć segmenty w [książkach adresowych DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="c6f94-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c6f94-133">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="c6f94-133">Known limitations</span></span>

- <span data-ttu-id="c6f94-134">Do 1 miliona profili na eksport do DotDigital.</span><span class="sxs-lookup"><span data-stu-id="c6f94-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="c6f94-135">Eksport do DotDigital jest ograniczony do segmentów.</span><span class="sxs-lookup"><span data-stu-id="c6f94-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="c6f94-136">Eksportowanie segmentów zawierających łącznie 1 milion profili może zająć do 3 godzin ze względu na ograniczenia po stronie dostawcy.</span><span class="sxs-lookup"><span data-stu-id="c6f94-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="c6f94-137">Liczba profilów, które można eksportować do DotDigital, jest zależna od kontraktu i ograniczona jego DotDigital.</span><span class="sxs-lookup"><span data-stu-id="c6f94-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c6f94-138">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="c6f94-138">Data privacy and compliance</span></span>

<span data-ttu-id="c6f94-139">Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi DotDigital można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="c6f94-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c6f94-140">Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że DotDigital spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="c6f94-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="c6f94-141">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c6f94-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c6f94-142">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="c6f94-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]