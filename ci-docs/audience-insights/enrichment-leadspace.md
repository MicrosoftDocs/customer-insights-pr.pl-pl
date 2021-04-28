---
title: Wzbogacanie profili firm o zewnętrzne wzbogacenie Leadspace
description: Ogólne informacje o wzbogacaniu strony trzeciej Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ccf4f661ecffb281556a4545b1f26ee809c697cd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895926"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="1178f-103">Wzbogacanie profili firm z Leadspace (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="1178f-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="1178f-104">Leadspace jest firmą badawczą, która dostarcza platformę danych klientów typu B2B.</span><span class="sxs-lookup"><span data-stu-id="1178f-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="1178f-105">Dzięki niej klienci z ujednoliconymi profilami klientów dla firm mogą wzbogacać swoje dane.</span><span class="sxs-lookup"><span data-stu-id="1178f-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="1178f-106">Wzbogacanie zawiera więcej atrybutów, takich jak wielkość firmy, lokalizacja, branża i inne.</span><span class="sxs-lookup"><span data-stu-id="1178f-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1178f-107">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="1178f-107">Prerequisites</span></span>

<span data-ttu-id="1178f-108">Aby skonfigurować Leadspce muszą być spełnione następujące wymagania wstępne:</span><span class="sxs-lookup"><span data-stu-id="1178f-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="1178f-109">Użytkownik ma aktywną licencję Leadspace.</span><span class="sxs-lookup"><span data-stu-id="1178f-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="1178f-110">Istnieją [ujednolicone profile klientów](customer-profiles.md) dla firm.</span><span class="sxs-lookup"><span data-stu-id="1178f-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="1178f-111">Połączenie Leadspace zostało już skonfigurowane przez administratora lub użytkownik ma uprawnienia [administratora](permissions.md#administrator) i „klucz bezterminowy” (nazywany **tokenem Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="1178f-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="1178f-112">Aby uzyskać szczegółowe informacje na temat produktu, należy bezpośrednio skontaktować się z [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/).</span><span class="sxs-lookup"><span data-stu-id="1178f-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="1178f-113">Konfiguracja wzbogacania</span><span class="sxs-lookup"><span data-stu-id="1178f-113">Configure the enrichment</span></span>

1. <span data-ttu-id="1178f-114">W analizach odbiorców przejdź do **Dane** > **Wzbogacenie**.</span><span class="sxs-lookup"><span data-stu-id="1178f-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="1178f-115">Wybierz **Wzbogać moje dane** na kafelku Leadspace i wybierz **Rozpocznij**.</span><span class="sxs-lookup"><span data-stu-id="1178f-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Zrzut ekranu kafelka Leadspace.":::

1. <span data-ttu-id="1178f-117">Wybierz [połączenie](connections.md) z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="1178f-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="1178f-118">Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.</span><span class="sxs-lookup"><span data-stu-id="1178f-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="1178f-119">Jeśli użytkownik jest administratorem, może on utworzyć połączenie, wybierając opcję **Dodaj połączenie** i wybierając **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="1178f-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="1178f-120">Wybierz opcję **Połącz z Leadspace**, aby potwierdzić wybrane połączenie.</span><span class="sxs-lookup"><span data-stu-id="1178f-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="1178f-121">Wybierz opcję **Dalej** i wybierz **Zestaw danych klienta**, który chcesz wzbogacić danymi firmy z Leadspace.</span><span class="sxs-lookup"><span data-stu-id="1178f-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="1178f-122">Można wybrać encję **Klient**, aby wzbogacić wszystkie profile klientów, lub wybierz jednostkę segmentu, aby wzbogacić tylko profile klientów zawarte w tym segmencie.</span><span class="sxs-lookup"><span data-stu-id="1178f-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Zrzut ekranu podczas wybierania zestawu danych klienta.":::

1. <span data-ttu-id="1178f-124">Wybierz opcję **Dalej** i zdefiniuj, jakiego typu pola z ujednoliconych profilów powinny być używane do wyszukiwania pasujących danych firmowych z Leadspace.</span><span class="sxs-lookup"><span data-stu-id="1178f-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="1178f-125">Pole **Nazwa firmy** jest wymagane.</span><span class="sxs-lookup"><span data-stu-id="1178f-125">The **Name of company** field is required.</span></span> <span data-ttu-id="1178f-126">Aby zwiększyć dokładność dopasowania, można dodać maksymalnie dwa inne pola, **Witrynę sieci Web firmy** i **Lokalizację firmy**.</span><span class="sxs-lookup"><span data-stu-id="1178f-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Okienko mapowania pola Leadspace.":::

1. <span data-ttu-id="1178f-128">Wybierz **Dalej**, by zakończyć mapowanie pól.</span><span class="sxs-lookup"><span data-stu-id="1178f-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="1178f-129">Po przejrzeniu wybranych opcji podaj nazwę wzbogacania i wybierz opcję **Zapisz wzbogacenie**.</span><span class="sxs-lookup"><span data-stu-id="1178f-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="1178f-130">Konfigurowanie połączenia dla Leadspace</span><span class="sxs-lookup"><span data-stu-id="1178f-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="1178f-131">Aby skonfigurować połączenia, użytkownik musi być administratorem.</span><span class="sxs-lookup"><span data-stu-id="1178f-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="1178f-132">Wybierz opcję **Dodaj połączenie** podczas konfigurowania wzbogacania *lub* wybierz pozycję **Admin** > **Połączenia** i wybierz opcję **Konfiguruj** na kafelku Leadspace.</span><span class="sxs-lookup"><span data-stu-id="1178f-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="1178f-133">Wybierz **Rozpocznij**</span><span class="sxs-lookup"><span data-stu-id="1178f-133">Select **Get Started**</span></span> 

1. <span data-ttu-id="1178f-134">Wprowadź nazwę połączenia w polu **Wyświetlana nazwa**.</span><span class="sxs-lookup"><span data-stu-id="1178f-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="1178f-135">Podaj prawidłowy token rozwiązania firmy Leadspace.</span><span class="sxs-lookup"><span data-stu-id="1178f-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="1178f-136">Sprawdź poprawność i wyraź zgodę na **Prywatność danych i zgodność z przepisami** zaznaczając pole wyboru **Zgadzam się**</span><span class="sxs-lookup"><span data-stu-id="1178f-136">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="1178f-137">Wybierz opcję **Weryfikuj**, aby sprawdzić poprawność konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="1178f-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="1178f-138">Po zakończeniu weryfikacji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="1178f-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Strona konfiguracji połączenia Leadspace.":::

## <a name="enrichment-results"></a><span data-ttu-id="1178f-140">Wyniki wzbogacenia</span><span class="sxs-lookup"><span data-stu-id="1178f-140">Enrichment results</span></span>

<span data-ttu-id="1178f-141">Po odświeżeniu wzbogacenia można zapoznać się z nowo wzbogaconymi danymi firmowymi w ramach [Moje wzbogacenia](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="1178f-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="1178f-142">Możesz sprawdzić czas ostatniej aktualizacji oraz liczbę wzbogaconych profilów.</span><span class="sxs-lookup"><span data-stu-id="1178f-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="1178f-143">Aby uzyskać dostęp do szczegółowego widoku poszczególnych wzbogaconych profilów, należy zaznaczyć **Wyświetl wzbogacone dane**.</span><span class="sxs-lookup"><span data-stu-id="1178f-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="1178f-144">Aby uzyskać więcej informacji, zobacz [Interfejsy API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="1178f-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="1178f-145">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="1178f-145">Next steps</span></span>

<span data-ttu-id="1178f-146">Kompiluj na wierzchu wzbogaconych danych klientów.</span><span class="sxs-lookup"><span data-stu-id="1178f-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="1178f-147">Utwórz [segmenty](segments.md), [miary](measures.md), a nawet [eksportuj dane](export-destinations.md), aby zapewnić klientom spersonalizowane rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="1178f-147">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1178f-148">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="1178f-148">Data privacy and compliance</span></span>

<span data-ttu-id="1178f-149">Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Leadspace można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="1178f-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1178f-150">Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że Leadspace spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="1178f-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1178f-151">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1178f-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1178f-152">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć wzbogacanie, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="1178f-152">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
