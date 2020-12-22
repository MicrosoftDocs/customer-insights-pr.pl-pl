---
title: Wzbogacanie danych za pomocą Experian innych firm
description: Ogólne informacje o wzbogacaniu strony trzeciej Experian.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668825"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="f6f74-103">Wzbogacanie profilów klientów za pomocą danych demograficznych z Experian (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="f6f74-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="f6f74-104">Experian jest globalnym liderem w zakresie sprawozdawczości kredytowej dla konsumentów i firm oraz usług marketingowych.</span><span class="sxs-lookup"><span data-stu-id="f6f74-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="f6f74-105">Dzięki usługom wzbogacania Experian można lepiej zrozumieć klientów, wzmacniając profile klientów danymi demograficznymi, takimi jak rozmiar gospodarstwa domowego, przychód itp.</span><span class="sxs-lookup"><span data-stu-id="f6f74-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f6f74-106">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="f6f74-106">Prerequisites</span></span>

<span data-ttu-id="f6f74-107">Aby skonfigurować Experian, należy spełnić następujące wymagania wstępne:</span><span class="sxs-lookup"><span data-stu-id="f6f74-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="f6f74-108">Użytkownik ma aktywną subskrypcję Experian.</span><span class="sxs-lookup"><span data-stu-id="f6f74-108">You have an active Experian subscription.</span></span> <span data-ttu-id="f6f74-109">Aby uzyskać subskrypcję, [skontaktuj się z Experian](https://www.experian.com/marketing-services/contact) bezpośrednio.</span><span class="sxs-lookup"><span data-stu-id="f6f74-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="f6f74-110">[Dowiedz się więcej na temat Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="f6f74-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="f6f74-111">Użytkownik posiada Identyfikator użytkownika, Identyfikator jednostki i numer modelu dla konta usługi Secure Transport (ST) SSH, które Experian utworzył dla użytkownika.</span><span class="sxs-lookup"><span data-stu-id="f6f74-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="f6f74-112">Posiadasz uprawnienia [Administratora](permissions.md#administrator) w analizach odbiorców.</span><span class="sxs-lookup"><span data-stu-id="f6f74-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="f6f74-113">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="f6f74-113">Configuration</span></span>

1. <span data-ttu-id="f6f74-114">Przejdź do **Dane** > **Wzbogacenie** i wybierz kartę **Odkrywanie**.</span><span class="sxs-lookup"><span data-stu-id="f6f74-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="f6f74-115">Wybierz **Wzbogać moje dane** na kafelku Experian.</span><span class="sxs-lookup"><span data-stu-id="f6f74-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f6f74-116">![Kafelek Experian](media/experian-tile.png "Kafelek Experian")</span><span class="sxs-lookup"><span data-stu-id="f6f74-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="f6f74-117">Wybierz **Rozpocznij** i wprowadź identyfikator użytkownika, identyfikator jednostki i numer modelu dla Twojego konta Experian Secure Transport.</span><span class="sxs-lookup"><span data-stu-id="f6f74-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="f6f74-118">Sprawdź poprawność i wyraź zgodę na **Prywatność danych i zgodność z przepisami** zaznaczając pole wyboru **Zgadzam się**.</span><span class="sxs-lookup"><span data-stu-id="f6f74-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="f6f74-119">Aby potwierdzić wszystkie dane, należy wybrać opcję **Zastosuj**.</span><span class="sxs-lookup"><span data-stu-id="f6f74-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="f6f74-120">Zamapuj swoje pola</span><span class="sxs-lookup"><span data-stu-id="f6f74-120">Map your fields</span></span>

1. <span data-ttu-id="f6f74-121">Wybierz opcję **Dodaj dane** i wybierz identyfikatory kluczy z **Nazwa i adres**, **E-mail** lub **Telefon**, aby wysłać do Experian w celu rozpoznania tożsamości.</span><span class="sxs-lookup"><span data-stu-id="f6f74-121">Select **Add data** and choose your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="f6f74-122">Więcej atrybutów identyfikatorów kluczy wysłanych do Experian prawdopodobnie zapewni wyższy współczynnik zgodności.</span><span class="sxs-lookup"><span data-stu-id="f6f74-122">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="f6f74-123">Wybierz **Dalej** i zamapuj odpowiednie atrybuty z encji Unified Customer dla wybranych pól identyfikatorów kluczy.</span><span class="sxs-lookup"><span data-stu-id="f6f74-123">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="f6f74-124">Wybierz **Dodaj atrybut**, aby zamapować wszelkie dodatkowe atrybuty, które chcesz wysłać do Experian.</span><span class="sxs-lookup"><span data-stu-id="f6f74-124">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="f6f74-125">Wybierz **Zapisz**, aby zakończyć mapowanie pola.</span><span class="sxs-lookup"><span data-stu-id="f6f74-125">Select **Save** to complete the field mapping.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f6f74-126">![Mapowanie pól Experian](media/experian-field-mapping.png "Mapowanie pól Experian")</span><span class="sxs-lookup"><span data-stu-id="f6f74-126">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="f6f74-127">Wyniki wzbogacenia</span><span class="sxs-lookup"><span data-stu-id="f6f74-127">Enrichment results</span></span>

<span data-ttu-id="f6f74-128">Aby rozpocząć proces wzbogacania, wybierz **Uruchom** na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="f6f74-128">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="f6f74-129">Można również zezwolić, aby system automatycznie uruchamiał wzbogacenie w ramach [zaplanowanego odświeżenia](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f6f74-129">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f6f74-130">Czas przetwarzania będzie uzależniony od wielkości danych klienta i procesów wzbogacania ustanowionych dla konta przez Experian.</span><span class="sxs-lookup"><span data-stu-id="f6f74-130">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="f6f74-131">Po zakończeniu procesu wzbogacania można przejrzeć dane nowo wzbogacone profile klientów w **Moje wzbogacenia**.</span><span class="sxs-lookup"><span data-stu-id="f6f74-131">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="f6f74-132">Ponadto znajdziesz tam czas ostatniej aktualizacji i liczbę wzbogaconych profilów.</span><span class="sxs-lookup"><span data-stu-id="f6f74-132">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="f6f74-133">Aby uzyskać dostęp do szczegółowego widoku poszczególnych wzbogaconych profilów, należy zaznaczyć **Wyświetl wzbogacone dane**.</span><span class="sxs-lookup"><span data-stu-id="f6f74-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f6f74-134">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="f6f74-134">Next steps</span></span>

<span data-ttu-id="f6f74-135">Kompiluj na wierzchu wzbogaconych danych klientów.</span><span class="sxs-lookup"><span data-stu-id="f6f74-135">Build on top of your enriched customer data.</span></span> <span data-ttu-id="f6f74-136">Utwórz [segmenty](segments.md), [miary](measures.md), a nawet [eksportuj dane](export-destinations.md), aby zapewnić klientom spersonalizowane rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="f6f74-136">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f6f74-137">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="f6f74-137">Data privacy and compliance</span></span>

<span data-ttu-id="f6f74-138">Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Experian można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="f6f74-138">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f6f74-139">Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że Experian spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="f6f74-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f6f74-140">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f6f74-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f6f74-141">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć wzbogacanie, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="f6f74-141">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
