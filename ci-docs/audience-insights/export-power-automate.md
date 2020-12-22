---
title: Łącznik Power Automate | Microsoft Docs
description: Utwórz przepływy w Microsoft Power Automate z poziomu Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406548"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="6a7d3-103">Łącznik Power Automate (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="6a7d3-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="6a7d3-104">Wyzwalaj automatyczne występowanie określonych zdarzeń przy zmianie danych i zarządzaj bardziej skomplikowanymi przepływami bezpośrednio w [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="6a7d3-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="6a7d3-105">Wyzwalacze Power Automate</span><span class="sxs-lookup"><span data-stu-id="6a7d3-105">Power Automate triggers</span></span>

<span data-ttu-id="6a7d3-106">Użytkownik może korzystać z różnorodnych wyzwalaczy, które umożliwiają tworzenie przepływów w celu automatyzacji powtarzalnych zadań, takich jak powiadomienia lub bardziej zaawansowane akcje.</span><span class="sxs-lookup"><span data-stu-id="6a7d3-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="6a7d3-107">Wyzwól, kiedy odświeżanie źródła danych zakończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="6a7d3-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="6a7d3-108">Wyzwól, kiedy odświeżanie źródła danych zakończy się sukcesem.</span><span class="sxs-lookup"><span data-stu-id="6a7d3-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="6a7d3-109">Wyzwól, kiedy w segmencie nastąpi przekroczenie progu.</span><span class="sxs-lookup"><span data-stu-id="6a7d3-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="6a7d3-110">Wyzwalacz jest ograniczony do przekraczania progu.</span><span class="sxs-lookup"><span data-stu-id="6a7d3-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="6a7d3-111">Wyzwól, kiedy w miarze biznesowej nastąpi przekroczenie progu.</span><span class="sxs-lookup"><span data-stu-id="6a7d3-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="6a7d3-112">Wyzwalacz jest ograniczony do przekraczania progu.</span><span class="sxs-lookup"><span data-stu-id="6a7d3-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="6a7d3-113">Wyzwalaj, gdy zostanie ukończone pełne odświeżanie (źródła danych, segmenty, miary,...).</span><span class="sxs-lookup"><span data-stu-id="6a7d3-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="6a7d3-114">Wyzwalaj po zakończeniu odświeżania procesu unifikacji (mapowanie, dopasowanie, scalanie).</span><span class="sxs-lookup"><span data-stu-id="6a7d3-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="6a7d3-115">[Skonfiguruj wyzwalacze w Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="6a7d3-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="6a7d3-116">Akcje Power Automate</span><span class="sxs-lookup"><span data-stu-id="6a7d3-116">Power Automate actions</span></span>
<span data-ttu-id="6a7d3-117">Łącznik Power Automate dostarcza innych akcji niż dostępne wyzwalacze.</span><span class="sxs-lookup"><span data-stu-id="6a7d3-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="6a7d3-118">Aby uzyskać więcej informacji, zobacz [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="6a7d3-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="6a7d3-119">Tworzenie przepływu Power Automate w statystykach odbiorców</span><span class="sxs-lookup"><span data-stu-id="6a7d3-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="6a7d3-120">W analizach odbiorców przejdź do **Administrator** > **System**.</span><span class="sxs-lookup"><span data-stu-id="6a7d3-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="6a7d3-121">Na stronie **System** wybierz kartę **Status**.</span><span class="sxs-lookup"><span data-stu-id="6a7d3-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="6a7d3-122">W sekcji **Źródła danych** wybierz **Przepływy** i wybierz **Utwórz przepływ** z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="6a7d3-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6a7d3-123">![Łącznik Power Automate pokazujący akcję utworzenia przepływu](media/power-automate-connector-create-flow.png "Łącznik Power Automate pokazujący akcję utworzenia przepływu")</span><span class="sxs-lookup"><span data-stu-id="6a7d3-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="6a7d3-124">W Power Automate wybierz jeden z dostępnych wyzwalaczy, aby utworzyć preferowany przepływ.</span><span class="sxs-lookup"><span data-stu-id="6a7d3-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="6a7d3-125">W przypadku tworzenia pierwszego przepływu należy najpierw uwierzytelnić się przy użyciu łącznika Power Automate.</span><span class="sxs-lookup"><span data-stu-id="6a7d3-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
