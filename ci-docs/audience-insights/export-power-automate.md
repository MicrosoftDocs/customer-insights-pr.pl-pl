---
title: Łącznik Power Automate | Microsoft Docs
description: Tworzenie przepływów w usłudze Microsoft Power Automate z poziomu aplikacji Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e973bb11b31c9e70b695ebec8aa2700fdaa5e44f
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597938"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="730ce-103">Łącznik Power Automate (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="730ce-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="730ce-104">Wyzwalaj automatyczne występowanie określonych zdarzeń przy zmianie danych i zarządzaj bardziej skomplikowanymi przepływami bezpośrednio w [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="730ce-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="730ce-105">Wyzwalacze Power Automate</span><span class="sxs-lookup"><span data-stu-id="730ce-105">Power Automate triggers</span></span>

<span data-ttu-id="730ce-106">Użyj wyzwalaczy do tworzenia przepływów w chmurze i automatyzacji powtarzalnych zadań, takich jak powiadomienia lub bardziej zaawansowane akcje.</span><span class="sxs-lookup"><span data-stu-id="730ce-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="730ce-107">Wyzwól, kiedy odświeżanie źródła danych zakończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="730ce-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="730ce-108">Wyzwól, kiedy odświeżanie źródła danych zakończy się sukcesem.</span><span class="sxs-lookup"><span data-stu-id="730ce-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="730ce-109">Wyzwól, kiedy w segmencie nastąpi przekroczenie progu.</span><span class="sxs-lookup"><span data-stu-id="730ce-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="730ce-110">Wyzwalacz jest ograniczony do przekraczania progu.</span><span class="sxs-lookup"><span data-stu-id="730ce-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="730ce-111">Wyzwól, kiedy w miarze biznesowej nastąpi przekroczenie progu.</span><span class="sxs-lookup"><span data-stu-id="730ce-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="730ce-112">Wyzwalacz jest ograniczony do przekraczania progu.</span><span class="sxs-lookup"><span data-stu-id="730ce-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="730ce-113">Wyzwalaj, gdy zostanie ukończone pełne odświeżanie (źródła danych, segmenty, miary,...).</span><span class="sxs-lookup"><span data-stu-id="730ce-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="730ce-114">Wyzwalaj po zakończeniu odświeżania procesu unifikacji (mapowanie, dopasowanie, scalanie).</span><span class="sxs-lookup"><span data-stu-id="730ce-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="730ce-115">[Skonfiguruj wyzwalacze w Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="730ce-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="730ce-116">Akcje Power Automate</span><span class="sxs-lookup"><span data-stu-id="730ce-116">Power Automate actions</span></span>
<span data-ttu-id="730ce-117">Łącznik Power Automate dostarcza innych akcji niż dostępne wyzwalacze.</span><span class="sxs-lookup"><span data-stu-id="730ce-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="730ce-118">Aby uzyskać więcej informacji, zobacz [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="730ce-118">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="730ce-119">Utwórz przepływ Power Automate</span><span class="sxs-lookup"><span data-stu-id="730ce-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="730ce-120">W analizach odbiorców przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.</span><span class="sxs-lookup"><span data-stu-id="730ce-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="730ce-121">Na kafelku **Power Automate** wybierz **Konfiguracja**.</span><span class="sxs-lookup"><span data-stu-id="730ce-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="730ce-122">Zostanie otwarty łącznik Customer Insights (wersja zapoznawcza) w usłudze Power Automate.</span><span class="sxs-lookup"><span data-stu-id="730ce-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="730ce-123">**Zaloguj się** do Power Automate.</span><span class="sxs-lookup"><span data-stu-id="730ce-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="730ce-124">Wybierz jeden z dostępnych przycisków i dodaj kolejne kroki do nowego przepływu.</span><span class="sxs-lookup"><span data-stu-id="730ce-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="730ce-125">Aby uzyskać więcej informacji, zobacz temat [Tworzenie przepływu w chmurze w Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="730ce-125">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="730ce-126">Przykłady korzystania z przepływów:</span><span class="sxs-lookup"><span data-stu-id="730ce-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="730ce-127">Opublikuj wiadomość w kanale Microsoft Teams, jeśli odświeżanie źródła danych nie powiedzie się.</span><span class="sxs-lookup"><span data-stu-id="730ce-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="730ce-128">Wyślij wiadomość e-mail do właścicieli danych, gdy zostanie przekroczony próg w segmencie.</span><span class="sxs-lookup"><span data-stu-id="730ce-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]