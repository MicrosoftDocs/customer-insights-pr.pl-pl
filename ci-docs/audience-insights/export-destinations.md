---
title: Eksportowanie danych z usługi Customer Insights
description: Zarządzaj eksportami do udostępniania danych.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253053"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="73827-103">Omówienie eksportów (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="73827-103">Exports (preview) overview</span></span>

<span data-ttu-id="73827-104">Na stronie **Eksporty** widać wszystkie skonfigurowane eksporty.</span><span class="sxs-lookup"><span data-stu-id="73827-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="73827-105">Eksporty udostępniają konkretne dane różnym aplikacjom.</span><span class="sxs-lookup"><span data-stu-id="73827-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="73827-106">Mogą one zawierać profile klientów lub encje, schematy i szczegóły mapowania.</span><span class="sxs-lookup"><span data-stu-id="73827-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="73827-107">Każdy eksport wymaga [połączenia, skonfigurowanego przez administratora, do zarządzania uwierzytelnianiem i dostępem](connections.md).</span><span class="sxs-lookup"><span data-stu-id="73827-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="73827-108">Przejdź do strony **Dane** > **Eksporty**, aby wyświetlić stronę eksportów.</span><span class="sxs-lookup"><span data-stu-id="73827-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="73827-109">Wszystkie role użytkowników mają dostęp do wyświetlania skonfigurowanych eksportów.</span><span class="sxs-lookup"><span data-stu-id="73827-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="73827-110">Użycie pola wyszukiwania na pasku poleceń w celu znalezienia eksportów według ich nazwy, nazwy połączenia lub typu połączenia.</span><span class="sxs-lookup"><span data-stu-id="73827-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="73827-111">Konfiguracja nowego eksportu</span><span class="sxs-lookup"><span data-stu-id="73827-111">Set up a new export</span></span>

<span data-ttu-id="73827-112">Aby skonfigurować lub edytować eksport, potrzebne są dostępne dla użytkownika połączenia.</span><span class="sxs-lookup"><span data-stu-id="73827-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="73827-113">Połączenia zależą od [roli użytkownika](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="73827-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="73827-114">Administratorzy mają dostęp do wszystkich połączeń.</span><span class="sxs-lookup"><span data-stu-id="73827-114">Administrators have access to all connections.</span></span> <span data-ttu-id="73827-115">Mogą oni także tworzyć nowe połączenia podczas konfigurowania eksportu.</span><span class="sxs-lookup"><span data-stu-id="73827-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="73827-116">Współautorzy mogą mieć dostęp do określonych połączeń.</span><span class="sxs-lookup"><span data-stu-id="73827-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="73827-117">Zależą od administratorów, którzy muszą konfigurować i udostępniać połączenia.</span><span class="sxs-lookup"><span data-stu-id="73827-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="73827-118">Na liście eksportowania są wyświetlani współautorzy, niezależnie od tego, czy mogą edytować lub wyświetlać tylko eksport w kolumnie **Uprawnienia użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="73827-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="73827-119">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="73827-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="73827-120">Wyświetlający mogą tylko wyświetlać istniejące eksporty, ale nie mogą ich tworzyć.</span><span class="sxs-lookup"><span data-stu-id="73827-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="73827-121">Definiowanie nowego eksportu</span><span class="sxs-lookup"><span data-stu-id="73827-121">Define a new export</span></span>

1. <span data-ttu-id="73827-122">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="73827-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="73827-123">Wybierz **Dodaj eksport**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="73827-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="73827-124">W okienku **Konfigurowanie eksportu** wybierz połączenie, które ma być użyte.</span><span class="sxs-lookup"><span data-stu-id="73827-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="73827-125">[Połączenia](connections.md) są zarządzane przez administratorów.</span><span class="sxs-lookup"><span data-stu-id="73827-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="73827-126">Podaj wymagane szczegóły i wybierz opcję **Zapisz**, aby utworzyć eksport.</span><span class="sxs-lookup"><span data-stu-id="73827-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="73827-127">Definiowanie nowego eksportu na podstawie istniejącego eksportu</span><span class="sxs-lookup"><span data-stu-id="73827-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="73827-128">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="73827-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="73827-129">Na liście eksportów wybierz eksport, który chcesz zduplikować.</span><span class="sxs-lookup"><span data-stu-id="73827-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="73827-130">Wybierz opcję **Utwórz duplikat** na pasku poleceń, aby otworzyć okienko **Konfigurowanie eksportu** ze szczegółami wybranego eksportu.</span><span class="sxs-lookup"><span data-stu-id="73827-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="73827-131">Przejrzyj i dostosuj eksport i wybierz opcję **Zapisz**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="73827-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="73827-132">Edytuj eksport</span><span class="sxs-lookup"><span data-stu-id="73827-132">Edit an export</span></span>

1. <span data-ttu-id="73827-133">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="73827-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="73827-134">Na liście eksportów wybierz eksport, który chcesz edytować.</span><span class="sxs-lookup"><span data-stu-id="73827-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="73827-135">Na pasku poleceń wybierz **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="73827-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="73827-136">Zmień wartości, które chcesz zaktualizować i wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="73827-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="73827-137">Wyświetlanie eksportów i szczegółów eksportów</span><span class="sxs-lookup"><span data-stu-id="73827-137">View exports and export details</span></span>

<span data-ttu-id="73827-138">Po utworzeniu miejsc docelowych eksportu są one wyświetlane w **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="73827-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="73827-139">Wszyscy użytkownicy mogą zobaczyć, które dane są udostępniane oraz ich najaktualniejszy stan.</span><span class="sxs-lookup"><span data-stu-id="73827-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="73827-140">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="73827-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="73827-141">Użytkownicy bez uprawnień do edytowania mogą wybrać opcję **Wyświetl** zamiast opcji **Edytuj**, zobacz szczegółowe informacje o eksportowaniu.</span><span class="sxs-lookup"><span data-stu-id="73827-141">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="73827-142">W okienku bocznym jest pokazana konfiguracja eksportu.</span><span class="sxs-lookup"><span data-stu-id="73827-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="73827-143">Bez uprawnień do edycji nie można zmienić wartości.</span><span class="sxs-lookup"><span data-stu-id="73827-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="73827-144">Wybierz opcję **Zamknij**, aby powrócić do strony eksportowania.</span><span class="sxs-lookup"><span data-stu-id="73827-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="73827-145">Zaplanuj i uruchom eksport</span><span class="sxs-lookup"><span data-stu-id="73827-145">Schedule and run exports</span></span>

<span data-ttu-id="73827-146">Każdy skonfigurowany eksport ma harmonogram odświeżania.</span><span class="sxs-lookup"><span data-stu-id="73827-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="73827-147">Podczas odświeżania system szuka nowych lub zaktualizowanych danych do uwzględnienia w eksporcie.</span><span class="sxs-lookup"><span data-stu-id="73827-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="73827-148">Domyślnie eksport jest uruchamiany w ramach każdego [zaplanowanego odświeżania systemu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="73827-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="73827-149">Można dostosować harmonogram odświeżania lub wyłączyć go, aby eksporty były wykonywane ręcznie.</span><span class="sxs-lookup"><span data-stu-id="73827-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="73827-150">Harmonogramy eksportu zależą od stanu środowiska.</span><span class="sxs-lookup"><span data-stu-id="73827-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="73827-151">Jeśli istnieją aktualizacje [zależności](system.md#refresh-policies), które są w trakcie uruchamiania zaplanowanego eksportu, system najpierw uzupełni zależności, a następnie uruchom eksport.</span><span class="sxs-lookup"><span data-stu-id="73827-151">If there are updates on [dependencies](system.md#refresh-policies) in progress when a scheduled export should start, the system will first complete the dependencies and then run the export.</span></span> <span data-ttu-id="73827-152">W ostatniej kolumnie **Odświeżony** eksport można zobaczyć, kiedy został ostatnio odświeżony eksport.</span><span class="sxs-lookup"><span data-stu-id="73827-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="73827-153">Harmonogram wywozu</span><span class="sxs-lookup"><span data-stu-id="73827-153">Schedule exports</span></span>

<span data-ttu-id="73827-154">Można zdefiniować niestandardowe harmonogramy odświeżania dla pojedynczego eksportu lub kilku eksportów jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="73827-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="73827-155">Aktualnie zdefiniowany harmonogram jest wymieniony w kolumnie **Harmonogram** na liście eksportu.</span><span class="sxs-lookup"><span data-stu-id="73827-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="73827-156">Uprawnienia do zmiany harmonogramu są takie same jak w przypadku [edytowania i definiowania eksportów](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="73827-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="73827-157">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="73827-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="73827-158">Wybierz eksport, który chcesz zaplanować.</span><span class="sxs-lookup"><span data-stu-id="73827-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="73827-159">Na pasku poleceń wybierz **Zaplanuj**.</span><span class="sxs-lookup"><span data-stu-id="73827-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="73827-160">W okienku **Zaplanuj eksport** ustaw **Zaplanuj uruchomienie** na wartość **Wł.**, aby automatycznie uruchamiać eksportowanie.</span><span class="sxs-lookup"><span data-stu-id="73827-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="73827-161">Ustaw wartość **Wyłącz**, aby odświeżyć go ręcznie.</span><span class="sxs-lookup"><span data-stu-id="73827-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="73827-162">W przypadku automatycznie odświeżanego eksportu wybierz wartość **Cykl** i określ jej szczegóły.</span><span class="sxs-lookup"><span data-stu-id="73827-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="73827-163">Zdefiniowany czas ma zastosowanie do wszystkich przypadków nawrotu.</span><span class="sxs-lookup"><span data-stu-id="73827-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="73827-164">To czas, w którym eksportowanie powinno rozpocząć odświeżanie.</span><span class="sxs-lookup"><span data-stu-id="73827-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="73827-165">Zastosuj i aktywuj zmiany, wybierając przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="73827-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="73827-166">Podczas edytowania harmonogramu dla kilku eksportów należy dokonać wyboru w obszarze **Zachowaj lub zastępowanie harmonogramów**:</span><span class="sxs-lookup"><span data-stu-id="73827-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="73827-167">**Zachowaj poszczególne harmonogramy**: Zachowaj poprzednio zdefiniowany harmonogram dla wybranych eksportów i tylko je wyłączaj lub włączaj.</span><span class="sxs-lookup"><span data-stu-id="73827-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="73827-168">**Zdefiniuj nowy harmonogram dla wszystkich wybranych eksportów**: zastąp istniejące harmonogramy wybranych eksportów.</span><span class="sxs-lookup"><span data-stu-id="73827-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="73827-169">Uruchamianie eksportów na żądanie</span><span class="sxs-lookup"><span data-stu-id="73827-169">Run exports on demand</span></span>

<span data-ttu-id="73827-170">Aby wyeksportować dane bez oczekiwania na zaplanowane odświeżenie, przejdź do strony **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="73827-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="73827-171">Aby uruchomić wszystkie eksporty, wybierz polecenie **Uruchom wszystkie** na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="73827-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="73827-172">Ta akcja uruchomi tylko eksporty, które mają aktywny harmonogram.</span><span class="sxs-lookup"><span data-stu-id="73827-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="73827-173">Aby uruchomić pojedynczy eksport, wybierz go z listy i wybierz przycisk **Uruchom** na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="73827-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="73827-174">Tak można uruchomić eksport bez aktywnego harmonogramu.</span><span class="sxs-lookup"><span data-stu-id="73827-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="73827-175">Usuwanie eksportu</span><span class="sxs-lookup"><span data-stu-id="73827-175">Remove an Export</span></span>

1. <span data-ttu-id="73827-176">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="73827-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="73827-177">Wybierz eksport, który chcesz usunąć.</span><span class="sxs-lookup"><span data-stu-id="73827-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="73827-178">Na pasku poleceń wybierz **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="73827-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="73827-179">Potwierdź usuwanie, zaznaczając pole **Usuń** na ekranie potwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="73827-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
