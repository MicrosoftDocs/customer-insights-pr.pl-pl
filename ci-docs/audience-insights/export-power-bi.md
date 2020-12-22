---
title: Łącznik usługi Power BI
description: Dowiedz się, jak używać łącznika Dynamics 365 Customer Insights w Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406553"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="9b50f-103">Łącznik dla Power BI (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="9b50f-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="9b50f-104">Utwórz wizualizacje danych za pomocą narzędzia Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="9b50f-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="9b50f-105">Tworzenie dodatkowych wyników analiz i raportów przy użyciu ujednoliconych danych klientów.</span><span class="sxs-lookup"><span data-stu-id="9b50f-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9b50f-106">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="9b50f-106">Prerequisites</span></span>

- <span data-ttu-id="9b50f-107">Posiadasz ujednolicone profile klientów.</span><span class="sxs-lookup"><span data-stu-id="9b50f-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="9b50f-108">Najnowsza wersja [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) jest zainstalowana na komputerze użytkownika.</span><span class="sxs-lookup"><span data-stu-id="9b50f-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="9b50f-109">[Więcej informacji o Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="9b50f-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="9b50f-110">Konfigurowanie łącznika dla Power BI</span><span class="sxs-lookup"><span data-stu-id="9b50f-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="9b50f-111">W Power BI Desktop wybierz **Plik** > **Pobierz dane**.</span><span class="sxs-lookup"><span data-stu-id="9b50f-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="9b50f-112">Wybierz **Zobacz więcej** i wyszukaj **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="9b50f-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="9b50f-113">Wybierz wyniki i wybierz **Połącz**.</span><span class="sxs-lookup"><span data-stu-id="9b50f-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="9b50f-114">**Zaloguj się**, korzystając z tego samego konta organizacyjnego, które będzie używane dla Customer Insights i wybierz **Połącz**.</span><span class="sxs-lookup"><span data-stu-id="9b50f-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="9b50f-115">Konto wskazywane w tym kroku służy do pobierania danych z Customer Insights i nie musi być tym samym, do którego użytkownik jest zalogowany w programie Power BI.</span><span class="sxs-lookup"><span data-stu-id="9b50f-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="9b50f-116">Aby zresetować konto używane do pobierania danych, otwórz Power BI i przejdź do **Plik** > **Opcje** > **Ustawienia** > **Ustawienia źródeł danych**.</span><span class="sxs-lookup"><span data-stu-id="9b50f-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="9b50f-117">Z listy źródeł danych wybierz **Logowanie w Dynamics 365 Customer Insights** i wybierz **Wyczyść uprawnienia**.</span><span class="sxs-lookup"><span data-stu-id="9b50f-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="9b50f-118">W oknie dialogowym **Nawigator**.</span><span class="sxs-lookup"><span data-stu-id="9b50f-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="9b50f-119">zobaczysz listę wszystkich środowisk, do których masz dostęp.</span><span class="sxs-lookup"><span data-stu-id="9b50f-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="9b50f-120">Rozwiń środowisko i otwórz dowolny z folderów (encje, miary, segmenty, wzbogacenia).</span><span class="sxs-lookup"><span data-stu-id="9b50f-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="9b50f-121">Na przykład otwórz folder **Encje**, aby wyświetlić wszystkie encje, które można importować.</span><span class="sxs-lookup"><span data-stu-id="9b50f-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="9b50f-122">![Nawigator łącznika Power BI](media/power-bi-navigator.png "Nawigator łącznika Power BI")</span><span class="sxs-lookup"><span data-stu-id="9b50f-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="9b50f-123">Zaznacz pola wyboru obok encji, które mają zostać dodane i **Załaduj**.</span><span class="sxs-lookup"><span data-stu-id="9b50f-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="9b50f-124">Możesz wybrać wiele encji z wielu środowisk.</span><span class="sxs-lookup"><span data-stu-id="9b50f-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="9b50f-125">Podczas ładowania encji zostanie wyświetlone okno dialogowe ładowania.</span><span class="sxs-lookup"><span data-stu-id="9b50f-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="9b50f-126">Kiedy wszystkie wybrane encje zostaną załadowane, można użyć funkcji Power BI do wizualizacji danych.</span><span class="sxs-lookup"><span data-stu-id="9b50f-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="9b50f-127">Duże zestawy danych</span><span class="sxs-lookup"><span data-stu-id="9b50f-127">Large data sets</span></span>

<span data-ttu-id="9b50f-128">Łącznik Customer Insights dla Power BI jest przeznaczony do pracy z zestawami danych zawierającymi do 1.000.000 profilów klientów.</span><span class="sxs-lookup"><span data-stu-id="9b50f-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="9b50f-129">Importowanie większych zestawów danych może się udać, ale zajmie dużo czasu.</span><span class="sxs-lookup"><span data-stu-id="9b50f-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="9b50f-130">Ponadto proces może przekroczyć limit czasu z powodu ograniczeń Power BI.</span><span class="sxs-lookup"><span data-stu-id="9b50f-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="9b50f-131">Aby uzyskać więcej informacji, zobacz [Power BI: Rekomendacje dotyczące dużych zestawów danych](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="9b50f-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="9b50f-132">Praca z podzbiorem danych</span><span class="sxs-lookup"><span data-stu-id="9b50f-132">Work with a subset of data</span></span>

<span data-ttu-id="9b50f-133">Weź pod uwagę pracę z podzbiorem danych programu.</span><span class="sxs-lookup"><span data-stu-id="9b50f-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="9b50f-134">Można na przykład utworzyć [segmenty](segments.md) zamiast eksportowania wszystkich rekordów klientów do Power BI.</span><span class="sxs-lookup"><span data-stu-id="9b50f-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
