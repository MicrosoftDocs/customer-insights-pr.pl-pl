---
title: Eksportowanie danych z usługi Customer Insights
description: Zarządzaj eksportami do udostępniania danych.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016649"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="2797a-103">Omówienie eksportów (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="2797a-103">Exports (preview) overview</span></span>

<span data-ttu-id="2797a-104">Na stronie **Eksporty** widać wszystkie skonfigurowane eksporty.</span><span class="sxs-lookup"><span data-stu-id="2797a-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="2797a-105">Eksporty udostępniają konkretne dane różnym aplikacjom.</span><span class="sxs-lookup"><span data-stu-id="2797a-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="2797a-106">Mogą one zawierać profile klientów lub encje, schematy i szczegóły mapowania.</span><span class="sxs-lookup"><span data-stu-id="2797a-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="2797a-107">Każdy eksport wymaga [połączenia, skonfigurowanego przez administratora, do zarządzania uwierzytelnianiem i dostępem](connections.md).</span><span class="sxs-lookup"><span data-stu-id="2797a-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="2797a-108">Przejdź do strony **Dane** > **Eksporty**, aby wyświetlić stronę eksportów.</span><span class="sxs-lookup"><span data-stu-id="2797a-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="2797a-109">Wszystkie role użytkowników mają dostęp do wyświetlania skonfigurowanych eksportów.</span><span class="sxs-lookup"><span data-stu-id="2797a-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="2797a-110">Użycie pola wyszukiwania na pasku poleceń w celu znalezienia eksportów według ich nazwy, nazwy połączenia lub typu połączenia.</span><span class="sxs-lookup"><span data-stu-id="2797a-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="2797a-111">Konfiguracja nowego eksportu</span><span class="sxs-lookup"><span data-stu-id="2797a-111">Set up a new export</span></span>

<span data-ttu-id="2797a-112">Aby skonfigurować lub edytować eksport, potrzebne są dostępne dla użytkownika połączenia.</span><span class="sxs-lookup"><span data-stu-id="2797a-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="2797a-113">Połączenia zależą od [roli użytkownika](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="2797a-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="2797a-114">Administratorzy mają dostęp do wszystkich połączeń.</span><span class="sxs-lookup"><span data-stu-id="2797a-114">Administrators have access to all connections.</span></span> <span data-ttu-id="2797a-115">Mogą oni także tworzyć nowe połączenia podczas konfigurowania eksportu.</span><span class="sxs-lookup"><span data-stu-id="2797a-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="2797a-116">Współautorzy mogą mieć dostęp do określonych połączeń.</span><span class="sxs-lookup"><span data-stu-id="2797a-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="2797a-117">Zależą od administratorów, którzy muszą konfigurować i udostępniać połączenia.</span><span class="sxs-lookup"><span data-stu-id="2797a-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="2797a-118">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="2797a-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="2797a-119">Wyświetlający mogą tylko wyświetlać istniejące eksporty, ale nie mogą ich tworzyć.</span><span class="sxs-lookup"><span data-stu-id="2797a-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="2797a-120">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="2797a-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2797a-121">Wybierz **Dodaj eksport**, aby utworzyć nowe miejsce docelowe eksportu.</span><span class="sxs-lookup"><span data-stu-id="2797a-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="2797a-122">W okienku **Konfigurowanie eksportu** wybierz połączenie, które ma być użyte.</span><span class="sxs-lookup"><span data-stu-id="2797a-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="2797a-123">[Połączenia](connections.md) są zarządzane przez administratorów.</span><span class="sxs-lookup"><span data-stu-id="2797a-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="2797a-124">Podaj wymagane szczegóły i wybierz opcję **Zapisz**, aby utworzyć eksport.</span><span class="sxs-lookup"><span data-stu-id="2797a-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="2797a-125">Edytuj eksport</span><span class="sxs-lookup"><span data-stu-id="2797a-125">Edit an export</span></span>

1. <span data-ttu-id="2797a-126">Wybierz pionowy wielokropek dla lokalizacji docelowej eksportu, którą chcesz edytować.</span><span class="sxs-lookup"><span data-stu-id="2797a-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="2797a-127">Z menu rozwijanego wybierz polecenie **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="2797a-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="2797a-128">Zmień wartości, które chcesz zaktualizować i wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="2797a-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="2797a-129">Wyświetlanie eksportów i szczegółów eksportów</span><span class="sxs-lookup"><span data-stu-id="2797a-129">View Exports and export details</span></span>

<span data-ttu-id="2797a-130">Po utworzeniu miejsc docelowych eksportu są one wyświetlane w **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="2797a-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="2797a-131">Wszyscy użytkownicy mogą zobaczyć, które dane są udostępniane oraz ich najaktualniejszy stan.</span><span class="sxs-lookup"><span data-stu-id="2797a-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="2797a-132">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="2797a-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2797a-133">Użytkownicy bez uprawnień do edytowania mogą wybrać opcję **Wyświetl** zamiast opcji **Edytuj**, zobacz szczegółowe informacje o eksportowaniu.</span><span class="sxs-lookup"><span data-stu-id="2797a-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="2797a-134">W tym okienku bocznym jest pokazana konfiguracja tego eksportu.</span><span class="sxs-lookup"><span data-stu-id="2797a-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="2797a-135">Bez uprawnień do edycji nie można zmienić wartości.</span><span class="sxs-lookup"><span data-stu-id="2797a-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="2797a-136">Wybierz opcję **Zamknij**, aby powrócić do strony eksportowania.</span><span class="sxs-lookup"><span data-stu-id="2797a-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="2797a-137">Uruchamianie eksportów na żądanie</span><span class="sxs-lookup"><span data-stu-id="2797a-137">Run exports on demand</span></span>

<span data-ttu-id="2797a-138">Po skonfigurowaniu eksportu będzie on uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab), o ile posiada działające połączenie.</span><span class="sxs-lookup"><span data-stu-id="2797a-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="2797a-139">Aby wyeksportować dane bez oczekiwania na zaplanowane odświeżenie, przejdź do strony **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="2797a-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="2797a-140">Dostępne są dwie opcje:</span><span class="sxs-lookup"><span data-stu-id="2797a-140">You have two options:</span></span>

- <span data-ttu-id="2797a-141">Aby uruchomić wszystkie eksporty, wybierz polecenie **Uruchom wszystkie** na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="2797a-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="2797a-142">Aby uruchomić pojedynczy eksport, wybierz wielokropek (...) dla elementu listy, a następnie wybierz opcję **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="2797a-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="2797a-143">Usuwanie eksportu</span><span class="sxs-lookup"><span data-stu-id="2797a-143">Remove an Export</span></span>

1. <span data-ttu-id="2797a-144">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="2797a-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2797a-145">Wybierz pionowy wielokropek dla eksportu, który chcesz usunąć.</span><span class="sxs-lookup"><span data-stu-id="2797a-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="2797a-146">Wybierz **Usuń** z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="2797a-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="2797a-147">Potwierdź usuwanie, zaznaczając pole **Usuń** na ekranie potwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="2797a-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
