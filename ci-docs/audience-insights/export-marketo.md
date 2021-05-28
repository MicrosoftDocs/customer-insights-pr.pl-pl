---
title: Eksportowanie danych Customer Insights do usługi Marketo
description: Dowiedz się, jak skonfigurować połączenie i eksport do programu Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059329"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="1a2c1-103">Eksportowanie segmentów do programu Marketo (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="1a2c1-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="1a2c1-104">Eksportuj segmenty ujednoliconych profili klientów w celu generowania kampanii, prowadzenia marketingu e-mailowego i korzystania z określonych grup klientów w Marketo.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="1a2c1-105">Wymagania wstępne dla połączenia</span><span class="sxs-lookup"><span data-stu-id="1a2c1-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="1a2c1-106">Użytkownik ma [konto usługi Marketo](https://login.marketo.com/) i odpowiadające mu poświadczenia administratora.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1a2c1-107">W Marketo istnieją już listy i odpowiadające im identyfikatory.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="1a2c1-108">Aby uzyskać więcej informacji, zobacz [listy Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="1a2c1-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="1a2c1-109">Posiadasz [skonfigurowane segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="1a2c1-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="1a2c1-110">Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1a2c1-111">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="1a2c1-111">Known limitations</span></span>

- <span data-ttu-id="1a2c1-112">Do 1 miliona profili na eksport do Marketo.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="1a2c1-113">Eksport do Marketo jest ograniczony do segmentów.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="1a2c1-114">Eksportowanie segmentów razem z profilem 1 000 000 może potrwać do 3 godzin.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="1a2c1-115">Liczba profilów, które można eksportować do Marketo, jest zależna od kontraktu i ograniczona jego Marketo.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="1a2c1-116">Skonfiguruj połączenie z usługą Marketo</span><span class="sxs-lookup"><span data-stu-id="1a2c1-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="1a2c1-117">Przejdź do **Admin** > **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1a2c1-118">Wybierz opcję **Dodaj połączenie** i wybierz opcję **Marketo**, aby skonfigurować połączenie.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="1a2c1-119">W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1a2c1-120">Wyświetlana nazwa i typ połączenia opisują to połączenie.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1a2c1-121">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1a2c1-122">Określ, kto może używać tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-122">Choose who can use this connection.</span></span> <span data-ttu-id="1a2c1-123">Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1a2c1-124">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1a2c1-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1a2c1-125">Wprowadź **[Identyfikator klienta Marketo, klucz tajny klienta i nazwa hosta punktu końcowego REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span> <span data-ttu-id="1a2c1-126">Nazwa hosta punktu końcowego REST jest tylko nazwą hosta, bez `https://`.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-126">The REST Endpoint Hostname is the hostname only, without `https://`.</span></span> <span data-ttu-id="1a2c1-127">Przykład: `xyz-abc-123.mktorest.com`.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-127">Example: `xyz-abc-123.mktorest.com`.</span></span> 

1. <span data-ttu-id="1a2c1-128">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność**, a następnie wybierz **Połącz**, aby zainicjować połączenie z Marketo.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-128">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="1a2c1-129">Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-129">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="1a2c1-130">Aby zakończyć połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-130">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="1a2c1-131">Konfigurowanie eksportu</span><span class="sxs-lookup"><span data-stu-id="1a2c1-131">Configure an export</span></span>

<span data-ttu-id="1a2c1-132">Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-132">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1a2c1-133">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1a2c1-133">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1a2c1-134">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1a2c1-135">Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-135">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1a2c1-136">W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Marketo.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-136">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="1a2c1-137">Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-137">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1a2c1-138">Wprowadź **[Identyfikator listy Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-138">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span></span> <span data-ttu-id="1a2c1-139">Identyfikator listy jest wartością wyłącznie numeryczną.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-139">The list ID is a purely numerical value.</span></span> <span data-ttu-id="1a2c1-140">Jeśli na przykład identyfikator listy Marketo to ST12345A7, usuń znak przed i po liczbach, a następnie wprowadź `12345`.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-140">For example, if your Marketo list ID is ST12345A7, remove the character before and after the numerals and enter `12345`.</span></span> 

1. <span data-ttu-id="1a2c1-141">W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="1a2c1-142">Opcjonalnie możesz wyeksportować **Imię**, **Nazwisko**, **Miejscowość**, **Województwo** i **Kraj/region**, aby utworzyć bardziej spersonalizowane wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-142">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="1a2c1-143">Wybierz opcję **Dodaj atrybut**, aby zamapować te pola.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-143">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="1a2c1-144">Wybierz segmenty, które chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-144">Select the segments you want to export.</span></span> <span data-ttu-id="1a2c1-145">W sumie do maksymalnie 1 000 000 profilów klientów można wyeksportować do Marketo.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-145">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="1a2c1-146">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-146">Select **Save**.</span></span>

<span data-ttu-id="1a2c1-147">Zapisanie eksportu nie uruchamia natychmiastowo eksportu.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-147">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1a2c1-148">Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1a2c1-148">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1a2c1-149">Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1a2c1-149">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="1a2c1-150">W programie Marketo można znaleźć segmenty na [listach Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="1a2c1-150">In Marketo, you can now find your segments under [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1a2c1-151">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="1a2c1-151">Data privacy and compliance</span></span>

<span data-ttu-id="1a2c1-152">Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Marketo można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-152">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1a2c1-153">Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że Marketo spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-153">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1a2c1-154">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1a2c1-154">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1a2c1-155">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="1a2c1-155">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
