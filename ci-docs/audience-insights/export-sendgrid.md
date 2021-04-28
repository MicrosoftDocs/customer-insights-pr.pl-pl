---
title: Eksportowanie danych Customer Insights do usługi SendGrid
description: Dowiedz się, jak skonfigurować połączenie i eksport do programu SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a4c64cf77c682e07f3d0759c43355336b5806fc8
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759778"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="ceec6-103">Eksportowanie segmentów do programu SendGrid (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="ceec6-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="ceec6-104">Eksportuj segmenty ujednoliconych profili klientów do list kontaktów SendGrid i używaj ich do kampanii i marketingu e-mailowego w SendGrid.</span><span class="sxs-lookup"><span data-stu-id="ceec6-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="ceec6-105">Wymagania wstępne dla połączenia</span><span class="sxs-lookup"><span data-stu-id="ceec6-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="ceec6-106">Użytkownik ma [konto usługi SendGrid](https://sendgrid.com/) i odpowiadające mu poświadczenia administratora.</span><span class="sxs-lookup"><span data-stu-id="ceec6-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ceec6-107">Istnieją listy kontaktów w SendGrid i odpowiadające im identyfikatory.</span><span class="sxs-lookup"><span data-stu-id="ceec6-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="ceec6-108">Aby uzyskać więcej informacji, zobacz temat [SendGrid — Zarządzanie kontaktami](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="ceec6-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="ceec6-109">Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.</span><span class="sxs-lookup"><span data-stu-id="ceec6-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ceec6-110">Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="ceec6-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ceec6-111">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="ceec6-111">Known limitations</span></span>

- <span data-ttu-id="ceec6-112">Łącznie do 100'000 profili do SendGrid.</span><span class="sxs-lookup"><span data-stu-id="ceec6-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="ceec6-113">Eksport do SendGrid jest ograniczony do segmentów.</span><span class="sxs-lookup"><span data-stu-id="ceec6-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="ceec6-114">Eksportowanie do 100 000 profili do SendGrid może zająć do kilku godzin.</span><span class="sxs-lookup"><span data-stu-id="ceec6-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="ceec6-115">Liczba profilów, które można eksportować do SendGrid, jest zależna od kontraktu i ograniczona jego SendGrid.</span><span class="sxs-lookup"><span data-stu-id="ceec6-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="ceec6-116">Skonfiguruj połączenie z usługą SendGrid</span><span class="sxs-lookup"><span data-stu-id="ceec6-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="ceec6-117">Przejdź do **Admin** > **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="ceec6-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ceec6-118">Wybierz opcję **Dodaj połączenie** i wybierz opcję **SendGrid**, aby skonfigurować połączenie.</span><span class="sxs-lookup"><span data-stu-id="ceec6-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="ceec6-119">W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="ceec6-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ceec6-120">Wyświetlana nazwa i typ połączenia opisują to połączenie.</span><span class="sxs-lookup"><span data-stu-id="ceec6-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ceec6-121">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.</span><span class="sxs-lookup"><span data-stu-id="ceec6-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ceec6-122">Określ, kto może używać tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="ceec6-122">Choose who can use this connection.</span></span> <span data-ttu-id="ceec6-123">Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy.</span><span class="sxs-lookup"><span data-stu-id="ceec6-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ceec6-124">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ceec6-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ceec6-125">Wprowadź **Klucz interfejsu API SendGrid** [Klucz interfejsu API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="ceec6-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="ceec6-126">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.</span><span class="sxs-lookup"><span data-stu-id="ceec6-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ceec6-127">Wybierz opcję **Połącz**, aby zainicjować połączenie z SendGrid.</span><span class="sxs-lookup"><span data-stu-id="ceec6-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="ceec6-128">Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ceec6-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ceec6-129">Aby zakończyć połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ceec6-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ceec6-130">Konfigurowanie eksportu</span><span class="sxs-lookup"><span data-stu-id="ceec6-130">Configure an export</span></span>

<span data-ttu-id="ceec6-131">Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="ceec6-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ceec6-132">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ceec6-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ceec6-133">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="ceec6-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ceec6-134">Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="ceec6-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ceec6-135">W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi SendGrid.</span><span class="sxs-lookup"><span data-stu-id="ceec6-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="ceec6-136">Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="ceec6-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ceec6-137">Wprowadź **[Identyfikator listy SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="ceec6-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="ceec6-138">W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta.</span><span class="sxs-lookup"><span data-stu-id="ceec6-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ceec6-139">Powtórz te kroki dla innych pól opcjonalnych, takich jak **Imię**, **Nazwisko**, **Kraj/Region**, **Stan**, **Miasto** i **Kod pocztowy**.</span><span class="sxs-lookup"><span data-stu-id="ceec6-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="ceec6-140">Wybierz segmenty, które chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="ceec6-140">Select the segments you want to export.</span></span> <span data-ttu-id="ceec6-141">Zdecydowanie **zalecamy, aby nie eksportować łącznie ponad 100 000 profili klientów** do SendGrid.</span><span class="sxs-lookup"><span data-stu-id="ceec6-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="ceec6-142">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ceec6-142">Select **Save**.</span></span>

<span data-ttu-id="ceec6-143">Zapisanie eksportu nie uruchamia natychmiastowo eksportu.</span><span class="sxs-lookup"><span data-stu-id="ceec6-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ceec6-144">Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ceec6-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ceec6-145">Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ceec6-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ceec6-146">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="ceec6-146">Data privacy and compliance</span></span>

<span data-ttu-id="ceec6-147">Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi SendGrid można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="ceec6-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ceec6-148">Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że SendGrid spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="ceec6-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="ceec6-149">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ceec6-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ceec6-150">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="ceec6-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]