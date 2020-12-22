---
title: Wzbogacanie profili firm o zewnętrzne wzbogacenie Leadspace
description: Ogólne informacje o wzbogacaniu strony trzeciej Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668736"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="ecad8-103">Wzbogacanie profili firm z Leadspace (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="ecad8-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="ecad8-104">Leadspace jest firmą badawczą, która dostarcza platformę danych klientów typu B2B.</span><span class="sxs-lookup"><span data-stu-id="ecad8-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="ecad8-105">Dzięki niej klienci z ujednoliconymi profilami klientów dla firm mogą wzbogacać swoje dane.</span><span class="sxs-lookup"><span data-stu-id="ecad8-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="ecad8-106">Wzbogacenia obejmują dodatkowe atrybuty, takie jak wielkość firmy, lokalizacja, branża i inne.</span><span class="sxs-lookup"><span data-stu-id="ecad8-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ecad8-107">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="ecad8-107">Prerequisites</span></span>

<span data-ttu-id="ecad8-108">Aby skonfigurować Leadspce muszą być spełnione następujące wymagania wstępne:</span><span class="sxs-lookup"><span data-stu-id="ecad8-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="ecad8-109">Posiadasz aktywną licencję Leadspace i „wieczysty klucz” (określany jako **token Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="ecad8-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="ecad8-110">Skontaktuj się bezpośrednio z [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/), aby uzyskać szczegółowe informacje na temat ich produktu.</span><span class="sxs-lookup"><span data-stu-id="ecad8-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="ecad8-111">Masz uprawnienia [Administratora](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="ecad8-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="ecad8-112">Istnieją [ujednolicone profile klientów](customer-profiles.md) dla firm.</span><span class="sxs-lookup"><span data-stu-id="ecad8-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="ecad8-113">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="ecad8-113">Configuration</span></span>

1. <span data-ttu-id="ecad8-114">W analizach odbiorców przejdź do **Dane** > **Wzbogacenie**.</span><span class="sxs-lookup"><span data-stu-id="ecad8-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="ecad8-115">Wybierz **Wzbogać moje dane** na kafelku Leadspace.</span><span class="sxs-lookup"><span data-stu-id="ecad8-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Zrzut ekranu kafelka Leadspace.":::

1. <span data-ttu-id="ecad8-117">Wybierz pozycję **Rozpocznij**, a następnie wprowadź aktywny **token Leadspace** (klucz wieczysty).</span><span class="sxs-lookup"><span data-stu-id="ecad8-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="ecad8-118">Sprawdź poprawność i wyraź zgodę na **Prywatność danych i zgodność z przepisami** zaznaczając pole wyboru **Zgadzam się**.</span><span class="sxs-lookup"><span data-stu-id="ecad8-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="ecad8-119">Potwierdzenie obydwu składników są wprowadzane po wybraniu opcji **Połącz z Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="ecad8-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="ecad8-120">Wybierz opcję **Mapowanie danych** i zdefiniuj pola w ujednoliconych profilach, aby wyszukać pasujące dane firmy pochodzące z Leadspace.</span><span class="sxs-lookup"><span data-stu-id="ecad8-120">Select **Map data** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="ecad8-121">Pole **Nazwa firmy** jest wymagane.</span><span class="sxs-lookup"><span data-stu-id="ecad8-121">The **Name of company** field is required.</span></span> <span data-ttu-id="ecad8-122">Aby zwiększyć dokładność dopasowania, można dodać maksymalnie dwa inne pola, **Witrynę sieci Web firmy** i **Lokalizację firmy**.</span><span class="sxs-lookup"><span data-stu-id="ecad8-122">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Okienko mapowania pola Leadspace.":::
   
1. <span data-ttu-id="ecad8-124">Wybierz opcję **Zastosuj**, aby zakończyć mapowanie pola.</span><span class="sxs-lookup"><span data-stu-id="ecad8-124">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="ecad8-125">Wybierz **Uruchom**, aby wzbogacić profile firm.</span><span class="sxs-lookup"><span data-stu-id="ecad8-125">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="ecad8-126">Czas trwania wzbogacenia zależy od liczby ujednoliconych profilów klientów.</span><span class="sxs-lookup"><span data-stu-id="ecad8-126">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="ecad8-127">Wyniki wzbogacenia</span><span class="sxs-lookup"><span data-stu-id="ecad8-127">Enrichment results</span></span>

<span data-ttu-id="ecad8-128">Po odświeżeniu wzbogacenia można zapoznać się z nowo wzbogaconymi danymi firmowymi w ramach [Moje wzbogacenia](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="ecad8-128">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="ecad8-129">Możesz sprawdzić czas ostatniej aktualizacji oraz liczbę wzbogaconych profilów.</span><span class="sxs-lookup"><span data-stu-id="ecad8-129">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="ecad8-130">Aby uzyskać dostęp do szczegółowego widoku poszczególnych wzbogaconych profilów, należy zaznaczyć **Wyświetl wzbogacone dane**.</span><span class="sxs-lookup"><span data-stu-id="ecad8-130">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="ecad8-131">Aby uzyskać więcej informacji, zobacz [Interfejsy API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="ecad8-131">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ecad8-132">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="ecad8-132">Next steps</span></span>

<span data-ttu-id="ecad8-133">Kompiluj na wierzchu wzbogaconych danych klientów.</span><span class="sxs-lookup"><span data-stu-id="ecad8-133">Build on top of your enriched customer data.</span></span> <span data-ttu-id="ecad8-134">Utwórz [segmenty](segments.md), [miary](measures.md), a nawet [eksportuj dane](export-destinations.md), aby zapewnić klientom spersonalizowane rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="ecad8-134">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ecad8-135">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="ecad8-135">Data privacy and compliance</span></span>

<span data-ttu-id="ecad8-136">Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Leadspace można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="ecad8-136">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ecad8-137">Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że Leadspace spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="ecad8-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ecad8-138">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ecad8-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ecad8-139">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć wzbogacanie, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="ecad8-139">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>