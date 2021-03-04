---
title: Wyszukiwanie i filtrowanie profilów klientów
description: Szybki dostęp do informacji o ujednoliconych profilach klientów i filtrach dla określonych atrybutów.
ms.date: 01/19/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d675738c43cbdb5f9b478d53d6124db38ba3004d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270079"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="37553-103">Profile klientów: Wyszukiwanie i indeks filtrów</span><span class="sxs-lookup"><span data-stu-id="37553-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="37553-104">Ujednolicenie danych klienta jest encją profilu klienta, która umożliwia zunifikowany widok całej podstawowej bazy klientów.</span><span class="sxs-lookup"><span data-stu-id="37553-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="37553-105">Aby szybko [znaleźć informacje o określonym kliencie lub grupie klientów](customer-profiles.md), można skonfigurować funkcje **Wyszukiwania** i **Filtrowania** na stronie **Klienci**.</span><span class="sxs-lookup"><span data-stu-id="37553-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="37553-106">W tym artykule opisano, jak Administratorzy mogą edytować atrybuty na stronie **Wyszukiwanie i indeks filtrów**, które są dostępne dla użytkowników w wyszukiwaniu i filtrowaniu.</span><span class="sxs-lookup"><span data-stu-id="37553-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="37553-107">![Filtr wyszukiwania](media/search-filter.png "Filtr wyszukiwania")</span><span class="sxs-lookup"><span data-stu-id="37553-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="37553-108">Dodawanie pól i określanie atrybutów</span><span class="sxs-lookup"><span data-stu-id="37553-108">Add fields and specify attributes</span></span>

<span data-ttu-id="37553-109">Jeśli za pierwszym razem definiuje się jako Administrator atrybuty jako atrybuty, które można wyszukiwać, należy najpierw zdefiniować pola indeksowane.</span><span class="sxs-lookup"><span data-stu-id="37553-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="37553-110">Sugerujemy wybranie wszystkich atrybutów, dzięki którym użytkownicy mogą wyszukiwać i filtrować klientów na stronie **klienci**.</span><span class="sxs-lookup"><span data-stu-id="37553-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="37553-111">Użytkownik może podać tylko te atrybuty, które istnieją w encji profil klienta, która została utworzona podczas procesu zjednoczenia danych.</span><span class="sxs-lookup"><span data-stu-id="37553-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="37553-112">Otwórz stronę **Klienci** i wybierz **Wyszukiwanie i indeks filtrów**.</span><span class="sxs-lookup"><span data-stu-id="37553-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="37553-113">Wybierz **+ Dodaj**, aby określić indeksowane pola.</span><span class="sxs-lookup"><span data-stu-id="37553-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="37553-114">Wybierz atrybuty z listy, które chcesz dodać jako pola indeksowane.</span><span class="sxs-lookup"><span data-stu-id="37553-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="37553-115">Zawsze możesz dodać więcej atrybutów wybierając **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="37553-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="37553-116">Można również usunąć dowolne wybrane atrybuty, wybierając symbol **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="37553-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="37553-117">Poznawanie tabeli pól indeksowanych klientów</span><span class="sxs-lookup"><span data-stu-id="37553-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="37553-118">Poniższe informacje przedstawiono w tabeli.</span><span class="sxs-lookup"><span data-stu-id="37553-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="37553-119">**Nazwa**: reprezentuje nazwę atrybutu, która jest wyświetlana w encji profil klienta.</span><span class="sxs-lookup"><span data-stu-id="37553-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="37553-120">**Typ danych**: określa, czy typem danych jest ciąg, liczba lub data.</span><span class="sxs-lookup"><span data-stu-id="37553-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="37553-121">**Uwzględnione w wyszukiwaniu**: określa, czy można korzystać z tego atrybutu do wyszukiwania klientów na stronie **klienci** w polu **Wyszukaj**.</span><span class="sxs-lookup"><span data-stu-id="37553-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="37553-122">**Dodaj filtr**: formant służący do definiowania sposobu korzystania z tego atrybutu w celu filtrowania na stronie **Klienci**.</span><span class="sxs-lookup"><span data-stu-id="37553-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="37553-123">Edytowanie opcji filtrowania dla danego atrybutu</span><span class="sxs-lookup"><span data-stu-id="37553-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="37553-124">Menu **Filtruj** na stronie **Klienci** może zawierać różną liczbę poziomów atrybutów (na przykład różne grupy wiekowe do filtrowania klientów).</span><span class="sxs-lookup"><span data-stu-id="37553-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="37553-125">Wybierz **Dodaj filtr** dla danego atrybutu na stronie **Wyszukiwanie i indeks filtrów**.</span><span class="sxs-lookup"><span data-stu-id="37553-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="37553-126">Można zdefiniować liczbę wyników i kolejność ich zorganizowania.</span><span class="sxs-lookup"><span data-stu-id="37553-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="37553-127">W zależności od typu danych atrybutu jest wyświetlane jedeno z następujących okienek.</span><span class="sxs-lookup"><span data-stu-id="37553-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="37553-128">Atrybuty będące ciągiem: Określ liczbę oczekiwanych wyników w okienku **Opcje filtru ciągów** oraz zasadę kolejności, zgodnie z którą będą one zorganizowane.</span><span class="sxs-lookup"><span data-stu-id="37553-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="37553-129">Atrybuty typu liczbowego: Określ interwały w okienku **Opcje filtru liczb** oraz zasadę kolejności, zgodnie z którą będą one zorganizowane.</span><span class="sxs-lookup"><span data-stu-id="37553-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="37553-130">Atrybuty typu dane:  Określ interwały w okienku **Opcje filtru danych** oraz zasadę kolejności, zgodnie z którą będą one zorganizowane.</span><span class="sxs-lookup"><span data-stu-id="37553-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="37553-131">Wybierz pozycję **Zapisz**, aby zastosować zmiany.</span><span class="sxs-lookup"><span data-stu-id="37553-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="37553-132">Wybierz opcję **Uruchom** po przygotowaniu się do zastosowania ustawień.</span><span class="sxs-lookup"><span data-stu-id="37553-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="37553-133">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="37553-133">Next steps</span></span>

<span data-ttu-id="37553-134">Przejdź na stronę **Klienci**, aby wyszukać profile klientów lub użyj pól indeksowanych, aby wyświetlić podzbiór wszystkich profilów klientów.</span><span class="sxs-lookup"><span data-stu-id="37553-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]