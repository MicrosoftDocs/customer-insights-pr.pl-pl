---
title: Eksportowanie danych Customer Insights do usługi Menedżer reklam Facebook
description: Informacje o konfigurowaniu połączenia z Menedżerem Facebook Ads.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8260e3b5e529f3d54678d9d6e11aebb2795e27fd
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643696"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="71ac2-103">Łącznik dla Menedżera Facebook Ads (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="71ac2-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="71ac2-104">Eksportuj segmenty zunifikowanych profilów klientów do Menedżera Facebook Ads, aby tworzyć kampanie Facebook i Instagram.</span><span class="sxs-lookup"><span data-stu-id="71ac2-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="71ac2-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="71ac2-105">Prerequisites</span></span>

- <span data-ttu-id="71ac2-106">Musisz posiadać [**konto reklam Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), obejmujące [**konto firmowe Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="71ac2-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="71ac2-107">Musisz być Administratorem [**konta reklam Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="71ac2-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="71ac2-108">Połącz z Menedżerem Facebook Ads</span><span class="sxs-lookup"><span data-stu-id="71ac2-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="71ac2-109">Przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.</span><span class="sxs-lookup"><span data-stu-id="71ac2-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="71ac2-110">W obszarze **Menedżer Facebook Ads** wybierz **Konfiguruj**.</span><span class="sxs-lookup"><span data-stu-id="71ac2-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="71ac2-111">W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej exportu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="71ac2-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="71ac2-112">Wybierz **Kontynuuj z Facebook**, aby zalogować się do swojego konta Facebook Ad.</span><span class="sxs-lookup"><span data-stu-id="71ac2-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="71ac2-113">Zezwalaj na uprawnienie **ads_management** po uwierzytelnieniu za pomocą Facebook.</span><span class="sxs-lookup"><span data-stu-id="71ac2-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="71ac2-114">Wybierz **Konto Facebook Ads**, z którym chcesz pracować.</span><span class="sxs-lookup"><span data-stu-id="71ac2-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="71ac2-115">Wybierz **Istniejącego odbiorcę niestandardowego** z listy rozwijanej lub utwórz **Nowego odbiorcę niestandardowego**.</span><span class="sxs-lookup"><span data-stu-id="71ac2-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="71ac2-116">Aby uzyskać więcej informacji, zobacz temat [**Odbiorcy w Menedżerze Facebook Ads**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="71ac2-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="71ac2-117">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.</span><span class="sxs-lookup"><span data-stu-id="71ac2-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="71ac2-118">Wybierz **Dalej**, aby skonfigurować eksport.</span><span class="sxs-lookup"><span data-stu-id="71ac2-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="71ac2-119">Skonfiguruj łącznik</span><span class="sxs-lookup"><span data-stu-id="71ac2-119">Configure the connector</span></span>

1. <span data-ttu-id="71ac2-120">W polu **Wybierz identyfikator klucza** wybierz **E-mail**, **Nazwisko i adres** lub **Telefon**, aby przesłać do Menedżera Facebook Ads.</span><span class="sxs-lookup"><span data-stu-id="71ac2-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="71ac2-121">Mapowanie odpowiednich atrybutów ze swojej zunifikowanej encji klienta dla wybranego identyfikatora klucza.</span><span class="sxs-lookup"><span data-stu-id="71ac2-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="71ac2-122">[WSKAZÓWKA] Największa szansa dopasowania pojawia się w przypadku wybrania opcji **E-mail** jako identyfikatora klucza.</span><span class="sxs-lookup"><span data-stu-id="71ac2-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="71ac2-123">Dodanie dodatkowych identyfikatorów może poprawić dopasowanie.</span><span class="sxs-lookup"><span data-stu-id="71ac2-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="71ac2-124">Wybierz **Dodaj atrybut**, aby zamapować dodatkowe atrybuty na wysyłanie do Menedżera Facebook Ads.</span><span class="sxs-lookup"><span data-stu-id="71ac2-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="71ac2-125">Atrybuty Menedżera Facebook Ads Ads są mapowane na poniższe przyjazne nazwy użytkowników: **FN** = **Imię**, **LN** = **Nazwisko**, **FI** = **Pierwszy inicjał**, **PHONE** = **Telefon**, **GEN** = **Płeć**, **DOB** = **Data urodzenia**, **ST** = **Stan**, **CT** = **Miasto**, **ZIP** = **Kod pocztowy**, **COUNTRY** = **Kraj / Region**</span><span class="sxs-lookup"><span data-stu-id="71ac2-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="71ac2-126">Wybierz segmenty, które chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="71ac2-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="71ac2-127">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="71ac2-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="71ac2-128">Eksportowanie danych</span><span class="sxs-lookup"><span data-stu-id="71ac2-128">Export the data</span></span>

<span data-ttu-id="71ac2-129">Możesz [eksportować dane na żądanie](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="71ac2-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="71ac2-130">Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="71ac2-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="71ac2-131">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="71ac2-131">Data privacy and compliance</span></span>

<span data-ttu-id="71ac2-132">Włączając Dynamics 365 Customer Insights przesyłanie danych do menedżera reklam Facebook, zezwalasz na przesyłanie danych poza granice zgodności dla Dynamics 365 Customer Insights, w tym potencjalnie wrażliwych danych, takich jak Dane Osobowe.</span><span class="sxs-lookup"><span data-stu-id="71ac2-132">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="71ac2-133">Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że reklamy Facebook spełniają wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="71ac2-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="71ac2-134">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="71ac2-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="71ac2-135">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="71ac2-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
