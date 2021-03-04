---
title: Połącz się z encjami w Lake zarządzanym przez Common Data Service
description: Zaimportuj dane z zarządzanego przez Common Data Service repozytorium typu data lake.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 18b6cd3fdaf5b738877a73b520b91dbc6ded40de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267827"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="d0a0f-103">Łączenie się z danymi w repozytorium typu data lake, którym zarządza Common Data Service</span><span class="sxs-lookup"><span data-stu-id="d0a0f-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="d0a0f-104">W tym artykule zamieszczono informacje dotyczące tego, w jaki sposób istniejący klienci Dynamics 365 mogą szybko połączyć się z encjami analitycznymi w zarządzanym przez Common Data Service repozytorium typu lake.</span><span class="sxs-lookup"><span data-stu-id="d0a0f-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="d0a0f-105">Aby kontynuować pracę i zobaczyć listę encji dostępnych w zarządzany repozytorium typu lake należy mieć uprawnienia administratora w organizacji Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d0a0f-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="d0a0f-106">Ważne uwagi</span><span class="sxs-lookup"><span data-stu-id="d0a0f-106">Important considerations</span></span>

<span data-ttu-id="d0a0f-107">Dane przechowywane w usługach online, np. Azure Data Lake Storage, mogą być przechowywane w innej lokalizacji niż miejsce przetwarzania danych lub przechowywanie ich w Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d0a0f-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="d0a0f-108"> Importując lub łącząc się z danymi w usługach online, użytkownik zgadza się, że dane mogą być przenoszone do programu Dynamics 365 Customer Insights i przechowywane w nim. [Dowiedz się więcej w Centrum zaufania firmy Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="d0a0f-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="d0a0f-109">Nawiązywanie połączenia z zarządzanym przez Common Data Service repozytorium typu lake</span><span class="sxs-lookup"><span data-stu-id="d0a0f-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="d0a0f-110">W analizach odbiorców przejdź do **Dane** > **Źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="d0a0f-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="d0a0f-111">Wybierz **Dodaj źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="d0a0f-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="d0a0f-112">Wybierz **Połącz z Common Data Service** i wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="d0a0f-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="d0a0f-113">Wprowadź **Nazwę** źródła danych i wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="d0a0f-113">Enter a **Name** for the data source and select **Next**.</span></span> <span data-ttu-id="d0a0f-114">Wytyczne dotyczące nazw:</span><span class="sxs-lookup"><span data-stu-id="d0a0f-114">Name guidelines:</span></span> 
   - <span data-ttu-id="d0a0f-115">Rozpocznij od litery.</span><span class="sxs-lookup"><span data-stu-id="d0a0f-115">Start with a letter.</span></span>
   - <span data-ttu-id="d0a0f-116">Używaj tylko liter i liczb.</span><span class="sxs-lookup"><span data-stu-id="d0a0f-116">Use letters and numbers only.</span></span> <span data-ttu-id="d0a0f-117">Spacje i znaki specjalne są niedozwolone.</span><span class="sxs-lookup"><span data-stu-id="d0a0f-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="d0a0f-118">Użyj między 3 do 64 znaków.</span><span class="sxs-lookup"><span data-stu-id="d0a0f-118">Use between 3 and 64 characters.</span></span>

5. <span data-ttu-id="d0a0f-119">Wprowadź **Adres serwera** dla organizacji Common Data Service i wybierz **Zaloguj się**.</span><span class="sxs-lookup"><span data-stu-id="d0a0f-119">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d0a0f-120">![Okno dialogowe umożliwiające wprowadzanie adresu serwera Common Data Service](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="d0a0f-120">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="d0a0f-121">Wybierz encje, które chcesz pozyskać z dostępnej listy.</span><span class="sxs-lookup"><span data-stu-id="d0a0f-121">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="d0a0f-122">Jeśli niektóre encje są już wybrane, mogą być używane przez inne aplikacje Dynamics 365 (na przykład Dynamics 365 Sales Insights lub Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="d0a0f-122">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="d0a0f-123">Nie można tego zmienić.</span><span class="sxs-lookup"><span data-stu-id="d0a0f-123">You can't change the selection.</span></span> <span data-ttu-id="d0a0f-124">Te encje będą dostępne po utworzeniu źródła danych.</span><span class="sxs-lookup"><span data-stu-id="d0a0f-124">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d0a0f-125">![Okno dialogowe pokazujące listę encji w organizacji Common Data Service](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="d0a0f-125">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="d0a0f-126">Aby rozpocząć synchronizowanie zaznaczonych encji z zarządzanym przez Common Data Service repozytorium typu lake zapisz wybrane opcje.</span><span class="sxs-lookup"><span data-stu-id="d0a0f-126">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="d0a0f-127">Ostatnio dodane połączenie będzie można znaleźć na stronie **Źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="d0a0f-127">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="d0a0f-128">Element zostanie umieszczony w kolejce do odświeżenia i będzie pokazywał liczbę encji jako 0, aż do chwili zsynchronizowania wszystkich encji.</span><span class="sxs-lookup"><span data-stu-id="d0a0f-128">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="d0a0f-129">Tylko jedna źródło danych środowiska może równocześnie korzystać z tego zamego Lake zarządzanego przez Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d0a0f-129">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="d0a0f-130">Edytowanie źródła danych zarządzanego przez Common Data Service repozytorium typu lake</span><span class="sxs-lookup"><span data-stu-id="d0a0f-130">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="d0a0f-131">Wybraną encję edytuje się tylko po utworzeniu źródła danych.</span><span class="sxs-lookup"><span data-stu-id="d0a0f-131">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="d0a0f-132">Jeśli na przykład dodano dodatkowe encje do Common Data Service i chcesz je również zaimportować.</span><span class="sxs-lookup"><span data-stu-id="d0a0f-132">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="d0a0f-133">Aby połączyć z innym Common Data Service, [utwórz nowe źródło danych](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="d0a0f-133">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="d0a0f-134">W analizach odbiorców przejdź do **Dane** > **Źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="d0a0f-134">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="d0a0f-135">Kliknij wielokropek obok źródła danych, który chcesz zaktualizować.</span><span class="sxs-lookup"><span data-stu-id="d0a0f-135">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="d0a0f-136">Wybierz opcję **Edytuj** z listy.</span><span class="sxs-lookup"><span data-stu-id="d0a0f-136">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="d0a0f-137">Wybierz dodatkowe encje z listy dostępnych encji i wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="d0a0f-137">Select additional entities from the available list of entities and select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]