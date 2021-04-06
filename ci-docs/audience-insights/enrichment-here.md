---
title: Wzbogacanie danych za pomocą HERE Technologies innych firm
description: Ogólne informacje o wzbogacaniu strony trzeciej HERE Technologies.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 8e8d6bfea4e0df54682501f60759c24c893444af
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597754"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="ea041-103">Wzbogacenie profili klientów za pomocą HERE Technologies (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="ea041-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="ea041-104">HERE Technologies to firma oferująca platformę lokalizacyjną, która dostarcza dane i usługi zorientowane na lokalizację.</span><span class="sxs-lookup"><span data-stu-id="ea041-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="ea041-105">Dzięki usługom wzbogacania danych HERE Technologies możesz dokładniej zrozumieć lokalizację swoich klientów dzięki normalizacji adresu, ekstrakcji szerokości i długości geograficznej i nie tylko.</span><span class="sxs-lookup"><span data-stu-id="ea041-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ea041-106">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="ea041-106">Prerequisites</span></span>

<span data-ttu-id="ea041-107">Aby skonfigurować wzbogacenia HERE Technologies, muszą zostać spełnione następujące wymagania wstępne:</span><span class="sxs-lookup"><span data-stu-id="ea041-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="ea041-108">Masz aktywną subskrypcję HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="ea041-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="ea041-109">Aby uzyskać subskrypcję, możesz zasubskrybować [tutaj](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) lub [skontaktować się bezpośrednio z HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="ea041-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="ea041-110">Dowiedz się więcej o wzbogacaniu lokalizacji HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="ea041-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="ea041-111">Masz klucz API HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="ea041-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="ea041-112">Masz uprawnienia [Administratora](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="ea041-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="ea041-113">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="ea041-113">Configuration</span></span>

1. <span data-ttu-id="ea041-114">Przejdź do **Dane** > **Wzbogacanie**.</span><span class="sxs-lookup"><span data-stu-id="ea041-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="ea041-115">Na kafelku importu niestandardowego HERE wybierz pozycję **Wzbogacanie danych**.</span><span class="sxs-lookup"><span data-stu-id="ea041-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ea041-116">![Kafelek HERE Technologies](media/HERE-tile.png "Kafelek HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="ea041-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="ea041-117">Wprowadź aktywny **klucz interfejsu API HERE Technologies**.</span><span class="sxs-lookup"><span data-stu-id="ea041-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="ea041-118">Sprawdź poprawność i wyraź zgodę na **Prywatność danych i zgodność z przepisami** zaznaczając pole wyboru **Zgadzam się**.</span><span class="sxs-lookup"><span data-stu-id="ea041-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="ea041-119">Potwierdzenie obydwu składników są wprowadzane po wybraniu opcji **Połącz z HERE**.</span><span class="sxs-lookup"><span data-stu-id="ea041-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1.  <span data-ttu-id="ea041-120">Wybierz opcję **Dodaj dane** i wybierz **Zestaw danych klienta**, który chcesz wzbogacić o dane lokalizacyjne z firmy HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="ea041-120">Select **Add data** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="ea041-121">Można wybrać encję **Klient**, aby wzbogacić wszystkie profile klientów, lub wybierz jednostkę segmentu, aby wzbogacić tylko profile klientów zawarte w tym segmencie.</span><span class="sxs-lookup"><span data-stu-id="ea041-121">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Zrzut ekranu podczas wybierania zestawu danych klienta.":::

1. <span data-ttu-id="ea041-123">Wybierz, jeśli chcesz zmapować pola na adres podstawowy i/lub pomocniczy.</span><span class="sxs-lookup"><span data-stu-id="ea041-123">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="ea041-124">Możesz określić mapowanie pól dla obu adresów (na przykład adresu domowego i adresu firmy) i wzbogacić profile dla obu adresów osobno.</span><span class="sxs-lookup"><span data-stu-id="ea041-124">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="ea041-125">Wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="ea041-125">Select **Next**.</span></span>

1. <span data-ttu-id="ea041-126">Zdefiniuj, które pola z ujednoliconych profili mają być używane do wyszukiwania pasujących danych o lokalizacji z HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="ea041-126">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="ea041-127">Pola **Ulica 1** i **Kod pocztowy** są wymagane dla wybranego adresu głównego i / lub dodatkowego.</span><span class="sxs-lookup"><span data-stu-id="ea041-127">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="ea041-128">Aby zwiększyć dokładność dopasowania, można dodać więcej pól.</span><span class="sxs-lookup"><span data-stu-id="ea041-128">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ea041-129">![Strona konfiguracji wzbogacenia HERE Technologies](media/enrichment-HERE-configuration.png "Strona konfiguracji wzbogacenia HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="ea041-129">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="ea041-130">Wybierz opcję **Zastosuj**, aby zakończyć mapowanie pola.</span><span class="sxs-lookup"><span data-stu-id="ea041-130">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="ea041-131">Wyniki wzbogacenia</span><span class="sxs-lookup"><span data-stu-id="ea041-131">Enrichment results</span></span>

<span data-ttu-id="ea041-132">Aby rozpocząć proces wzbogacania, wybierz **Uruchom** na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="ea041-132">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="ea041-133">Można również zezwolić, aby system automatycznie uruchamiał wzbogacenie w ramach [zaplanowanego odświeżenia](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ea041-133">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ea041-134">Czas przetwarzania będzie zależał od rozmiaru danych klienta i czasów odpowiedzi API firmy HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="ea041-134">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="ea041-135">Po zakończeniu procesu wzbogacania można przejrzeć dane nowo wzbogacone profile klientów w **Moje wzbogacenia**.</span><span class="sxs-lookup"><span data-stu-id="ea041-135">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="ea041-136">Ponadto znajdziesz tam czas ostatniej aktualizacji i liczbę wzbogaconych profilów.</span><span class="sxs-lookup"><span data-stu-id="ea041-136">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="ea041-137">Aby uzyskać dostęp do szczegółowego widoku poszczególnych wzbogaconych profilów, należy zaznaczyć **Wyświetl wzbogacone dane**.</span><span class="sxs-lookup"><span data-stu-id="ea041-137">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ea041-138">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="ea041-138">Next steps</span></span>

<span data-ttu-id="ea041-139">Kompiluj na wierzchu wzbogaconych danych klientów.</span><span class="sxs-lookup"><span data-stu-id="ea041-139">Build on top of your enriched customer data.</span></span> <span data-ttu-id="ea041-140">Utwórz [segmenty](segments.md), [miary](measures.md), a nawet [eksportuj dane](export-destinations.md), aby zapewnić klientom spersonalizowane rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="ea041-140">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ea041-141">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="ea041-141">Data privacy and compliance</span></span>

<span data-ttu-id="ea041-142">Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi HERE Technologies można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="ea041-142">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ea041-143">Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że HERE Technologies spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="ea041-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ea041-144">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ea041-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ea041-145">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć wzbogacanie, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="ea041-145">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]