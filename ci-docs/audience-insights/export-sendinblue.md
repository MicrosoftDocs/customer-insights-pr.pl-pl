---
title: Eksportowanie danych usługi Customer Insights do Sendinblue
description: Dowiedz się, jak skonfigurować połączenie i wyeksportować je do usługi Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314655"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="8c66f-103">Eksportowanie segmentów do Sendinblue (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="8c66f-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="8c66f-104">Eksportuj segmenty ujednoliconych profili klientów, aby generować kampanie, prowadzić email marketing i korzystać z określonych grup klientów z Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="8c66f-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="8c66f-105">Wymagania wstępne dla połączenia</span><span class="sxs-lookup"><span data-stu-id="8c66f-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="8c66f-106">Użytkownik ma konto [Sendinblue](https://www.sendinblue.com/) i odpowiednie uprawnienia administratora.</span><span class="sxs-lookup"><span data-stu-id="8c66f-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="8c66f-107">Istnieją listy w Sendinblue i odpowiadające im identyfikatory.</span><span class="sxs-lookup"><span data-stu-id="8c66f-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="8c66f-108">Posiadasz [skonfigurowane segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="8c66f-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="8c66f-109">Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="8c66f-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8c66f-110">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="8c66f-110">Known limitations</span></span>

- <span data-ttu-id="8c66f-111">Do 1 miliona profili podczas eksportu do Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="8c66f-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="8c66f-112">Eksport do Sendinblue jest ograniczony do segmentów.</span><span class="sxs-lookup"><span data-stu-id="8c66f-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="8c66f-113">Eksport segmentów o łącznej liczbie 1 miliona profili może trwać do 90 minut.</span><span class="sxs-lookup"><span data-stu-id="8c66f-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="8c66f-114">Liczba profili, które możesz eksportować do Sendinblue, jest zależna i ograniczona od Twojej umowy z Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="8c66f-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="8c66f-115">Konfiguruj połączenie z Sendinblue</span><span class="sxs-lookup"><span data-stu-id="8c66f-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="8c66f-116">Przejdź do **Admin** > **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="8c66f-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="8c66f-117">Wybierz opcję **Dodaj połączenie** i wybierz opcję **Sendinblue**, aby skonfigurować połączenie.</span><span class="sxs-lookup"><span data-stu-id="8c66f-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="8c66f-118">W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="8c66f-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="8c66f-119">Wyświetlana nazwa i typ połączenia opisują to połączenie.</span><span class="sxs-lookup"><span data-stu-id="8c66f-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="8c66f-120">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.</span><span class="sxs-lookup"><span data-stu-id="8c66f-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="8c66f-121">Określ, kto może używać tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="8c66f-121">Choose who can use this connection.</span></span> <span data-ttu-id="8c66f-122">Domyślnie to tylko administratorzy.</span><span class="sxs-lookup"><span data-stu-id="8c66f-122">By default it's only administrators.</span></span> <span data-ttu-id="8c66f-123">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="8c66f-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="8c66f-124">Wprowadź **[klucz interfejsu API Sendinblue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span><span class="sxs-lookup"><span data-stu-id="8c66f-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="8c66f-125">Zaznacz opcję **Wyrażam zgodę** na **Zapisy zasad ochrony prywatności i zgodności** i wybierz opcję **Połącz**, aby inicjować połączenie z Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="8c66f-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="8c66f-126">Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8c66f-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="8c66f-127">Aby zakończyć połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="8c66f-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="8c66f-128">Konfigurowanie eksportu</span><span class="sxs-lookup"><span data-stu-id="8c66f-128">Configure an export</span></span>

<span data-ttu-id="8c66f-129">Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="8c66f-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="8c66f-130">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="8c66f-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="8c66f-131">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="8c66f-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8c66f-132">Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="8c66f-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="8c66f-133">W polu **Połączenie do eksportu** wybierz połączenie z sekcji Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="8c66f-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="8c66f-134">Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="8c66f-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="8c66f-135">Wprowadź **Identyfikator listy usługi**</span><span class="sxs-lookup"><span data-stu-id="8c66f-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="8c66f-136">W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta.</span><span class="sxs-lookup"><span data-stu-id="8c66f-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="8c66f-137">Opcjonalnie możesz wyeksportować **Imię**, **Nazwisko** i **Telefon**, aby stworzyć bardziej spersonalizowane wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="8c66f-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="8c66f-138">Wybierz opcję **Dodaj atrybut**, aby zamapować te pola.</span><span class="sxs-lookup"><span data-stu-id="8c66f-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="8c66f-139">Wybierz segmenty, które chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="8c66f-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="8c66f-140">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="8c66f-140">Select **Save**.</span></span>

<span data-ttu-id="8c66f-141">Zapisanie eksportu nie uruchamia natychmiastowo eksportu.</span><span class="sxs-lookup"><span data-stu-id="8c66f-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="8c66f-142">Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8c66f-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8c66f-143">Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="8c66f-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8c66f-144">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="8c66f-144">Data privacy and compliance</span></span>

<span data-ttu-id="8c66f-145">Włączenie Dynamics 365 Customer Insights w celu przekazywania danych do usługi Sendinblue umożliwia przesyłanie danych poza granice obszaru zgodności dla Dynamics 365 Customer Insights, w tym potencjalnie poufne dane, takie jak dane osobiste.</span><span class="sxs-lookup"><span data-stu-id="8c66f-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8c66f-146">Microsoft będzie przekazywać takie dane zgodnie z Twoimi instrukcjami, ale to Ty jesteś odpowiedzialny za zapewnienie, że Sendinblue spełnia wszelkie zobowiązania dotyczące prywatności i bezpieczeństwa, jakie możesz mieć.</span><span class="sxs-lookup"><span data-stu-id="8c66f-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8c66f-147">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8c66f-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8c66f-148">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="8c66f-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
