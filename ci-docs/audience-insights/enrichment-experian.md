---
title: Wzbogacanie danych za pomocą Experian innych firm
description: Ogólne informacje o wzbogacaniu strony trzeciej Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896386"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="875e5-103">Wzbogacanie profilów klientów za pomocą danych demograficznych z Experian (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="875e5-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="875e5-104">Experian jest globalnym liderem w zakresie sprawozdawczości kredytowej dla konsumentów i firm oraz usług marketingowych.</span><span class="sxs-lookup"><span data-stu-id="875e5-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="875e5-105">Dzięki usługom wzbogacania Experian można lepiej zrozumieć klientów, wzmacniając profile klientów danymi demograficznymi, takimi jak rozmiar gospodarstwa domowego, przychód itp.</span><span class="sxs-lookup"><span data-stu-id="875e5-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="875e5-106">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="875e5-106">Prerequisites</span></span>

<span data-ttu-id="875e5-107">Aby skonfigurować Experian, należy spełnić następujące wymagania wstępne:</span><span class="sxs-lookup"><span data-stu-id="875e5-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="875e5-108">Użytkownik ma aktywną subskrypcję Experian.</span><span class="sxs-lookup"><span data-stu-id="875e5-108">You have an active Experian subscription.</span></span> <span data-ttu-id="875e5-109">Aby uzyskać subskrypcję, [skontaktuj się z Experian](https://www.experian.com/marketing-services/contact) bezpośrednio.</span><span class="sxs-lookup"><span data-stu-id="875e5-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="875e5-110">[Dowiedz się więcej na temat Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="875e5-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="875e5-111">Połączenie z programem Experian jest już skonfigurowane przez administratora *lub* użytkownik ma uprawnienia [administratora](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="875e5-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="875e5-112">Potrzebny jest także identyfikator użytkownika, identyfikator strony i numer modelu dla konta bezpiecznego transportu (ST) z włączoną usługą SSH, które utworzył dla użytkownika program Experian.</span><span class="sxs-lookup"><span data-stu-id="875e5-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="875e5-113">Konfiguracja wzbogacania</span><span class="sxs-lookup"><span data-stu-id="875e5-113">Configure the enrichment</span></span>

1. <span data-ttu-id="875e5-114">Przejdź do **Dane** > **Wzbogacenie** i wybierz kartę **Odkrywanie**.</span><span class="sxs-lookup"><span data-stu-id="875e5-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="875e5-115">Wybierz **Wzbogać moje dane** na kafelku Experian.</span><span class="sxs-lookup"><span data-stu-id="875e5-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="875e5-116">![Kafelek Experian](media/experian-tile.png "Kafelek Experian")</span><span class="sxs-lookup"><span data-stu-id="875e5-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="875e5-117">Wybierz [połączenie](connections.md) z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="875e5-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="875e5-118">Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.</span><span class="sxs-lookup"><span data-stu-id="875e5-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="875e5-119">Jeśli użytkownik jest administratorem, może on utworzyć połączenie, wybierając opcję **Dodaj połączenie** i wybierając pozycję Experian z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="875e5-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="875e5-120">Wybierz opcję **Połącz z programem Experian**, aby potwierdzić wybrane połączenie.</span><span class="sxs-lookup"><span data-stu-id="875e5-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="875e5-121">Wybierz opcję **Dalej** i wybierz **Zestaw danych klienta**, który chcesz wzbogacić danymi demograficznymi z programu Experian.</span><span class="sxs-lookup"><span data-stu-id="875e5-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="875e5-122">Można wybrać encję **Klient**, aby wzbogacić wszystkie profile klientów, lub wybierz jednostkę segmentu, aby wzbogacić tylko profile klientów zawarte w tym segmencie.</span><span class="sxs-lookup"><span data-stu-id="875e5-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Zrzut ekranu podczas wybierania zestawu danych klienta.":::

1. <span data-ttu-id="875e5-124">Wybierz opcję **Dalej** i zdefiniuj, jakiego typu pola z ujednoliconych profilów powinny być używane do wyszukiwania pasujących danych demograficznych z programu Experian.</span><span class="sxs-lookup"><span data-stu-id="875e5-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="875e5-125">Wymagane jest co najmniej jedno z pól **Nazwa i adres**, **Telefon** lub **Wiadomość e-mail**.</span><span class="sxs-lookup"><span data-stu-id="875e5-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="875e5-126">Aby dokładność dopasowania było lepsza, można dodać maksymalnie dwa inne pola.</span><span class="sxs-lookup"><span data-stu-id="875e5-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="875e5-127">Ten wybór będzie miał wpływ na pola mapowania, do których użytkownik będzie miał dostęp w następnym kroku.</span><span class="sxs-lookup"><span data-stu-id="875e5-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="875e5-128">Więcej atrybutów identyfikatorów kluczy wysłanych do Experian prawdopodobnie zapewni wyższy współczynnik zgodności.</span><span class="sxs-lookup"><span data-stu-id="875e5-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="875e5-129">Wybierz **Dalej**, by rozpocząć mapowanie.</span><span class="sxs-lookup"><span data-stu-id="875e5-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="875e5-130">Zdefiniuj, jakie pola z ujednoliconych profilów powinny być używane do wyszukiwania pasujących danych demograficznych z programu Experian.</span><span class="sxs-lookup"><span data-stu-id="875e5-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="875e5-131">Zaznaczone pola są wymagane.</span><span class="sxs-lookup"><span data-stu-id="875e5-131">Required fields are marked.</span></span>

1. <span data-ttu-id="875e5-132">Podaj nazwę dla wzbogacania oraz nazwę encji wyjściowej.</span><span class="sxs-lookup"><span data-stu-id="875e5-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="875e5-133">Wybierz opcję **Zapisz wzbogacenie** po przejrzeniu wybranych opcji.</span><span class="sxs-lookup"><span data-stu-id="875e5-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="875e5-134">Konfigurowanie połączenia dla programu Experian</span><span class="sxs-lookup"><span data-stu-id="875e5-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="875e5-135">Aby skonfigurować połączenia, użytkownik musi być administratorem.</span><span class="sxs-lookup"><span data-stu-id="875e5-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="875e5-136">Wybierz opcję **Dodaj połączenie** podczas konfigurowania wzbogacania *lub* wybierz pozycję **Admin** > **Połączenia** i wybierz opcję **Konfiguruj** na kafelku Experian.</span><span class="sxs-lookup"><span data-stu-id="875e5-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="875e5-137">Wybierz **Rozpocznij**.</span><span class="sxs-lookup"><span data-stu-id="875e5-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="875e5-138">Wprowadź nazwę połączenia w polu **Wyświetlana nazwa**.</span><span class="sxs-lookup"><span data-stu-id="875e5-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="875e5-139">Wprowadź prawidłowy identyfikator użytkownika, identyfikator strony i numer modelu dla swojego konta bezpiecznego transportu Experian.</span><span class="sxs-lookup"><span data-stu-id="875e5-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="875e5-140">Sprawdź poprawność i wyraź zgodę na **Prywatność danych i zgodność z przepisami** zaznaczając pole wyboru **Zgadzam się**</span><span class="sxs-lookup"><span data-stu-id="875e5-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="875e5-141">Wybierz opcję **Weryfikuj**, aby sprawdzić poprawność konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="875e5-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="875e5-142">Po zakończeniu weryfikacji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="875e5-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Okienko konfiguracji połączenia programu Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="875e5-144">Wyniki wzbogacenia</span><span class="sxs-lookup"><span data-stu-id="875e5-144">Enrichment results</span></span>

<span data-ttu-id="875e5-145">Aby rozpocząć proces wzbogacania, wybierz **Uruchom** na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="875e5-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="875e5-146">Można również zezwolić, aby system automatycznie uruchamiał wzbogacenie w ramach [zaplanowanego odświeżenia](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="875e5-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="875e5-147">Czas przetwarzania będzie uzależniony od wielkości danych klienta i procesów wzbogacania ustanowionych dla konta przez Experian.</span><span class="sxs-lookup"><span data-stu-id="875e5-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="875e5-148">Po zakończeniu procesu wzbogacania można przejrzeć dane nowo wzbogacone profile klientów w **Moje wzbogacenia**.</span><span class="sxs-lookup"><span data-stu-id="875e5-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="875e5-149">Ponadto znajdziesz tam czas ostatniej aktualizacji i liczbę wzbogaconych profilów.</span><span class="sxs-lookup"><span data-stu-id="875e5-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="875e5-150">Aby uzyskać dostęp do szczegółowego widoku poszczególnych wzbogaconych profilów, należy zaznaczyć **Wyświetl wzbogacone dane**.</span><span class="sxs-lookup"><span data-stu-id="875e5-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="875e5-151">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="875e5-151">Next steps</span></span>

<span data-ttu-id="875e5-152">Kompiluj na wierzchu wzbogaconych danych klientów.</span><span class="sxs-lookup"><span data-stu-id="875e5-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="875e5-153">Utwórz [segmenty](segments.md), [miary](measures.md), a nawet [eksportuj dane](export-destinations.md), aby zapewnić klientom spersonalizowane rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="875e5-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="875e5-154">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="875e5-154">Data privacy and compliance</span></span>

<span data-ttu-id="875e5-155">Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Experian można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="875e5-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="875e5-156">Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że Experian spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="875e5-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="875e5-157">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="875e5-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="875e5-158">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć wzbogacanie, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="875e5-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
