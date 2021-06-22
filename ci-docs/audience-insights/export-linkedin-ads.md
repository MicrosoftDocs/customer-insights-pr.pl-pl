---
title: Eksportowanie danych usługi Customer Insights do usługi LinkedIn Ads
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124533"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="da4dd-103">Eksportowanie segmentów do usługi LinkedIn Ads (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="da4dd-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="da4dd-104">Eksportuj segmenty ujednoliconych profili klientów do LinkedIn Ads, aby tworzyć dopasowane grupy Matched Audiences.</span><span class="sxs-lookup"><span data-stu-id="da4dd-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="da4dd-105">Wykorzystaj dopasowane grupy Matched Audiences do targetowania firm i kontaktów.</span><span class="sxs-lookup"><span data-stu-id="da4dd-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="da4dd-106">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="da4dd-106">Prerequisites</span></span>

-   <span data-ttu-id="da4dd-107">Użytkownik ma [konto LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) i odpowiednie dane logowania administratora.</span><span class="sxs-lookup"><span data-stu-id="da4dd-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="da4dd-108">Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.</span><span class="sxs-lookup"><span data-stu-id="da4dd-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="da4dd-109">Profile klientów w wyeksportowanych segmentach zawierają pole z adresem e-mail.</span><span class="sxs-lookup"><span data-stu-id="da4dd-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="da4dd-110">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="da4dd-110">Known limitations</span></span>

- <span data-ttu-id="da4dd-111">Do usługi LinkedIn Ads można wyeksportować do 100 000 profili.</span><span class="sxs-lookup"><span data-stu-id="da4dd-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="da4dd-112">Eksportowanie do usługi LinkedIn Ads jest ograniczone do segmentów.</span><span class="sxs-lookup"><span data-stu-id="da4dd-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="da4dd-113">Wyeksportowanie do 100 tysięcy profilów do usługi LinkedIn Ads może potrwać do 10 minut.</span><span class="sxs-lookup"><span data-stu-id="da4dd-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="da4dd-114">Skonfiguruj połączenie z usługą LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="da4dd-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="da4dd-115">W analizie odbiorcy przejdź do pozycji **Admin** > **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="da4dd-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="da4dd-116">Wybierz opcję **Dodaj połączenie** i wybierz opcję **LinkedIn Ads**, aby skonfigurować połączenie.</span><span class="sxs-lookup"><span data-stu-id="da4dd-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="da4dd-117">W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="da4dd-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="da4dd-118">Wyświetlana nazwa i typ połączenia opisują to połączenie.</span><span class="sxs-lookup"><span data-stu-id="da4dd-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="da4dd-119">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.</span><span class="sxs-lookup"><span data-stu-id="da4dd-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="da4dd-120">Określ, kto może używać tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="da4dd-120">Choose who can use this connection.</span></span> <span data-ttu-id="da4dd-121">Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy.</span><span class="sxs-lookup"><span data-stu-id="da4dd-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="da4dd-122">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="da4dd-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="da4dd-123">Należy podać [Identyfikator konta LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).</span><span class="sxs-lookup"><span data-stu-id="da4dd-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="da4dd-124">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.</span><span class="sxs-lookup"><span data-stu-id="da4dd-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="da4dd-125">Wybierz opcję **Połącz**, aby inicjować połączenie z usługą Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="da4dd-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="da4dd-126">Wybierz opcję **Uwierzytelnij za pomocą usługi LinkedIn** i podaj swoje poświadczenia administratora dla usługi LinkedIn Campaign Manager.</span><span class="sxs-lookup"><span data-stu-id="da4dd-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="da4dd-127">Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="da4dd-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="da4dd-128">Aby zakończyć połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="da4dd-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="da4dd-129">Konfigurowanie eksportu</span><span class="sxs-lookup"><span data-stu-id="da4dd-129">Configure an export</span></span>

<span data-ttu-id="da4dd-130">Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="da4dd-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="da4dd-131">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="da4dd-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="da4dd-132">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="da4dd-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="da4dd-133">Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="da4dd-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="da4dd-134">W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="da4dd-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="da4dd-135">Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="da4dd-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="da4dd-136">Możesz określić, czy chcesz eksportować dane, aby [ukierunkowywać kontakty](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting), czy [ukierunkowywać przedsiębiorstwa](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) w usłudze LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="da4dd-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="da4dd-137">W sekcji **Dopasowywanie danych** wybierz pole w ujednoliconym profilu klienta reprezentujące adres e-mail klienta.</span><span class="sxs-lookup"><span data-stu-id="da4dd-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="da4dd-138">Wymagane jest wyeksportowanie segmentów do usługi LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="da4dd-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="da4dd-139">Wybierz segmenty, które chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="da4dd-139">Select the segments you want to export.</span></span> <span data-ttu-id="da4dd-140">Matched Audiences w LinkedIn Campaign Manager zostaną automatycznie utworzone z nazwą segmentów, które wybrałeś do eksportu.</span><span class="sxs-lookup"><span data-stu-id="da4dd-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="da4dd-141">W przypadku każdego z segmentów będzie to oddzielne dopasowanie odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="da4dd-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="da4dd-142">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="da4dd-142">Select **Save**.</span></span>

<span data-ttu-id="da4dd-143">Zapisanie eksportu nie uruchamia natychmiastowo eksportu.</span><span class="sxs-lookup"><span data-stu-id="da4dd-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="da4dd-144">Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="da4dd-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="da4dd-145">Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="da4dd-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="da4dd-146">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="da4dd-146">Data privacy and compliance</span></span>

<span data-ttu-id="da4dd-147">Włączenie rozwiązania Dynamics 365 Customer Insights do przekazywania danych do usługi LinkedIn Ads umożliwia przesyłanie danych poza granicą zgodności z przepisami Dynamics 365 Customer Insights, w tym potencjalnie poufnych danych, takich jak dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="da4dd-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="da4dd-148">Microsoft przesyła takie dane zgodnie z instrukcjami użytkownika, ale użytkownik musi zagwarantować, że usługa LinkedIn Ads będzie spełniać wszelkie zobowiązania dotyczące prywatności lub bezpieczeństwa, jakie może mieć użytkownik.</span><span class="sxs-lookup"><span data-stu-id="da4dd-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="da4dd-149">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="da4dd-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="da4dd-150">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="da4dd-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
