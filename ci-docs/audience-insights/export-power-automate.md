---
title: Łącznik Power Automate | Microsoft Docs
description: Tworzenie przepływów w usłudze Microsoft Power Automate z poziomu aplikacji Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 57be0a204ef920b7a4bb31cf9a5b3a77f96eca0d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305077"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="41977-103">Łącznik Power Automate (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="41977-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="41977-104">Wyzwalaj automatyczne występowanie określonych zdarzeń przy zmianie danych i zarządzaj bardziej skomplikowanymi przepływami bezpośrednio w [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="41977-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="41977-105">Wyzwalacze Power Automate</span><span class="sxs-lookup"><span data-stu-id="41977-105">Power Automate triggers</span></span>

<span data-ttu-id="41977-106">Użyj wyzwalaczy do tworzenia przepływów w chmurze i automatyzacji powtarzalnych zadań, takich jak powiadomienia lub bardziej zaawansowane akcje.</span><span class="sxs-lookup"><span data-stu-id="41977-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="41977-107">Wyzwól, kiedy odświeżanie źródła danych zakończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="41977-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="41977-108">Wyzwól, kiedy odświeżanie źródła danych zakończy się sukcesem.</span><span class="sxs-lookup"><span data-stu-id="41977-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="41977-109">Wyzwól, kiedy w segmencie nastąpi przekroczenie progu.</span><span class="sxs-lookup"><span data-stu-id="41977-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="41977-110">Wyzwalacz jest ograniczony do przekraczania progu.</span><span class="sxs-lookup"><span data-stu-id="41977-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="41977-111">Wyzwól, kiedy w miarze biznesowej nastąpi przekroczenie progu.</span><span class="sxs-lookup"><span data-stu-id="41977-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="41977-112">Obsługiwane są tylko miary biznesowe bez wymiaru.</span><span class="sxs-lookup"><span data-stu-id="41977-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="41977-113">Wyzwalacz jest ograniczony do przekraczania progu.</span><span class="sxs-lookup"><span data-stu-id="41977-113">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="41977-114">Wyzwalaj, gdy zostanie ukończone pełne odświeżanie (źródła danych, segmenty, miary, ...).</span><span class="sxs-lookup"><span data-stu-id="41977-114">Trigger when a full refresh of (data sources, segments, measures, ...) is completed.</span></span>
- <span data-ttu-id="41977-115">Wyzwalaj po zakończeniu odświeżania procesu unifikacji (mapowanie, dopasowanie, scalanie).</span><span class="sxs-lookup"><span data-stu-id="41977-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

[<span data-ttu-id="41977-116">Skonfiguruj wyzwalacze w Power Automate.</span><span class="sxs-lookup"><span data-stu-id="41977-116">Configure your triggers in Power Automate.</span></span>](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a><span data-ttu-id="41977-117">Akcje Power Automate</span><span class="sxs-lookup"><span data-stu-id="41977-117">Power Automate actions</span></span>

<span data-ttu-id="41977-118">Łącznik Power Automate dostarcza innych akcji niż dostępne wyzwalacze.</span><span class="sxs-lookup"><span data-stu-id="41977-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="41977-119">Aby uzyskać więcej informacji, zobacz [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="41977-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="41977-120">Utwórz przepływ Power Automate</span><span class="sxs-lookup"><span data-stu-id="41977-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="41977-121">W analizach odbiorców przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.</span><span class="sxs-lookup"><span data-stu-id="41977-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="41977-122">Na kafelku **Power Automate** wybierz **Konfiguracja**.</span><span class="sxs-lookup"><span data-stu-id="41977-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="41977-123">Zostanie otwarty łącznik Customer Insights (wersja zapoznawcza) w usłudze Power Automate.</span><span class="sxs-lookup"><span data-stu-id="41977-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="41977-124">**Zaloguj się** do Power Automate.</span><span class="sxs-lookup"><span data-stu-id="41977-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="41977-125">Wybierz jeden z dostępnych przycisków i dodaj kolejne kroki do nowego przepływu.</span><span class="sxs-lookup"><span data-stu-id="41977-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="41977-126">Aby uzyskać więcej informacji, zobacz temat [Tworzenie przepływu w chmurze w Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="41977-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="41977-127">Przykłady korzystania z przepływów:</span><span class="sxs-lookup"><span data-stu-id="41977-127">Examples of how to use flows:</span></span> 
- <span data-ttu-id="41977-128">Opublikuj wiadomość w kanale Microsoft Teams, jeśli odświeżanie źródła danych nie powiedzie się.</span><span class="sxs-lookup"><span data-stu-id="41977-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="41977-129">Wyślij wiadomość e-mail do właścicieli danych, gdy zostanie przekroczony próg w segmencie.</span><span class="sxs-lookup"><span data-stu-id="41977-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
