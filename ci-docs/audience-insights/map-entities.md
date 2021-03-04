---
title: Mapowanie encji do ujednolicenia danych
description: Mapowanie danych w celu utworzenia ujednoliconych profili klientów.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 0088daae0be0cb3e71f87387648430d2353081c9
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267048"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="f4376-103">Mapowanie encji i atrybutów</span><span class="sxs-lookup"><span data-stu-id="f4376-103">Map entities and attributes</span></span>

<span data-ttu-id="f4376-104">**Mapowanie** jest pierwszym etapem procesu ujednolicenia danych w analizach odbiorców.</span><span class="sxs-lookup"><span data-stu-id="f4376-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="f4376-105">Mapowanie składa się z trzech faz:</span><span class="sxs-lookup"><span data-stu-id="f4376-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="f4376-106">*Wybór encji*: należy zidentyfikować encje, które prowadzą do zestawu danych z pełniejszymi informacjami o klientach.</span><span class="sxs-lookup"><span data-stu-id="f4376-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="f4376-107">*Wybór atrybutu*: dla każdej encji należy określić kolumny, które mają zostać połączone i uzgodnić w fazach *dopasowywania* i *scalania*.</span><span class="sxs-lookup"><span data-stu-id="f4376-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="f4376-108">Te kolumny są nazywane *Atrybutami*.</span><span class="sxs-lookup"><span data-stu-id="f4376-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="f4376-109">*Wybór klucza podstawowego i typu semantycznego*: Dla każdej encji zidentyfikuj atrybut, który chcesz zdefiniować jako klucz podstawowy dla tej encji, a dla każdego atrybutu zidentyfikuj typ semantyczny, który najlepiej opisuje ten atrybut.</span><span class="sxs-lookup"><span data-stu-id="f4376-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="f4376-110">Aby uzyskać więcej informacji na temat ogólnego przebiegu zjednoczenia danych, zobacz [Ujednolicanie](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="f4376-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="f4376-111">Zaznacz pierwsze encje</span><span class="sxs-lookup"><span data-stu-id="f4376-111">Select the first entities</span></span>

1. <span data-ttu-id="f4376-112">W analizach odbiorców przejdź do **Dane** > **Ujednolicanie** > **Mapowanie**.</span><span class="sxs-lookup"><span data-stu-id="f4376-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="f4376-113">Rozpocznij fazę mapowania, zaznaczając **Wybierz encje**.</span><span class="sxs-lookup"><span data-stu-id="f4376-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="f4376-114">W fazach *dopasuj* i *scal* wybierz encje i atrybuty, które mają być używane.</span><span class="sxs-lookup"><span data-stu-id="f4376-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="f4376-115">Wymagane atrybuty można wybrać z encji oddzielnie lub dodać wszystkie atrybuty z encji, zaznaczając pole wyboru **Dołącz wszystkie pola** na poziomie encji.</span><span class="sxs-lookup"><span data-stu-id="f4376-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="f4376-116">Zalecamy wybranie co najmniej dwóch encji, które mają być korzystne w procesie zjednoczenia danych.</span><span class="sxs-lookup"><span data-stu-id="f4376-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f4376-117">![Dodaj encje przykład](media/data-manager-configure-map-add-entities-example.png "Dodaj encje przykład")</span><span class="sxs-lookup"><span data-stu-id="f4376-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="f4376-118">W tym przykładzie dodajemy encje **eCommerceContacts** i **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="f4376-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="f4376-119">Wybierając te encje, można uzyskać wgląd w informacje o tym, których użytkownicy biznesowi w trybie online są członkami programu lojalnościowego.</span><span class="sxs-lookup"><span data-stu-id="f4376-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="f4376-120">Korzystając z słów kluczowych można przeszukiwać atrybuty i encje, aby wybrać wymagane, które mają zostać zamapowane.</span><span class="sxs-lookup"><span data-stu-id="f4376-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f4376-121">![Przykład przeszukiwanych pól](media/data-manager-configure-map-search-fields-example.png "Przykład przeszukiwanych pól")</span><span class="sxs-lookup"><span data-stu-id="f4376-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="f4376-122">Wybierz **Zastosuj**, aby potwierdzić wybrane opcje.</span><span class="sxs-lookup"><span data-stu-id="f4376-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="f4376-123">Wybierz klucz podstawowy i typ semantyczny dla atrybutów</span><span class="sxs-lookup"><span data-stu-id="f4376-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="f4376-124">Po wybraniu encji strona **Mapa** wymienia wybrane encje do przejrzenia.</span><span class="sxs-lookup"><span data-stu-id="f4376-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="f4376-125">Zdefiniuj klucz podstawowy encji i zidentyfikuj typ semantyczny atrybutu w encji.</span><span class="sxs-lookup"><span data-stu-id="f4376-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="f4376-126">**Klucz podstawowy**: Wybierz jeden atrybut jako klucz podstawowy dla każdej encji.</span><span class="sxs-lookup"><span data-stu-id="f4376-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="f4376-127">Aby atrybut był prawidłowym kluczem podstawowym, nie może zawierać zduplikowanych wartości, brakujących wartości ani wartości null.</span><span class="sxs-lookup"><span data-stu-id="f4376-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="f4376-128">Atrybuty typu danych ciąg, liczba całkowita i GUID są obsługiwane jako klucze podstawowe i będą wyświetlane w polu, w którym będzie można dokonać wyboru.</span><span class="sxs-lookup"><span data-stu-id="f4376-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="f4376-129">**Typ semantyczny atrybutu**: Kategorie atrybutów, takie jak adres e-mail lub nazwa.</span><span class="sxs-lookup"><span data-stu-id="f4376-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="f4376-130">Aby używać modeli AI do inteligentnego przewidywania semantyki, zaoszczędzić czas i poprawić dokładność, ustaw **Inteligentne mapowanie** na **Włączone**.</span><span class="sxs-lookup"><span data-stu-id="f4376-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="f4376-131">Inteligentne mapowanie podświetla rekomendacje semantyki w oparciu o AI w polu **Typ**.</span><span class="sxs-lookup"><span data-stu-id="f4376-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="f4376-132">Po ustawieniu na **Wyłączone**, zobaczysz nasze zwykłe rekomendacje dotyczące mapowania.</span><span class="sxs-lookup"><span data-stu-id="f4376-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="f4376-133">Dowolny typ semantyczny można wybrać z listy dostępnych opcji i zastąpić sugerowany wybór.</span><span class="sxs-lookup"><span data-stu-id="f4376-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f4376-134">![Typ atrybutu i przewidywanie semantyczne](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Typ atrybutu i przewidywanie semantyczne")</span><span class="sxs-lookup"><span data-stu-id="f4376-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="f4376-135">Możliwe jest również dodanie niestandardowego typu semantycznego.</span><span class="sxs-lookup"><span data-stu-id="f4376-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="f4376-136">Zaznacz pole typu dla atrybutu i wpisz nazwę niestandardowego typu semantycznego.</span><span class="sxs-lookup"><span data-stu-id="f4376-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="f4376-137">Użytkownik może w ten sposób również zmieniać typy atrybutów, które były identyfikowane przez system.</span><span class="sxs-lookup"><span data-stu-id="f4376-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="f4376-138">Wszystkie atrybuty, w przypadku których typ semantyczny jest identyfikowany automatycznie, są zgrupowane w sekcji **Przegląd zamapowanych pól**.</span><span class="sxs-lookup"><span data-stu-id="f4376-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="f4376-139">Przejrzyj te atrybuty i ich typy semantyczne, ponieważ zostaną użyte do połączenia encji w kroku scalania ujednolicania danych.</span><span class="sxs-lookup"><span data-stu-id="f4376-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="f4376-140">Atrybuty, które nie są automatycznie mapowane na typ semantyczny, są zgrupowane w sekcji **Definiuj dane w niezamapowanych polach**.</span><span class="sxs-lookup"><span data-stu-id="f4376-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="f4376-141">Zaznacz pole typu semantycznego dla niezamapowanych atrybutów, lub wprowadź niestandardową nazwę typu atrybutu.</span><span class="sxs-lookup"><span data-stu-id="f4376-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f4376-142">![Klucz podstawowy i typ atrybutu](media/data-manager-configure-map-add-attributes.png "Klucz podstawowy i typ atrybutu")</span><span class="sxs-lookup"><span data-stu-id="f4376-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="f4376-143">Jedno pole powinno być zamapowane na typ semantyczny Person.FullName, aby wypełnić nazwę klienta na karcie klienta.</span><span class="sxs-lookup"><span data-stu-id="f4376-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="f4376-144">W przeciwnym razie karty klientów nie będą posiadały nazw.</span><span class="sxs-lookup"><span data-stu-id="f4376-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="f4376-145">Dodawanie i usuwanie atrybutów i encji</span><span class="sxs-lookup"><span data-stu-id="f4376-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="f4376-146">Na **Ujednolicanie** > **Mapa** wybierz **Edytuj pola**.</span><span class="sxs-lookup"><span data-stu-id="f4376-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="f4376-147">W okienku **Edytuj pola** dodaj lub usuń atrybuty i encje.</span><span class="sxs-lookup"><span data-stu-id="f4376-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="f4376-148">Aby znaleźć i wybrać swoje atrybuty i encje, należy użyć narzędzia Wyszukaj lub przewinąć.</span><span class="sxs-lookup"><span data-stu-id="f4376-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="f4376-149">Nie można usunąć atrybutu lub encji, jeśli zostały już dopasowane.</span><span class="sxs-lookup"><span data-stu-id="f4376-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f4376-150">![Dodawanie lub usuwanie atrybutów](media/configure-data-map-edit.png "Dodawanie lub usuwanie atrybutów")</span><span class="sxs-lookup"><span data-stu-id="f4376-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="f4376-151">Wybierz **Zastosuj**.</span><span class="sxs-lookup"><span data-stu-id="f4376-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="f4376-152">Dodawanie obrazów do profilów</span><span class="sxs-lookup"><span data-stu-id="f4376-152">Add images to profiles</span></span>

<span data-ttu-id="f4376-153">Jeśli encja zawiera adresy URL publicznie dostępnych obrazów profilów lub logo, można dodać je do profilu ujednoliconego klienta.</span><span class="sxs-lookup"><span data-stu-id="f4376-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="f4376-154">Wybierz encję i znajdź pole zawierające adres URL do obrazu profilu.</span><span class="sxs-lookup"><span data-stu-id="f4376-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="f4376-155">W polu wejściowym **Wpisz** ręcznie wprowadź poniższą wartość:</span><span class="sxs-lookup"><span data-stu-id="f4376-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="f4376-156">Dla osoby: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="f4376-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="f4376-157">Dla organizacji: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="f4376-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="f4376-158">Wykonaj kroki procedury ujednolicania i upewnij się, że atrybut zawierający adres URL obrazu jest dodany również w kroku [Scal](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="f4376-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="f4376-159">Ustawianie atrybutów dla organizacji</span><span class="sxs-lookup"><span data-stu-id="f4376-159">Set attributes for organizations</span></span>

<span data-ttu-id="f4376-160">Dla organizacji (wersja zapoznawcza) typ atrybutu powinien zostać zamapowany na „Organization.Name”</span><span class="sxs-lookup"><span data-stu-id="f4376-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="f4376-161">![Klucz podstawowy i typ atrybutu B2B](media/configure-data-map-edit-b2b.png "Klucz podstawowy i typ atrybutu B2B")</span><span class="sxs-lookup"><span data-stu-id="f4376-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="f4376-162">Następny krok</span><span class="sxs-lookup"><span data-stu-id="f4376-162">Next step</span></span>

<span data-ttu-id="f4376-163">W ramach procesu ujednolicenia danych przejdź na stronę **Dopasowywanie**.</span><span class="sxs-lookup"><span data-stu-id="f4376-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="f4376-164">Więcej informacji na temat tej fazy można przeczytać na stronie [**Dopasowywanie**](match-entities.md).</span><span class="sxs-lookup"><span data-stu-id="f4376-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="f4376-165">Zapoznaj się z następującym filmem: [Wprowadzenie: Tworzenie ujednoliconego profilu klienta](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="f4376-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]