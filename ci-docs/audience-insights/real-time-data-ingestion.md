---
title: Spożycie i ograniczenia dotyczące danych w czasie rzeczywistym
description: Ogólne informacje o możliwościach czasu rzeczywistego w statystykach odbiorców.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3c84cfe7441eb026c1fd45eda1f72421388d01d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598582"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="44d57-103">Pozyskiwanie danych w czasie rzeczywistym (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="44d57-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="44d57-104">Działająca niemal w czasie rzeczywistym funkcja umożliwia wyświetlenie, w ciągu zaledwie sekund, najnowszych interakcji między klientami a produktami lub usługami.</span><span class="sxs-lookup"><span data-stu-id="44d57-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="44d57-105">[W zaplanowanym odświeżaniu](system.md#schedule-tab) znajduje się wiele rekordów i przedstawiono wiele operacji złożonych.</span><span class="sxs-lookup"><span data-stu-id="44d57-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="44d57-106">Po pierwsze, dane są pobierane ze źródła danych.</span><span class="sxs-lookup"><span data-stu-id="44d57-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="44d57-107">Następnie dane są ujednolicane i wzbogacane o dodatkowe informacje.</span><span class="sxs-lookup"><span data-stu-id="44d57-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="44d57-108">Każdy przebieg tego procesu może potrwać od kilku minut do kilku godzin.</span><span class="sxs-lookup"><span data-stu-id="44d57-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="44d57-109">Funkcjonalność czasu rzeczywistego zapewnia natychmiastowe wykorzystanie danych do momentu, gdy kolejne zaplanowane odświeżanie pobierze te dane ze źródła danych.</span><span class="sxs-lookup"><span data-stu-id="44d57-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="44d57-110">Aktualizacje w czasie rzeczywistym mają czas wygaśnięcia, po którym nie będą już zastępować wartości ze źródła danych:</span><span class="sxs-lookup"><span data-stu-id="44d57-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="44d57-111">Aktualizacje profilu będą przechowywane przez 4 godziny</span><span class="sxs-lookup"><span data-stu-id="44d57-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="44d57-112">Działania będą przechowywane przez 30 dni</span><span class="sxs-lookup"><span data-stu-id="44d57-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="44d57-113">Te wartości są parametrami wywołania interfejsu API, które można zmienić.</span><span class="sxs-lookup"><span data-stu-id="44d57-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="44d57-114">Mają one na celu zagwarantowanie, że dane źródłowe pozostaną źródłem prawdy.</span><span class="sxs-lookup"><span data-stu-id="44d57-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="44d57-115">Jeśli chcesz, aby aktualizacje w czasie rzeczywistym były uwzględniane dłużej, musisz dodać je do źródła danych, aby były pobierane podczas następnego zaplanowanego odświeżania.</span><span class="sxs-lookup"><span data-stu-id="44d57-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="44d57-116">Aktualizacja w czasie rzeczywistym ujednoliconych pól profilu klienta</span><span class="sxs-lookup"><span data-stu-id="44d57-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="44d57-117">Zaktualizowane profile będą wyświetlane w widoku karty klientów lub innej wizualizacji w ciągu kilku sekund.</span><span class="sxs-lookup"><span data-stu-id="44d57-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="44d57-118">Ponieważ operacje w czasie rzeczywistym mają miejsce po zakończeniu ujednolicania danych, mają one zastosowanie wyłącznie w przypadku ujednoliconych profili klientów.</span><span class="sxs-lookup"><span data-stu-id="44d57-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="44d57-119">W rezultacie zmiany profilu w czasie rzeczywistym nie będą aktualizować miar, członkostwa w segmencie ani wzbogaceń.</span><span class="sxs-lookup"><span data-stu-id="44d57-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="44d57-120">Ograniczenia</span><span class="sxs-lookup"><span data-stu-id="44d57-120">Limitations</span></span>

- <span data-ttu-id="44d57-121">Profile klientów mogą być aktualizowane, ale nie można ich tworzyć ani usuwać.</span><span class="sxs-lookup"><span data-stu-id="44d57-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="44d57-122">Obecnie nie jest możliwe eksportowanie aktualizacji w czasie rzeczywistym do systemów zewnętrznych, takich jak Power BI.</span><span class="sxs-lookup"><span data-stu-id="44d57-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="44d57-123">Tworzenie działań w czasie rzeczywistym</span><span class="sxs-lookup"><span data-stu-id="44d57-123">Real-time creation of activities</span></span>

<span data-ttu-id="44d57-124">Interfejs API czasu rzeczywistego umożliwia publikowanie nowej aktywności z systemu źródłowego (indywidualny rekord źródłowy) w ujednoliconym profilu klienta.</span><span class="sxs-lookup"><span data-stu-id="44d57-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="44d57-125">Nowe działanie będzie dostępne jako ujednolicone działanie w tej osi czasu ujednoliconego profilu klienta w ciągu sekund.</span><span class="sxs-lookup"><span data-stu-id="44d57-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="44d57-126">Możesz zobaczyć oś czasu w widoku karty klienta lub dowolnej innej skonfigurowanej integracji osi czasu.</span><span class="sxs-lookup"><span data-stu-id="44d57-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="44d57-127">Działania są niezmienne.</span><span class="sxs-lookup"><span data-stu-id="44d57-127">Activities are immutable.</span></span> <span data-ttu-id="44d57-128">Nie zmienią się po utworzeniu.</span><span class="sxs-lookup"><span data-stu-id="44d57-128">They don't change once created.</span></span>
> - <span data-ttu-id="44d57-129">Obecnie segmenty i miary nie są aktualizowane w oparciu o nowe działanie.</span><span class="sxs-lookup"><span data-stu-id="44d57-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="44d57-130">Działania dodane wyłącznie za pośrednictwem interfejsu API w czasie rzeczywistym nie są częścią eksportów i nie będą widoczne w usłudze PowerBI.</span><span class="sxs-lookup"><span data-stu-id="44d57-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="44d57-131">Istnieją dwa sposoby łączenia się z interfejsem API w czasie rzeczywistym:</span><span class="sxs-lookup"><span data-stu-id="44d57-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="44d57-132">[pośrednio](#connect-via-the-dynamics-365-customer-insights-connector), za pomocą [łącznika Dynamics 365 Customer Insights](/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="44d57-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](/connectors/customerinsights/)</span></span>
- <span data-ttu-id="44d57-133">[bezpośrednio](#connect-directly-to-the-real-time-api), przy użyciu kodu</span><span class="sxs-lookup"><span data-stu-id="44d57-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="44d57-134">Oba sposoby wiążą się z poniższymi wymaganiami wstępnymi:</span><span class="sxs-lookup"><span data-stu-id="44d57-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="44d57-135">Środowisko Customer Insights</span><span class="sxs-lookup"><span data-stu-id="44d57-135">A Customer Insights environment</span></span>
- <span data-ttu-id="44d57-136">Ujednolicone profile klientów</span><span class="sxs-lookup"><span data-stu-id="44d57-136">Unified customer profiles</span></span>
- <span data-ttu-id="44d57-137">Działania skonfigurowane i wykonane</span><span class="sxs-lookup"><span data-stu-id="44d57-137">Activities configured and run</span></span>
- <span data-ttu-id="44d57-138">Uprawnienia współautora lub administratora do uwierzytelniania konta</span><span class="sxs-lookup"><span data-stu-id="44d57-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="44d57-139">Połącz za pośrednictwem łącznika Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="44d57-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="44d57-140">Interfejs API w czasie rzeczywistym może pobierać dane z dedykowanego łącznika Power Platform, [łącznik Dynamics 365 Customer Insights](/connectors/customerinsights/), bez konieczności pisania i wdrażania kodu.</span><span class="sxs-lookup"><span data-stu-id="44d57-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="44d57-141">Łącznik może wykonywać te same akcje w czasie rzeczywistym, co interfejs API.</span><span class="sxs-lookup"><span data-stu-id="44d57-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="44d57-142">Użytkownik musi mieć ważną licencję na łączniki Premium.</span><span class="sxs-lookup"><span data-stu-id="44d57-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="44d57-143">Aby uzyskać więcej informacji, zobacz [Licencje na Power Apps i Power Automate, często zadawane pytania](/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="44d57-143">For more information, see [Power Apps and Power Automate licensing FAQs](/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="44d57-144">Power Platform [Power Apps i/lub Power Automate](/connectors/)</span><span class="sxs-lookup"><span data-stu-id="44d57-144">Power Platform [Power Apps and/or Power Automate](/connectors/)</span></span>
- <span data-ttu-id="44d57-145">Azure [Logic Apps](/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="44d57-145">Azure [Logic Apps](/azure/connectors/apis-list)</span></span>

<span data-ttu-id="44d57-146">Szczegółowe informacje o tworzeniu przepływów można znaleźć w artykule [Dokumentacja Power Automate](/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="44d57-146">For details about creating flows, see the [Power Automate documentation](/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="44d57-147">Połącz bezpośrednio z interfejsem API w czasie rzeczywistym</span><span class="sxs-lookup"><span data-stu-id="44d57-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="44d57-148">Możesz korzystać z funkcji czasu rzeczywistego, tworząc własny potok i łącząc się bezpośrednio z interfejsem API czasu rzeczywistego.</span><span class="sxs-lookup"><span data-stu-id="44d57-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="44d57-149">Działanie można ogłosić w formacie systemu źródłowego lub w formacie UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="44d57-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="44d57-150">Pobierz format, tworząc wywołanie interfejsu API do /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="44d57-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="44d57-151">Szczegółowe informacje o tym interfejsie API, w tym parametry i odpowiedzi, można znaleźć w sekcji **EntityData** w [skorowidzu interfejsów API Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="44d57-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="44d57-152">Aby uzyskać więcej informacji, zobacz temat [Praca z interfejsami API Customer Insights](apis.md).</span><span class="sxs-lookup"><span data-stu-id="44d57-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="44d57-153">Informacje o sposobie korzystania z telemetrii w czasie rzeczywistym</span><span class="sxs-lookup"><span data-stu-id="44d57-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="44d57-154">Uzyskaj przegląd liczby żądań do interfejsu API czasu rzeczywistego i informacje o problemach, które może napotkać system.</span><span class="sxs-lookup"><span data-stu-id="44d57-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="44d57-155">Można uzyskać dostęp do [telemetryki w czasie rzeczywistym](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="44d57-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]