---
title: Połączenia z innymi usługami z aplikacji Customer Insights.
description: Udostępnianie danych w innych usługach.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 17e04b243e9b3d4375c86f5a890a18be35956835
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304985"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="9c5c8-103">Omówienie (podgląd) połączeń</span><span class="sxs-lookup"><span data-stu-id="9c5c8-103">Connections (preview) overview</span></span>

<span data-ttu-id="9c5c8-104">Połączenia to klucz do włączenia udostępniania danych do i z funkcji Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="9c5c8-105">Każde połączenie ustanawia udostępnianie danych w określonej usłudze.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="9c5c8-106">Połączenia są podstawą do [konfigurowania wzbogaceń innych firm](enrichment-hub.md) i [konfigurowania eksportów](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="9c5c8-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="9c5c8-107">To samo połączenie może być używane wiele razy.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="9c5c8-108">Na przykład jedno połączenie z usługą Dynamics 365 Marketing działa dla wielu eksportów, a jedno połączenie Leadspace może zostać użyte dla kilku wzbogaceń.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="9c5c8-109">Przejdź do połączeń **Admin** > **Połączenia**, aby utworzyć i wyświetlić połączenia.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="9c5c8-110">Na karcie **Połączenia** widać wszystkie aktywne połączenia.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="9c5c8-111">Na liście zostanie wyświetlony wiersz dla każdego połączenia.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="9c5c8-112">Uzyskaj szybkie omówienie, opis i dowiedz się, co można zrobić z każdą opcją rozszerzania na karcie **Odkryj**.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="9c5c8-113">Eksporty</span><span class="sxs-lookup"><span data-stu-id="9c5c8-113">Exports</span></span>

<span data-ttu-id="9c5c8-114">Tylko administratorzy mogą konfigurować nowe połączenia, ale mogą udzielać współautorom dostęp do korzystania z istniejących połączeń.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="9c5c8-115">Administratorzy określają, gdzie mogą się znaleźć dane, współautorzy definiują ładunek i częstotliwość określania ich potrzeb.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="9c5c8-116">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="9c5c8-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="9c5c8-117">Wzbogacenia</span><span class="sxs-lookup"><span data-stu-id="9c5c8-117">Enrichments</span></span>

<span data-ttu-id="9c5c8-118">Tylko administratorzy mogą konfigurować nowe połączenia, ale utworzone połączenia są zawsze dostępne zarówno dla administratorów, jak i współautorów.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="9c5c8-119">Administratorzy zarządzają poświadczeniami i wyrażają zgodę na przenoszenie danych.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="9c5c8-120">Połączenia mogą być następnie używane do wzbogacania przez administratorów i współautorów.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="9c5c8-121">Dodaj nowe połączenie</span><span class="sxs-lookup"><span data-stu-id="9c5c8-121">Add a new connection</span></span>

<span data-ttu-id="9c5c8-122">Aby dodawać połączenia, trzeba mieć [uprawnienia administratora](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="9c5c8-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="9c5c8-123">W przypadku łączenia się z innymi usługami Microsoft założono, że obie usługi są w tej samej organizacji.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="9c5c8-124">Przejdź do **Admin** > **Połączenia (wersja zapoznawcza)**.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="9c5c8-125">Przejdź do karty **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="9c5c8-126">Wybrać **Dodaj połączenie**, aby utworzyć nowe połączenie.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="9c5c8-127">Wybierz z menu rozwijanego typ połączenia, które chcesz utworzyć.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-127">Choose from the dropdown menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="9c5c8-128">Podaj wymagane szczegóły w okienku **Konfigurowanie połączenia**.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="9c5c8-129">**Wyświetlana nazwa** i typ połączenia opisują połączenie.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="9c5c8-130">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="9c5c8-131">Dokładnie jakie pola będzie zależeć od tego, z jaką usługą jest nawiązywana połączenie.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="9c5c8-132">Szczegółowe informacje o określonym typie połączenia można znaleźć w artykule dotyczących usługi docelowej.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="9c5c8-133">Aby utworzyć połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="9c5c8-134">Możesz również wybrać **Konfiguruj** na kafelku na karcie **Odnajdź**.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="9c5c8-135">Zezwalaj współautorom na używanie połączenia do eksportowania</span><span class="sxs-lookup"><span data-stu-id="9c5c8-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="9c5c8-136">Podczas konfigurowania lub edytowania połączenia eksportowania należy wybrać użytkowników, którzy mogą korzystać z tego konkretnego połączenia w celu zdefiniowania [eksportów](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="9c5c8-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="9c5c8-137">Domyślnie połączenie jest dostępne dla użytkowników, którzy mają rolę administratora.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="9c5c8-138">To ustawienie można zmienić w obszarze **Określ, kto może korzystać z tego połączenia** i zezwolić użytkownikom z rolą współautora na korzystanie z tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="9c5c8-139">Współautorzy nie mogą wyświetlać ani edytować połączenia.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="9c5c8-140">Podczas tworzenia eksportu będą widzieć tylko wyświetlaną nazwę i typ.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="9c5c8-141">Udostępniając połączenie, można umożliwić współautorom korzystanie z połączenia.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="9c5c8-142">Współautorzy będą widzieć udostępnione połączenia podczas skonfigurowania eksportu.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="9c5c8-143">Mogą zarządzać każdym eksportem, który korzysta z tego określonego połączenia.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="9c5c8-144">To ustawienie można zmienić, zachowując przy tym eksporty, które zostały już zdefiniowane przez współautorów.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="9c5c8-145">Edytowanie połączenia</span><span class="sxs-lookup"><span data-stu-id="9c5c8-145">Edit a connection</span></span>

1. <span data-ttu-id="9c5c8-146">Przejdź do **Admin** > **Połączenia (wersja zapoznawcza)**.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="9c5c8-147">Przejdź do karty **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="9c5c8-148">Wybierz pionowy wielokropek dla połączenia, które chcesz edytować.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="9c5c8-149">Zaznacz **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-149">Select **Edit**.</span></span>

1. <span data-ttu-id="9c5c8-150">Zmień wartości, które chcesz zaktualizować i wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="9c5c8-151">Usuwanie połączenia</span><span class="sxs-lookup"><span data-stu-id="9c5c8-151">Remove a connection</span></span>

<span data-ttu-id="9c5c8-152">Jeśli usuwane połączenie jest używane przez wzbogacanie lub eksportowanie, należy je najpierw odłączyć lub usunąć.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="9c5c8-153">Okno dialogowe usuwania przeprowadzi do odpowiedniego wzbogacenia lub eksportu.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> 

<span data-ttu-id="9c5c8-154">Odłączone wzbogacenia i eksporty stają się nieaktywne.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="9c5c8-155">Można je ponownie aktywować, dodając do nich inne połączenie na stronie [Wzbogacenia](enrichment-hub.md) lub [Eksporty](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="9c5c8-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="9c5c8-156">Przejdź do **Admin** > **Połączenia (wersja zapoznawcza)**.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="9c5c8-157">Przejdź do karty **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="9c5c8-158">Wybierz pionowy wielokropek dla połączenia, które chcesz usunąć.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="9c5c8-159">Wybierz **Usuń** z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="9c5c8-160">Pojawia się okno dialogowe potwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="9c5c8-161">Jeśli są dostępne wzbogacenia lub eksporty używające tego połączenia, wybierz przycisk, aby wyświetlić informacje o połączeniu.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="9c5c8-162">**Eksport:** można usunąć lub odłączyć eksport, aby można było usunąć połączenie.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="9c5c8-163">Aby odłączyć eksport, administratorzy mogą używać akcji **Odłącz**.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="9c5c8-164">Ta akcja jest dostępna dla pojedynczego i wielu wybranych eksportów.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="9c5c8-165">Odłączenie spowoduje zachowanie konfiguracji eksportu, ale nie zostanie on uruchomiony, dopóki nie zostanie dodane do niego inne połączenie.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="9c5c8-166">**Wzbogacenia:** można usunąć lub dezaktywować wzbogacenia, aby można było usunąć połączenie.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="9c5c8-167">Gdy połączenie nie ma więcej zależności, wróć do opcji **Admin** > **Połączenia** i spróbuj ponownie usunąć połączenie.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="9c5c8-168">Aby potwierdzić usunięcie, wybierz opcję **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="9c5c8-168">To confirm the deletion, select **Remove**.</span></span>

