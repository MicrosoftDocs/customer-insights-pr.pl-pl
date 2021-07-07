---
title: Wzbogacanie za pomocą strony trzeciej – Experian
description: Ogólne informacje o wzbogaceniach od zewnętrznej firmy Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309833"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="c6c2f-103">Wzbogać profile klientów dzięki danych demograficznych z Experian (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="c6c2f-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="c6c2f-104">Firma Experian jest światowym liderem w dziedzinie sprawozdawczości kredytowej dla konsumentów i przedsiębiorstw oraz usług marketingowych.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="c6c2f-105">Dzięki usługom wzbogacania danych firmy Experian możesz lepiej poznać swoich klientów, wzbogacając ich profile o dane demograficzne, takie jak wielkość gospodarstwa domowego, dochody i inne.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c6c2f-106">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="c6c2f-106">Prerequisites</span></span>

<span data-ttu-id="c6c2f-107">Aby można było skonfigurować wpisy do usługi Experian, muszą być spełnione następujące wymagania wstępne:</span><span class="sxs-lookup"><span data-stu-id="c6c2f-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="c6c2f-108">Użytkownik musi mieć aktywną subskrypcję Experian.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-108">You have an active Experian subscription.</span></span> <span data-ttu-id="c6c2f-109">Aby uzyskać subskrypcję, skontaktuj się z [Experian](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="c6c2f-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="c6c2f-110">[Dowiedz się więcej o wzbogacaniu danych Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="c6c2f-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="c6c2f-111">Połączenie Experian z usługą SFTP jest już skonfigurowane przez administratora *lub* użytkownik ma uprawnienia [administratora](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="c6c2f-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="c6c2f-112">Potrzebujesz także identyfikatora użytkownika, identyfikatora strony i numeru modelu konta Secure Transport (ST) z obsługą SSH, które zostało utworzone przez Experian.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="c6c2f-113">Obsługiwane kraje/regiony</span><span class="sxs-lookup"><span data-stu-id="c6c2f-113">Supported countries/regions</span></span>

<span data-ttu-id="c6c2f-114">Obecnie profily klientów są wzbogacane wyłącznie w Stanach Zjednoczonych.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="c6c2f-115">Konfiguracja wzbogacania</span><span class="sxs-lookup"><span data-stu-id="c6c2f-115">Configure the enrichment</span></span>

1. <span data-ttu-id="c6c2f-116">Przejdź do **Dane** > **Wzbogacenie** i wybierz kartę **Odkrywanie**.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="c6c2f-117">Wybierz opcję **Wzbogać dane** na kafelku Experian.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c6c2f-118">![Kafelek Experian](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="c6c2f-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="c6c2f-119">Wybierz [połączenie](connections.md) z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="c6c2f-120">Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="c6c2f-121">Jeśli jesteś administratorem, możesz utworzyć połączenie, wybierając **Dodaj połączenie** i wybierając Experian z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="c6c2f-122">Wybierz opcję **Połącz z Experian**, aby potwierdzić wybór połączenia.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="c6c2f-123">Wybierz opcję **Dalej** i wybierz **zestaw danych klienta**, który chcesz wzbogacić danymi demograficznymi z Experian.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="c6c2f-124">Można wybrać encję **Klient**, aby wzbogacić wszystkie profile klientów, lub wybierz jednostkę segmentu, aby wzbogacić tylko profile klientów zawarte w tym segmencie.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Zrzut ekranu podczas wybierania zestawu danych klienta.":::

1. <span data-ttu-id="c6c2f-126">Wybierz opcję **Dalej** i zdefiniuj, jakiego typu pola z ujednoliconych profilów powinny być używane do wyszukiwania pasujących danych demograficznych w Experian.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="c6c2f-127">Wymagane jest co najmniej jedno z pól **Nazwa i adres**, **Telefon** lub **Wiadomość e-mail**.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="c6c2f-128">Aby dokładność dopasowania było lepsza, można dodać maksymalnie dwa inne pola.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="c6c2f-129">Ten wybór będzie miał wpływ na pola mapowania, do których użytkownik będzie miał dostęp w następnym kroku.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="c6c2f-130">Więcej wysłanych atrybutów kluczowych identyfikatorów do Experian daje większy odsetek dopasowania.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="c6c2f-131">Wybierz **Dalej**, by rozpocząć mapowanie.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="c6c2f-132">Zdefiniuj, jakiego typu pola z ujednoliconych profilów powinny być używane do wyszukiwania pasujących danych demograficznych w Experian.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="c6c2f-133">Zaznaczone pola są wymagane.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-133">Required fields are marked.</span></span>

1. <span data-ttu-id="c6c2f-134">Podaj nazwę dla wzbogacania oraz nazwę encji wyjściowej.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="c6c2f-135">Wybierz opcję **Zapisz wzbogacenie** po przejrzeniu wybranych opcji.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="c6c2f-136">Konfigurowanie ról połączeń w Experian</span><span class="sxs-lookup"><span data-stu-id="c6c2f-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="c6c2f-137">Aby skonfigurować połączenia, użytkownik musi być administratorem.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="c6c2f-138">Wybierz opcję **Dodaj połączenie** podczas konfigurowania wzbogacania *lub* wybierz pozycję **Administracja** > **Połączenia** i wybierz opcję **Skonfiguruj** na kafelku Experian.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="c6c2f-139">Wybierz **Rozpocznij**.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="c6c2f-140">Wprowadź nazwę połączenia w polu **Wyświetlana nazwa**.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="c6c2f-141">Wprowadź prawidłowy identyfikator użytkownika, identyfikator strony i numer modelu dla swojego konta Experian Secure Transport.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="c6c2f-142">Przejrzyj i wyraź zgodę na **Zasady ochrony prywatności danych**, wybierając przycisk **I agree (Wyrażam zgodę)**.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="c6c2f-143">Wybierz opcję **Weryfikuj**, aby sprawdzić poprawność konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="c6c2f-144">Po zakończeniu weryfikacji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Menu konfiguracji łączności Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="c6c2f-146">Wyniki wzbogacenia</span><span class="sxs-lookup"><span data-stu-id="c6c2f-146">Enrichment results</span></span>

<span data-ttu-id="c6c2f-147">Aby rozpocząć proces wzbogacania, wybierz **Uruchom** na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="c6c2f-148">Można również zezwolić, aby system automatycznie uruchamiał wzbogacenie w ramach [zaplanowanego odświeżenia](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c6c2f-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c6c2f-149">Czas przetwarzania będzie zależał od wielkości danych klienta i procesów wzbogacania ustawionych dla konta przez Experian.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="c6c2f-150">Po zakończeniu procesu wzbogacania można przejrzeć dane nowo wzbogacone profile klientów w **Moje wzbogacenia**.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="c6c2f-151">Ponadto znajdziesz tam czas ostatniej aktualizacji i liczbę wzbogaconych profilów.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="c6c2f-152">Aby uzyskać dostęp do szczegółowego widoku poszczególnych wzbogaconych profilów, należy zaznaczyć **Wyświetl wzbogacone dane**.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c6c2f-153">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="c6c2f-153">Next steps</span></span>

<span data-ttu-id="c6c2f-154">Kompiluj na wierzchu wzbogaconych danych klientów.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="c6c2f-155">Twórz [segmenty](segments.md) i [miary](measures.md) oraz [eksportuj dane](export-destinations.md) w celu świadczenia klientom spersonalizowanych usług.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c6c2f-156">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="c6c2f-156">Data privacy and compliance</span></span>

<span data-ttu-id="c6c2f-157">Włączenie w Dynamics 365 Customer Insights opcji przekazywania danych do usługi Experian umożliwia przesyłanie danych poza granice obszaru zgodności dla Dynamics 365 Customer Insights, w tym potencjalnie poufne dane, takie jak dane osobiste.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c6c2f-158">Microsoft będzie przekazywać takie dane zgodnie z Twoimi instrukcjami, ale to Ty jesteś odpowiedzialny za zapewnienie, że Experian spełnia wszelkie zobowiązania dotyczące prywatności i bezpieczeństwa, jakie możesz mieć.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c6c2f-159">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c6c2f-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c6c2f-160">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć wzbogacanie, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="c6c2f-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
