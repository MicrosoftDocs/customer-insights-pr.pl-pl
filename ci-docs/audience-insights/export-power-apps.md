---
title: Łącznik usługi Power Apps
description: Połącz z Power Apps i Power Automate.
ms.date: 01/19/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a8bbb9a09218d54228589d43c21c8894680b56e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268929"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="39673-103">Łącznik Microsoft Power Apps (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="39673-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="39673-104">Przenieś ujednolicone profile klientów do spersonalizowanych aplikacji za pomocą Power Apps.</span><span class="sxs-lookup"><span data-stu-id="39673-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="39673-105">Tworzenie połączenia rozwiązania Power Apps z usługą Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="39673-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="39673-106">Funkcja Customer Insights jest jednym z wielu [dostępnych źródeł danych w Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="39673-106">Customer Insights is one of the many [available sources for data in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="39673-107">Zapoznaj się z dokumentacją Power Apps, aby dowiedzieć się, jak [dodać połączenie danych z aplikacją](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="39673-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="39673-108">Zaleca się również zapoznanie się z artykułem [jak Power Apps używają delegowania w celu obsługi dużych zestawów danych w aplikacjach kanwy](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="39673-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="39673-109">Dostępne encje</span><span class="sxs-lookup"><span data-stu-id="39673-109">Available entities</span></span>

<span data-ttu-id="39673-110">Po dodaniu Customer Insights jako połączenia danych można wybrać następujące encje w Power Apps:</span><span class="sxs-lookup"><span data-stu-id="39673-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="39673-111">Klient: aby korzystać z danych z [ujednoliconego profilu klienta](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="39673-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="39673-112">UnifiedActivity: aby wyświetlić ujednoliconą [oś czasu działań](activities.md) w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="39673-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="39673-113">Ograniczenia</span><span class="sxs-lookup"><span data-stu-id="39673-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="39673-114">Encje, które można odzyskać</span><span class="sxs-lookup"><span data-stu-id="39673-114">Retrievable entities</span></span>

<span data-ttu-id="39673-115">Można odzyskać tylko encje **Klient**, **UnifiedActivity**, i **Segmenty** za pośrednictwem łącznika Power Apps.</span><span class="sxs-lookup"><span data-stu-id="39673-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="39673-116">Pozostałe encje są widoczne, ponieważ związany z nimi łącznik obsługuje je za pomocą wyzwalaczy w Power Automate.</span><span class="sxs-lookup"><span data-stu-id="39673-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="39673-117">Delegowanie</span><span class="sxs-lookup"><span data-stu-id="39673-117">Delegation</span></span>

<span data-ttu-id="39673-118">Delegacja działa w przypadku encji Klient i UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="39673-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="39673-119">Delegowanie dla encji **Klient**: Aby używać delegowania dla tej encji, pola muszą zostać zindeksowane w [Indeks wyszukiwania i filtrów](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="39673-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="39673-120">Delegowanie dla **UnifiedActivity**: Delegacja dla tej encji działa tylko dla pól **ActivityId** i **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="39673-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="39673-121">Więcej informacji na temat delegowania znajduje się w artykule [Delegowalne funkcje i operacje w Power Apps](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="39673-121">For more information about delegation, see [Power Apps delegable functions and operations](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="39673-122">Przykładowy formant galerii</span><span class="sxs-lookup"><span data-stu-id="39673-122">Example gallery control</span></span>

<span data-ttu-id="39673-123">Można na przykład dodać profile klientów do [kontrolki galerii](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="39673-123">For example, you add customer profiles to a [gallery control](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="39673-124">Dodaj formant **Galeria** do konstruowanej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="39673-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="39673-125">![Dodawanie elementu galerii](media/connector-powerapps9.png "Dodawanie elementu galerii")</span><span class="sxs-lookup"><span data-stu-id="39673-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="39673-126">Wybierz **Klienta** jako źródło danych dla elementów.</span><span class="sxs-lookup"><span data-stu-id="39673-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="39673-127">![Wybierz źródło danych](media/choose-datasource-powerapps.png "Wybierz źródło danych")</span><span class="sxs-lookup"><span data-stu-id="39673-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="39673-128">Możesz zmienić panel danych po prawej stronie, aby wybrać pole, które encja klienta ma wyświetlać w galerii.</span><span class="sxs-lookup"><span data-stu-id="39673-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="39673-129">Aby wyświetlić dowolne pole z wybranego klienta w galerii, wypełnij właściwość tekstu etykiety:  **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="39673-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="39673-130">Przykład: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="39673-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="39673-131">Aby wyświetlić ujednoliconą oś czasu dla klienta, należy dodać element galerii i dodać właściwość elementu: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="39673-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="39673-132">Przykład: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="39673-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]