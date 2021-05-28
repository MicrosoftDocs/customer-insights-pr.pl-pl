---
title: Eksportowanie danych Customer Insights do usługi Google ads
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 73f3257a3ae6e8423f45410546535df5e3b400ce
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976331"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="a6995-103">Eksportowanie segmentów do usługi Google Ads (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="a6995-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="a6995-104">Eksportuj segmenty ujednoliconych profili klientów na listę odbiorców Google Ads i używaj ich do reklamowania się w wyszukiwarce Google, Gmailu, YouTube i sieci reklamowej Google.</span><span class="sxs-lookup"><span data-stu-id="a6995-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="a6995-105">Wymagania wstępne dla połączenia</span><span class="sxs-lookup"><span data-stu-id="a6995-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="a6995-106">Użytkownik ma [konto usługi Google Ads](https://ads.google.com/) i odpowiadające mu poświadczenia administratora.</span><span class="sxs-lookup"><span data-stu-id="a6995-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a6995-107">Masz [zatwierdzony token dewelopera Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="a6995-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="a6995-108">Spełniasz wymagania [zasad dopasowania do klienta](https://support.google.com/adspolicy/answer/6299717)</span><span class="sxs-lookup"><span data-stu-id="a6995-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="a6995-109">Spełniasz wymagania [rozmiarów list marketingowych](https://support.google.com/google-ads/answer/7558048)</span><span class="sxs-lookup"><span data-stu-id="a6995-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="a6995-110">W Google Ads istnieją już odbiorcy i odpowiadające im identyfikatory.</span><span class="sxs-lookup"><span data-stu-id="a6995-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="a6995-111">Aby uzyskać więcej informacji, zobacz temat [Odbiorcy Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="a6995-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="a6995-112">Posiadasz [skonfigurowane segmenty](segments.md)</span><span class="sxs-lookup"><span data-stu-id="a6995-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="a6995-113">Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pola reprezentujące adresy e-mail, imię i nazwisko</span><span class="sxs-lookup"><span data-stu-id="a6995-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a6995-114">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="a6995-114">Known limitations</span></span>

- <span data-ttu-id="a6995-115">Do 1 miliona profili na eksport do Google Ads.</span><span class="sxs-lookup"><span data-stu-id="a6995-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="a6995-116">Eksport do Google Ads jest ograniczony do segmentów.</span><span class="sxs-lookup"><span data-stu-id="a6995-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="a6995-117">Eksportowanie segmentów zawierających łącznie 1 milion profili może zająć do 5 minut ze względu na ograniczenia po stronie dostawcy.</span><span class="sxs-lookup"><span data-stu-id="a6995-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="a6995-118">Dopasowanie w usłudze Google Ads może potrwać do 48 godzin.</span><span class="sxs-lookup"><span data-stu-id="a6995-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="a6995-119">Konfiguruj połączenie z usługą Google Ads</span><span class="sxs-lookup"><span data-stu-id="a6995-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="a6995-120">Przejdź do **Admin** > **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="a6995-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a6995-121">Wybierz opcję **Dodaj połączenie** i wybierz opcję **Google Ads**, aby skonfigurować połączenie.</span><span class="sxs-lookup"><span data-stu-id="a6995-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="a6995-122">W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="a6995-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a6995-123">Wyświetlana nazwa i typ połączenia opisują to połączenie.</span><span class="sxs-lookup"><span data-stu-id="a6995-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a6995-124">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.</span><span class="sxs-lookup"><span data-stu-id="a6995-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a6995-125">Określ, kto może używać tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="a6995-125">Choose who can use this connection.</span></span> <span data-ttu-id="a6995-126">Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy.</span><span class="sxs-lookup"><span data-stu-id="a6995-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a6995-127">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a6995-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a6995-128">Wpisz **[Identyfikator klienta usługi Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="a6995-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="a6995-129">Wprowadź **[zatwierdzony token dewelopera usługi Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="a6995-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="a6995-130">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.</span><span class="sxs-lookup"><span data-stu-id="a6995-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a6995-131">Wybierz **Uwierzytelnianie za pomocą usługi Google Ads** i przekaż swoje poświadczenia w usłudze Google AD.</span><span class="sxs-lookup"><span data-stu-id="a6995-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="a6995-132">Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a6995-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a6995-133">Aby zakończyć połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="a6995-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="a6995-134">Konfigurowanie eksportu</span><span class="sxs-lookup"><span data-stu-id="a6995-134">Configure an export</span></span>

<span data-ttu-id="a6995-135">Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="a6995-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a6995-136">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a6995-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a6995-137">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="a6995-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a6995-138">Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="a6995-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a6995-139">W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Google Ads.</span><span class="sxs-lookup"><span data-stu-id="a6995-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="a6995-140">Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="a6995-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a6995-141">Wprowadź **[identyfikator odbiorcy usługi Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** i wybierz pozycję **Połącz**, aby zainicjować połączenie z usługą Google Ads.</span><span class="sxs-lookup"><span data-stu-id="a6995-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="a6995-142">W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta.</span><span class="sxs-lookup"><span data-stu-id="a6995-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="a6995-143">Powtórz te same kroki dla pól **Imię** i **Nazwisko**.</span><span class="sxs-lookup"><span data-stu-id="a6995-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="a6995-144">Wybierz segmenty, które chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="a6995-144">Select the segments you want to export.</span></span> <span data-ttu-id="a6995-145">W sumie do maksymalnie 1 000 000 profilów klientów można wyeksportować do Google Ads.</span><span class="sxs-lookup"><span data-stu-id="a6995-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="a6995-146">Zapisanie eksportu nie uruchamia natychmiastowo eksportu.</span><span class="sxs-lookup"><span data-stu-id="a6995-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a6995-147">Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a6995-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a6995-148">Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a6995-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a6995-149">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="a6995-149">Data privacy and compliance</span></span>

<span data-ttu-id="a6995-150">Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Google Ads można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="a6995-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a6995-151">Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że Google Ads spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="a6995-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="a6995-152">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a6995-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a6995-153">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="a6995-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
