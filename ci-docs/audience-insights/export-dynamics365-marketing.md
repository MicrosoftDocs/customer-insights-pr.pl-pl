---
title: Eksport danych z Customer Insights do Dynamics 365 Marketing
description: Informacje o konfigurowaniu połączenia z Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597616"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="a5a68-103">Łącznik dla Dynamics 365 Marketing (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="a5a68-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a5a68-104">Za pomocą [segmentów](segments.md) utworzonych w aplikacji Customer Insights możesz generować kampanie oraz nawiązać kontakt z wybranymi grupami klientów w rozwiązaniu Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="a5a68-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="a5a68-105">Aby uzyskać więcej informacji, zobacz [Korzystanie z segmentów w Dynamics 365 Customer Insights z Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="a5a68-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="a5a68-106">Warunek wstępny</span><span class="sxs-lookup"><span data-stu-id="a5a68-106">Prerequisite</span></span>

- <span data-ttu-id="a5a68-107">Rekordy kontaktów muszą być obecne w Dynamics 365 Marketing, zanim będzie można wyeksportować segment z Customer Insights do Marketing.</span><span class="sxs-lookup"><span data-stu-id="a5a68-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="a5a68-108">Przeczytaj więcej o tym, jak pozyskiwać kontakty w [Dynamics 365 Marketing, używając Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="a5a68-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="a5a68-109">Eksportowanie segmentów ze statystyk odbiorców do Marketingu nie spowoduje utworzenia nowych rekordów kontaktów w wystąpieniach Marketing.</span><span class="sxs-lookup"><span data-stu-id="a5a68-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="a5a68-110">Rekordy kontaktów z działu Marketing muszą być pozyskiwane w statystykach odbiorców i używane jako źródło danych.</span><span class="sxs-lookup"><span data-stu-id="a5a68-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="a5a68-111">Muszą również zostać uwzględnione w ujednoliconej encji Customer, aby zmapować identyfikatory klientów do identyfikatorów kontaktów, zanim segmenty będą mogły zostać wyeksportowane.</span><span class="sxs-lookup"><span data-stu-id="a5a68-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="a5a68-112">Konfigurowanie łącznika dla modułu Marketing</span><span class="sxs-lookup"><span data-stu-id="a5a68-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="a5a68-113">W analizach odbiorców przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.</span><span class="sxs-lookup"><span data-stu-id="a5a68-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a5a68-114">W obszarze **Dynamics 365 Marketing** wybierz **Konfiguruj**.</span><span class="sxs-lookup"><span data-stu-id="a5a68-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="a5a68-115">W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej exportu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="a5a68-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="a5a68-116">W polu adres serwera **Adres serwera** wprowadź adres URL modułu Marketing organizacji.</span><span class="sxs-lookup"><span data-stu-id="a5a68-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="a5a68-117">W sekcji **Konto Administratora serwera** wybierz **Zaloguj się** i wybierz konto Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="a5a68-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="a5a68-118">Zamapuj pole identyfikatora klienta na identyfikator kontaktu Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="a5a68-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="a5a68-119">Wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="a5a68-119">Select **Next**.</span></span>

1. <span data-ttu-id="a5a68-120">Wybierz jeden lub więcej segmentów.</span><span class="sxs-lookup"><span data-stu-id="a5a68-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="a5a68-121">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="a5a68-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a5a68-122">Eksportowanie danych</span><span class="sxs-lookup"><span data-stu-id="a5a68-122">Export the data</span></span>

<span data-ttu-id="a5a68-123">Możesz [eksportować dane na żądanie](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a5a68-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="a5a68-124">Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a5a68-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]