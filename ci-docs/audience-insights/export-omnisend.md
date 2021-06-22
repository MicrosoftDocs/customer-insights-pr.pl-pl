---
title: Eksportowanie danych usługi Customer Insights do usługi Omnisend
description: Dowiedz się, jak skonfigurować połączenie i eksport do programu Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124532"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="4fa55-103">Eksportowanie segmentów do programu Omnisend (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="4fa55-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="4fa55-104">Wyeksportuj segmenty ujednoliconych profilów klientów do usługi Omnisend i użyj ich w działaniach marketingowych.</span><span class="sxs-lookup"><span data-stu-id="4fa55-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4fa55-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="4fa55-105">Prerequisites</span></span>

-   <span data-ttu-id="4fa55-106">Użytkownik ma konto [Kontakt administracyjny usługi Omnisend](https://www.omnisend.com/) i odpowiednie dane logowania administratora.</span><span class="sxs-lookup"><span data-stu-id="4fa55-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="4fa55-107">Posiadasz [skonfigurowane segmenty](segments.md) w analizach odbiorców.</span><span class="sxs-lookup"><span data-stu-id="4fa55-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="4fa55-108">Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="4fa55-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="4fa55-109">Znane ograniczenia</span><span class="sxs-lookup"><span data-stu-id="4fa55-109">Known limitations</span></span>

- <span data-ttu-id="4fa55-110">Możesz wyeksportować do 1 miliona profili na jeden eksport do Omnisend i może to zająć do 4 godzin.</span><span class="sxs-lookup"><span data-stu-id="4fa55-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="4fa55-111">Eksportowanie do usługi Omnisend jest ograniczone do segmentów.</span><span class="sxs-lookup"><span data-stu-id="4fa55-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="4fa55-112">Liczba profili, które możesz eksportować do Omnisend zależy od Twojej umowy z Omnisend.</span><span class="sxs-lookup"><span data-stu-id="4fa55-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="4fa55-113">Skonfiguruj połączenie z usługą Omnisend</span><span class="sxs-lookup"><span data-stu-id="4fa55-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="4fa55-114">Przejdź do **Admin** > **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="4fa55-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="4fa55-115">Wybierz opcję **Dodaj połączenie** i wybierz opcję **Omnisend**, aby skonfigurować połączenie.</span><span class="sxs-lookup"><span data-stu-id="4fa55-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="4fa55-116">W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="4fa55-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="4fa55-117">Wyświetlana nazwa i typ połączenia opisują to połączenie.</span><span class="sxs-lookup"><span data-stu-id="4fa55-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="4fa55-118">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.</span><span class="sxs-lookup"><span data-stu-id="4fa55-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="4fa55-119">Określ, kto może używać tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="4fa55-119">Choose who can use this connection.</span></span> <span data-ttu-id="4fa55-120">Domyślnie to tylko administratorzy.</span><span class="sxs-lookup"><span data-stu-id="4fa55-120">By default it's only administrators.</span></span> <span data-ttu-id="4fa55-121">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="4fa55-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="4fa55-122">Wprowadź [klucz interfejsu API Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span><span class="sxs-lookup"><span data-stu-id="4fa55-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="4fa55-123">Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.</span><span class="sxs-lookup"><span data-stu-id="4fa55-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="4fa55-124">Wybierz opcję **Połącz**, aby inicjować połączenie z usługą Omnisend.</span><span class="sxs-lookup"><span data-stu-id="4fa55-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="4fa55-125">Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4fa55-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="4fa55-126">Aby zakończyć połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="4fa55-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="4fa55-127">Konfigurowanie eksportu</span><span class="sxs-lookup"><span data-stu-id="4fa55-127">Configure an export</span></span>

<span data-ttu-id="4fa55-128">Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="4fa55-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="4fa55-129">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="4fa55-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="4fa55-130">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="4fa55-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="4fa55-131">Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="4fa55-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="4fa55-132">W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Omnisend.</span><span class="sxs-lookup"><span data-stu-id="4fa55-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="4fa55-133">Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="4fa55-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="4fa55-134">W sekcji dotyczącej **Porównywanych danych** w polu **e-mail** wybierz pole w ujednoliconym profilu klienta, które reprezentuje adres e-mail klienta.</span><span class="sxs-lookup"><span data-stu-id="4fa55-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="4fa55-135">Wymagane jest wyeksportowanie segmentów do usługi Omnisend.</span><span class="sxs-lookup"><span data-stu-id="4fa55-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="4fa55-136">Opcjonalnie możesz wyeksportować Imię, Nazwisko, Adres, Kraj/region, Województwo, Miasto i Kod pocztowy aby utworzyć bardziej spersonalizowane wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="4fa55-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="4fa55-137">Wybierz opcję **Dodaj atrybut**, aby zamapować te pola.</span><span class="sxs-lookup"><span data-stu-id="4fa55-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="4fa55-138">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="4fa55-138">Select **Save**.</span></span>

<span data-ttu-id="4fa55-139">Zapisanie eksportu nie uruchamia natychmiastowo eksportu.</span><span class="sxs-lookup"><span data-stu-id="4fa55-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="4fa55-140">Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4fa55-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4fa55-141">Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="4fa55-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4fa55-142">Prywatność danych i zgodność z przepisami</span><span class="sxs-lookup"><span data-stu-id="4fa55-142">Data privacy and compliance</span></span>

<span data-ttu-id="4fa55-143">Włączenie rozwiązania Dynamics 365 Customer Insights do przekazywania danych do usługi Ommisend umożliwia przesyłanie danych poza granicą zgodności z przepisami Dynamics 365 Customer Insights, w tym potencjalnie poufnych danych, takich jak dane osobowe.</span><span class="sxs-lookup"><span data-stu-id="4fa55-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4fa55-144">Microsoft przesyła takie dane zgodnie z instrukcjami użytkownika, ale użytkownik musi zagwarantować, że usługa Ommisend będzie spełniać wszelkie zobowiązania dotyczące prywatności lub bezpieczeństwa, jakie może mieć użytkownik.</span><span class="sxs-lookup"><span data-stu-id="4fa55-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="4fa55-145">Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="4fa55-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="4fa55-146">Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="4fa55-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
