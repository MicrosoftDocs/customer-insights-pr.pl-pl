---
title: Eksport danych z Customer Insights do Dynamics 365 Sales
description: Informacje o konfigurowaniu połączenia z Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598122"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="57b95-103">Łącznik dla Dynamics 365 Sales (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="57b95-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="57b95-104">Używając danych klientów, możesz tworzyć listy marketingowe oraz przepływy pracy kolejnych czynności, a także wysyłać materiały promocyjne z poziomu rozwiązania Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="57b95-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="57b95-105">Warunek wstępny</span><span class="sxs-lookup"><span data-stu-id="57b95-105">Prerequisite</span></span>

1. <span data-ttu-id="57b95-106">Rekordy kontaktów muszą być obecne w Dynamics 365 Sales, zanim będzie można wyeksportować segment z Customer Insights do Sales.</span><span class="sxs-lookup"><span data-stu-id="57b95-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="57b95-107">Przeczytaj więcej o tym, jak pozyskiwać kontakty w [Dynamics 365 Sales, używając Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="57b95-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="57b95-108">Eksportowanie segmentów ze statystyk odbiorców do Sales nie spowoduje utworzenia nowych rekordów kontaktów w wystąpieniach Sales.</span><span class="sxs-lookup"><span data-stu-id="57b95-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="57b95-109">Rekordy kontaktów z działu Sales muszą być pozyskiwane w statystykach odbiorców i używane jako źródło danych.</span><span class="sxs-lookup"><span data-stu-id="57b95-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="57b95-110">Muszą również zostać uwzględnione w ujednoliconej encji Customer, aby zmapować identyfikatory klientów do identyfikatorów kontaktów, zanim segmenty będą mogły zostać wyeksportowane.</span><span class="sxs-lookup"><span data-stu-id="57b95-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="57b95-111">Konfigurowanie łącznika do modułu Sales</span><span class="sxs-lookup"><span data-stu-id="57b95-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="57b95-112">W analizach odbiorców przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.</span><span class="sxs-lookup"><span data-stu-id="57b95-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="57b95-113">W obszarze **Dynamics 365 Sales** wybierz **Konfiguruj**.</span><span class="sxs-lookup"><span data-stu-id="57b95-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="57b95-114">W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej exportu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="57b95-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="57b95-115">W polu adres serwera **Adres serwera** wprowadź adres URL modułu Sales organizacji.</span><span class="sxs-lookup"><span data-stu-id="57b95-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="57b95-116">W sekcji **Konto Administratora serwera** wybierz **Zaloguj się** i wybierz konto Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="57b95-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="57b95-117">Zamapuj pole identyfikatora klienta na identyfikator kontaktu Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="57b95-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="57b95-118">Wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="57b95-118">Select **Next**.</span></span>

1. <span data-ttu-id="57b95-119">Wybierz jeden lub więcej segmentów.</span><span class="sxs-lookup"><span data-stu-id="57b95-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="57b95-120">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="57b95-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="57b95-121">Eksportowanie danych</span><span class="sxs-lookup"><span data-stu-id="57b95-121">Export the data</span></span>

<span data-ttu-id="57b95-122">Możesz [eksportować dane na żądanie](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="57b95-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="57b95-123">Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="57b95-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]