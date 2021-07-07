---
title: Wzbogacanie za pomocą strony trzeciej – HERE Technologies
description: Ogólne informacje o wzbogacaniu strony trzeciej HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b3c1da0f541efb85b2ca9d87a2e3b97bbfb6ca7f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305307"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="91d9a-103">Wzbogacenie profili klientów za pomocą HERE Technologies (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="91d9a-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="91d9a-104">HERE Technologies to firma oferująca platformę lokalizacyjną, która dostarcza dane i usługi zorientowane na lokalizację.</span><span class="sxs-lookup"><span data-stu-id="91d9a-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="91d9a-105">Dzięki usługom wzbogacania danych HERE Technologies możesz dokładniej zrozumieć lokalizację swoich klientów dzięki normalizacji adresu, ekstrakcji szerokości i długości geograficznej i nie tylko.</span><span class="sxs-lookup"><span data-stu-id="91d9a-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="91d9a-106">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="91d9a-106">Prerequisites</span></span>

<span data-ttu-id="91d9a-107">Aby skonfigurować wzbogacenia HERE Technologies, muszą zostać spełnione następujące wymagania wstępne:</span><span class="sxs-lookup"><span data-stu-id="91d9a-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="91d9a-108">Masz aktywną subskrypcję HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="91d9a-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="91d9a-109">Aby uzyskać subskrypcję, możesz zasubskrybować [tutaj](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) lub [skontaktować się bezpośrednio z HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="91d9a-109">To get a subscription, you can [sign up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="91d9a-110">Dowiedz się więcej o wzbogacaniu lokalizacji HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="91d9a-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="91d9a-111">[Połączenie](connections.md) HERE jest dostępne *lub* jeśli masz uprawnienia[administratora](permissions.md#administrator) i klucz interfejsu API HERE.</span><span class="sxs-lookup"><span data-stu-id="91d9a-111">A HERE [connection](connections.md) is available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="91d9a-112">Konfiguracja wzbogacania</span><span class="sxs-lookup"><span data-stu-id="91d9a-112">Configure the enrichment</span></span>

1. <span data-ttu-id="91d9a-113">Przejdź do **Dane** > **Wzbogacanie**.</span><span class="sxs-lookup"><span data-stu-id="91d9a-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="91d9a-114">Wybierz **Wzbogać moje dane** na kafelku HERE Technologies i wybierz **Rozpocznij**.</span><span class="sxs-lookup"><span data-stu-id="91d9a-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="91d9a-115">![Kafelek HERE Technologies](media/HERE-tile.png "Kafelek HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="91d9a-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="91d9a-116">Wybierz [połączenie](connections.md) z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="91d9a-116">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="91d9a-117">Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.</span><span class="sxs-lookup"><span data-stu-id="91d9a-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="91d9a-118">Jeśli użytkownik jest administratorem, może on utworzyć połączenie, wybierając opcję **Dodaj połączenie**.</span><span class="sxs-lookup"><span data-stu-id="91d9a-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="91d9a-119">Z listy rozwijanej wybierz pozycję **HERE Technologies**.</span><span class="sxs-lookup"><span data-stu-id="91d9a-119">Choose **HERE Technologies** from the dropdown list.</span></span> 

1. <span data-ttu-id="91d9a-120">Wybierz opcję **Połącz z HERE Technologies**, aby potwierdzić wybrane połączenie.</span><span class="sxs-lookup"><span data-stu-id="91d9a-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="91d9a-121">Wybierz opcję **Dalej** i wybierz **Zestaw danych klienta**, który chcesz wzbogacić danymi lokalizacji z HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="91d9a-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="91d9a-122">Można wybrać encję **Klient**, aby wzbogacić wszystkie profile klientów, lub wybierz jednostkę segmentu, aby wzbogacić tylko profile klientów zawarte w tym segmencie.</span><span class="sxs-lookup"><span data-stu-id="91d9a-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Zrzut ekranu podczas wybierania zestawu danych klienta.":::

1. <span data-ttu-id="91d9a-124">Wybierz, jeśli chcesz zmapować pola na adres podstawowy i/lub pomocniczy.</span><span class="sxs-lookup"><span data-stu-id="91d9a-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="91d9a-125">Można oddzielnie określić mapowanie pól dla obu adresów i wzbogacić profile dla obu adresów.</span><span class="sxs-lookup"><span data-stu-id="91d9a-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="91d9a-126">Na przykład jeśli istnieje adres domowy i służbowy.</span><span class="sxs-lookup"><span data-stu-id="91d9a-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="91d9a-127">Wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="91d9a-127">Select **Next**.</span></span>

1. <span data-ttu-id="91d9a-128">Zdefiniuj, które pola z ujednoliconych profili mają być używane do wyszukiwania pasujących danych o lokalizacji z HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="91d9a-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="91d9a-129">Pola **Ulica 1** i **Kod pocztowy** są wymagane dla wybranego adresu głównego i / lub dodatkowego.</span><span class="sxs-lookup"><span data-stu-id="91d9a-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="91d9a-130">Aby zwiększyć dokładność dopasowania, można dodać więcej pól.</span><span class="sxs-lookup"><span data-stu-id="91d9a-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="91d9a-131">![Strona konfiguracji wzbogacenia HERE Technologies](media/enrichment-HERE-configuration.png "Strona konfiguracji wzbogacenia HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="91d9a-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="91d9a-132">Wybierz **Dalej**, by zakończyć mapowanie pól.</span><span class="sxs-lookup"><span data-stu-id="91d9a-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="91d9a-133">Podaj nazwę wzbogacenia.</span><span class="sxs-lookup"><span data-stu-id="91d9a-133">Provide a name for the enrichment.</span></span> 

1. <span data-ttu-id="91d9a-134">Wybierz opcję **Zapisz wzbogacenie** po przejrzeniu wybranych opcji.</span><span class="sxs-lookup"><span data-stu-id="91d9a-134">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="91d9a-135">Konfigurowanie połączenia dla HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="91d9a-135">Configure the connection for HERE Technologies</span></span> 

<span data-ttu-id="91d9a-136">Aby skonfigurować połączenia, użytkownik musi być administratorem.</span><span class="sxs-lookup"><span data-stu-id="91d9a-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="91d9a-137">Wybierz opcję **Dodaj połączenie** podczas konfigurowania wzbogacania *lub* wybierz pozycję **Admin** > **Połączenia** i wybierz opcję **Konfiguruj** na kafelku HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="91d9a-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="91d9a-138">Wprowadź nazwę połączenia w polu **Wyświetlana nazwa**.</span><span class="sxs-lookup"><span data-stu-id="91d9a-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="91d9a-139">Podaj prawidłowy klucz interfejsu API technologii HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="91d9a-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="91d9a-140">Przejrzyj i wyraź zgodę na **Zasady ochrony prywatności danych**, wybierając przycisk **I agree (Wyrażam zgodę)**.</span><span class="sxs-lookup"><span data-stu-id="91d9a-140">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="91d9a-141">Wybierz opcję **Weryfikuj**, aby sprawdzić poprawność konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="91d9a-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="91d9a-142">Po zakończeniu weryfikacji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="91d9a-142">After completing the verification, select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="91d9a-143">![Strona konfiguracji połączenia HERE Technologies](media/enrichment-HERE-connection.png "Strona konfiguracji połączenia HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="91d9a-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="91d9a-144">Wyniki wzbogacenia</span><span class="sxs-lookup"><span data-stu-id="91d9a-144">Enrichment results</span></span>

<span data-ttu-id="91d9a-145">Aby rozpocząć proces wzbogacania, wybierz **Uruchom** na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="91d9a-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="91d9a-146">Można również zezwolić, aby system automatycznie uruchamiał wzbogacenie w ramach [zaplanowanego odświeżenia](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="91d9a-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="91d9a-147">Czas przetwarzania będzie zależał od rozmiaru danych klienta i czasów odpowiedzi API firmy HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="91d9a-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="91d9a-148">Po zakończeniu procesu wzbogacania można przejrzeć dane nowo wzbogacone profile klientów w **Moje wzbogacenia**.</span><span class="sxs-lookup"><span data-stu-id="91d9a-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="91d9a-149">Ponadto znajdziesz tam czas ostatniej aktualizacji i liczbę wzbogaconych profilów.</span><span class="sxs-lookup"><span data-stu-id="91d9a-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="91d9a-150">Aby uzyskać dostęp do szczegółowego widoku poszczególnych wzbogaconych profilów, należy zaznaczyć **Wyświetl wzbogacone dane**.</span><span class="sxs-lookup"><span data-stu-id="91d9a-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="91d9a-151">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="91d9a-151">Next steps</span></span>

<span data-ttu-id="91d9a-152">Kompiluj na wierzchu wzbogaconych danych klientów.</span><span class="sxs-lookup"><span data-stu-id="91d9a-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="91d9a-153">Twórz [segmenty](segments.md) i [miary](measures.md) oraz [eksportuj dane](export-destinations.md) w celu świadczenia klientom spersonalizowanych usług.</span><span class="sxs-lookup"><span data-stu-id="91d9a-153">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="91d9a-154">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="91d9a-154">Data privacy and compliance</span></span>

<span data-ttu-id="91d9a-155">Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi HERE Technologies można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="91d9a-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="91d9a-156">Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że HERE Technologies spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="91d9a-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="91d9a-157">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="91d9a-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="91d9a-158">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć wzbogacanie, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="91d9a-158">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
