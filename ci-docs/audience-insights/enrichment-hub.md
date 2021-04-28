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
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896018"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="9ced2-103">Wzbogacenie profilów klientów (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="9ced2-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="9ced2-104">Aby wzbogacić dane klientów, należy użyć danych pochodzących ze źródeł, takich jak Microsoft i inni partnerzy.</span><span class="sxs-lookup"><span data-stu-id="9ced2-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Strona centrum wzbogacania":::

<span data-ttu-id="9ced2-106">W statystykach odbiorców przejdź do **Dane** > **Wzbogacenie**, aby pracować z opcjami wzbogacania.</span><span class="sxs-lookup"><span data-stu-id="9ced2-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="9ced2-107">Aby tworzyć lub edytować wzbogacenia, trzeba mieć uprawnienia Współautor lub Administrator.</span><span class="sxs-lookup"><span data-stu-id="9ced2-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="9ced2-108">Aby uzyskać więcej informacji, zobacz [Uprawnienia](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="9ced2-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="9ced2-109">Na karcie **Odkryj** znajdziesz następujące wzbogacenia:</span><span class="sxs-lookup"><span data-stu-id="9ced2-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="9ced2-110">[Marki](enrichment-microsoft.md) dostarczone przez Microsoft</span><span class="sxs-lookup"><span data-stu-id="9ced2-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="9ced2-111">[Zainteresowania](enrichment-microsoft.md) dostarczone przez Microsoft</span><span class="sxs-lookup"><span data-stu-id="9ced2-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="9ced2-112">[Dane firmy](enrichment-leadspace.md) zapewniane przez Leadspace</span><span class="sxs-lookup"><span data-stu-id="9ced2-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="9ced2-113">[Dane demograficzne](enrichment-experian.md) zapewniane przez Experian</span><span class="sxs-lookup"><span data-stu-id="9ced2-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="9ced2-114">[Dane lokalizacji](enrichment-here.md) dostarczane przez HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="9ced2-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="9ced2-115">[Dane niestandardowe](enrichment-SFTP-custom-import.md) za pomocą protokołu SFTP (Secure File Transfer Protocol)</span><span class="sxs-lookup"><span data-stu-id="9ced2-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="9ced2-116">Na karcie **Moje wzbogacenia** użytkownik może zobaczyć skonfigurowane przez siebie wzbogacenia i edytować ich właściwości.</span><span class="sxs-lookup"><span data-stu-id="9ced2-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="9ced2-117">Zarządzanie istniejącymi wzbogaceniami</span><span class="sxs-lookup"><span data-stu-id="9ced2-117">Manage existing enrichments</span></span>

<span data-ttu-id="9ced2-118">Przejdź do **Moje wzbogacenia**, aby wyświetlić wszystkie skonfigurowane wzbogacenia.</span><span class="sxs-lookup"><span data-stu-id="9ced2-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="9ced2-119">Każde wzbogacenie jest reprezentowane jako wiersz zawierający dodatkowe informacje na temat wzbogacenia.</span><span class="sxs-lookup"><span data-stu-id="9ced2-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="9ced2-120">Wybierz wzbogacenie, aby wyświetlić dostępne opcje.</span><span class="sxs-lookup"><span data-stu-id="9ced2-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="9ced2-121">Aby wyświetlić opcje, wybierz wielokropek (...) na elemencie listy.</span><span class="sxs-lookup"><span data-stu-id="9ced2-121">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcje służące do zarządzania wzbogaceniami na liście wzbogaceń":::

- <span data-ttu-id="9ced2-123">**Wyświetl** szczegóły wzbogacenia dzięki liczbie ulepszonych profilów klientów.</span><span class="sxs-lookup"><span data-stu-id="9ced2-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="9ced2-124">**Edytuj** konfigurację wzbogacenia.</span><span class="sxs-lookup"><span data-stu-id="9ced2-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="9ced2-125">**Uruchom** wzbogacenie, aby zaktualizować profile klientów za pomocą najnowszych danych.</span><span class="sxs-lookup"><span data-stu-id="9ced2-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="9ced2-126">**Dezaktywuj** istniejące wzbogacenie, aby zapobiec jego automatycznemu odświeżaniu przy każdym planowanym odświeżeniu.</span><span class="sxs-lookup"><span data-stu-id="9ced2-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="9ced2-127">Dane ostatniego pomyślnego odświeżenia będą nadal dostępne.</span><span class="sxs-lookup"><span data-stu-id="9ced2-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="9ced2-128">**Uaktywnij** nieaktywne wzbogacanie, aby ponownie uruchomić odświeżanie automatyczne przy każdym planowanym odświeżeniu.</span><span class="sxs-lookup"><span data-stu-id="9ced2-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="9ced2-129">**Usuń** wzbogacenie.</span><span class="sxs-lookup"><span data-stu-id="9ced2-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="9ced2-130">Można uruchomić lub zdezaktywować wiele operacji wzbogacania naraz, wybierając je na liście.</span><span class="sxs-lookup"><span data-stu-id="9ced2-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="9ced2-131">Opcje wyświetlania i edycji nie są dostępne jako działanie zbiorcze i w danej chwili działają tylko w jednym wzbogaceniu.</span><span class="sxs-lookup"><span data-stu-id="9ced2-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="9ced2-132">Wzbogacenia i połączenia</span><span class="sxs-lookup"><span data-stu-id="9ced2-132">Enrichments and connections</span></span>

<span data-ttu-id="9ced2-133">Wzbogacenia innych firm konfiguruje się przy użyciu [połączeń](connections.md), które administrator konfiguruje się z poświadczeniami i wyraża zgodę na przesyłanie danych.</span><span class="sxs-lookup"><span data-stu-id="9ced2-133">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="9ced2-134">Połączenie może być następnie używane do konfiguracji wzbogaceń przez administratorów i współautorów.</span><span class="sxs-lookup"><span data-stu-id="9ced2-134">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="9ced2-135">Wiele wzbogaceń tego samego typu</span><span class="sxs-lookup"><span data-stu-id="9ced2-135">Multiple enrichments of the same type</span></span>

<span data-ttu-id="9ced2-136">Podczas konfigurowania wzbogacania jest określana encja do wzbogacenia, która umożliwia wzbogacenie tylko podzestawu profilów.</span><span class="sxs-lookup"><span data-stu-id="9ced2-136">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="9ced2-137">Na przykład wzbogacenie danych tylko dla określonego segmentu.</span><span class="sxs-lookup"><span data-stu-id="9ced2-137">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="9ced2-138">Można skonfigurować wiele wzbogaceń tego samego typu i ponownie używać tego samego połączenia.</span><span class="sxs-lookup"><span data-stu-id="9ced2-138">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="9ced2-139">Niektóre wzbogacenia będą mieć ograniczoną liczbę wzbogaceń tego samego typu, które można utworzyć.</span><span class="sxs-lookup"><span data-stu-id="9ced2-139">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="9ced2-140">Ograniczenia i bieżące użycie są widoczne na stronie **Wzbogacanie**.</span><span class="sxs-lookup"><span data-stu-id="9ced2-140">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
