---
title: Wyszukiwanie i filtrowanie profilów klientów
description: Szybki dostęp do informacji o ujednoliconych profilach klientów i filtrach dla określonych atrybutów.
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406595"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="f3e13-103">Profile klientów: Wyszukiwanie i indeks filtrów</span><span class="sxs-lookup"><span data-stu-id="f3e13-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="f3e13-104">Ujednolicenie danych klienta jest encją profilu klienta, która umożliwia zunifikowany widok całej podstawowej bazy klientów.</span><span class="sxs-lookup"><span data-stu-id="f3e13-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="f3e13-105">Aby szybko [znaleźć informacje o określonym kliencie lub grupie klientów](customer-profiles.md), można skonfigurować funkcje **Wyszukiwania** i **Filtrowania** na stronie **Klienci**.</span><span class="sxs-lookup"><span data-stu-id="f3e13-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="f3e13-106">W tym artykule opisano, jak Administratorzy mogą edytować atrybuty na stronie **Wyszukiwanie i indeks filtrów**, które są dostępne dla użytkowników w wyszukiwaniu i filtrowaniu.</span><span class="sxs-lookup"><span data-stu-id="f3e13-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f3e13-107">![Filtr wyszukiwania](media/search-filter.png "Filtr wyszukiwania")</span><span class="sxs-lookup"><span data-stu-id="f3e13-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="f3e13-108">Dodawanie pól i określanie atrybutów</span><span class="sxs-lookup"><span data-stu-id="f3e13-108">Add fields and specify attributes</span></span>

<span data-ttu-id="f3e13-109">Jeśli za pierwszym razem definiuje się jako Administrator atrybuty jako atrybuty, które można wyszukiwać, należy najpierw zdefiniować pola indeksowane.</span><span class="sxs-lookup"><span data-stu-id="f3e13-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="f3e13-110">Sugerujemy wybranie wszystkich atrybutów, dzięki którym użytkownicy mogą wyszukiwać i filtrować klientów na stronie **klienci**.</span><span class="sxs-lookup"><span data-stu-id="f3e13-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="f3e13-111">Użytkownik może podać tylko te atrybuty, które istnieją w encji profil klienta, która została utworzona podczas procesu zjednoczenia danych.</span><span class="sxs-lookup"><span data-stu-id="f3e13-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="f3e13-112">Otwórz stronę **Klienci** i wybierz **Wyszukiwanie i indeks filtrów**.</span><span class="sxs-lookup"><span data-stu-id="f3e13-112">Open the **Customers** page and select **Search & filter index**.</span></span>

> [!NOTE]
> <span data-ttu-id="f3e13-113">Tworzymy domyślną konfigurację indeksu wyszukiwania na atrybutach dostępnych w encji Klient z poziomu następujących typów semantycznych, jak zdefiniowano na stronie Mapa.</span><span class="sxs-lookup"><span data-stu-id="f3e13-113">We create a default search index configuration on the available attributes in the Customer entity from the following semantic types as defined on the Map page.</span></span>
> - <span data-ttu-id="f3e13-114">Imię, Nazwisko, Drugie imię, Imię i nazwisko</span><span class="sxs-lookup"><span data-stu-id="f3e13-114">Person First name, Last name, Middle name, Full Name</span></span>
> - <span data-ttu-id="f3e13-115">Nazwa organizacji</span><span class="sxs-lookup"><span data-stu-id="f3e13-115">Organization Name</span></span>
> - <span data-ttu-id="f3e13-116">Adres e-mail</span><span class="sxs-lookup"><span data-stu-id="f3e13-116">Email address</span></span>
> - <span data-ttu-id="f3e13-117">Numer telefonu</span><span class="sxs-lookup"><span data-stu-id="f3e13-117">Phone number</span></span>
> - <span data-ttu-id="f3e13-118">Informacje o lokalizacji</span><span class="sxs-lookup"><span data-stu-id="f3e13-118">Location information</span></span>

2. <span data-ttu-id="f3e13-119">Wybierz **+ Dodaj**, aby określić indeksowane pola.</span><span class="sxs-lookup"><span data-stu-id="f3e13-119">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="f3e13-120">Wybierz atrybuty z listy, które chcesz dodać jako pola indeksowane.</span><span class="sxs-lookup"><span data-stu-id="f3e13-120">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="f3e13-121">Zawsze możesz dodać więcej atrybutów wybierając **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="f3e13-121">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="f3e13-122">Można również usunąć dowolne wybrane atrybuty, wybierając symbol **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="f3e13-122">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="f3e13-123">Poznawanie tabeli pól indeksowanych klientów</span><span class="sxs-lookup"><span data-stu-id="f3e13-123">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="f3e13-124">Poniższe informacje przedstawiono w tabeli.</span><span class="sxs-lookup"><span data-stu-id="f3e13-124">The following information is presented in the table.</span></span>

- <span data-ttu-id="f3e13-125">**Nazwa**: reprezentuje nazwę atrybutu, która jest wyświetlana w encji profil klienta.</span><span class="sxs-lookup"><span data-stu-id="f3e13-125">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="f3e13-126">**Typ danych**: określa, czy typem danych jest ciąg, liczba lub data.</span><span class="sxs-lookup"><span data-stu-id="f3e13-126">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="f3e13-127">**Uwzględnione w wyszukiwaniu**: określa, czy można korzystać z tego atrybutu do wyszukiwania klientów na stronie **klienci** w polu **Wyszukaj**.</span><span class="sxs-lookup"><span data-stu-id="f3e13-127">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="f3e13-128">**Dodaj filtr**: formant służący do definiowania sposobu korzystania z tego atrybutu w celu filtrowania na stronie **Klienci**.</span><span class="sxs-lookup"><span data-stu-id="f3e13-128">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="f3e13-129">Edytowanie opcji filtrowania dla danego atrybutu</span><span class="sxs-lookup"><span data-stu-id="f3e13-129">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="f3e13-130">Menu **Filtruj** na stronie **Klienci** może zawierać różną liczbę poziomów atrybutów (na przykład różne grupy wiekowe do filtrowania klientów).</span><span class="sxs-lookup"><span data-stu-id="f3e13-130">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="f3e13-131">Wybierz **Dodaj filtr** dla danego atrybutu na stronie **Wyszukiwanie i indeks filtrów**.</span><span class="sxs-lookup"><span data-stu-id="f3e13-131">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="f3e13-132">Można zdefiniować liczbę wyników i kolejność ich zorganizowania.</span><span class="sxs-lookup"><span data-stu-id="f3e13-132">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="f3e13-133">W zależności od typu danych atrybutu jest wyświetlane jedeno z następujących okienek.</span><span class="sxs-lookup"><span data-stu-id="f3e13-133">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="f3e13-134">Atrybuty będące ciągiem: Określ liczbę oczekiwanych wyników w okienku **Opcje filtru ciągów** oraz zasadę kolejności, zgodnie z którą będą one zorganizowane.</span><span class="sxs-lookup"><span data-stu-id="f3e13-134">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="f3e13-135">Atrybuty typu liczbowego: Określ interwały w okienku **Opcje filtru liczb** oraz zasadę kolejności, zgodnie z którą będą one zorganizowane.</span><span class="sxs-lookup"><span data-stu-id="f3e13-135">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="f3e13-136">Atrybuty typu dane:  Określ interwały w okienku **Opcje filtru danych** oraz zasadę kolejności, zgodnie z którą będą one zorganizowane.</span><span class="sxs-lookup"><span data-stu-id="f3e13-136">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="f3e13-137">Wybierz pozycję **Zapisz**, aby zastosować zmiany.</span><span class="sxs-lookup"><span data-stu-id="f3e13-137">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="f3e13-138">Wybierz opcję **Uruchom** po przygotowaniu się do zastosowania ustawień.</span><span class="sxs-lookup"><span data-stu-id="f3e13-138">Select **Run** once you're ready to apply your settings.</span></span>
