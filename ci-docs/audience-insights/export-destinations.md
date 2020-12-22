---
title: Lokalizacje docelowe eksportu
description: Eksportuj dane i zarządzaj miejscami docelowymi eksportu.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643876"
---
# <a name="export-destinations-preview"></a><span data-ttu-id="c3f06-103">Lokalizacje docelowe eksportu (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="c3f06-103">Export destinations (preview)</span></span>

<span data-ttu-id="c3f06-104">Strona **Lokalizacje docelowe eksportu** ukazuje wszystkie lokalizacje, w których skonfigurowano eksportowanie danych do programu.</span><span class="sxs-lookup"><span data-stu-id="c3f06-104">The **Export destinations** page shows you all locations you've set up to export data to.</span></span> <span data-ttu-id="c3f06-105">Można również dodać nowe miejsca docelowe dla eksportu.</span><span class="sxs-lookup"><span data-stu-id="c3f06-105">You can also add new destinations for export.</span></span> <span data-ttu-id="c3f06-106">Dodatkowo pokazuje aktualnie dostępne opcje eksportu.</span><span class="sxs-lookup"><span data-stu-id="c3f06-106">Additionally, it shows export currently available options.</span></span> <span data-ttu-id="c3f06-107">Pobierz szybki przegląd, opis i dowiedz się, co możesz zrobić z poszczególnymi opcjami rozszerzania.</span><span class="sxs-lookup"><span data-stu-id="c3f06-107">Get a quick overview, description, and find out what you can do with each extensibility option.</span></span> <span data-ttu-id="c3f06-108">Wyeksportuj zunifikowane profile, miary i segmenty do obsługiwanych aplikacji przydatnych w prowadzonej działalności.</span><span class="sxs-lookup"><span data-stu-id="c3f06-108">Export unified profiles, measures, and segments to supported apps relevant for your business.</span></span>

<span data-ttu-id="c3f06-109">Przejdź do **Administracja** > **Lokalizacje docelowe eksportu**, aby znaleźć następujące opcje rozszerzania:</span><span class="sxs-lookup"><span data-stu-id="c3f06-109">Go to **Admin** > **Export destinations** to find the following extensibility options:</span></span>

- [<span data-ttu-id="c3f06-110">Dodatek Karta klienta Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="c3f06-110">Dynamics 365 Customer Card Add-in</span></span>](customer-card-add-in.md)
- [<span data-ttu-id="c3f06-111">Łącznik Managera Facebook Ads</span><span class="sxs-lookup"><span data-stu-id="c3f06-111">Facebook Ads Manager connector</span></span>](export-facebook.md)
- [<span data-ttu-id="c3f06-112">Łącznik Power Automate</span><span class="sxs-lookup"><span data-stu-id="c3f06-112">Power Automate connector</span></span>](export-power-automate.md)
- [<span data-ttu-id="c3f06-113">Łącznik Power Apps</span><span class="sxs-lookup"><span data-stu-id="c3f06-113">Power Apps connector</span></span>](export-power-apps.md)
- [<span data-ttu-id="c3f06-114">Łącznik Power BI</span><span class="sxs-lookup"><span data-stu-id="c3f06-114">Power BI connector</span></span>](export-power-bi.md)
- [<span data-ttu-id="c3f06-115">DotDigital</span><span class="sxs-lookup"><span data-stu-id="c3f06-115">DotDigital</span></span>](export-dotdigital.md)
- [<span data-ttu-id="c3f06-116">Dynamics 365 — sprzedaż</span><span class="sxs-lookup"><span data-stu-id="c3f06-116">Dynamics 365 Sales</span></span>](export-dynamics365-sales.md)
- [<span data-ttu-id="c3f06-117">Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="c3f06-117">Dynamics 365 Marketing</span></span>](export-dynamics365-marketing.md)
- [<span data-ttu-id="c3f06-118">Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="c3f06-118">Azure Blob Storage</span></span>](export-azure-blob-storage.md)
- [<span data-ttu-id="c3f06-119">Łącznik LiveRamp&reg;</span><span class="sxs-lookup"><span data-stu-id="c3f06-119">LiveRamp&reg; connector</span></span>](export-liveramp.md)
- [<span data-ttu-id="c3f06-120">Bot dla Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c3f06-120">Bot for Microsoft Teams</span></span>](export-teams-bot.md)
- [<span data-ttu-id="c3f06-121">Mailchimp</span><span class="sxs-lookup"><span data-stu-id="c3f06-121">Mailchimp</span></span>](export-mailchimp.md)
- [<span data-ttu-id="c3f06-122">Customer Insights API</span><span class="sxs-lookup"><span data-stu-id="c3f06-122">Customer Insights API</span></span>](apis.md)

## <a name="add-a-new-export-destination"></a><span data-ttu-id="c3f06-123">Dodaj nową lokalizację docelową eksportu</span><span class="sxs-lookup"><span data-stu-id="c3f06-123">Add a new export destination</span></span>

<span data-ttu-id="c3f06-124">Aby dodać docelowe lokalizacje eksportu, użytkownik musi mieć [uprawnienia administratora](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c3f06-124">To add export destinations, you have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="c3f06-125">W przypadku eksportu do usług Microsoft należy założyć, że obie usługi znajdują się w tej samej organizacji.</span><span class="sxs-lookup"><span data-stu-id="c3f06-125">If you export to Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="c3f06-126">Przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.</span><span class="sxs-lookup"><span data-stu-id="c3f06-126">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c3f06-127">Przejdź do karty **Moje lokalizacje docelowe eksportu**.</span><span class="sxs-lookup"><span data-stu-id="c3f06-127">Switch to the **My export destinations** tab.</span></span>

1. <span data-ttu-id="c3f06-128">Wybierz **Dodaj lokalizację**, aby utworzyć nową lokalizację docelową eksportu.</span><span class="sxs-lookup"><span data-stu-id="c3f06-128">Select **Add destination** to create a new export destination.</span></span>

1. <span data-ttu-id="c3f06-129">W okienku **Dodawaj lokalizację** wybierz **Typ** lokalizacji docelowej eksportu z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="c3f06-129">In the **Add destination** pane, select the **Type** of export destination in the drop-down.</span></span>

1. <span data-ttu-id="c3f06-130">Wprowadź wymagane informacje i wybierz **Dalej**, aby utworzyć lokalizację docelową eksportu.</span><span class="sxs-lookup"><span data-stu-id="c3f06-130">Provide the required details and select **Next** to create the export destination.</span></span>

<span data-ttu-id="c3f06-131">Możesz również wybrać **Konfiguruj** na kafelku na karcie **Odnajdź**.</span><span class="sxs-lookup"><span data-stu-id="c3f06-131">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

## <a name="view-export-destinations"></a><span data-ttu-id="c3f06-132">Wyświetl lokalizacje docelowe eksportu</span><span class="sxs-lookup"><span data-stu-id="c3f06-132">View Export destinations</span></span>

<span data-ttu-id="c3f06-133">Po utworzeniu miejsc docelowych eksportowania można je znaleźć w tabeli na karcie **Moje lokalizacje docelowe eksportu**. Ta tabela zawiera trzy kolumny:</span><span class="sxs-lookup"><span data-stu-id="c3f06-133">After creating export destinations, you'll find them in a table on the **My export destinations** tab. This table has three columns:</span></span>

- <span data-ttu-id="c3f06-134">**Wyświetlana nazwa**: Nazwa wprowadzana podczas tworzenia lokalizacji docelowej.</span><span class="sxs-lookup"><span data-stu-id="c3f06-134">**Display name**: The name you entered when creating the destination.</span></span>
- <span data-ttu-id="c3f06-135">**Typ**: Typ lokalizacji docelowej eksportu, który ustawisz podczas tworzenia lokalizacji docelowej.</span><span class="sxs-lookup"><span data-stu-id="c3f06-135">**Type**: The export destination type you set when creating the destination.</span></span>
- <span data-ttu-id="c3f06-136">**Utworzono**: Data utworzenia lokalizacji docelowej.</span><span class="sxs-lookup"><span data-stu-id="c3f06-136">**Created**: The date you created the destination.</span></span>

## <a name="edit-an-export-destination"></a><span data-ttu-id="c3f06-137">Edytuj lokalizację docelową eksportu</span><span class="sxs-lookup"><span data-stu-id="c3f06-137">Edit an export destination</span></span>

1. <span data-ttu-id="c3f06-138">Wybierz pionowy wielokropek dla lokalizacji docelowej eksportu, którą chcesz edytować.</span><span class="sxs-lookup"><span data-stu-id="c3f06-138">Select the vertical ellipsis for the Export destination you want to edit.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c3f06-139">![Wielokropek pionowy](media/export-destinations-page-ellipsis.png "Wielokropek pionowy")</span><span class="sxs-lookup"><span data-stu-id="c3f06-139">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

1. <span data-ttu-id="c3f06-140">Wybierz **Edytuj** z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="c3f06-140">Select **Edit** from the dropdown menu.</span></span>

1. <span data-ttu-id="c3f06-141">Zmień wartości, które wymagają aktualizacji, i wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="c3f06-141">Change the values that require update and select **Save**.</span></span>

## <a name="export-data-on-demand"></a><span data-ttu-id="c3f06-142">Eksportuj dane na żądanie</span><span class="sxs-lookup"><span data-stu-id="c3f06-142">Export data on demand</span></span>

<span data-ttu-id="c3f06-143">Po skonfigurowaniu łącznika dla docelowej lokalizacji eksportu eksporty będą wykonywane podczas wszystkich [zaplanowanych odświeżeń](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c3f06-143">After configuring a connector for an export destination, exports will run with every [scheduled refresh](system.md#schedule-tab).</span></span>

<span data-ttu-id="c3f06-144">Aby wyeksportować dane bez czekania na zaplanowane odświeżanie, przejdź do karty **Moje lokalizacje docelowe eksportowania** na **Administracja** > **Eksportowanie lokalizacji docelowych**.</span><span class="sxs-lookup"><span data-stu-id="c3f06-144">To export data without waiting for a scheduled refresh, go the **My export destinations** tab on **Admin** > **Export destinations**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c3f06-145">![Wielokropek pionowy](media/export-destinations-page-ellipsis.png "Wielokropek pionowy")</span><span class="sxs-lookup"><span data-stu-id="c3f06-145">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

- <span data-ttu-id="c3f06-146">Wybierz **Eksportuj** nad listą, aby uruchomić eksportowanie do wszystkich miejsc docelowych jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="c3f06-146">Select **Export** above the list to run the export to all export destinations simultaneously.</span></span>
- <span data-ttu-id="c3f06-147">Wybierz wielokropek (...) przy pozycji na liście a następnie wybierz opcję **Eksportuj**, aby uruchomić eksportowanie dla pojedynczej lokalizacji docelowej eksportu.</span><span class="sxs-lookup"><span data-stu-id="c3f06-147">Select the ellipsis (...) after a list item and then choose the **Export** option to run the export for a single export destination.</span></span>

## <a name="remove-an-export-destination"></a><span data-ttu-id="c3f06-148">Usuń lokalizację docelową eksportu</span><span class="sxs-lookup"><span data-stu-id="c3f06-148">Remove an Export destination</span></span>

<span data-ttu-id="c3f06-149">Aby usunąć lokalizację docelową eksportu, zacznij na stronie głównej **Lokalizacje docelowe eksportu**.</span><span class="sxs-lookup"><span data-stu-id="c3f06-149">To remove an Export destination, start from the main **Export destinations** page.</span></span>

1. <span data-ttu-id="c3f06-150">Wybierz pionowy wielokropek dla lokalizacji docelowej eksportu, którą chcesz usunąć.</span><span class="sxs-lookup"><span data-stu-id="c3f06-150">Select the vertical ellipsis for the Export destination you want to remove.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c3f06-151">![Wielokropek pionowy](media/export-destinations-page-ellipsis.png "Wielokropek pionowy")</span><span class="sxs-lookup"><span data-stu-id="c3f06-151">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

2. <span data-ttu-id="c3f06-152">Wybierz **Usuń** z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="c3f06-152">Select **Remove** from the dropdown menu.</span></span>

3. <span data-ttu-id="c3f06-153">Potwierdź usuwanie, zaznaczając pole **Usuń** na ekranie potwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="c3f06-153">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>
