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
ms.openlocfilehash: 28563e3a76535cb0c92bfcda4ef5037430d00cfa
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305491"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="99c39-103">Omówienie eksportów (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="99c39-103">Exports (preview) overview</span></span>

<span data-ttu-id="99c39-104">Na stronie **Eksporty** widać wszystkie skonfigurowane eksporty.</span><span class="sxs-lookup"><span data-stu-id="99c39-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="99c39-105">Eksporty udostępniają konkretne dane różnym aplikacjom.</span><span class="sxs-lookup"><span data-stu-id="99c39-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="99c39-106">Mogą one zawierać profile klientów lub encje, schematy i szczegóły mapowania.</span><span class="sxs-lookup"><span data-stu-id="99c39-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="99c39-107">Każdy eksport wymaga [połączenia, skonfigurowanego przez administratora, do zarządzania uwierzytelnianiem i dostępem](connections.md).</span><span class="sxs-lookup"><span data-stu-id="99c39-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="99c39-108">Przejdź do strony **Dane** > **Eksporty**, aby wyświetlić stronę eksportów.</span><span class="sxs-lookup"><span data-stu-id="99c39-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="99c39-109">Wszystkie role użytkowników mogą przeglądać skonfigurowane eksporty.</span><span class="sxs-lookup"><span data-stu-id="99c39-109">All user roles can view configured exports.</span></span> <span data-ttu-id="99c39-110">Użyj pola wyszukiwania na pasku poleceń, aby znaleźć eksporty według ich nazwy, nazwy połączenia lub typu połączenia.</span><span class="sxs-lookup"><span data-stu-id="99c39-110">Use the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="99c39-111">Konfiguracja nowego eksportu</span><span class="sxs-lookup"><span data-stu-id="99c39-111">Set up a new export</span></span>

<span data-ttu-id="99c39-112">Aby skonfigurować lub edytować eksport, potrzebne są dostępne dla użytkownika połączenia.</span><span class="sxs-lookup"><span data-stu-id="99c39-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="99c39-113">Połączenia zależą od [roli użytkownika](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="99c39-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="99c39-114">Administratorzy mają dostęp do wszystkich połączeń.</span><span class="sxs-lookup"><span data-stu-id="99c39-114">Administrators have access to all connections.</span></span> <span data-ttu-id="99c39-115">Mogą oni także tworzyć nowe połączenia podczas konfigurowania eksportu.</span><span class="sxs-lookup"><span data-stu-id="99c39-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="99c39-116">Współautorzy mogą mieć dostęp do określonych połączeń.</span><span class="sxs-lookup"><span data-stu-id="99c39-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="99c39-117">Zależą od administratorów, którzy muszą konfigurować i udostępniać połączenia.</span><span class="sxs-lookup"><span data-stu-id="99c39-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="99c39-118">Na liście eksportowania są wyświetlani współautorzy, niezależnie od tego, czy mogą edytować lub wyświetlać tylko eksport w kolumnie **Uprawnienia użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="99c39-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="99c39-119">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="99c39-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="99c39-120">Wyświetlający mogą tylko wyświetlać istniejące eksporty, ale nie mogą ich tworzyć.</span><span class="sxs-lookup"><span data-stu-id="99c39-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="99c39-121">Definiowanie nowego eksportu</span><span class="sxs-lookup"><span data-stu-id="99c39-121">Define a new export</span></span>

1. <span data-ttu-id="99c39-122">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="99c39-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="99c39-123">Wybierz **Dodaj eksport**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="99c39-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="99c39-124">W okienku **Konfigurowanie eksportu** wybierz połączenie, które ma być użyte.</span><span class="sxs-lookup"><span data-stu-id="99c39-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="99c39-125">[Połączenia](connections.md) są zarządzane przez administratorów.</span><span class="sxs-lookup"><span data-stu-id="99c39-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="99c39-126">Podaj wymagane szczegóły i wybierz opcję **Zapisz**, aby utworzyć eksport.</span><span class="sxs-lookup"><span data-stu-id="99c39-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="99c39-127">Definiowanie nowego eksportu na podstawie istniejącego eksportu</span><span class="sxs-lookup"><span data-stu-id="99c39-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="99c39-128">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="99c39-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="99c39-129">Na liście eksportów wybierz eksport, który chcesz zduplikować.</span><span class="sxs-lookup"><span data-stu-id="99c39-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="99c39-130">Wybierz opcję **Utwórz duplikat** na pasku poleceń, aby otworzyć okienko **Konfigurowanie eksportu** ze szczegółami wybranego eksportu.</span><span class="sxs-lookup"><span data-stu-id="99c39-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="99c39-131">Przejrzyj i dostosuj eksport i wybierz opcję **Zapisz**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="99c39-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="99c39-132">Edytuj eksport</span><span class="sxs-lookup"><span data-stu-id="99c39-132">Edit an export</span></span>

1. <span data-ttu-id="99c39-133">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="99c39-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="99c39-134">Na liście eksportów wybierz eksport, który chcesz edytować.</span><span class="sxs-lookup"><span data-stu-id="99c39-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="99c39-135">Na pasku poleceń wybierz **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="99c39-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="99c39-136">Zmień wartości, które chcesz zaktualizować i wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="99c39-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="99c39-137">Wyświetlanie eksportów i szczegółów eksportów</span><span class="sxs-lookup"><span data-stu-id="99c39-137">View exports and export details</span></span>

<span data-ttu-id="99c39-138">Po utworzeniu miejsc docelowych eksportu są one wyświetlane w **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="99c39-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="99c39-139">Wszyscy użytkownicy mogą zobaczyć, które dane są udostępniane oraz ich najaktualniejszy stan.</span><span class="sxs-lookup"><span data-stu-id="99c39-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="99c39-140">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="99c39-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="99c39-141">Użytkownicy bez edytowania uprawnień wybrać opcję **Wyświetl** zamiast opcji **Edycja**, aby wyświetlić szczegóły eksportowania.</span><span class="sxs-lookup"><span data-stu-id="99c39-141">Users without edit permissions select **View** instead of **Edit** to see the export details.</span></span>

1. <span data-ttu-id="99c39-142">W okienku bocznym jest pokazana konfiguracja eksportu.</span><span class="sxs-lookup"><span data-stu-id="99c39-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="99c39-143">Bez uprawnień do edycji nie można zmienić wartości.</span><span class="sxs-lookup"><span data-stu-id="99c39-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="99c39-144">Wybierz opcję **Zamknij**, aby powrócić do strony eksportowania.</span><span class="sxs-lookup"><span data-stu-id="99c39-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="99c39-145">Zaplanuj i uruchom eksport</span><span class="sxs-lookup"><span data-stu-id="99c39-145">Schedule and run exports</span></span>

<span data-ttu-id="99c39-146">Każdy skonfigurowany eksport ma harmonogram odświeżania.</span><span class="sxs-lookup"><span data-stu-id="99c39-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="99c39-147">Podczas odświeżania system szuka nowych lub zaktualizowanych danych do uwzględnienia w eksporcie.</span><span class="sxs-lookup"><span data-stu-id="99c39-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="99c39-148">Domyślnie eksport jest uruchamiany w ramach każdego [zaplanowanego odświeżania systemu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="99c39-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="99c39-149">Można dostosować harmonogram odświeżania lub wyłączyć go, aby eksporty były wykonywane ręcznie.</span><span class="sxs-lookup"><span data-stu-id="99c39-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="99c39-150">Harmonogramy eksportu zależą od stanu środowiska.</span><span class="sxs-lookup"><span data-stu-id="99c39-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="99c39-151">Jeśli istnieją aktualizacje dotyczące [zależności](system.md#refresh-policies) po uruchomieniu zaplanowanego eksportu, system najpierw je uzupełni, a następnie uruchomi eksport.</span><span class="sxs-lookup"><span data-stu-id="99c39-151">If there are updates in progress on [dependencies](system.md#refresh-policies) when a scheduled export should start, the system will first complete the updates and then run the export.</span></span> <span data-ttu-id="99c39-152">W ostatniej kolumnie **Odświeżony** eksport można zobaczyć, kiedy został ostatnio odświeżony eksport.</span><span class="sxs-lookup"><span data-stu-id="99c39-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="99c39-153">Harmonogram wywozu</span><span class="sxs-lookup"><span data-stu-id="99c39-153">Schedule exports</span></span>

<span data-ttu-id="99c39-154">Można zdefiniować niestandardowe harmonogramy odświeżania dla pojedynczego eksportu lub kilku eksportów jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="99c39-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="99c39-155">Aktualnie zdefiniowany harmonogram jest wymieniony w kolumnie **Harmonogram** na liście eksportu.</span><span class="sxs-lookup"><span data-stu-id="99c39-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="99c39-156">Uprawnienia do zmiany harmonogramu są takie same jak w przypadku [edytowania i definiowania eksportów](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="99c39-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="99c39-157">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="99c39-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="99c39-158">Wybierz eksport, który chcesz zaplanować.</span><span class="sxs-lookup"><span data-stu-id="99c39-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="99c39-159">Na pasku poleceń wybierz **Zaplanuj**.</span><span class="sxs-lookup"><span data-stu-id="99c39-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="99c39-160">W okienku **Zaplanuj eksport** ustaw **Zaplanuj uruchomienie** na wartość **Wł.**, aby automatycznie uruchamiać eksportowanie.</span><span class="sxs-lookup"><span data-stu-id="99c39-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="99c39-161">Ustaw wartość **Wyłącz**, aby odświeżyć go ręcznie.</span><span class="sxs-lookup"><span data-stu-id="99c39-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="99c39-162">W przypadku automatycznie odświeżanego eksportu wybierz wartość **Cykl** i określ jej szczegóły.</span><span class="sxs-lookup"><span data-stu-id="99c39-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="99c39-163">Zdefiniowany czas ma zastosowanie do wszystkich przypadków nawrotu.</span><span class="sxs-lookup"><span data-stu-id="99c39-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="99c39-164">To czas, w którym eksportowanie powinno rozpocząć odświeżanie.</span><span class="sxs-lookup"><span data-stu-id="99c39-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="99c39-165">Zastosuj i aktywuj zmiany, wybierając przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="99c39-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="99c39-166">Podczas edytowania harmonogramu dla kilku eksportów należy dokonać wyboru w obszarze **Zachowaj lub zastępowanie harmonogramów**:</span><span class="sxs-lookup"><span data-stu-id="99c39-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="99c39-167">**Zachowaj poszczególne harmonogramy**: Zachowaj poprzednio zdefiniowany harmonogram dla wybranych eksportów i tylko je wyłączaj lub włączaj.</span><span class="sxs-lookup"><span data-stu-id="99c39-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="99c39-168">**Zdefiniuj nowy harmonogram dla wszystkich wybranych eksportów**: zastąp istniejące harmonogramy wybranych eksportów.</span><span class="sxs-lookup"><span data-stu-id="99c39-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="99c39-169">Uruchamianie eksportów na żądanie</span><span class="sxs-lookup"><span data-stu-id="99c39-169">Run exports on demand</span></span>

<span data-ttu-id="99c39-170">Aby wyeksportować dane bez oczekiwania na zaplanowane odświeżenie, przejdź do strony **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="99c39-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="99c39-171">Aby uruchomić wszystkie eksporty, wybierz polecenie **Uruchom wszystkie** na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="99c39-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="99c39-172">Ta akcja uruchomi tylko eksporty, które mają aktywny harmonogram.</span><span class="sxs-lookup"><span data-stu-id="99c39-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="99c39-173">Aby uruchomić pojedynczy eksport, wybierz go z listy i wybierz przycisk **Uruchom** na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="99c39-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="99c39-174">Tak można uruchomić eksport bez aktywnego harmonogramu.</span><span class="sxs-lookup"><span data-stu-id="99c39-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="99c39-175">Usuwanie eksportu</span><span class="sxs-lookup"><span data-stu-id="99c39-175">Remove an Export</span></span>

1. <span data-ttu-id="99c39-176">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="99c39-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="99c39-177">Wybierz eksport, który chcesz usunąć.</span><span class="sxs-lookup"><span data-stu-id="99c39-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="99c39-178">Na pasku poleceń wybierz **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="99c39-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="99c39-179">Potwierdź usuwanie, zaznaczając pole **Usuń** na ekranie potwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="99c39-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
