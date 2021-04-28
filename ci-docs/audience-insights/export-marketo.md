---
title: Eksportowanie danych Customer Insights do usługi Marketo
description: Dowiedz się, jak skonfigurować połączenie i eksport do programu Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759834"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="37e00-103">Eksportowanie segmentów do programu Marketo (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="37e00-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="37e00-104">Eksportuj segmenty ujednoliconych profili klientów w celu generowania kampanii, prowadzenia marketingu e-mailowego i korzystania z określonych grup klientów w Marketo.</span><span class="sxs-lookup"><span data-stu-id="37e00-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="37e00-105">Wymagania wstępne dla połączenia</span><span class="sxs-lookup"><span data-stu-id="37e00-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="37e00-106">Użytkownik ma [konto usługi Marketo](https://login.marketo.com/) i odpowiadające mu poświadczenia administratora.</span><span class="sxs-lookup"><span data-stu-id="37e00-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="37e00-107">W Marketo istnieją już listy i odpowiadające im identyfikatory.</span><span class="sxs-lookup"><span data-stu-id="37e00-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="37e00-108">Aby uzyskać więcej informacji, zobacz [listy Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="37e00-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="37e00-109">Posiadasz [skonfigurowane segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="37e00-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="37e00-110">Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="37e00-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="37e00-111">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="37e00-111">Known limitations</span></span>

- <span data-ttu-id="37e00-112">Do 1 miliona profili na eksport do Marketo.</span><span class="sxs-lookup"><span data-stu-id="37e00-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="37e00-113">Eksport do Marketo jest ograniczony do segmentów.</span><span class="sxs-lookup"><span data-stu-id="37e00-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="37e00-114">Eksportowanie segmentów razem z profilem 1 000 000 może potrwać do 3 godzin.</span><span class="sxs-lookup"><span data-stu-id="37e00-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="37e00-115">Liczba profilów, które można eksportować do Marketo, jest zależna od kontraktu i ograniczona jego Marketo.</span><span class="sxs-lookup"><span data-stu-id="37e00-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="37e00-116">Skonfiguruj połączenie z usługą Marketo</span><span class="sxs-lookup"><span data-stu-id="37e00-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="37e00-117">Przejdź do **Admin** > **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="37e00-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="37e00-118">Wybierz opcję **Dodaj połączenie** i wybierz opcję **Marketo**, aby skonfigurować połączenie.</span><span class="sxs-lookup"><span data-stu-id="37e00-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="37e00-119">W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="37e00-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="37e00-120">Wyświetlana nazwa i typ połączenia opisują to połączenie.</span><span class="sxs-lookup"><span data-stu-id="37e00-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="37e00-121">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.</span><span class="sxs-lookup"><span data-stu-id="37e00-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="37e00-122">Określ, kto może używać tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="37e00-122">Choose who can use this connection.</span></span> <span data-ttu-id="37e00-123">Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy.</span><span class="sxs-lookup"><span data-stu-id="37e00-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="37e00-124">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="37e00-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="37e00-125">Wprowadź **[Identyfikator klienta Marketo, klucz tajny klienta i nazwa hosta punktu końcowego REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="37e00-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="37e00-126">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność**, a następnie wybierz **Połącz**, aby zainicjować połączenie z Marketo.</span><span class="sxs-lookup"><span data-stu-id="37e00-126">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="37e00-127">Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="37e00-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="37e00-128">Aby zakończyć połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="37e00-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="37e00-129">Konfigurowanie eksportu</span><span class="sxs-lookup"><span data-stu-id="37e00-129">Configure an export</span></span>

<span data-ttu-id="37e00-130">Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="37e00-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="37e00-131">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="37e00-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="37e00-132">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="37e00-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="37e00-133">Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="37e00-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="37e00-134">W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Marketo.</span><span class="sxs-lookup"><span data-stu-id="37e00-134">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="37e00-135">Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="37e00-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="37e00-136">Wprowadź **[Identyfikator listy Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="37e00-136">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="37e00-137">W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta.</span><span class="sxs-lookup"><span data-stu-id="37e00-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="37e00-138">Opcjonalnie możesz wyeksportować **Imię**, **Nazwisko**, **Miejscowość**, **Województwo** i **Kraj/region**, aby utworzyć bardziej spersonalizowane wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="37e00-138">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="37e00-139">Wybierz opcję **Dodaj atrybut**, aby zamapować te pola.</span><span class="sxs-lookup"><span data-stu-id="37e00-139">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="37e00-140">Wybierz segmenty, które chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="37e00-140">Select the segments you want to export.</span></span> <span data-ttu-id="37e00-141">W sumie do maksymalnie 1 000 000 profilów klientów można wyeksportować do Marketo.</span><span class="sxs-lookup"><span data-stu-id="37e00-141">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="37e00-142">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="37e00-142">Select **Save**.</span></span>

<span data-ttu-id="37e00-143">Zapisanie eksportu nie uruchamia natychmiastowo eksportu.</span><span class="sxs-lookup"><span data-stu-id="37e00-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="37e00-144">Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="37e00-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="37e00-145">Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="37e00-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="37e00-146">W programie Marketo można znaleźć segmenty na [listach Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="37e00-146">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="37e00-147">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="37e00-147">Data privacy and compliance</span></span>

<span data-ttu-id="37e00-148">Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi Marketo można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="37e00-148">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="37e00-149">Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że Marketo spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="37e00-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="37e00-150">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="37e00-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="37e00-151">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="37e00-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]