---
title: Eksportowanie danych usługi Customer Insights do ActiveCampaign
description: Dowiedz się, jak skonfigurować połączenie i wyeksportować je do usługi ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314656"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="ec128-103">Eksportowanie segmentów do ActiveCampaign (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="ec128-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="ec128-104">Eksportuj segmenty ujednoliconych profili klientów do ActiveCampaign i wykorzystaj je w działaniach marketingowych.</span><span class="sxs-lookup"><span data-stu-id="ec128-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ec128-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="ec128-105">Prerequisites</span></span>

-   <span data-ttu-id="ec128-106">Użytkownik ma konto [ActiveCampaign](https://www.activecampaign.com/) i odpowiednie uprawnienia administratora.</span><span class="sxs-lookup"><span data-stu-id="ec128-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ec128-107">Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.</span><span class="sxs-lookup"><span data-stu-id="ec128-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ec128-108">Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole z adresem e-mail.</span><span class="sxs-lookup"><span data-stu-id="ec128-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ec128-109">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="ec128-109">Known limitations</span></span>

- <span data-ttu-id="ec128-110">Podczas jednego eksportu do ActiveCampaign możesz wyeksportować do 1 miliona profili, a cały proces może trwać do 90 minut.</span><span class="sxs-lookup"><span data-stu-id="ec128-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="ec128-111">Eksportowanie do usługi ActiveCampaign jest ograniczone do segmentów.</span><span class="sxs-lookup"><span data-stu-id="ec128-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="ec128-112">Liczba profili, które możesz wyeksportować do ActiveCampaign, zależy od Twojej umowy z ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="ec128-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="ec128-113">Skonfiguruj połączenie z aplikacjami usługi ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="ec128-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="ec128-114">Przejdź do **Admin** > **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="ec128-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ec128-115">Wybierz opcję **Dodaj połączenie** i wybierz opcję **ActiveCampaign**, aby skonfigurować połączenie.</span><span class="sxs-lookup"><span data-stu-id="ec128-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="ec128-116">W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="ec128-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ec128-117">Wyświetlana nazwa i typ połączenia opisują to połączenie.</span><span class="sxs-lookup"><span data-stu-id="ec128-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ec128-118">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.</span><span class="sxs-lookup"><span data-stu-id="ec128-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ec128-119">Określ, kto może używać tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="ec128-119">Choose who can use this connection.</span></span> <span data-ttu-id="ec128-120">Domyślnie – tylko administratorzy.</span><span class="sxs-lookup"><span data-stu-id="ec128-120">By default, it's only administrators.</span></span> <span data-ttu-id="ec128-121">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ec128-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ec128-122">Wprowadź [klucz interfejsu API ActiveCampaign i nazwę hosta REST punktu końcowego](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span><span class="sxs-lookup"><span data-stu-id="ec128-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="ec128-123">Nazwa hosta punktu końcowego REST jest tylko nazwą hosta, bez https://.</span><span class="sxs-lookup"><span data-stu-id="ec128-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="ec128-124">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.</span><span class="sxs-lookup"><span data-stu-id="ec128-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ec128-125">Wybierz opcję **Połącz**, aby zainicjować połączenie z ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="ec128-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="ec128-126">Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ec128-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ec128-127">Aby zakończyć połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ec128-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ec128-128">Konfigurowanie eksportu</span><span class="sxs-lookup"><span data-stu-id="ec128-128">Configure an export</span></span>

<span data-ttu-id="ec128-129">Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="ec128-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="ec128-130">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ec128-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ec128-131">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="ec128-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ec128-132">Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="ec128-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ec128-133">W polu **Połączenie do eksportu** wybierz połączenie z sekcji ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="ec128-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="ec128-134">Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="ec128-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ec128-135">Wprowadź [**Identyfikator listy usługi ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span><span class="sxs-lookup"><span data-stu-id="ec128-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="ec128-136">W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta.</span><span class="sxs-lookup"><span data-stu-id="ec128-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ec128-137">Jest on niezbędny do eksportu segmentów do ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="ec128-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="ec128-138">Opcjonalnie możesz wyeksportować Imię, Nazwisko i Telefon, aby stworzyć bardziej spersonalizowane wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="ec128-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="ec128-139">Wybierz opcję Dodaj atrybut, aby zamapować te pola.</span><span class="sxs-lookup"><span data-stu-id="ec128-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="ec128-140">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ec128-140">Select **Save**.</span></span>

<span data-ttu-id="ec128-141">Zapisanie eksportu nie uruchamia natychmiastowo eksportu.</span><span class="sxs-lookup"><span data-stu-id="ec128-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ec128-142">Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ec128-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ec128-143">Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ec128-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ec128-144">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="ec128-144">Data privacy and compliance</span></span>

<span data-ttu-id="ec128-145">Włączenie Dynamics 365 Customer Insights w celu przekazywania danych do usługi ActiveCampaign umożliwia przesyłanie danych poza granice obszaru zgodności dla Dynamics 365 Customer Insights, w tym potencjalnie poufne dane, takie jak dane osobiste.</span><span class="sxs-lookup"><span data-stu-id="ec128-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ec128-146">Microsoft będzie przekazywać takie dane zgodnie z Twoimi instrukcjami, ale to Ty jesteś odpowiedzialny za zapewnienie, że ActiveCampaign spełnia wszelkie zobowiązania dotyczące prywatności i bezpieczeństwa, jakie możesz mieć.</span><span class="sxs-lookup"><span data-stu-id="ec128-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ec128-147">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ec128-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="ec128-148">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="ec128-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
