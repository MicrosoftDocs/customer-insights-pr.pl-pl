---
title: Łącznik LiveRamp
description: Dowiedz się, jak eksportować dane do LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 64d781f52e8124fc3e83a7b84f468830c5249cfd
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270171"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="31b3b-103">LiveRamp &reg;łącznik (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="31b3b-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="31b3b-104">Aktywuj swoje dane w LiveRamp, aby łączyć się z ponad 500 platformami obejmującymi ekosystemy cyfrowe, społecznościowe i telewizyjne.</span><span class="sxs-lookup"><span data-stu-id="31b3b-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="31b3b-105">Pracuj z danymi w LiveRamp, aby kierować, pomijać i personalizować kampanie reklamowe.</span><span class="sxs-lookup"><span data-stu-id="31b3b-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="31b3b-106">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="31b3b-106">Prerequisites</span></span>

- <span data-ttu-id="31b3b-107">Aby korzystać z tego łącznika, należy dysponować subskrypcją LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="31b3b-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="31b3b-108">Aby uzyskać subskrypcję, [skontaktuj się z LiveRamp](https://liveramp.com/contact/) bezpośrednio.</span><span class="sxs-lookup"><span data-stu-id="31b3b-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="31b3b-109">[Dowiedz się więcej na temat dołączania do LiveRamp](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="31b3b-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="31b3b-110">Połącz z LiveRamp</span><span class="sxs-lookup"><span data-stu-id="31b3b-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="31b3b-111">W analizach odbiorców przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.</span><span class="sxs-lookup"><span data-stu-id="31b3b-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="31b3b-112">Na kafelku **LiveRamp** wybierz **Konfiguracja**.</span><span class="sxs-lookup"><span data-stu-id="31b3b-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="31b3b-113">W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="31b3b-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="31b3b-114">Wprowadź **Nazwę użytkownika** i **Hasło** dla swojego konta LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="31b3b-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="31b3b-115">Poświadczenia te mogą być inne niż poświadczenia LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="31b3b-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="31b3b-116">Wybierz **Weryfikuj**, aby przetestować połączenie z LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="31b3b-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="31b3b-117">Po pomyślnym sprawdzeniu zapewnij zgodę na **Prywatność danych i zgodność z przepisami** zaznaczając pole wyboru **Zgadzam się**.</span><span class="sxs-lookup"><span data-stu-id="31b3b-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="31b3b-118">Wybierz **Dalej**, aby skonfigurować łącznik LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="31b3b-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="31b3b-119">Skonfiguruj łącznik</span><span class="sxs-lookup"><span data-stu-id="31b3b-119">Configure the connector</span></span>

1. <span data-ttu-id="31b3b-120">W polu **Wybierz identyfikator klucza** wybierz **Email**, **Nazwisko i adres** lub **Telefon**, aby wysłać do LiveRamp w celu rozpoznania tożsamości.</span><span class="sxs-lookup"><span data-stu-id="31b3b-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="31b3b-121">Mapowanie odpowiednich atrybutów ze swojej zunifikowanej encji klienta dla wybranego identyfikatora klucza.</span><span class="sxs-lookup"><span data-stu-id="31b3b-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="31b3b-122">Wybierz **Dodaj atrybut**, aby zamapować dodatkowe atrybuty do wysyłania do LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="31b3b-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="31b3b-123">Wysłanie większej liczby atrybutów z identyfikatorami kluczy do LiveRamp może pomóc uzyskać więcej dopasowań.</span><span class="sxs-lookup"><span data-stu-id="31b3b-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="31b3b-124">Zaznacz segmenty, które chcesz eksportować do LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="31b3b-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="31b3b-125">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="31b3b-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="31b3b-126">![Łącznik LiveRamp z mapowaniem atrybutu](media/export-liveramp-segments.png "Łącznik LiveRamp z mapowaniem atrybutu")</span><span class="sxs-lookup"><span data-stu-id="31b3b-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="31b3b-127">Eksportowanie danych</span><span class="sxs-lookup"><span data-stu-id="31b3b-127">Export the data</span></span>

<span data-ttu-id="31b3b-128">Eksport zostanie rozpoczęty krótko po zakończeniu wszystkich wymagań wstępnych dotyczących eksportu.</span><span class="sxs-lookup"><span data-stu-id="31b3b-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="31b3b-129">Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="31b3b-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="31b3b-130">Po pomyślnym zakończeniu eksportu możesz zalogować się w LiveRamp Onboarding, aby aktywować i rozesłać dane.</span><span class="sxs-lookup"><span data-stu-id="31b3b-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="31b3b-131">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="31b3b-131">Data privacy and compliance</span></span>

<span data-ttu-id="31b3b-132">Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Liveramp można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="31b3b-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="31b3b-133">Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że Liveramp spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="31b3b-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="31b3b-134">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="31b3b-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="31b3b-135">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="31b3b-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]