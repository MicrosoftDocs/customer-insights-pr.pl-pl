---
title: Eksportowanie danych z usługi Customer Insights
description: Zarządzaj eksportami do udostępniania danych.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896156"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="470eb-103">Omówienie eksportów (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="470eb-103">Exports (preview) overview</span></span>

<span data-ttu-id="470eb-104">Na stronie **Eksporty** widać wszystkie skonfigurowane eksporty.</span><span class="sxs-lookup"><span data-stu-id="470eb-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="470eb-105">Eksporty udostępniają konkretne dane różnym aplikacjom.</span><span class="sxs-lookup"><span data-stu-id="470eb-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="470eb-106">Mogą one zawierać profile klientów lub encje, schematy i szczegóły mapowania.</span><span class="sxs-lookup"><span data-stu-id="470eb-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="470eb-107">Każdy eksport wymaga [połączenia, skonfigurowanego przez administratora, do zarządzania uwierzytelnianiem i dostępem](connections.md).</span><span class="sxs-lookup"><span data-stu-id="470eb-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="470eb-108">Do marca 2021 r. eksporty automatycznie tworzyły połączenie z odpowiednią usługą.</span><span class="sxs-lookup"><span data-stu-id="470eb-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="470eb-109">Eksporty wymagają teraz [połączenia, utworzonego i udostępnionego przez administratora](connections.md), zanim będzie można je utworzyć.</span><span class="sxs-lookup"><span data-stu-id="470eb-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="470eb-110">Przejdź do strony **Dane** > **Eksporty**, aby wyświetlić stronę eksportów.</span><span class="sxs-lookup"><span data-stu-id="470eb-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="470eb-111">Wszystkie role użytkowników mają dostęp do wyświetlania skonfigurowanych eksportów.</span><span class="sxs-lookup"><span data-stu-id="470eb-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="470eb-112">Użycie pola wyszukiwania na pasku poleceń w celu znalezienia eksportów według ich nazwy, nazwy połączenia lub typu połączenia.</span><span class="sxs-lookup"><span data-stu-id="470eb-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="470eb-113">Konfiguracja nowego eksportu</span><span class="sxs-lookup"><span data-stu-id="470eb-113">Set up a new export</span></span>

<span data-ttu-id="470eb-114">Aby skonfigurować lub edytować eksport, potrzebne są dostępne dla użytkownika połączenia.</span><span class="sxs-lookup"><span data-stu-id="470eb-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="470eb-115">Połączenia zależą od [roli użytkownika](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="470eb-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="470eb-116">Administratorzy mają dostęp do wszystkich połączeń.</span><span class="sxs-lookup"><span data-stu-id="470eb-116">Administrators have access to all connections.</span></span> <span data-ttu-id="470eb-117">Mogą oni także tworzyć nowe połączenia podczas konfigurowania eksportu.</span><span class="sxs-lookup"><span data-stu-id="470eb-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="470eb-118">Współautorzy mogą mieć dostęp do określonych połączeń.</span><span class="sxs-lookup"><span data-stu-id="470eb-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="470eb-119">Zależą od administratorów, którzy muszą konfigurować i udostępniać połączenia.</span><span class="sxs-lookup"><span data-stu-id="470eb-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="470eb-120">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="470eb-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="470eb-121">Wyświetlający mogą tylko wyświetlać istniejące eksporty, ale nie mogą ich tworzyć.</span><span class="sxs-lookup"><span data-stu-id="470eb-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="470eb-122">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="470eb-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="470eb-123">Wybierz **Dodaj eksport**, aby utworzyć nowe miejsce docelowe eksportu.</span><span class="sxs-lookup"><span data-stu-id="470eb-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="470eb-124">W okienku **Konfigurowanie eksportu** wybierz połączenie, które ma być użyte.</span><span class="sxs-lookup"><span data-stu-id="470eb-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="470eb-125">[Połączenia](connections.md) są zarządzane przez administratorów.</span><span class="sxs-lookup"><span data-stu-id="470eb-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="470eb-126">Podaj wymagane szczegóły i wybierz opcję **Zapisz**, aby utworzyć eksport.</span><span class="sxs-lookup"><span data-stu-id="470eb-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="470eb-127">Edytuj eksport</span><span class="sxs-lookup"><span data-stu-id="470eb-127">Edit an export</span></span>

1. <span data-ttu-id="470eb-128">Wybierz pionowy wielokropek dla lokalizacji docelowej eksportu, którą chcesz edytować.</span><span class="sxs-lookup"><span data-stu-id="470eb-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="470eb-129">Z menu rozwijanego wybierz polecenie **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="470eb-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="470eb-130">Zmień wartości, które chcesz zaktualizować i wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="470eb-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="470eb-131">Wyświetlanie eksportów i szczegółów eksportów</span><span class="sxs-lookup"><span data-stu-id="470eb-131">View Exports and export details</span></span>

<span data-ttu-id="470eb-132">Po utworzeniu miejsc docelowych eksportu są one wyświetlane w **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="470eb-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="470eb-133">Wszyscy użytkownicy mogą zobaczyć, które dane są udostępniane oraz ich najaktualniejszy stan.</span><span class="sxs-lookup"><span data-stu-id="470eb-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="470eb-134">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="470eb-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="470eb-135">Użytkownicy bez uprawnień do edytowania mogą wybrać opcję **Wyświetl** zamiast opcji **Edytuj**, zobacz szczegółowe informacje o eksportowaniu.</span><span class="sxs-lookup"><span data-stu-id="470eb-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="470eb-136">W tym okienku bocznym jest pokazana konfiguracja tego eksportu.</span><span class="sxs-lookup"><span data-stu-id="470eb-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="470eb-137">Bez uprawnień do edycji nie można zmienić wartości.</span><span class="sxs-lookup"><span data-stu-id="470eb-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="470eb-138">Wybierz opcję **Zamknij**, aby powrócić do strony eksportowania.</span><span class="sxs-lookup"><span data-stu-id="470eb-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="470eb-139">Uruchamianie eksportów na żądanie</span><span class="sxs-lookup"><span data-stu-id="470eb-139">Run exports on demand</span></span>

<span data-ttu-id="470eb-140">Po skonfigurowaniu eksportu będzie on uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab), o ile posiada działające połączenie.</span><span class="sxs-lookup"><span data-stu-id="470eb-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="470eb-141">Aby wyeksportować dane bez oczekiwania na zaplanowane odświeżenie, przejdź do strony **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="470eb-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="470eb-142">Dostępne są dwie opcje:</span><span class="sxs-lookup"><span data-stu-id="470eb-142">You have two options:</span></span>

- <span data-ttu-id="470eb-143">Aby uruchomić wszystkie eksporty, wybierz polecenie **Uruchom wszystkie** na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="470eb-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="470eb-144">Aby uruchomić pojedynczy eksport, wybierz wielokropek (...) dla elementu listy, a następnie wybierz opcję **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="470eb-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="470eb-145">Usuwanie eksportu</span><span class="sxs-lookup"><span data-stu-id="470eb-145">Remove an Export</span></span>

1. <span data-ttu-id="470eb-146">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="470eb-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="470eb-147">Wybierz pionowy wielokropek dla eksportu, który chcesz usunąć.</span><span class="sxs-lookup"><span data-stu-id="470eb-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="470eb-148">Wybierz **Usuń** z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="470eb-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="470eb-149">Potwierdź usuwanie, zaznaczając pole **Usuń** na ekranie potwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="470eb-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
