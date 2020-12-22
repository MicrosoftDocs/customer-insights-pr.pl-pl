---
title: Eksport danych z Customer Insights do Dynamics 365 Marketing
description: Informacje o konfigurowaniu połączenia z Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643786"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="f63c8-103">Łącznik dla Dynamics 365 Marketing (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="f63c8-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="f63c8-104">Za pomocą [segmentów](segments.md) utworzonych w aplikacji Customer Insights możesz generować kampanie oraz nawiązać kontakt z wybranymi grupami klientów w rozwiązaniu Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="f63c8-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="f63c8-105">Aby uzyskać więcej informacji, zobacz [Korzystanie z segmentów w Dynamics 365 Customer Insights z Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="f63c8-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="f63c8-106">Warunek wstępny</span><span class="sxs-lookup"><span data-stu-id="f63c8-106">Prerequisite</span></span>

<span data-ttu-id="f63c8-107">Rekordy kontaktów [z Dynamics 365 Marketing pozyskane przy użyciu Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="f63c8-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="f63c8-108">Konfigurowanie łącznika dla modułu Marketing</span><span class="sxs-lookup"><span data-stu-id="f63c8-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="f63c8-109">W analizach odbiorców przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.</span><span class="sxs-lookup"><span data-stu-id="f63c8-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f63c8-110">W obszarze **Dynamics 365 Marketing** wybierz **Konfiguruj**.</span><span class="sxs-lookup"><span data-stu-id="f63c8-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="f63c8-111">W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej exportu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="f63c8-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="f63c8-112">W polu adres serwera **Adres serwera** wprowadź adres URL modułu Marketing organizacji.</span><span class="sxs-lookup"><span data-stu-id="f63c8-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="f63c8-113">W sekcji **Konto Administratora serwera** wybierz **Zaloguj się** i wybierz konto Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="f63c8-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="f63c8-114">Zamapuj pole identyfikatora klienta na identyfikator kontaktu Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="f63c8-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="f63c8-115">Wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="f63c8-115">Select **Next**.</span></span>

1. <span data-ttu-id="f63c8-116">Wybierz jeden lub więcej segmentów.</span><span class="sxs-lookup"><span data-stu-id="f63c8-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="f63c8-117">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f63c8-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="f63c8-118">Eksportowanie danych</span><span class="sxs-lookup"><span data-stu-id="f63c8-118">Export the data</span></span>

<span data-ttu-id="f63c8-119">Możesz [eksportować dane na żądanie](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f63c8-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="f63c8-120">Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f63c8-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
