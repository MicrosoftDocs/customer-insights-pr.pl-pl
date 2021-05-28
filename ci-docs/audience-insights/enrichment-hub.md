---
title: Wzbogać ujednolicone profile klientów
description: Korzystanie z funkcji w celu wzbogacenia danych klienta.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c8e4a7247ccf575a62440038180010916b09d51b
ms.sourcegitcommit: f9e2fa3f11ecf11a5d9cccc376fdeb1ecea54880
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/28/2021
ms.locfileid: "5954500"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="7e34a-103">Wzbogacenie profilów klientów (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="7e34a-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="7e34a-104">Aby wzbogacić dane klientów, należy użyć danych pochodzących ze źródeł, takich jak Microsoft i inni partnerzy.</span><span class="sxs-lookup"><span data-stu-id="7e34a-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Strona centrum wzbogacania":::

<span data-ttu-id="7e34a-106">W statystykach odbiorców przejdź do **Dane** > **Wzbogacenie**, aby pracować z opcjami wzbogacania.</span><span class="sxs-lookup"><span data-stu-id="7e34a-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="7e34a-107">Aby tworzyć lub edytować wzbogacenia, trzeba mieć uprawnienia Współautor lub Administrator.</span><span class="sxs-lookup"><span data-stu-id="7e34a-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="7e34a-108">Aby uzyskać więcej informacji, zobacz [Uprawnienia](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="7e34a-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="7e34a-109">Na karcie **Odkryj** znajdziesz następujące wzbogacenia:</span><span class="sxs-lookup"><span data-stu-id="7e34a-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="7e34a-110">[Marki](enrichment-microsoft.md) dostarczone przez Microsoft</span><span class="sxs-lookup"><span data-stu-id="7e34a-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="7e34a-111">[Zainteresowania](enrichment-microsoft.md) dostarczone przez Microsoft</span><span class="sxs-lookup"><span data-stu-id="7e34a-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="7e34a-112">[Ulepszone adresy](enrichment-enhanced-addresses.md) od Microsoft</span><span class="sxs-lookup"><span data-stu-id="7e34a-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="7e34a-113">[Dane firmy](enrichment-leadspace.md) zapewniane przez Leadspace</span><span class="sxs-lookup"><span data-stu-id="7e34a-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="7e34a-114">[Dane demograficzne](enrichment-experian.md) zapewniane przez Experian</span><span class="sxs-lookup"><span data-stu-id="7e34a-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="7e34a-115">[Dane lokalizacji](enrichment-here.md) dostarczane przez HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="7e34a-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="7e34a-116">[Dane niestandardowe](enrichment-SFTP-custom-import.md) za pomocą protokołu SFTP (Secure File Transfer Protocol)</span><span class="sxs-lookup"><span data-stu-id="7e34a-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="7e34a-117">Na karcie **Moje wzbogacenia** użytkownik może zobaczyć skonfigurowane przez siebie wzbogacenia i edytować ich właściwości.</span><span class="sxs-lookup"><span data-stu-id="7e34a-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="7e34a-118">Zarządzanie istniejącymi wzbogaceniami</span><span class="sxs-lookup"><span data-stu-id="7e34a-118">Manage existing enrichments</span></span>

<span data-ttu-id="7e34a-119">Przejdź do **Moje wzbogacenia**, aby wyświetlić wszystkie skonfigurowane wzbogacenia.</span><span class="sxs-lookup"><span data-stu-id="7e34a-119">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="7e34a-120">Każde wzbogacenie jest reprezentowane jako wiersz zawierający dodatkowe informacje na temat wzbogacenia.</span><span class="sxs-lookup"><span data-stu-id="7e34a-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="7e34a-121">Wybierz wzbogacenie, aby wyświetlić dostępne opcje.</span><span class="sxs-lookup"><span data-stu-id="7e34a-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="7e34a-122">Aby wyświetlić opcje, wybierz wielokropek (...) na elemencie listy.</span><span class="sxs-lookup"><span data-stu-id="7e34a-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcje służące do zarządzania wzbogaceniami na liście wzbogaceń":::

- <span data-ttu-id="7e34a-124">**Wyświetl** szczegóły wzbogacenia dzięki liczbie ulepszonych profilów klientów.</span><span class="sxs-lookup"><span data-stu-id="7e34a-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="7e34a-125">**Edytuj** konfigurację wzbogacenia.</span><span class="sxs-lookup"><span data-stu-id="7e34a-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="7e34a-126">**Uruchom** wzbogacenie, aby zaktualizować profile klientów za pomocą najnowszych danych.</span><span class="sxs-lookup"><span data-stu-id="7e34a-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="7e34a-127">**Dezaktywuj** istniejące wzbogacenie, aby zapobiec jego automatycznemu odświeżaniu przy każdym planowanym odświeżeniu.</span><span class="sxs-lookup"><span data-stu-id="7e34a-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="7e34a-128">Dane ostatniego pomyślnego odświeżenia będą nadal dostępne.</span><span class="sxs-lookup"><span data-stu-id="7e34a-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="7e34a-129">**Uaktywnij** nieaktywne wzbogacanie, aby ponownie uruchomić odświeżanie automatyczne przy każdym planowanym odświeżeniu.</span><span class="sxs-lookup"><span data-stu-id="7e34a-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="7e34a-130">**Usuń** wzbogacenie.</span><span class="sxs-lookup"><span data-stu-id="7e34a-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="7e34a-131">Można uruchomić lub zdezaktywować wiele operacji wzbogacania naraz, wybierając je na liście.</span><span class="sxs-lookup"><span data-stu-id="7e34a-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="7e34a-132">Opcje wyświetlania i edycji nie są dostępne jako działanie zbiorcze i w danej chwili działają tylko w jednym wzbogaceniu.</span><span class="sxs-lookup"><span data-stu-id="7e34a-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="7e34a-133">Wzbogacenia i połączenia</span><span class="sxs-lookup"><span data-stu-id="7e34a-133">Enrichments and connections</span></span>

<span data-ttu-id="7e34a-134">Wzbogacenia innych firm konfiguruje się przy użyciu [połączeń](connections.md), które administrator konfiguruje się z poświadczeniami i wyraża zgodę na przesyłanie danych.</span><span class="sxs-lookup"><span data-stu-id="7e34a-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="7e34a-135">Połączenie może być następnie używane do konfiguracji wzbogaceń przez administratorów i współautorów.</span><span class="sxs-lookup"><span data-stu-id="7e34a-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="7e34a-136">Wiele wzbogaceń tego samego typu</span><span class="sxs-lookup"><span data-stu-id="7e34a-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="7e34a-137">Podczas konfigurowania wzbogacania jest określana encja do wzbogacenia, która umożliwia wzbogacenie tylko podzestawu profilów.</span><span class="sxs-lookup"><span data-stu-id="7e34a-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="7e34a-138">Na przykład wzbogacenie danych tylko dla określonego segmentu.</span><span class="sxs-lookup"><span data-stu-id="7e34a-138">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="7e34a-139">Można skonfigurować wiele wzbogaceń tego samego typu i ponownie używać tego samego połączenia.</span><span class="sxs-lookup"><span data-stu-id="7e34a-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="7e34a-140">Niektóre wzbogacenia będą mieć ograniczoną liczbę wzbogaceń tego samego typu, które można utworzyć.</span><span class="sxs-lookup"><span data-stu-id="7e34a-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="7e34a-141">Ograniczenia i bieżące użycie są widoczne na stronie **Wzbogacanie**.</span><span class="sxs-lookup"><span data-stu-id="7e34a-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
