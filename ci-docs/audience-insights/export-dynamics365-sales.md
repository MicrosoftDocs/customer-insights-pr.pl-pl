---
title: Eksport danych z Customer Insights do Dynamics 365 Sales
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc1a05ba4d21d96aa1a9724d158687bbb86949b6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759617"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="e6e8a-103">Używanie segmentów w usłudze Dynamics 365 Sales (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="e6e8a-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="e6e8a-104">Używając danych klientów, możesz tworzyć listy marketingowe oraz przepływy pracy kolejnych czynności, a także wysyłać materiały promocyjne z poziomu rozwiązania Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="e6e8a-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="e6e8a-105">Wymaganie wstępne dla połączenia</span><span class="sxs-lookup"><span data-stu-id="e6e8a-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="e6e8a-106">Rekordy kontaktów muszą być obecne w Dynamics 365 Sales, zanim będzie można wyeksportować segment z Customer Insights do Sales.</span><span class="sxs-lookup"><span data-stu-id="e6e8a-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="e6e8a-107">Przeczytaj więcej o tym, jak pozyskiwać kontakty w [Dynamics 365 Sales, używając Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="e6e8a-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="e6e8a-108">Eksportowanie segmentów ze statystyk odbiorców do Sales nie spowoduje utworzenia nowych rekordów kontaktów w wystąpieniach Sales.</span><span class="sxs-lookup"><span data-stu-id="e6e8a-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="e6e8a-109">Rekordy kontaktów z działu Sales muszą być pozyskiwane w statystykach odbiorców i używane jako źródło danych.</span><span class="sxs-lookup"><span data-stu-id="e6e8a-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="e6e8a-110">Muszą również zostać uwzględnione w ujednoliconej encji Customer, aby zmapować identyfikatory klientów do identyfikatorów kontaktów, zanim segmenty będą mogły zostać wyeksportowane.</span><span class="sxs-lookup"><span data-stu-id="e6e8a-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="e6e8a-111">Skonfiguruj połączenie z usługą Sales</span><span class="sxs-lookup"><span data-stu-id="e6e8a-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="e6e8a-112">Przejdź do **Admin** > **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="e6e8a-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e6e8a-113">Wybierz opcję **Dodaj połączenie** i wybierz opcję **Dynamics 365 Sales**, aby skonfigurować połączenie.</span><span class="sxs-lookup"><span data-stu-id="e6e8a-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="e6e8a-114">W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="e6e8a-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e6e8a-115">Wyświetlana nazwa i typ połączenia opisują to połączenie.</span><span class="sxs-lookup"><span data-stu-id="e6e8a-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e6e8a-116">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.</span><span class="sxs-lookup"><span data-stu-id="e6e8a-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e6e8a-117">Określ, kto może używać tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="e6e8a-117">Choose who can use this connection.</span></span> <span data-ttu-id="e6e8a-118">Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy.</span><span class="sxs-lookup"><span data-stu-id="e6e8a-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e6e8a-119">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e6e8a-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e6e8a-120">W polu adres serwera **Adres serwera** wprowadź adres URL modułu Sales organizacji.</span><span class="sxs-lookup"><span data-stu-id="e6e8a-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="e6e8a-121">W sekcji **Konto Administratora serwera** wybierz **Zaloguj się** i wybierz konto Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="e6e8a-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="e6e8a-122">Zamapuj pole identyfikatora klienta na identyfikator kontaktu Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e6e8a-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="e6e8a-123">Aby zakończyć połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="e6e8a-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="e6e8a-124">Konfigurowanie eksportu</span><span class="sxs-lookup"><span data-stu-id="e6e8a-124">Configure an export</span></span>

<span data-ttu-id="e6e8a-125">Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="e6e8a-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e6e8a-126">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e6e8a-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e6e8a-127">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="e6e8a-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e6e8a-128">Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="e6e8a-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e6e8a-129">W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="e6e8a-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="e6e8a-130">Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="e6e8a-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e6e8a-131">Wybierz jeden lub więcej segmentów.</span><span class="sxs-lookup"><span data-stu-id="e6e8a-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="e6e8a-132">Wybierz pozycję **Zapisz**</span><span class="sxs-lookup"><span data-stu-id="e6e8a-132">Select **Save**</span></span>

<span data-ttu-id="e6e8a-133">Zapisanie eksportu nie uruchamia natychmiastowo eksportu.</span><span class="sxs-lookup"><span data-stu-id="e6e8a-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e6e8a-134">Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e6e8a-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e6e8a-135">Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e6e8a-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
