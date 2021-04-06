---
title: Łącznik usługi Power BI
description: Dowiedz się, jak używać łącznika Dynamics 365 Customer Insights w Power BI.
ms.date: 09/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e43e2f9dbc84ebfbf2154990a752740f973296cb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596052"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="48b49-103">Łącznik dla Power BI (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="48b49-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="48b49-104">Utwórz wizualizacje danych za pomocą narzędzia Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="48b49-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="48b49-105">Tworzenie dodatkowych wyników analiz i raportów przy użyciu ujednoliconych danych klientów.</span><span class="sxs-lookup"><span data-stu-id="48b49-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="48b49-106">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="48b49-106">Prerequisites</span></span>

- <span data-ttu-id="48b49-107">Posiadasz ujednolicone profile klientów.</span><span class="sxs-lookup"><span data-stu-id="48b49-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="48b49-108">Na komputerze została zainstalowana najnowsza wersja programu [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/).</span><span class="sxs-lookup"><span data-stu-id="48b49-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="48b49-109">[Więcej informacji o Power BI Desktop](/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="48b49-109">[Learn more about Power BI Desktop](/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="48b49-110">Konfigurowanie łącznika dla Power BI</span><span class="sxs-lookup"><span data-stu-id="48b49-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="48b49-111">W Power BI Desktop wybierz **Plik** > **Pobierz dane**.</span><span class="sxs-lookup"><span data-stu-id="48b49-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="48b49-112">Wybierz **Zobacz więcej** i wyszukaj **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="48b49-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="48b49-113">Wybierz pozycję **Połącz**.</span><span class="sxs-lookup"><span data-stu-id="48b49-113">Select **Connect**.</span></span>

1. <span data-ttu-id="48b49-114">**Zaloguj się**, korzystając z tego samego konta organizacyjnego, które będzie używane dla Customer Insights i wybierz **Połącz**.</span><span class="sxs-lookup"><span data-stu-id="48b49-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="48b49-115">Konto wskazywane w tym kroku służy do pobierania danych z Customer Insights i nie musi być tym samym, do którego użytkownik jest zalogowany w programie Power BI.</span><span class="sxs-lookup"><span data-stu-id="48b49-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="48b49-116">Aby zresetować konto używane do pobierania danych, otwórz Power BI i przejdź do **Plik** > **Opcje** > **Ustawienia** > **Ustawienia źródeł danych**.</span><span class="sxs-lookup"><span data-stu-id="48b49-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="48b49-117">Z listy źródeł danych wybierz **Logowanie w Dynamics 365 Customer Insights** i wybierz **Wyczyść uprawnienia**.</span><span class="sxs-lookup"><span data-stu-id="48b49-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="48b49-118">W oknie dialogowym **Nawigator**.</span><span class="sxs-lookup"><span data-stu-id="48b49-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="48b49-119">zobaczysz listę wszystkich środowisk, do których masz dostęp.</span><span class="sxs-lookup"><span data-stu-id="48b49-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="48b49-120">Rozwiń środowisko i otwórz dowolny z folderów (encje, miary, segmenty, wzbogacenia).</span><span class="sxs-lookup"><span data-stu-id="48b49-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="48b49-121">Na przykład otwórz folder **Encje**, aby wyświetlić wszystkie encje, które można importować.</span><span class="sxs-lookup"><span data-stu-id="48b49-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="48b49-122">![Nawigator łącznika Power BI](media/power-bi-navigator.png "Nawigator łącznika Power BI")</span><span class="sxs-lookup"><span data-stu-id="48b49-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="48b49-123">Zaznacz pola wyboru obok encji, które mają zostać dodane i **Załaduj**.</span><span class="sxs-lookup"><span data-stu-id="48b49-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="48b49-124">Możesz wybrać wiele encji z wielu środowisk.</span><span class="sxs-lookup"><span data-stu-id="48b49-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="48b49-125">Podczas ładowania encji zostanie wyświetlone okno dialogowe ładowania.</span><span class="sxs-lookup"><span data-stu-id="48b49-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="48b49-126">Kiedy wszystkie wybrane encje zostaną załadowane, można użyć funkcji Power BI do wizualizacji danych.</span><span class="sxs-lookup"><span data-stu-id="48b49-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="48b49-127">Duże zestawy danych</span><span class="sxs-lookup"><span data-stu-id="48b49-127">Large data sets</span></span>

<span data-ttu-id="48b49-128">Łącznik Customer Insights dla Power BI jest przeznaczony do pracy z zestawami danych zawierającymi do 1.000.000 profilów klientów.</span><span class="sxs-lookup"><span data-stu-id="48b49-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="48b49-129">Importowanie większych zestawów danych może się udać, ale zajmie dużo czasu.</span><span class="sxs-lookup"><span data-stu-id="48b49-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="48b49-130">Ponadto proces może przekroczyć limit czasu z powodu ograniczeń Power BI.</span><span class="sxs-lookup"><span data-stu-id="48b49-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="48b49-131">Aby uzyskać więcej informacji, zobacz [Power BI: Rekomendacje dotyczące dużych zestawów danych](/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="48b49-131">For more information, see [Power BI: Recommendations for large data sets](/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="48b49-132">Praca z podzbiorem danych</span><span class="sxs-lookup"><span data-stu-id="48b49-132">Work with a subset of data</span></span>

<span data-ttu-id="48b49-133">Weź pod uwagę pracę z podzbiorem danych programu.</span><span class="sxs-lookup"><span data-stu-id="48b49-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="48b49-134">Można na przykład utworzyć [segmenty](segments.md) zamiast eksportowania wszystkich rekordów klientów do Power BI.</span><span class="sxs-lookup"><span data-stu-id="48b49-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="48b49-135">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="48b49-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="48b49-136">Środowisko Customer Insights nie jest wyświetlane w programie Power BI</span><span class="sxs-lookup"><span data-stu-id="48b49-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="48b49-137">Środowiska, które mają więcej niż jedną [relację](relationships.md) zdefiniowaną między dwoma identycznymi jednostkami w szczegółowych informacjach o odbiorcach, nie będą dostępne w łączniku usługi Power BI.</span><span class="sxs-lookup"><span data-stu-id="48b49-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="48b49-138">Możesz zidentyfikować i usunąć zduplikowane relacje.</span><span class="sxs-lookup"><span data-stu-id="48b49-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="48b49-139">W odbiorcy danych przejdź do strony **Dane** > **Relacje** w środowisku, w którym nie ma Power BI.</span><span class="sxs-lookup"><span data-stu-id="48b49-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="48b49-140">Zidentyfikuj zduplikowane relacje:</span><span class="sxs-lookup"><span data-stu-id="48b49-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="48b49-141">Sprawdź, czy istnieje więcej niż jedna relacja zdefiniowana między tymi samymi dwoma obiektami.</span><span class="sxs-lookup"><span data-stu-id="48b49-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="48b49-142">Sprawdź, czy istnieje relacja utworzona między dwiema jednostkami, które są objęte procesem unifikacji.</span><span class="sxs-lookup"><span data-stu-id="48b49-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="48b49-143">Istnieje domniemana relacja między wszystkimi jednostkami uwzględnionymi w procesie unifikacji.</span><span class="sxs-lookup"><span data-stu-id="48b49-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="48b49-144">Usuń wszystkie zidentyfikowane zduplikowane relacje.</span><span class="sxs-lookup"><span data-stu-id="48b49-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="48b49-145">Po usunięciu zduplikowanych relacji spróbuj ponownie skonfigurować łącznik usługi Power BI.</span><span class="sxs-lookup"><span data-stu-id="48b49-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="48b49-146">Środowisko powinno być teraz dostępne.</span><span class="sxs-lookup"><span data-stu-id="48b49-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]