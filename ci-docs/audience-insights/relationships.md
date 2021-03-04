---
title: Relacje między encjami i ścieżkami encji
description: Tworzenie relacji między encjami z wielu źródeł danych i zarządzanie nimi.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 292da986faa7f62d8aa73ed7214075612178e2e1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269894"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="89294-103">Relacje między encjami</span><span class="sxs-lookup"><span data-stu-id="89294-103">Relationships between entities</span></span>

<span data-ttu-id="89294-104">Relacje ułatwiają łączenie encji i generowanie wykresu danych w przypadku, gdy encje mają wspólny identyfikator (klucz obcy), który może być przywoływany między encjami.</span><span class="sxs-lookup"><span data-stu-id="89294-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="89294-105">Połączone encje umożliwiają zdefiniowanie segmentów i miar na podstawie wielu źródeł danych.</span><span class="sxs-lookup"><span data-stu-id="89294-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="89294-106">Istnieją dwa typy relacji:</span><span class="sxs-lookup"><span data-stu-id="89294-106">There are two types of relationships.</span></span> <span data-ttu-id="89294-107">Relacje systemowe, których nie można edytować i które są tworzone automatycznie, oraz niestandardowe relacje utworzone i skonfigurowane przez użytkowników.</span><span class="sxs-lookup"><span data-stu-id="89294-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="89294-108">Podczas procesów dopasowywania i scalania relacje systemu są tworzone w tle w zależności od inteligentnego dopasowania.</span><span class="sxs-lookup"><span data-stu-id="89294-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="89294-109">Te relacje ułatwiają powiązanie rekordów Profilu klienta z innymi rekordami odpowiednich encji.</span><span class="sxs-lookup"><span data-stu-id="89294-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="89294-110">Na poniższym diagramie pokazano, jak utworzyć trzy relacje systemowe w przypadku dopasowania obiektu klienta do dodatkowych encji w celu utworzenia ostatecznej encji Profilu klienta.</span><span class="sxs-lookup"><span data-stu-id="89294-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="89294-111">![Tworzenie relacji](media/relationships-entities-merge.png "Tworzenie relacji")</span><span class="sxs-lookup"><span data-stu-id="89294-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="89294-112">**Relacja *CustomerToContact*** jest utworzona między encją klienta i encją kontaktu.</span><span class="sxs-lookup"><span data-stu-id="89294-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="89294-113">Encja klienta otrzymuje pole kluczowe **Contact_contactId** w celu powiązania jej z polem kluczowym encji kontaktu **contactId**.</span><span class="sxs-lookup"><span data-stu-id="89294-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="89294-114">**Relacja *CustomerToAccount*** jest utworzona między encją klienta i encją konta.</span><span class="sxs-lookup"><span data-stu-id="89294-114">***CustomerToAccount* relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="89294-115">Encja klienta otrzymuje pole kluczowe **Account_accountId** w celu powiązania jej z polem kluczowym encji konta **accountId**.</span><span class="sxs-lookup"><span data-stu-id="89294-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="89294-116">**Relacja *CustomerToWebAccount*** jest utworzona między encją klienta i encją konta sieci Web.</span><span class="sxs-lookup"><span data-stu-id="89294-116">***CustomerToWebAccount* relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="89294-117">Encja klienta otrzymuje pole kluczowe **WebAccount_webaccountId** w celu powiązania jej z polem kluczowym encji konta sieci Web **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="89294-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="89294-118">Utwórz relację</span><span class="sxs-lookup"><span data-stu-id="89294-118">Create a relationship</span></span>

<span data-ttu-id="89294-119">Relacje niestandardowe należy zdefiniować na stronie **Relacje**.</span><span class="sxs-lookup"><span data-stu-id="89294-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="89294-120">Każda relacja składa się z encji źródłowej (encja przechowująca klucz obcy) i encji docelowej (encja, na którą wskazuje klucz obcy encji źródłowej).</span><span class="sxs-lookup"><span data-stu-id="89294-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="89294-121">W analizach odbiorców przejdź do **Dane** > **Relacje**.</span><span class="sxs-lookup"><span data-stu-id="89294-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="89294-122">Wybierz **Nowa relacja**.</span><span class="sxs-lookup"><span data-stu-id="89294-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="89294-123">W okienku **Dodaj relację** podaj następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="89294-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="89294-124">![Wprowadź szczegóły relacji](media/relationships-add.png "Wprowadź szczegóły relacji")</span><span class="sxs-lookup"><span data-stu-id="89294-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="89294-125">**Nazwa relacji**: nazwa, która odzwierciedla cel relacji (na przykład **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="89294-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="89294-126">**Opis**: opis relacji.</span><span class="sxs-lookup"><span data-stu-id="89294-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="89294-127">**Encja źródłowa**: należy wybrać encję używaną jako źródło w relacji (np. dziennik sieci Web).</span><span class="sxs-lookup"><span data-stu-id="89294-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="89294-128">**Kardynalność**: wybierz kardynalność rekordów encji źródłowej.</span><span class="sxs-lookup"><span data-stu-id="89294-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="89294-129">Na przykład „wiele” oznacza, że wiele rekordów dziennika sieci Web jest skojarzonych z jednym kontem sieci Web.</span><span class="sxs-lookup"><span data-stu-id="89294-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="89294-130">**Pole klucza źródłowego**: to pole oznacza klucz obcy w encji źródłowej.</span><span class="sxs-lookup"><span data-stu-id="89294-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="89294-131">Na przykład dziennik sieci Web zawiera pole klucza obcego **accountId**.</span><span class="sxs-lookup"><span data-stu-id="89294-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="89294-132">**Encja docelowa**: należy wybrać encję używaną jako cel w relacji (np. konto sieci Web).</span><span class="sxs-lookup"><span data-stu-id="89294-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="89294-133">**Kardynalność docelowa**: wybierz kardynalność rekordów encji docelowej.</span><span class="sxs-lookup"><span data-stu-id="89294-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="89294-134">Na przykład „jeden” oznacza, że wiele rekordów dziennika sieci Web jest skojarzonych z jednym kontem sieci Web.</span><span class="sxs-lookup"><span data-stu-id="89294-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="89294-135">**Pole klucza docelowego**: to pole reprezentuje pole klucza encji docelowej.</span><span class="sxs-lookup"><span data-stu-id="89294-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="89294-136">Na przykład konto sieci Web zawiera pole klucza **accountId**.</span><span class="sxs-lookup"><span data-stu-id="89294-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="89294-137">Relacje obsługują tylko wiele-do-jednego i jeden-do-jednego.</span><span class="sxs-lookup"><span data-stu-id="89294-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="89294-138">Relacje wiele-do-wielu można utworzyć przy użyciu dwóch relacji wiele-do-jednego i połączyć encje (encji, która jest używana do łączenia encji źródłowej i encji docelowej).</span><span class="sxs-lookup"><span data-stu-id="89294-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="89294-139">Usuń relację</span><span class="sxs-lookup"><span data-stu-id="89294-139">Delete a relationship</span></span>

1. <span data-ttu-id="89294-140">W analizach odbiorców przejdź do **Dane** > **Relacje**.</span><span class="sxs-lookup"><span data-stu-id="89294-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="89294-141">Zaznacz pole wyboru dla relacji, którą chcesz usunąć.</span><span class="sxs-lookup"><span data-stu-id="89294-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="89294-142">Wybierz **Usuń** na górze tabeli **Relacje**.</span><span class="sxs-lookup"><span data-stu-id="89294-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="89294-143">Potwierdź usunięcie.</span><span class="sxs-lookup"><span data-stu-id="89294-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="89294-144">Następny krok</span><span class="sxs-lookup"><span data-stu-id="89294-144">Next step</span></span>

<span data-ttu-id="89294-145">System i relacje niestandardowe służą do tworzenia segmentów na podstawie wielu źródeł danych, które nie są już izolowane.</span><span class="sxs-lookup"><span data-stu-id="89294-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="89294-146">Aby uzyskać więcej informacji, zobacz [Segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="89294-146">For more information, see [Segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]