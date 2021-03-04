---
title: Żądania podmiotów danych osobowych (DSR) w kontekście rozporządzenia RODO | Microsoft Docs
description: Odpowiadaj na żądania osób, których dotyczą dane, dotyczące możliwości wglądu odbiorców w Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed9aa09fba938606611c6ce86c2b250c5e19c606
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268699"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="56ad3-103">Żądania osób, których dotyczą dane, w kontekście rozporządzenia RODO</span><span class="sxs-lookup"><span data-stu-id="56ad3-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="56ad3-104">Odpowiadanie na żądania usunięcia przez osobę, której dane dotyczą, dotyczące RODO dotyczące możliwości wglądu odbiorców w Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="56ad3-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="56ad3-105">„Prawo do usunięcia danych osobowych” poprzez usunięcie prywatnych danych klienta organizacji jest kluczową ochroną w Ogólnym rozporządzeniu o ochronie danych (RODO).</span><span class="sxs-lookup"><span data-stu-id="56ad3-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="56ad3-106">Usuwanie danych osobowych polega na usunięciu wszystkich danych osobowych i dzienników generowanych przez system, poza informacjami dotyczącymi dziennika inspekcji.</span><span class="sxs-lookup"><span data-stu-id="56ad3-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="56ad3-107">Zarządzanie żądaniami usuwania danych</span><span class="sxs-lookup"><span data-stu-id="56ad3-107">Manage data subject delete requests</span></span>

<span data-ttu-id="56ad3-108">Analiza odbiorców oferuje następujące doświadczenia w produkcie, które usuwają dane osobowe dotyczące konkretnego użytkownika lub klienta:</span><span class="sxs-lookup"><span data-stu-id="56ad3-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="56ad3-109">**Zarządzanie żądaniami usuwania danych klienta**: dane klienta w Customer Insights są pobierane z oryginalnych źródeł danych spoza Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="56ad3-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="56ad3-110">Wszystkie żądania dotyczące usuwania danych według RODO muszą zostać wykonane w oryginalnym źródle danych.</span><span class="sxs-lookup"><span data-stu-id="56ad3-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="56ad3-111">**Zarządzanie żądaniami usunięcia danych użytkownika Customer Insights**: Dane dla użytkowników są tworzone przez Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="56ad3-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="56ad3-112">Wszystkie żądania dotyczące usuwania danych według RODO muszą zostać wykonane w Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="56ad3-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="56ad3-113">Zarządzanie żądaniami usunięcia danych klienta</span><span class="sxs-lookup"><span data-stu-id="56ad3-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="56ad3-114">Administrator Customer Insights może wykonać poniższe kroki w celu usunięcia danych klienta, które zostały usunięte ze źródła danych:</span><span class="sxs-lookup"><span data-stu-id="56ad3-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="56ad3-115">Zaloguj się w Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="56ad3-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="56ad3-116">W analizach odbiorców przejdź do **Dane** > **Źródła danych**</span><span class="sxs-lookup"><span data-stu-id="56ad3-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="56ad3-117">Dla każdego źródła danych z listy, które zawiera usunięte dane klienta:</span><span class="sxs-lookup"><span data-stu-id="56ad3-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="56ad3-118">Wybierz (...) i wybierz **Odśwież**.</span><span class="sxs-lookup"><span data-stu-id="56ad3-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="56ad3-119">Sprawdź status źródła danych w **Stan**.</span><span class="sxs-lookup"><span data-stu-id="56ad3-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="56ad3-120">Znacznik wyboru oznacza, że odświeżanie zakończyło się powodzeniem.</span><span class="sxs-lookup"><span data-stu-id="56ad3-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="56ad3-121">Trójkąt ostrzegawczy oznacza, że wystąpił problem.</span><span class="sxs-lookup"><span data-stu-id="56ad3-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="56ad3-122">Jeśli zostanie wyświetlony trójkąt ostrzegawczy, skontaktuj się z D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="56ad3-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="56ad3-123">![Zarządzanie żądaniami usunięcia danych klienta według RODO](media/gdpr-data-sources.png "Zarządzanie żądaniami usunięcia danych klienta według RODO")</span><span class="sxs-lookup"><span data-stu-id="56ad3-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="56ad3-124">Zarządzanie żądaniami usunięcia danych użytkownika</span><span class="sxs-lookup"><span data-stu-id="56ad3-124">Manage delete requests for user data</span></span>

<span data-ttu-id="56ad3-125">Administrator Customer Insights może wykonać poniższe kroki w celu usunięcia danych użytkownika Customer Insights:</span><span class="sxs-lookup"><span data-stu-id="56ad3-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="56ad3-126">Zaloguj się w Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="56ad3-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="56ad3-127">W analizach odbiorców przejdź do **Administrator** > **Uprawnienia**.</span><span class="sxs-lookup"><span data-stu-id="56ad3-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="56ad3-128">Zaznacz pole wyboru dla użytkownika, którego chcesz usunąć.</span><span class="sxs-lookup"><span data-stu-id="56ad3-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="56ad3-129">Wybierz **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="56ad3-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="56ad3-130">![Obsługa żądań usunięcia RODO dotyczących danych użytkownika](media/gdpr-permissions.png "Obsługa żądań usunięcia RODO dotyczących danych użytkownika")</span><span class="sxs-lookup"><span data-stu-id="56ad3-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="56ad3-131">Odpowiadanie na żądania podmiotów o eksport danych osobowych zgodnie z RODO</span><span class="sxs-lookup"><span data-stu-id="56ad3-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="56ad3-132">W ramach naszych starań, aby wspierać użytkowników w trakcie wdrażania Ogólnego rozporządzenia o ochronie danych (RODO), opracowano dokumentację ułatwiającą przygotowanie.</span><span class="sxs-lookup"><span data-stu-id="56ad3-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="56ad3-133">W tej dokumentacji opisano kroki, które możesz podjąć dzisiaj, aby zapewnić zgodność z RODO podczas korzystania ze statystyk odbiorców.</span><span class="sxs-lookup"><span data-stu-id="56ad3-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="56ad3-134">Zarządzanie żądaniami eksportowania i wyświetlania</span><span class="sxs-lookup"><span data-stu-id="56ad3-134">Manage export and view requests</span></span>

<span data-ttu-id="56ad3-135">Prawo do przenoszenia danych osobowych pozwala podmiotowi danych składać wniosek o kopię danych osobowych w formacie elektronicznym („struktura, powszechnie stosowana, czytelna i wieloprogramowa”), który może być przekazywany innemu kontrolerowi danych.</span><span class="sxs-lookup"><span data-stu-id="56ad3-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="56ad3-136">Eksportowanie danych klienta (Administrator dzierżawcy)</span><span class="sxs-lookup"><span data-stu-id="56ad3-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="56ad3-137">W celu wyeksportowania danych administrator dzierżawy może wykonać następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="56ad3-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="56ad3-138">Wysłąć wiadomość e-mail na adres D365CI@microsoft.com określając adres e-mail klienta w żądaniu.</span><span class="sxs-lookup"><span data-stu-id="56ad3-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="56ad3-139">Zespół Customer Insights wyśle wiadomość e-mail na adres e-mail zarejestrowanego administratora dzierżawcy, pytając o potwierdzenie wyeksportowania danych.</span><span class="sxs-lookup"><span data-stu-id="56ad3-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="56ad3-140">Zatwierdź potwierdzenie wyeksportowania danych dla żądanego klienta.</span><span class="sxs-lookup"><span data-stu-id="56ad3-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="56ad3-141">Pobierz eksportowane dane za pomocą adresu e-mail administratora dzierżawcy.</span><span class="sxs-lookup"><span data-stu-id="56ad3-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="56ad3-142">Eksportuj dane użytkownika (administrator dzierżawy)</span><span class="sxs-lookup"><span data-stu-id="56ad3-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="56ad3-143">Wysłąć wiadomość e-mail na adres D365CI@microsoft.com określając adres e-mail użytkownika w żądaniu.</span><span class="sxs-lookup"><span data-stu-id="56ad3-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="56ad3-144">Zespół Customer Insights wyśle wiadomość e-mail na adres e-mail zarejestrowanego administratora dzierżawcy, pytając o potwierdzenie wyeksportowania danych.</span><span class="sxs-lookup"><span data-stu-id="56ad3-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="56ad3-145">Zatwierdź potwierdzenie wyeksportowania danych dla żądanego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="56ad3-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="56ad3-146">Pobierz eksportowane dane za pomocą adresu e-mail administratora dzierżawcy.</span><span class="sxs-lookup"><span data-stu-id="56ad3-146">Receive the exported data through the tenant admin email address.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]