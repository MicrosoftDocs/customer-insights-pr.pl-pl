---
title: Wzbogać ujednolicone profile klientów
description: Korzystanie z funkcji w celu wzbogacenia danych klienta.
ms.date: 11/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 36e6f7f8fcd64fc2591e913910918b83bf27567b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597708"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="fbbbc-103">Wzbogacenie profilów klientów (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="fbbbc-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="fbbbc-104">Aby wzbogacić dane klientów, należy użyć danych pochodzących ze źródeł, takich jak Microsoft i inni partnerzy.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Strona centrum wzbogacania":::

<span data-ttu-id="fbbbc-106">W statystykach odbiorców przejdź do **Dane** > **Wzbogacenie**, aby pracować z opcjami wzbogacania.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="fbbbc-107">Aby tworzyć lub edytować wzbogacenia, trzeba mieć uprawnienia Współautor lub Administrator.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="fbbbc-108">Aby uzyskać więcej informacji, zobacz [Uprawnienia](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="fbbbc-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="fbbbc-109">Na karcie **Odkryj** znajdziesz następujące wzbogacenia:</span><span class="sxs-lookup"><span data-stu-id="fbbbc-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="fbbbc-110">[Marki](enrichment-microsoft-graph.md) są dostarczane przez Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="fbbbc-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="fbbbc-111">[Zainteresowania](enrichment-microsoft-graph.md) są dostarczane przez Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="fbbbc-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="fbbbc-112">[Dane firmy](enrichment-leadspace.md) zapewniane przez Leadspace</span><span class="sxs-lookup"><span data-stu-id="fbbbc-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="fbbbc-113">[Dane demograficzne](enrichment-experian.md) zapewniane przez Experian</span><span class="sxs-lookup"><span data-stu-id="fbbbc-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="fbbbc-114">[Dane lokalizacji](enrichment-here.md) dostarczane przez HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="fbbbc-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="fbbbc-115">[Dane niestandardowe](enrichment-SFTP-custom-import.md) za pomocą protokołu SFTP (Secure File Transfer Protocol)</span><span class="sxs-lookup"><span data-stu-id="fbbbc-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="fbbbc-116">Na karcie **Moje wzbogacenia** użytkownik może zobaczyć skonfigurowane przez siebie wzbogacenia i edytować ich właściwości.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="fbbbc-117">Zarządzanie istniejącymi wzbogaceniami</span><span class="sxs-lookup"><span data-stu-id="fbbbc-117">Manage existing enrichments</span></span>

<span data-ttu-id="fbbbc-118">Przejdź do **Moje wzbogacenia**, aby wyświetlić wszystkie skonfigurowane wzbogacenia.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="fbbbc-119">Każde wzbogacenie jest reprezentowane jako wiersz zawierający dodatkowe informacje na temat wzbogacenia.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="fbbbc-120">Wybierz wzbogacenie, aby wyświetlić dostępne opcje.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="fbbbc-121">Można też wybrać wielokropek (...) na elemencie listy, aby wyświetlić dostępne opcje.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcje służące do zarządzania wzbogaceniami na liście wzbogaceń":::

- <span data-ttu-id="fbbbc-123">**Wyświetl** szczegóły wzbogacenia dzięki liczbie ulepszonych profilów klientów.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="fbbbc-124">**Edytuj** konfigurację wzbogacenia.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="fbbbc-125">**Uruchom** wzbogacenie, aby zaktualizować profile klientów za pomocą najnowszych danych.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="fbbbc-126">**Dezaktywuj** istniejące wzbogacenie, aby zapobiec jego automatycznemu odświeżaniu przy każdym planowanym odświeżeniu.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="fbbbc-127">Dane ostatniego pomyślnego odświeżenia będą nadal dostępne.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="fbbbc-128">**Uaktywnij** nieaktywne wzbogacanie, aby ponownie uruchomić odświeżanie automatyczne przy każdym planowanym odświeżeniu.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="fbbbc-129">**Usuń** wzbogacenie.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="fbbbc-130">Można uruchomić lub zdezaktywować wiele operacji wzbogacania naraz, wybierając je na liście.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="fbbbc-131">Opcje wyświetlania i edycji nie są dostępne jako działanie zbiorcze i w danej chwili działają tylko w jednym wzbogaceniu.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]