---
title: Eksportowanie danych Customer Insights do usługi DotDigital
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8b0bda638c9bc7bb9cb2fdb01be11489b44f28a5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124424"
---
# <a name="export-segments-to-dotdigital-preview"></a><span data-ttu-id="d4ba6-103">Eksportowanie segmentów do usługi DotDigital (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="d4ba6-103">Export segments to DotDigital (preview)</span></span>

<span data-ttu-id="d4ba6-104">Eksportuj segmenty ujednoliconych profili klientów do książek adresowych DotDigital i wykorzystuj je do prowadzenia kampanii, marketingu e-mailowego i budowania segmentów klientów za pomocą DotDigital.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="d4ba6-105">Wymagania wstępne dla połączenia</span><span class="sxs-lookup"><span data-stu-id="d4ba6-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="d4ba6-106">Użytkownik ma [konto usługi DotDigital](https://dotdigital.com/) i odpowiadające mu poświadczenia administratora.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d4ba6-107">Istnieją książki adresowe w DotDigital i odpowiadające im identyfikatory.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="d4ba6-108">Identyfikator można znaleźć w adresie URL podczas wybierania i otwierania książki adresowej.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="d4ba6-109">Aby uzyskać więcej informacji, zobacz temat [Książka adresowa DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="d4ba6-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="d4ba6-110">Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="d4ba6-111">Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d4ba6-112">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="d4ba6-112">Known limitations</span></span>

- <span data-ttu-id="d4ba6-113">Do 1 miliona profili na eksport do DotDigital.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="d4ba6-114">Eksport do DotDigital jest ograniczony do segmentów.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="d4ba6-115">Eksportowanie segmentów zawierających łącznie 1 milion profili może zająć do 3 godzin ze względu na ograniczenia po stronie dostawcy.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="d4ba6-116">Liczba profilów, które można eksportować do DotDigital, jest zależna od kontraktu i ograniczona jego DotDigital.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="d4ba6-117">Konfiguruj połączenie z usługą DotDigital</span><span class="sxs-lookup"><span data-stu-id="d4ba6-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="d4ba6-118">Przejdź do **Admin** > **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d4ba6-119">Wybierz opcję **Dodaj połączenie** i wybierz opcję **DotDigital**, aby skonfigurować połączenie.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="d4ba6-120">W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d4ba6-121">Wyświetlana nazwa i typ połączenia opisują to połączenie.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d4ba6-122">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d4ba6-123">Określ, kto może używać tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-123">Choose who can use this connection.</span></span> <span data-ttu-id="d4ba6-124">Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d4ba6-125">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d4ba6-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d4ba6-126">Wprowadź **Nazwę użytkownika i hasło DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="d4ba6-127">Wprowadź **[Identyfikator książki adresowej DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="d4ba6-128">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d4ba6-129">Wybierz opcję **Połącz**, aby zainicjować połączenie z DotDigital.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="d4ba6-130">Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d4ba6-131">Aby zakończyć połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="d4ba6-132">Konfigurowanie eksportu</span><span class="sxs-lookup"><span data-stu-id="d4ba6-132">Configure an export</span></span>

<span data-ttu-id="d4ba6-133">Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d4ba6-134">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d4ba6-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d4ba6-135">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d4ba6-136">Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d4ba6-137">W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi DotDigital.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="d4ba6-138">Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="d4ba6-139">W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="d4ba6-140">Powtórz te kroki dla innych pól opcjonalnych, takich jak **Imię**, **Nazwisko**, **Imię i nazwisko**, **Płeć** i **Kod pocztowy**.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="d4ba6-141">Wybierz segmenty, które chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-141">Select the segments you want to export.</span></span> <span data-ttu-id="d4ba6-142">W sumie do maksymalnie 1 000 000 profilów klientów można wyeksportować do DotDigital.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="d4ba6-143">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-143">Select **Save**.</span></span>

<span data-ttu-id="d4ba6-144">Zapisanie eksportu nie uruchamia natychmiastowo eksportu.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d4ba6-145">Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d4ba6-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d4ba6-146">Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d4ba6-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="d4ba6-147">W DotDigital można teraz znaleźć segmenty w [książkach adresowych DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="d4ba6-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d4ba6-148">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="d4ba6-148">Data privacy and compliance</span></span>

<span data-ttu-id="d4ba6-149">Po włączeniu Dynamics 365 Customer Insights do transmisji danych do usługi DotDigital można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d4ba6-150">Microsoft przekaże takie dane na Twoje polecenie, ale jesteś odpowiedzialny za zapewnienie, że DotDigital spełnia wszelkie Twoje zobowiązania dotyczące prywatności i bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="d4ba6-151">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d4ba6-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d4ba6-152">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
