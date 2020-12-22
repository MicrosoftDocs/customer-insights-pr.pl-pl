---
title: Eksport danych z Customer Insights do Dynamics 365 Sales
description: Informacje o konfigurowaniu połączenia z Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643831"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="559a9-103">Łącznik dla Dynamics 365 Sales (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="559a9-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="559a9-104">Używając danych klientów, możesz tworzyć listy marketingowe oraz przepływy pracy kolejnych czynności, a także wysyłać materiały promocyjne z poziomu rozwiązania Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="559a9-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="559a9-105">Warunek wstępny</span><span class="sxs-lookup"><span data-stu-id="559a9-105">Prerequisite</span></span>

<span data-ttu-id="559a9-106">Rekordy kontaktów [z Dynamics 365 Sales pozyskane przy użyciu Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="559a9-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="559a9-107">Konfigurowanie łącznika do modułu Sales</span><span class="sxs-lookup"><span data-stu-id="559a9-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="559a9-108">W analizach odbiorców przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.</span><span class="sxs-lookup"><span data-stu-id="559a9-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="559a9-109">W obszarze **Dynamics 365 Sales** wybierz **Konfiguruj**.</span><span class="sxs-lookup"><span data-stu-id="559a9-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="559a9-110">W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej exportu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="559a9-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="559a9-111">W polu adres serwera **Adres serwera** wprowadź adres URL modułu Sales organizacji.</span><span class="sxs-lookup"><span data-stu-id="559a9-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="559a9-112">W sekcji **Konto Administratora serwera** wybierz **Zaloguj się** i wybierz konto Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="559a9-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="559a9-113">Zamapuj pole identyfikatora klienta na identyfikator kontaktu Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="559a9-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="559a9-114">Wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="559a9-114">Select **Next**.</span></span>

1. <span data-ttu-id="559a9-115">Wybierz jeden lub więcej segmentów.</span><span class="sxs-lookup"><span data-stu-id="559a9-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="559a9-116">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="559a9-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="559a9-117">Eksportowanie danych</span><span class="sxs-lookup"><span data-stu-id="559a9-117">Export the data</span></span>

<span data-ttu-id="559a9-118">Możesz [eksportować dane na żądanie](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="559a9-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="559a9-119">Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="559a9-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
