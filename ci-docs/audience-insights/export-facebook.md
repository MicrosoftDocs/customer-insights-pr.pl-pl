---
title: Eksportowanie danych Customer Insights do usługi Menedżer reklam Facebook
description: Informacje o konfigurowaniu połączenia z Menedżerem Facebook Ads.
ms.date: 06/05/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3e2b52fe743563e4bf61d870cbf1718e6c752a67
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596696"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="f07ab-103">Łącznik dla Menedżera Facebook Ads (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="f07ab-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="f07ab-104">Eksportuj segmenty zunifikowanych profilów klientów do Menedżera Facebook Ads, aby tworzyć kampanie Facebook i Instagram.</span><span class="sxs-lookup"><span data-stu-id="f07ab-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f07ab-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="f07ab-105">Prerequisites</span></span>

- <span data-ttu-id="f07ab-106">Musisz posiadać [**konto reklam Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), obejmujące [**konto firmowe Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="f07ab-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="f07ab-107">Musisz być Administratorem [**konta reklam Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="f07ab-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="f07ab-108">Połącz z Menedżerem Facebook Ads</span><span class="sxs-lookup"><span data-stu-id="f07ab-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="f07ab-109">Przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.</span><span class="sxs-lookup"><span data-stu-id="f07ab-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f07ab-110">W obszarze **Menedżer Facebook Ads** wybierz **Konfiguruj**.</span><span class="sxs-lookup"><span data-stu-id="f07ab-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="f07ab-111">W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej exportu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="f07ab-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="f07ab-112">Wybierz **Kontynuuj z Facebook**, aby zalogować się do swojego konta Facebook Ad.</span><span class="sxs-lookup"><span data-stu-id="f07ab-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="f07ab-113">Zezwalaj na uprawnienie **ads_management** po uwierzytelnieniu za pomocą Facebook.</span><span class="sxs-lookup"><span data-stu-id="f07ab-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="f07ab-114">Wybierz **Konto Facebook Ads**, z którym chcesz pracować.</span><span class="sxs-lookup"><span data-stu-id="f07ab-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="f07ab-115">Wybierz **Istniejącego odbiorcę niestandardowego** z listy rozwijanej lub utwórz **Nowego odbiorcę niestandardowego**.</span><span class="sxs-lookup"><span data-stu-id="f07ab-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="f07ab-116">Aby uzyskać więcej informacji, zobacz temat [**Odbiorcy w Menedżerze Facebook Ads**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="f07ab-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="f07ab-117">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.</span><span class="sxs-lookup"><span data-stu-id="f07ab-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f07ab-118">Wybierz **Dalej**, aby skonfigurować eksport.</span><span class="sxs-lookup"><span data-stu-id="f07ab-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="f07ab-119">Skonfiguruj łącznik</span><span class="sxs-lookup"><span data-stu-id="f07ab-119">Configure the connector</span></span>

1. <span data-ttu-id="f07ab-120">W polu **Wybierz identyfikator klucza** wybierz **E-mail**, **Nazwisko i adres** lub **Telefon**, aby przesłać do Menedżera Facebook Ads.</span><span class="sxs-lookup"><span data-stu-id="f07ab-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="f07ab-121">Mapowanie odpowiednich atrybutów ze swojej zunifikowanej encji klienta dla wybranego identyfikatora klucza.</span><span class="sxs-lookup"><span data-stu-id="f07ab-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="f07ab-122">[WSKAZÓWKA] Największa szansa dopasowania pojawia się w przypadku wybrania opcji **E-mail** jako identyfikatora klucza.</span><span class="sxs-lookup"><span data-stu-id="f07ab-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="f07ab-123">Dodanie dodatkowych identyfikatorów może poprawić dopasowanie.</span><span class="sxs-lookup"><span data-stu-id="f07ab-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="f07ab-124">Wybierz **Dodaj atrybut**, aby zamapować dodatkowe atrybuty na wysyłanie do Menedżera Facebook Ads.</span><span class="sxs-lookup"><span data-stu-id="f07ab-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="f07ab-125">Atrybuty Menedżera Facebook Ads Ads są mapowane na poniższe przyjazne nazwy użytkowników: **FN** = **Imię**, **LN** = **Nazwisko**, **FI** = **Pierwszy inicjał**, **PHONE** = **Telefon**, **GEN** = **Płeć**, **DOB** = **Data urodzenia**, **ST** = **Stan**, **CT** = **Miasto**, **ZIP** = **Kod pocztowy**, **COUNTRY** = **Kraj / Region**</span><span class="sxs-lookup"><span data-stu-id="f07ab-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="f07ab-126">Wybierz segmenty, które chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="f07ab-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="f07ab-127">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f07ab-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="f07ab-128">Eksportowanie danych</span><span class="sxs-lookup"><span data-stu-id="f07ab-128">Export the data</span></span>

<span data-ttu-id="f07ab-129">Możesz [eksportować dane na żądanie](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f07ab-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="f07ab-130">Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f07ab-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f07ab-131">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="f07ab-131">Known limitations</span></span>

- <span data-ttu-id="f07ab-132">Do 10 milionów profili klientów na eksport do Menedżera reklam na Facebook</span><span class="sxs-lookup"><span data-stu-id="f07ab-132">Up to 10 million customer profile per export to Facebook Ads Manager</span></span> 
- <span data-ttu-id="f07ab-133">Eksport do Menedżera reklam na Facebook jest ograniczony do segmentów</span><span class="sxs-lookup"><span data-stu-id="f07ab-133">Export to Facebook Ads Manager is limited to segments</span></span>
- <span data-ttu-id="f07ab-134">Eksportowanie segmentów zawierających łącznie 10 milionów profili może zająć do 90 minut</span><span class="sxs-lookup"><span data-stu-id="f07ab-134">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f07ab-135">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="f07ab-135">Data privacy and compliance</span></span>

<span data-ttu-id="f07ab-136">Włączając Dynamics 365 Customer Insights przesyłanie danych do menedżera reklam Facebook, zezwalasz na przesyłanie danych poza granice zgodności dla Dynamics 365 Customer Insights, w tym potencjalnie wrażliwych danych, takich jak Dane Osobowe.</span><span class="sxs-lookup"><span data-stu-id="f07ab-136">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f07ab-137">Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że reklamy Facebook spełniają wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="f07ab-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="f07ab-138">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f07ab-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f07ab-139">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="f07ab-139">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]