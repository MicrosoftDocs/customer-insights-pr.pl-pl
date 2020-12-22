---
title: Odświeżanie przyrostowe dla źródeł danych opartych na Power Query
description: Odświeżanie nowych i zaktualizowanych danych dla dużych źródeł danych na podstawie Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b7e834f5f2fd1328563139675d7f850008348734
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406583"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="c9d7f-103">Odświeżanie przyrostowe dla źródeł danych opartych na Power Query</span><span class="sxs-lookup"><span data-stu-id="c9d7f-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="c9d7f-104">Odświeżanie przyrostowe dla źródeł danych daje następujące korzyści:</span><span class="sxs-lookup"><span data-stu-id="c9d7f-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="c9d7f-105">**Szybsze odświeżenia** — Odświeżane są tylko te dane, które zostały zmienione.</span><span class="sxs-lookup"><span data-stu-id="c9d7f-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="c9d7f-106">Można na przykład odświeżyć tylko ostatnie pięć dni z historycznego zestawu danych.</span><span class="sxs-lookup"><span data-stu-id="c9d7f-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="c9d7f-107">**Zwiększona niezawodność** — Wraz z mniejszą liczbą odświeżeń nie jest konieczne długie utrzymywanie połączeń z nietrwałymi systemami źródłowymi, co zmniejsza ryzyko problemów z połączeniem.</span><span class="sxs-lookup"><span data-stu-id="c9d7f-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="c9d7f-108">**Zmniejszone zużycie zasobów** — Odświeżanie tylko podzbioru wszystkich danych zwiększa efektywność korzystania z zasobów obliczeniowych i obniża zużycie środowiska.</span><span class="sxs-lookup"><span data-stu-id="c9d7f-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="c9d7f-109">Konfiguruj odświeżanie przyrostowe</span><span class="sxs-lookup"><span data-stu-id="c9d7f-109">Configure incremental refresh</span></span>

<span data-ttu-id="c9d7f-110">Informacje o odbiorcach umożliwiają przyrostowe odświeżanie źródeł danych importowanych za pomocą dodatku Power Query, które obsługują pozyskiwanie przyrostowe.</span><span class="sxs-lookup"><span data-stu-id="c9d7f-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="c9d7f-111">Na przykład bazy danych Azure SQL z polami Data i godzina, które wskazują, kiedy rekordy danych były ostatnio aktualizowane.</span><span class="sxs-lookup"><span data-stu-id="c9d7f-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="c9d7f-112">[Utwórz nowe źródło danych na podstawie Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="c9d7f-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="c9d7f-113">Podaj nazwę źródła danych.</span><span class="sxs-lookup"><span data-stu-id="c9d7f-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="c9d7f-114">Wybierz źródło danych, które obsługuje odświeżanie przyrostowe, na przykład Azure SQL Database.</span><span class="sxs-lookup"><span data-stu-id="c9d7f-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="c9d7f-115">Wybierz encje lub tabele, które mają zostać pozyskane.</span><span class="sxs-lookup"><span data-stu-id="c9d7f-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="c9d7f-116">Wykonaj kroki przekształcenia i wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="c9d7f-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="c9d7f-117">W oknie dialogowym **Konfigurowanie odświeżania przyrostowego** wybierz **Konfiguruj**, aby otworzyć **Ustawienia odświeżania przyrostowego**.</span><span class="sxs-lookup"><span data-stu-id="c9d7f-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="c9d7f-118">W przypadku wybrania **Pomiń** źródło danych będzie odświeżać cały zestaw danych.</span><span class="sxs-lookup"><span data-stu-id="c9d7f-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="c9d7f-119">Można również zastosować odświeżanie przyrostowe później, edytując istniejące źródło danych.</span><span class="sxs-lookup"><span data-stu-id="c9d7f-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="c9d7f-120">W **Ustawienia odświeżania przyrostowego** skonfigurujesz odświeżanie przyrostowe dla wszystkich encji wybranych podczas tworzenia źródła danych.</span><span class="sxs-lookup"><span data-stu-id="c9d7f-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c9d7f-121">![Konfigurowanie encji w źródle danych dla odświeżania przyrostowego](media/incremental-refresh-settings.png "Konfigurowanie encji w źródle danych dla odświeżania przyrostowego")</span><span class="sxs-lookup"><span data-stu-id="c9d7f-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="c9d7f-122">Wybierz encję i wprowadź następujące informacje szczegółowe:</span><span class="sxs-lookup"><span data-stu-id="c9d7f-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="c9d7f-123">**Zdefiniuj klucz podstawowy**: Wybierz klucz podstawowy encji lub tabeli.</span><span class="sxs-lookup"><span data-stu-id="c9d7f-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="c9d7f-124">**Zdefiniuj pole "Ostatnia aktualizacja"**: W tym polu są wyświetlane tylko atrybuty typu Data i godzina.</span><span class="sxs-lookup"><span data-stu-id="c9d7f-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="c9d7f-125">Wybierz atrybut wskazujący datę ostatniej aktualizacji rekordu.</span><span class="sxs-lookup"><span data-stu-id="c9d7f-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="c9d7f-126">Będzie on używany do identyfikowania rekordów, które mieszczą się w horyzont czasowy odświeżania przyrostowego.</span><span class="sxs-lookup"><span data-stu-id="c9d7f-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="c9d7f-127">**Sprawdzaj aktualizacje co**: Określ, jak długo ma trwać horyzont czasowy odświeżania przyrostowego.</span><span class="sxs-lookup"><span data-stu-id="c9d7f-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="c9d7f-128">Wybierz **Zapisz**, aby zakończyć tworzenie źródła danych.</span><span class="sxs-lookup"><span data-stu-id="c9d7f-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="c9d7f-129">Początkowe odświeżanie danych będzie pełnym odświeżaniem.</span><span class="sxs-lookup"><span data-stu-id="c9d7f-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="c9d7f-130">Następnie przyrostowe odświeżanie danych będzie mieć miejsce zgodnie z konfiguracją podaną w poprzednim kroku.</span><span class="sxs-lookup"><span data-stu-id="c9d7f-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>
