---
title: Relacje między encjami i ścieżkami encji
description: Tworzenie relacji między encjami z wielu źródeł danych i zarządzanie nimi.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171177"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="a8fce-103">Relacje między encjami</span><span class="sxs-lookup"><span data-stu-id="a8fce-103">Relationships between entities</span></span>

<span data-ttu-id="a8fce-104">Relacje łączą encje i definiują graf Twoich danych, gdy encje posiadają wspólny identyfikator, klucz obcy.</span><span class="sxs-lookup"><span data-stu-id="a8fce-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="a8fce-105">Do tego klucza obcego można się odwoływać z jednej encji do drugiej.</span><span class="sxs-lookup"><span data-stu-id="a8fce-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="a8fce-106">Połączone podmioty umożliwiają definiowanie segmentów i miar w oparciu o wiele źródeł danych.</span><span class="sxs-lookup"><span data-stu-id="a8fce-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="a8fce-107">Istnieją trzy typy relacje:</span><span class="sxs-lookup"><span data-stu-id="a8fce-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="a8fce-108">Nieedytowalne relacje systemowe, tworzone przez system w ramach procesu ujednolicania danych</span><span class="sxs-lookup"><span data-stu-id="a8fce-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="a8fce-109">Nieedytowalne relacje dziedziczone, które są tworzone automatycznie na podstawie pobieranych źródeł danych</span><span class="sxs-lookup"><span data-stu-id="a8fce-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="a8fce-110">Edytowalne relacje niestandardowe, tworzone i konfigurowane przez użytkowników</span><span class="sxs-lookup"><span data-stu-id="a8fce-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="a8fce-111">Nieedytowalne powiązania systemowe</span><span class="sxs-lookup"><span data-stu-id="a8fce-111">Non-editable system relationships</span></span>

<span data-ttu-id="a8fce-112">Podczas ujednolicania danych relacje systemowe są tworzone automatycznie na podstawie inteligentnego dopasowania.</span><span class="sxs-lookup"><span data-stu-id="a8fce-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="a8fce-113">Te relacje pomagają powiązać rekordy profilu klienta z odpowiadającymi im rekordami.</span><span class="sxs-lookup"><span data-stu-id="a8fce-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="a8fce-114">Na poniższym diagramie przedstawiono tworzenie trzech baz danych opartych relacje.</span><span class="sxs-lookup"><span data-stu-id="a8fce-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="a8fce-115">Encja klienta zostanie dopasowana do innych obiektów w celu uzyskania ujednoliconej encji *Klient*.</span><span class="sxs-lookup"><span data-stu-id="a8fce-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagram ze ścieżkami relacji dla encji klient z trzema relacjami 1-n.":::

- <span data-ttu-id="a8fce-117">**Relacja *CustomerToContact*** jest utworzona między encją *klienta* i encją *kontaktu*.</span><span class="sxs-lookup"><span data-stu-id="a8fce-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="a8fce-118">Encja *klienta* otrzymuje pole kluczowe **Contact_contactID** w celu powiązania jej z polem kluczowym encji *kontaktu* **contactID**.</span><span class="sxs-lookup"><span data-stu-id="a8fce-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="a8fce-119">**Relacja *CustomerToAccount*** jest utworzona między encją *klienta* i encją *konta*.</span><span class="sxs-lookup"><span data-stu-id="a8fce-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="a8fce-120">Encja *klienta* otrzymuje pole kluczowe **Account_accountID** w celu powiązania jej z polem kluczowym encji *konta* **accountID**.</span><span class="sxs-lookup"><span data-stu-id="a8fce-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="a8fce-121">**Relacja *CustomerToWebAccount*** jest utworzona między encją *klienta* i encją *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="a8fce-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="a8fce-122">Encja *klienta* otrzymuje pole kluczowe **WebAccount_webaccountID** w celu powiązania jej z polem kluczowym **webaccountID** encji *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="a8fce-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="a8fce-123">Odziedziczone relacje nieedytowalne</span><span class="sxs-lookup"><span data-stu-id="a8fce-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="a8fce-124">Podczas procesu pozyskiwania danych system sprawdza źródła danych pod kątem istniejących relacji.</span><span class="sxs-lookup"><span data-stu-id="a8fce-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="a8fce-125">Jeśli nie istnieje żadna relacja, system automatycznie je tworzy.</span><span class="sxs-lookup"><span data-stu-id="a8fce-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="a8fce-126">Relacje te są również wykorzystywane w dalszych procesach.</span><span class="sxs-lookup"><span data-stu-id="a8fce-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="a8fce-127">Utwórz niestandardową relację</span><span class="sxs-lookup"><span data-stu-id="a8fce-127">Create a custom relationship</span></span>

<span data-ttu-id="a8fce-128">Relacja składa się z *encji źródłowej* zawierającej klucz obcy i *encję docelową*, na którą wskazuje klucz obcy encji źródłowej.</span><span class="sxs-lookup"><span data-stu-id="a8fce-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="a8fce-129">W analizach odbiorców przejdź do **Dane** > **Relacje**.</span><span class="sxs-lookup"><span data-stu-id="a8fce-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="a8fce-130">Wybierz **Nowa relacja**.</span><span class="sxs-lookup"><span data-stu-id="a8fce-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="a8fce-131">W okienku **Nowa relacja** podaj następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="a8fce-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Nowy panel boczny relacji z pustymi polami wejściowymi.":::

   - <span data-ttu-id="a8fce-133">**Nazwa relacji**: nazwa odzwierciedlająca cel relacji.</span><span class="sxs-lookup"><span data-stu-id="a8fce-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="a8fce-134">Przykład: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="a8fce-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="a8fce-135">**Opis**: opis relacji.</span><span class="sxs-lookup"><span data-stu-id="a8fce-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="a8fce-136">**Encja źródłowa**: Encja używana jako źródło w relacji.</span><span class="sxs-lookup"><span data-stu-id="a8fce-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="a8fce-137">Przykład: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="a8fce-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="a8fce-138">**Encja docelowa**: Encja używana jako cel w relacji.</span><span class="sxs-lookup"><span data-stu-id="a8fce-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="a8fce-139">Przykład: Klient.</span><span class="sxs-lookup"><span data-stu-id="a8fce-139">Example: Customer.</span></span>
   - <span data-ttu-id="a8fce-140">**Kardynalność źródła**: Określ kardynalność encji źródłowej.</span><span class="sxs-lookup"><span data-stu-id="a8fce-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="a8fce-141">Podobieństwo opisuje liczbę możliwych elementów w zestawie.</span><span class="sxs-lookup"><span data-stu-id="a8fce-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="a8fce-142">Zawsze odnosi się do kardynalności docelowej.</span><span class="sxs-lookup"><span data-stu-id="a8fce-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="a8fce-143">Można wybrać **Jedna** lub **Wiele**.</span><span class="sxs-lookup"><span data-stu-id="a8fce-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="a8fce-144">Relacje obsługują tylko wiele-do-jednego i jeden-do-jednego.</span><span class="sxs-lookup"><span data-stu-id="a8fce-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="a8fce-145">Wiele do jednego: wiele rekordów źródłowych może odnosić się do jednego rekordu docelowego.</span><span class="sxs-lookup"><span data-stu-id="a8fce-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="a8fce-146">Przykład: wiele spraw pomocy technicznej od jednego klienta.</span><span class="sxs-lookup"><span data-stu-id="a8fce-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="a8fce-147">Jeden-do-jednego: pojedynczy rekord źródłowy odnosi się do rekordu jednego docelowego.</span><span class="sxs-lookup"><span data-stu-id="a8fce-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="a8fce-148">Przykład: jeden identyfikator lojalnościowy dla pojedynczego klienta.</span><span class="sxs-lookup"><span data-stu-id="a8fce-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="a8fce-149">Relacje wiele-do-wielu można tworzyć przy użyciu dwóch relacji wiele-do-jednego i encji łączącej, która łączy encję źródłową i encję docelową.</span><span class="sxs-lookup"><span data-stu-id="a8fce-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="a8fce-150">**Kardynalność docelowa**: wybierz kardynalność rekordów encji docelowej.</span><span class="sxs-lookup"><span data-stu-id="a8fce-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="a8fce-151">**Pole klucza źródłowego**: pole klucza obcych w encji źródłowej.</span><span class="sxs-lookup"><span data-stu-id="a8fce-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="a8fce-152">Przykład: SupportCase może użyć pola CaseID jako pola klucza obcych.</span><span class="sxs-lookup"><span data-stu-id="a8fce-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="a8fce-153">**Pole klucza docelowego**: Pole kluczowe encji docelowej.</span><span class="sxs-lookup"><span data-stu-id="a8fce-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="a8fce-154">Przykład klient może użyć pola klucza **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="a8fce-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="a8fce-155">Wybierz pozycję **ZApisz**, aby utworzyć niestandardową relację.</span><span class="sxs-lookup"><span data-stu-id="a8fce-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="a8fce-156">Widok relacji</span><span class="sxs-lookup"><span data-stu-id="a8fce-156">View relationships</span></span>

<span data-ttu-id="a8fce-157">Strona Relacje zawiera listę wszystkich utworzonych relacji.</span><span class="sxs-lookup"><span data-stu-id="a8fce-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="a8fce-158">Każdy wiersz reprezentuje relację, która zawiera również szczegółowe informacje o encji źródłowej, encji docelowej i kardynalności.</span><span class="sxs-lookup"><span data-stu-id="a8fce-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Lista relacji i opcji na pasku akcji strony Relacje.":::

<span data-ttu-id="a8fce-160">Ta strona oferuje zestaw opcji dla istniejących i nowych relacji:</span><span class="sxs-lookup"><span data-stu-id="a8fce-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="a8fce-161">**Nowa rezerwacji:** [Utwórz niestandardową relację](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="a8fce-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="a8fce-162">**Wizualizacja**: [poznaj wizualizację relacji](#explore-the-relationship-visualizer) w celu odszukania diagramu sieciowego istniejącego relacje i ich podobieństwa.</span><span class="sxs-lookup"><span data-stu-id="a8fce-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="a8fce-163">**Filtruj według**: wybierz typ relacje, które mają być wyświetlane na liście.</span><span class="sxs-lookup"><span data-stu-id="a8fce-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="a8fce-164">**Wyszukiwanie relacje**: Użyj wyszukiwania tekstowego według właściwości relacji.</span><span class="sxs-lookup"><span data-stu-id="a8fce-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="a8fce-165">Poznawanie wizualizacji relacji</span><span class="sxs-lookup"><span data-stu-id="a8fce-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="a8fce-166">Wizualizator relacji pokazuje diagram sieciowy istniejących relacji między połączonymi podmiotami i ich kardynalności.</span><span class="sxs-lookup"><span data-stu-id="a8fce-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="a8fce-167">Aby dostosować widok, możesz zmienić położenie pól, przeciągając je na kanwę.</span><span class="sxs-lookup"><span data-stu-id="a8fce-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Zrzut ekranu diagramu sieci wizualizatora relacji z połączeniami między powiązanymi podmiotami.":::

<span data-ttu-id="a8fce-169">Dostępne opcje:</span><span class="sxs-lookup"><span data-stu-id="a8fce-169">Available options:</span></span> 
- <span data-ttu-id="a8fce-170">**Eksportuj jako plik obrazu**: zapisz bieżący widok jako plik obrazu.</span><span class="sxs-lookup"><span data-stu-id="a8fce-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="a8fce-171">**Zmień na układ poziomy/pionowy**: zmień wyrównanie encji i relacji.</span><span class="sxs-lookup"><span data-stu-id="a8fce-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="a8fce-172">**Edycja**: Zaktualizuj właściwości relacji niestandardowych w okienku edycji i zapisz zmiany.</span><span class="sxs-lookup"><span data-stu-id="a8fce-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="a8fce-173">Zarządzaj istniejącymi relacjami</span><span class="sxs-lookup"><span data-stu-id="a8fce-173">Manage existing relationships</span></span> 

<span data-ttu-id="a8fce-174">Na stronie Relacje każda relacja jest reprezentowana przez wiersz.</span><span class="sxs-lookup"><span data-stu-id="a8fce-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="a8fce-175">Wybierz relację i wybierz jedną z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="a8fce-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="a8fce-176">**Edycja**: Zaktualizuj właściwości relacji niestandardowych w okienku edycji i zapisz zmiany.</span><span class="sxs-lookup"><span data-stu-id="a8fce-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="a8fce-177">**Usuń**: usuń niestandardowe relacje.</span><span class="sxs-lookup"><span data-stu-id="a8fce-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="a8fce-178">**Widok**: Wyświetlanie utworzonych w systemie i dziedziczonych relacji.</span><span class="sxs-lookup"><span data-stu-id="a8fce-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="a8fce-179">Następny krok</span><span class="sxs-lookup"><span data-stu-id="a8fce-179">Next step</span></span>

<span data-ttu-id="a8fce-180">System i relacje niestandardowe służą do [tworzenia segmentów](segments.md) na podstawie wielu źródeł danych, które nie są już izolowane.</span><span class="sxs-lookup"><span data-stu-id="a8fce-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
