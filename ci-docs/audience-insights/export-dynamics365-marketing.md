---
title: Eksport danych z Customer Insights do Dynamics 365 Marketing
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 195bee789dc043057b47c12c8d93e6d53edb59cd
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976813"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="d527a-103">Używanie segmentów w usłudze Dynamics 365 Marketing (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="d527a-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="d527a-104">Za pomocą [segmentów](segments.md) utworzonych w aplikacji Customer Insights możesz generować kampanie oraz nawiązać kontakt z wybranymi grupami klientów w rozwiązaniu Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="d527a-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="d527a-105">Aby uzyskać więcej informacji, zobacz [Korzystanie z segmentów w Dynamics 365 Customer Insights z Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="d527a-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="d527a-106">Wymaganie wstępne dla połączenia</span><span class="sxs-lookup"><span data-stu-id="d527a-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="d527a-107">Rekordy kontaktów muszą być obecne w Dynamics 365 Marketing, zanim będzie można wyeksportować segment z Customer Insights do Marketing.</span><span class="sxs-lookup"><span data-stu-id="d527a-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="d527a-108">Przeczytaj więcej o tym, jak pozyskiwać kontakty w [Dynamics 365 Marketing, używając Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="d527a-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="d527a-109">Eksportowanie segmentów ze statystyk odbiorców do Marketingu nie spowoduje utworzenia nowych rekordów kontaktów w wystąpieniach Marketing.</span><span class="sxs-lookup"><span data-stu-id="d527a-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="d527a-110">Rekordy kontaktów z działu Marketing muszą być pozyskiwane w statystykach odbiorców i używane jako źródło danych.</span><span class="sxs-lookup"><span data-stu-id="d527a-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="d527a-111">Muszą również zostać uwzględnione w ujednoliconej encji Customer, aby zmapować identyfikatory klientów do identyfikatorów kontaktów, zanim segmenty będą mogły zostać wyeksportowane.</span><span class="sxs-lookup"><span data-stu-id="d527a-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="d527a-112">Skonfiguruj połączenie z usługą Marketing</span><span class="sxs-lookup"><span data-stu-id="d527a-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="d527a-113">Przejdź do **Admin** > **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="d527a-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d527a-114">Wybierz opcję **Dodaj połączenie** i wybierz opcję **Dynamics 365 Marketing**, aby skonfigurować połączenie.</span><span class="sxs-lookup"><span data-stu-id="d527a-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="d527a-115">W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="d527a-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d527a-116">Wyświetlana nazwa i typ połączenia opisują to połączenie.</span><span class="sxs-lookup"><span data-stu-id="d527a-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d527a-117">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.</span><span class="sxs-lookup"><span data-stu-id="d527a-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d527a-118">Określ, kto może używać tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="d527a-118">Choose who can use this connection.</span></span> <span data-ttu-id="d527a-119">Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy.</span><span class="sxs-lookup"><span data-stu-id="d527a-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d527a-120">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d527a-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d527a-121">W polu adres serwera **Adres serwera** wprowadź adres URL modułu Marketing organizacji.</span><span class="sxs-lookup"><span data-stu-id="d527a-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="d527a-122">W sekcji **Konto Administratora serwera** wybierz **Zaloguj się** i wybierz konto Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="d527a-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="d527a-123">Zamapuj pole identyfikatora klienta na identyfikator kontaktu Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d527a-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="d527a-124">Aby zakończyć połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="d527a-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="d527a-125">Konfigurowanie eksportu</span><span class="sxs-lookup"><span data-stu-id="d527a-125">Configure an export</span></span>

<span data-ttu-id="d527a-126">Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="d527a-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d527a-127">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d527a-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d527a-128">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="d527a-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d527a-129">Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="d527a-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d527a-130">W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="d527a-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="d527a-131">Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="d527a-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d527a-132">Wybierz jeden lub więcej segmentów.</span><span class="sxs-lookup"><span data-stu-id="d527a-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="d527a-133">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="d527a-133">Select **Save**.</span></span>

<span data-ttu-id="d527a-134">Zapisanie eksportu nie uruchamia natychmiastowo eksportu.</span><span class="sxs-lookup"><span data-stu-id="d527a-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d527a-135">Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d527a-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d527a-136">Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d527a-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
