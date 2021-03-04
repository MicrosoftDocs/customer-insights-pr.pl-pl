---
title: Wyświetlaj profile klientów
description: Umożliwia uzyskanie połączonego widoku ujednoliconych danych klienta.
ms.date: 12/01/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a5d928ae518f3cb1afbf8e2b197e51b27665f6e0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269757"
---
# <a name="customer-profiles"></a><span data-ttu-id="21dc1-103">Profile klientów</span><span class="sxs-lookup"><span data-stu-id="21dc1-103">Customer profiles</span></span>

<span data-ttu-id="21dc1-104">Na stronie **Klienci** jest wyświetlany połączony widok klientów na podstawie danych z profilu zgromadzonych na podstawie [wszystkich źródeł danych](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="21dc1-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="21dc1-105">Profile klientów są dostępne po [utworzeniu ujednoliconej encji klienta](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="21dc1-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="21dc1-106">Należy się upewnić, że użytkownik zakończy proces ujednolicania danych w celu uzyskania bogatszych widoków klientów.</span><span class="sxs-lookup"><span data-stu-id="21dc1-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="21dc1-107">Strona umożliwia również wyszukiwanie klientów.</span><span class="sxs-lookup"><span data-stu-id="21dc1-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="21dc1-108">Klienci mogą być osobami lub organizacjami (wersja zapoznawcza).</span><span class="sxs-lookup"><span data-stu-id="21dc1-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="21dc1-109">Każdy profil klienta lub organizacji jest reprezentowany przez kafelek.</span><span class="sxs-lookup"><span data-stu-id="21dc1-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="21dc1-110">Wybierz kafelek, aby wyświetlić dodatkowe informacje o danym kliencie lub organizacji.</span><span class="sxs-lookup"><span data-stu-id="21dc1-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="21dc1-111">Aby wyświetlić dodatkowe rekordy, należy użyć formantów podziału na strony u dołu strony.</span><span class="sxs-lookup"><span data-stu-id="21dc1-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="21dc1-112">![Profile klientów B2C](media/profiles-customers.png "Profile klientów B2C")</span><span class="sxs-lookup"><span data-stu-id="21dc1-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="21dc1-113">Organizacje (Wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="21dc1-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="21dc1-114">![Profile klientów B2B](media/profile-customers-b2b.png "Profile klientów B2B")</span><span class="sxs-lookup"><span data-stu-id="21dc1-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="21dc1-115">Jeśli nie widzisz kafelków po wybraniu **Klienci** w nawigacji, Administrator musi [zdefiniować co najmniej jeden atrybut z możliwością wyszukiwania](search-filter-index.md) w **Wyszukiwanie i indeks filtrów**.</span><span class="sxs-lookup"><span data-stu-id="21dc1-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="21dc1-116">Wyszukaj klientów</span><span class="sxs-lookup"><span data-stu-id="21dc1-116">Search for customers</span></span>

<span data-ttu-id="21dc1-117">Wyszukaj klientów, wprowadzając nazwę lub inny atrybut w polu wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="21dc1-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="21dc1-118">Wyszukiwanie działa tylko w encji profilu klienta utworzonej podczas procesu zjednoczenia danych.</span><span class="sxs-lookup"><span data-stu-id="21dc1-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="21dc1-119">Administrator może skonfigurować atrybuty, które można przeszukiwać, korzystając ze strony **Wyszukiwanie i indeks filtrów**.</span><span class="sxs-lookup"><span data-stu-id="21dc1-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="21dc1-120">Aby uzyskać więcej informacji, zobacz [zarządzanie wyszukiwaniem i indeksem filtrów](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="21dc1-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="21dc1-121">Filtrowanie klientów</span><span class="sxs-lookup"><span data-stu-id="21dc1-121">Filter customers</span></span>

<span data-ttu-id="21dc1-122">Klientów można przyfiltrować według pól encji profilu klienta.</span><span class="sxs-lookup"><span data-stu-id="21dc1-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="21dc1-123">Podobnie jak w przypadku funkcji wyszukiwania administrator będzie musiał zdefiniować pola jako filtrowane przy użyciu strony **Wyszukiwanie i indeks filtrów**.</span><span class="sxs-lookup"><span data-stu-id="21dc1-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="21dc1-124">Wybierz **Filtruj** na stronie **Klienci**.</span><span class="sxs-lookup"><span data-stu-id="21dc1-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="21dc1-125">Zaznacz pola wyboru obok atrybutów, według których chcesz filtrować klientów.</span><span class="sxs-lookup"><span data-stu-id="21dc1-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="21dc1-126">![Profile klientów](media/profiles-customers3.png "Profile klientów")</span><span class="sxs-lookup"><span data-stu-id="21dc1-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="21dc1-127">Aby usunąć filtry, wybierz pozycję **Wyczyść filtry** na stronie **Klienci**.</span><span class="sxs-lookup"><span data-stu-id="21dc1-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="21dc1-128">Strona Szczegóły klienta</span><span class="sxs-lookup"><span data-stu-id="21dc1-128">Customer details page</span></span>

<span data-ttu-id="21dc1-129">Wybierz dowolną tabliczkę z klientami, aby otworzyć **Stronę szczegółów klienta**.</span><span class="sxs-lookup"><span data-stu-id="21dc1-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="21dc1-130">Ten widok zawiera zunifikowane informacje dotyczące wybranego klienta.</span><span class="sxs-lookup"><span data-stu-id="21dc1-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="21dc1-131">Szczegóły klienta zawierają:</span><span class="sxs-lookup"><span data-stu-id="21dc1-131">Customer details include:</span></span>

-   <span data-ttu-id="21dc1-132">**Kafelek profil klienta:** na tym kafelku są wyświetlane różne wartości z obiektu profilu ujdenoliconego klienta.</span><span class="sxs-lookup"><span data-stu-id="21dc1-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="21dc1-133">Informacje te mogą obejmować adresy e-mail, nazwy, miasta itp.</span><span class="sxs-lookup"><span data-stu-id="21dc1-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="21dc1-134">**Potencjalne zainteresowania, potencjalne marki:** Pokazuje, czy skonfigurowano wzbogacenie własne.</span><span class="sxs-lookup"><span data-stu-id="21dc1-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="21dc1-135">Reprezentuje potencjalne zainteresowania i podobieństwa do marek, które może mieć klient o profilu podobnym do tego klienta.</span><span class="sxs-lookup"><span data-stu-id="21dc1-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="21dc1-136">Aby uzyskać więcej informacji, zobacz [Wzbogacanie profilów klientów o koligacje marki i zainteresowania](enrichment-microsoft-graph.md).</span><span class="sxs-lookup"><span data-stu-id="21dc1-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

-   <span data-ttu-id="21dc1-137">**Miary:** Pokazuje, czy skonfigurowano jedną lub więcej miar określonego typu: miary atrybutów klienta.</span><span class="sxs-lookup"><span data-stu-id="21dc1-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="21dc1-138">Obejmują one obliczone KPI wokół Twoich klientów na poziomie klienta indywidualnego.</span><span class="sxs-lookup"><span data-stu-id="21dc1-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="21dc1-139">Aby uzyskać więcej informacji, zobacz [Definiuj miary i zarządzaj nimi](measures.md).</span><span class="sxs-lookup"><span data-stu-id="21dc1-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="21dc1-140">**Oś czasu działania:** pokazuje, czy są skonfigurowane działania.</span><span class="sxs-lookup"><span data-stu-id="21dc1-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="21dc1-141">Widok osi czasu zawiera chronologicznie posortowane działania tego klienta, zaczynając od ostatniej aktywności.</span><span class="sxs-lookup"><span data-stu-id="21dc1-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="21dc1-142">Aby uzyskać więcej informacji, zobacz [Działania klientów](activities.md).</span><span class="sxs-lookup"><span data-stu-id="21dc1-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="21dc1-143">Wybierz **Powrót do klienta**, aby powrócić do strony wyszukiwania klienta.</span><span class="sxs-lookup"><span data-stu-id="21dc1-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="21dc1-144">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="21dc1-144">Next steps</span></span>

<span data-ttu-id="21dc1-145">[Dodawanie większej liczby źródeł danych](data-sources.md) lub [tworzenie segmentów klientów](segments.md).</span><span class="sxs-lookup"><span data-stu-id="21dc1-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]