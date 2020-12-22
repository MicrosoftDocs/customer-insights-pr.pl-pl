---
title: Encje i zestawy danych
description: Wyświetlanie danych na stronie Encji.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e3f41c0424b2cd756d72ae6af9d5225ebba92628
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406559"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="4552b-103">Encje w analizach odbiorców</span><span class="sxs-lookup"><span data-stu-id="4552b-103">Entities in audience insights</span></span>

<span data-ttu-id="4552b-104">Po [skonfigurowaniu źródeł danych](data-sources.md) przejdź na stronę **Encje**, aby oceniać jakość pobranych danych.</span><span class="sxs-lookup"><span data-stu-id="4552b-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="4552b-105">Encje są traktowane jako zestawy danych.</span><span class="sxs-lookup"><span data-stu-id="4552b-105">Entities are considered datasets.</span></span> <span data-ttu-id="4552b-106">Wokół tych encji jest zbudowanych wiele funkcji Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4552b-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="4552b-107">Ich ścisłe przejrzenie może pomóc w sprawdzeniu poprawności danych wyjściowych możliwości.</span><span class="sxs-lookup"><span data-stu-id="4552b-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="4552b-108">Na stronie **Encje** znajduje się lista encji i zawiera kilka kolumn:</span><span class="sxs-lookup"><span data-stu-id="4552b-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="4552b-109">**Nazwa**: Nazwa encji danych.</span><span class="sxs-lookup"><span data-stu-id="4552b-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="4552b-110">Jeśli obok nazwy encji zostanie wyświetlony symbol ostrzeżenia, oznacza to, że dane dotyczące tej encji nie zostały pomyślnie załadowane.</span><span class="sxs-lookup"><span data-stu-id="4552b-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="4552b-111">**Źródło**: Typ źródła danych, które pobrało encję</span><span class="sxs-lookup"><span data-stu-id="4552b-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="4552b-112">**Autor**: Imię i nazwisko osoby, która utworzyła encję</span><span class="sxs-lookup"><span data-stu-id="4552b-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="4552b-113">**Utworzono**: Data i godzina utworzenia encji</span><span class="sxs-lookup"><span data-stu-id="4552b-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="4552b-114">**Zaktualizowane przez**: Imię i nazwisko osoby, która zaktualizowała encję</span><span class="sxs-lookup"><span data-stu-id="4552b-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="4552b-115">**Ostatnia aktualizacja**: Data i godzina ostatniej aktualizacji encji</span><span class="sxs-lookup"><span data-stu-id="4552b-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="4552b-116">**Ostatnie odświeżenie**: Data i godzina ostatniego odświeżenia danych</span><span class="sxs-lookup"><span data-stu-id="4552b-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="4552b-117">Eksplorowanie danych określonej encji</span><span class="sxs-lookup"><span data-stu-id="4552b-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="4552b-118">Wybierz encję, aby poznać różne pola i rekordy zawarte w tej encji.</span><span class="sxs-lookup"><span data-stu-id="4552b-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4552b-119">![Wybierz encję](media/data-manager-entities-data.png "Wybierz encję")</span><span class="sxs-lookup"><span data-stu-id="4552b-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="4552b-120">Karta **Dane** jest domyślnie zaznaczona i zawiera tabelę zawierającą szczegółowe informacje na temat poszczególnych rekordów encji.</span><span class="sxs-lookup"><span data-stu-id="4552b-120">The **Data** tab is selected by default and shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4552b-121">![Tabela pól](media/data-manager-entities-fields.PNG "Tabela pól")</span><span class="sxs-lookup"><span data-stu-id="4552b-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="4552b-122">Na karcie **Pola** jest wyświetlona tabela służąca do przejrzenia szczegółowych informacji o wybranej encji, takich jak nazwy pól, typy danych i typy.</span><span class="sxs-lookup"><span data-stu-id="4552b-122">The **Fields** tab shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="4552b-123">W kolumnie **Typ** są wyświetlane typy skojarzone z Common Data Model, które są automatycznie identyfikowane przez system lub [ręcznie mapowane](map-entities.md) przez użytkowników.</span><span class="sxs-lookup"><span data-stu-id="4552b-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="4552b-124">Są to typy semantyczne, które mogą różnić się w zależności od typów danych atrybutów — na przykład pole *Poczta e-mail* poniżej zawiera typ danych *Tekst*, ale jego (semantycznym) typem Common Data Model może być *Email* lub *EmailAddress*.</span><span class="sxs-lookup"><span data-stu-id="4552b-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="4552b-125">W obu tabelach przedstawiono tylko próbkę danych encji.</span><span class="sxs-lookup"><span data-stu-id="4552b-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="4552b-126">Aby wyświetlić pełny zestaw danych, przejdź na stronę **Źródła danych**, wybierz encję, wybierz pozycję **Edytuj**, a następnie wyświetl dane tej encji przy użyciu edytora Power Query, jak wyjaśniono w [Źródła danych](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="4552b-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="4552b-127">Aby dowiedzieć się więcej o danych pobranych w encji, kolumna **Podsumowanie** dostarcza znaczących cech danych, takich jak wartości zerowe, brakujące wartości, unikatowe wartości, zliczenia i rozkłady, które mają zastosowanie do danych.</span><span class="sxs-lookup"><span data-stu-id="4552b-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="4552b-128">Aby wyświetlić podsumowanie danych, należy wybrać ikonę wykresu.</span><span class="sxs-lookup"><span data-stu-id="4552b-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4552b-129">![Symbol podsumowania](media/data-manager-entities-summary.png "Tabela podsumowania danych")</span><span class="sxs-lookup"><span data-stu-id="4552b-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="4552b-130">Następny krok</span><span class="sxs-lookup"><span data-stu-id="4552b-130">Next step</span></span>

<span data-ttu-id="4552b-131">Zobacz temat [Ujednolicanie](data-unification.md), aby dowiedzieć się jak *mapować*, *dopasowywać* i *scalić* pobrane dane.</span><span class="sxs-lookup"><span data-stu-id="4552b-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>
