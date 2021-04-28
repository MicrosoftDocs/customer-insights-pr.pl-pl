---
title: Eksportowanie danych Customer Insights do usługi Menedżer reklam Facebook
description: Dowiedz się, jak skonfigurować połączenie i eksport do Menedżera reklam na portalu Facebook.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ca32906a98bc734639fb369d6f5a92e8888fd850
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906823"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="86145-103">Eksportowanie listy segmentów do Menedżera reklam na portalu Facebook (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="86145-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="86145-104">Eksportuj segmenty zunifikowanych profilów klientów do Menedżera Facebook Ads, aby tworzyć kampanie Facebook i Instagram.</span><span class="sxs-lookup"><span data-stu-id="86145-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="86145-105">Wymagania wstępne dla połączenia</span><span class="sxs-lookup"><span data-stu-id="86145-105">Prerequisites for connection</span></span>

- <span data-ttu-id="86145-106">Musisz mieć [**konto reklamowe na portalu Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) zawierające [**konto firmowe na portalu Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="86145-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="86145-107">Musisz być Administratorem [**konta reklam Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="86145-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="86145-108">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="86145-108">Known limitations</span></span>

- <span data-ttu-id="86145-109">Do 10 milionów profili klientów na eksport do Menedżera reklam na portalu Facebook.</span><span class="sxs-lookup"><span data-stu-id="86145-109">Up to 10 million customer profile per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="86145-110">Eksport do Menedżera reklam na portalu Facebook jest ograniczony do segmentów.</span><span class="sxs-lookup"><span data-stu-id="86145-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="86145-111">Tworzenie lub aktualizowanie niestandardowych odbiorców na portalu Facebook tylko typu *lista klientów*.</span><span class="sxs-lookup"><span data-stu-id="86145-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="86145-112">Eksportowanie segmentów zawierających łącznie 10 milionów profili może zająć do 90 minut.</span><span class="sxs-lookup"><span data-stu-id="86145-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="86145-113">Konfiguruj połączenie z Menedżerem reklam na portalu Facebook</span><span class="sxs-lookup"><span data-stu-id="86145-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="86145-114">Przed utworzeniem eksportu administrator musi skonfigurować połączenie z usługą i umożliwić współautorom korzystanie z połączenia.</span><span class="sxs-lookup"><span data-stu-id="86145-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="86145-115">Przejdź do **Admin** > **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="86145-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="86145-116">Wybierz opcję **Dodaj połączenie** i wybierz opcję **Menedżer reklam na portalu Facebook**, aby skonfigurować połączenie.</span><span class="sxs-lookup"><span data-stu-id="86145-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="86145-117">W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="86145-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="86145-118">Wyświetlana nazwa i typ połączenia opisują to połączenie.</span><span class="sxs-lookup"><span data-stu-id="86145-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="86145-119">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.</span><span class="sxs-lookup"><span data-stu-id="86145-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="86145-120">Określ, kto może używać tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="86145-120">Choose who can use this connection.</span></span> <span data-ttu-id="86145-121">Jeśli nie podejmiesz działania, ustawieniem domyślnym będą **Administratorzy**.</span><span class="sxs-lookup"><span data-stu-id="86145-121">If you take no action, the default will be **Administrators**.</span></span> <span data-ttu-id="86145-122">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="86145-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="86145-123">Uwierzytelnianie przy użyciu reklam na portalu Facebook:</span><span class="sxs-lookup"><span data-stu-id="86145-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="86145-124">Wybierz **Kontynuuj z Facebook**, aby zalogować się do swojego konta Facebook Ad.</span><span class="sxs-lookup"><span data-stu-id="86145-124">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

   1. <span data-ttu-id="86145-125">Zezwalaj na uprawnienie **ads_management** po uwierzytelnieniu za pomocą Facebook.</span><span class="sxs-lookup"><span data-stu-id="86145-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="86145-126">Wybierz **Konto Facebook Ads**, z którym chcesz pracować.</span><span class="sxs-lookup"><span data-stu-id="86145-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="86145-127">Wybierz **Istniejącego odbiorcę niestandardowego** z listy rozwijanej lub utwórz **Nowego odbiorcę niestandardowego**.</span><span class="sxs-lookup"><span data-stu-id="86145-127">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="86145-128">Aby uzyskać więcej informacji, zobacz temat [**Odbiorcy w Menedżerze Facebook Ads**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="86145-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="86145-129">Za pomocą tego eksportu można tylko tworzyć lub aktualizować odbiorców na portalu Facebook typu *lista klientów*.</span><span class="sxs-lookup"><span data-stu-id="86145-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="86145-130">W niektórych przypadkach na liście rozwijanej można zobaczyć niestandardowych odbiorców różnych typów.</span><span class="sxs-lookup"><span data-stu-id="86145-130">In some cases, you see custom audiences of different types in the drop-down list.</span></span> <span data-ttu-id="86145-131">Wybranie innego typu danych niż *lista klientów* spowoduje niepowodzenie eksportu.</span><span class="sxs-lookup"><span data-stu-id="86145-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="86145-132">Przejrzyj zasady **Prywatność danych i zgodność z przepisami** i wybierz opcję **Wyrażam zgodę**.</span><span class="sxs-lookup"><span data-stu-id="86145-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="86145-133">Aby zakończyć połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="86145-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="86145-134">Konfigurowanie eksportu</span><span class="sxs-lookup"><span data-stu-id="86145-134">Configure an export</span></span>

<span data-ttu-id="86145-135">Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="86145-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="86145-136">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="86145-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="86145-137">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="86145-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="86145-138">Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="86145-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="86145-139">W opcji **Połączenia dla eksportu** wybierz połączenie z sekcji Menedżer reklam na portalu **Facebook**.</span><span class="sxs-lookup"><span data-stu-id="86145-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="86145-140">Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="86145-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="86145-141">W polu **Wybierz identyfikator klucza** wybierz **E-mail**, **Nazwisko i adres** lub **Telefon**, aby przesłać do Menedżera Facebook Ads.</span><span class="sxs-lookup"><span data-stu-id="86145-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="86145-142">W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="86145-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="86145-143">Mapowanie odpowiednich atrybutów ze swojej zunifikowanej encji klienta dla wybranego identyfikatora klucza.</span><span class="sxs-lookup"><span data-stu-id="86145-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="86145-144">[WSKAZÓWKA] Największa szansa dopasowania pojawia się w przypadku wybrania opcji **E-mail** jako identyfikatora klucza.</span><span class="sxs-lookup"><span data-stu-id="86145-144">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="86145-145">Dodanie dodatkowych identyfikatorów może poprawić dopasowanie.</span><span class="sxs-lookup"><span data-stu-id="86145-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="86145-146">Wybierz **Dodaj atrybut**, aby zamapować więcej atrybutów do Menedżera reklam na portalu Facebook.</span><span class="sxs-lookup"><span data-stu-id="86145-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="86145-147">Atrybuty Menedżera Facebook Ads Ads są mapowane na poniższe przyjazne nazwy użytkowników: **FN** = **Imię**, **LN** = **Nazwisko**, **FI** = **Pierwszy inicjał**, **PHONE** = **Telefon**, **GEN** = **Płeć**, **DOB** = **Data urodzenia**, **ST** = **Stan**, **CT** = **Miasto**, **ZIP** = **Kod pocztowy**, **COUNTRY** = **Kraj / Region**</span><span class="sxs-lookup"><span data-stu-id="86145-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="86145-148">Wybierz segmenty, które chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="86145-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="86145-149">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="86145-149">Select **Save**.</span></span>

<span data-ttu-id="86145-150">Zapisanie eksportu nie uruchamia natychmiastowo eksportu.</span><span class="sxs-lookup"><span data-stu-id="86145-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="86145-151">Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="86145-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="86145-152">Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="86145-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="86145-153">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="86145-153">Data privacy and compliance</span></span>

<span data-ttu-id="86145-154">Włączając Dynamics 365 Customer Insights przesyłanie danych do menedżera reklam Facebook, zezwalasz na przesyłanie danych poza granice zgodności dla Dynamics 365 Customer Insights, w tym potencjalnie wrażliwych danych, takich jak Dane Osobowe.</span><span class="sxs-lookup"><span data-stu-id="86145-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="86145-155">Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że reklamy Facebook spełniają wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="86145-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="86145-156">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="86145-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="86145-157">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="86145-157">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
