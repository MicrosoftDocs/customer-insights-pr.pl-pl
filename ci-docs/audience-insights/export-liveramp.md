---
title: Łącznik LiveRamp
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760340"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="1ac0f-103">Eksportowanie segmentów do usługi LiveRamp&reg; (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="1ac0f-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="1ac0f-104">Aktywuj dane w u usłudze LiveRamp, aby połączyć się z ponad 500 platformami za pośrednictwem mediów cyfrowych, społecznościowych i telewizji.</span><span class="sxs-lookup"><span data-stu-id="1ac0f-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="1ac0f-105">Pracuj z danymi w LiveRamp, aby kierować, pomijać i personalizować kampanie reklamowe.</span><span class="sxs-lookup"><span data-stu-id="1ac0f-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="1ac0f-106">Wymagania wstępne dla połączenia</span><span class="sxs-lookup"><span data-stu-id="1ac0f-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="1ac0f-107">Aby korzystać z tego łącznika, należy dysponować subskrypcją LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="1ac0f-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="1ac0f-108">Aby uzyskać subskrypcję, [skontaktuj się z LiveRamp](https://liveramp.com/contact/) bezpośrednio.</span><span class="sxs-lookup"><span data-stu-id="1ac0f-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="1ac0f-109">[Dowiedz się więcej na temat dołączania do LiveRamp](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="1ac0f-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="1ac0f-110">Skonfiguruj połączenie z usługą LiveRamp</span><span class="sxs-lookup"><span data-stu-id="1ac0f-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="1ac0f-111">Przejdź do **Admin** > **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="1ac0f-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1ac0f-112">Wybierz opcję **Dodaj połączenie** i wybierz opcję **LiveRamp**, aby skonfigurować połączenie.</span><span class="sxs-lookup"><span data-stu-id="1ac0f-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="1ac0f-113">W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="1ac0f-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1ac0f-114">Wyświetlana nazwa i typ połączenia opisują to połączenie.</span><span class="sxs-lookup"><span data-stu-id="1ac0f-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1ac0f-115">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.</span><span class="sxs-lookup"><span data-stu-id="1ac0f-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1ac0f-116">Określ, kto może używać tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="1ac0f-116">Choose who can use this connection.</span></span> <span data-ttu-id="1ac0f-117">Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy.</span><span class="sxs-lookup"><span data-stu-id="1ac0f-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1ac0f-118">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1ac0f-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1ac0f-119">Wprowadź **Nazwę użytkownika** i **Hasło** dla swojego konta LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="1ac0f-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="1ac0f-120">Poświadczenia te mogą być inne niż poświadczenia LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="1ac0f-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="1ac0f-121">Wybierz **Weryfikuj**, aby przetestować połączenie z LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="1ac0f-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="1ac0f-122">Po pomyślnym sprawdzeniu zapewnij zgodę na **Prywatność danych i zgodność z przepisami** zaznaczając pole wyboru **Zgadzam się**.</span><span class="sxs-lookup"><span data-stu-id="1ac0f-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="1ac0f-123">Aby zakończyć połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="1ac0f-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="1ac0f-124">Konfigurowanie eksportu</span><span class="sxs-lookup"><span data-stu-id="1ac0f-124">Configure an export</span></span>

<span data-ttu-id="1ac0f-125">Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="1ac0f-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1ac0f-126">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1ac0f-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1ac0f-127">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="1ac0f-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1ac0f-128">Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="1ac0f-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1ac0f-129">W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="1ac0f-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="1ac0f-130">Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="1ac0f-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1ac0f-131">W polu **Wybierz identyfikator klucza** wybierz **Email**, **Nazwisko i adres** lub **Telefon**, aby wysłać do LiveRamp w celu rozpoznania tożsamości.</span><span class="sxs-lookup"><span data-stu-id="1ac0f-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1ac0f-132">![Łącznik LiveRamp z mapowaniem atrybutu](media/export-liveramp-segments.png "Łącznik LiveRamp z mapowaniem atrybutu")</span><span class="sxs-lookup"><span data-stu-id="1ac0f-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="1ac0f-133">Mapowanie odpowiednich atrybutów ze swojej zunifikowanej encji klienta dla wybranego identyfikatora klucza.</span><span class="sxs-lookup"><span data-stu-id="1ac0f-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="1ac0f-134">Wybierz **Dodaj atrybut**, aby zamapować więcej atrybutów do usługi LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="1ac0f-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="1ac0f-135">Wysłanie większej liczby atrybutów z identyfikatorami kluczy do LiveRamp może pomóc uzyskać więcej dopasowań.</span><span class="sxs-lookup"><span data-stu-id="1ac0f-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="1ac0f-136">Zaznacz segmenty, które chcesz eksportować do LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="1ac0f-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="1ac0f-137">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="1ac0f-137">Select **Save**.</span></span>

<span data-ttu-id="1ac0f-138">Zapisanie eksportu nie uruchamia natychmiastowo eksportu.</span><span class="sxs-lookup"><span data-stu-id="1ac0f-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1ac0f-139">Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1ac0f-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1ac0f-140">Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1ac0f-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1ac0f-141">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="1ac0f-141">Data privacy and compliance</span></span>

<span data-ttu-id="1ac0f-142">Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Liveramp można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="1ac0f-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1ac0f-143">Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że Liveramp spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="1ac0f-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1ac0f-144">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1ac0f-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1ac0f-145">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="1ac0f-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
