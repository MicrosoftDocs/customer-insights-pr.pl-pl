---
title: Eksportowanie danych usługi Customer Insights do usługi Constant Contact
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3a9372cc4ffa4fb112a96b1286aee9dc35059a50
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760601"
---
# <a name="export-segment-lists-to-constant-contact-preview"></a><span data-ttu-id="18d5d-103">Eksportowanie list segmentów do usługi Constant Contact (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="18d5d-103">Export segment lists to Constant Contact (preview)</span></span>

<span data-ttu-id="18d5d-104">Wyeksportuj segmenty ujednoliconych profilów klientów do usługi Constant Contact i użyj ich w działaniach marketingowych.</span><span class="sxs-lookup"><span data-stu-id="18d5d-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="18d5d-105">Wymagania wstępne dla połączenia</span><span class="sxs-lookup"><span data-stu-id="18d5d-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="18d5d-106">Użytkownik ma konto [Kontakt administracyjny usługi Constant Contact](https://www.constantcontact.com/account-home) i odpowiednie dane logowania administratora.</span><span class="sxs-lookup"><span data-stu-id="18d5d-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="18d5d-107">Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.</span><span class="sxs-lookup"><span data-stu-id="18d5d-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="18d5d-108">Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="18d5d-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="18d5d-109">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="18d5d-109">Known limitations</span></span>

- <span data-ttu-id="18d5d-110">Do usługi Constant Contact można wyeksportować do 1 miliona profili.</span><span class="sxs-lookup"><span data-stu-id="18d5d-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="18d5d-111">Eksportowanie do usługi Constant Contact jest ograniczone do segmentów.</span><span class="sxs-lookup"><span data-stu-id="18d5d-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="18d5d-112">Wyeksportowanie do 1 miliona profilów do usługi Constant Contact może potrwać do 1 godziny.</span><span class="sxs-lookup"><span data-stu-id="18d5d-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="18d5d-113">Liczba profilów, które można eksportować usługi Constant Contact, jest ograniczona i zależy od kontraktu użytkownika z usługą Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="18d5d-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="18d5d-114">Konfiguracja połączenia z usługą Constant Contact</span><span class="sxs-lookup"><span data-stu-id="18d5d-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="18d5d-115">Przejdź do **Admin** > **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="18d5d-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="18d5d-116">Wybierz opcję **Dodaj połączenie** i wybierz opcję **Constant Contact**, aby skonfigurować połączenie.</span><span class="sxs-lookup"><span data-stu-id="18d5d-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="18d5d-117">W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="18d5d-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="18d5d-118">Wyświetlana nazwa i typ połączenia opisują to połączenie.</span><span class="sxs-lookup"><span data-stu-id="18d5d-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="18d5d-119">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.</span><span class="sxs-lookup"><span data-stu-id="18d5d-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="18d5d-120">Określ, kto może używać tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="18d5d-120">Choose who can use this connection.</span></span> <span data-ttu-id="18d5d-121">Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy.</span><span class="sxs-lookup"><span data-stu-id="18d5d-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="18d5d-122">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="18d5d-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="18d5d-123">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.</span><span class="sxs-lookup"><span data-stu-id="18d5d-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="18d5d-124">Wybierz opcję **Połącz**, aby inicjować połączenie z usługą Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="18d5d-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="18d5d-125">Wybierz opcję **Uwierzytelnij za pomocą usługi AdRoll** i podaj swoje poświadczenia administratora dla usługi Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="18d5d-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="18d5d-126">Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="18d5d-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="18d5d-127">Aby zakończyć połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="18d5d-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="18d5d-128">Konfigurowanie eksportu</span><span class="sxs-lookup"><span data-stu-id="18d5d-128">Configure an export</span></span>

<span data-ttu-id="18d5d-129">Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="18d5d-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="18d5d-130">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="18d5d-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="18d5d-131">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="18d5d-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="18d5d-132">Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="18d5d-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="18d5d-133">W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="18d5d-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="18d5d-134">Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="18d5d-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="18d5d-135">Wprowadź swój [**Identyfikator listy usługi Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists).</span><span class="sxs-lookup"><span data-stu-id="18d5d-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="18d5d-136">Otwórz listę w usłudze Constant Contact, aby znaleźć identyfikator listy w adresie URL.</span><span class="sxs-lookup"><span data-stu-id="18d5d-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="18d5d-137">W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta.</span><span class="sxs-lookup"><span data-stu-id="18d5d-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="18d5d-138">Wymagane jest wyeksportowanie segmentów do usługi Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="18d5d-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="18d5d-139">Można też eksportować imię i Nazwisko jako dodatkowe pola, aby utworzyć bardziej spersonalizowane wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="18d5d-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="18d5d-140">Wybierz opcję **Dodaj atrybut**, aby zamapować te pola.</span><span class="sxs-lookup"><span data-stu-id="18d5d-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="18d5d-141">Wybierz segmenty, które chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="18d5d-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="18d5d-142">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="18d5d-142">Select **Save**.</span></span>

<span data-ttu-id="18d5d-143">Zapisanie eksportu nie uruchamia natychmiastowo eksportu.</span><span class="sxs-lookup"><span data-stu-id="18d5d-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="18d5d-144">Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="18d5d-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="18d5d-145">Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="18d5d-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="18d5d-146">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="18d5d-146">Data privacy and compliance</span></span>

<span data-ttu-id="18d5d-147">Włączenie rozwiązania Dynamics 365 Customer Insights do przekazywania danych do usługi Constant Contact umożliwia przesyłanie danych poza granicą zgodności z przepisami Dynamics 365 Customer Insights, w tym potencjalnie poufnych danych, takich jak dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="18d5d-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="18d5d-148">Microsoft przesyła takie dane zgodnie z instrukcjami użytkownika, ale użytkownik musi zagwarantować, że usługa Constant Contact będzie spełniać wszelkie zobowiązania dotyczące prywatności lub bezpieczeństwa, jakie może mieć użytkownik.</span><span class="sxs-lookup"><span data-stu-id="18d5d-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="18d5d-149">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="18d5d-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="18d5d-150">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="18d5d-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
