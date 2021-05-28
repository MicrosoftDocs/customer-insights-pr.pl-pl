---
title: Sugerowane segmenty na podstawie aktywności.
description: Pozwól, aby uczenie maszynowe pomogło Ci znaleźć nowe i interesujące segmenty na podstawie aktywności klientów.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034101"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="b603a-103">Sugerowane segmenty na podstawie danych aktywności (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="b603a-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="b603a-104">Odkryj interesujące segmenty klientów w oparciu o dane dotyczące aktywności klientów, które są wprowadzane do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b603a-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="b603a-105">Przykładami danych dotyczących aktywności są transakcje, czas trwania rozmów z działem pomocy technicznej, zakupy lub zwroty.</span><span class="sxs-lookup"><span data-stu-id="b603a-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="b603a-106">Aby zasugerować segmenty, dane dotyczące aktywności są analizowane pod kątem powtarzalności, częstotliwości i wartości pieniężnej (lub czasu trwania).</span><span class="sxs-lookup"><span data-stu-id="b603a-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="b603a-107">Można też wygenerować [sugerowane segmenty, aby udoskonalić miarę lub lepiej zrozumieć, co ma jaki wpływ na atrybut](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="b603a-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Zakładka Sugerowane segmenty zawierająca propozycje segmentów dla segmentów opartych na aktywności i segmentów opartych na atrybutach.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="b603a-109">Dzielenie klientów na kategorie według działań</span><span class="sxs-lookup"><span data-stu-id="b603a-109">Categorize customers by activity</span></span>

<span data-ttu-id="b603a-110">Dzięki dostępnym w aplikacji Customer Insights [danym z aktywności](activities.md) można tworzyć sugestie reprezentujące grupy klientów:</span><span class="sxs-lookup"><span data-stu-id="b603a-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="b603a-111">najaktywniejsi klienci</span><span class="sxs-lookup"><span data-stu-id="b603a-111">most active customers</span></span> 
- <span data-ttu-id="b603a-112">klienci, którzy dokonali największej liczby zakupów</span><span class="sxs-lookup"><span data-stu-id="b603a-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="b603a-113">klienci, którzy wygenerowali największy przychód</span><span class="sxs-lookup"><span data-stu-id="b603a-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="b603a-114">klienci, którzy nie byli ostatnio aktywni</span><span class="sxs-lookup"><span data-stu-id="b603a-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="b603a-115">klienci, którzy często wchodzą w interakcje z Twoją firmą</span><span class="sxs-lookup"><span data-stu-id="b603a-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="b603a-116">Jeśli prowadzisz biznes detaliczny, możesz dowiedzieć się, którzy klienci generują największe przychody i nagrodzić ich kuponem.</span><span class="sxs-lookup"><span data-stu-id="b603a-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="b603a-117">Możesz też zidentyfikować okazjonalnych klientów i zaoferować im udział w programie nagród, dzięki któremu będą częściej odwiedzać Twoją firmę.</span><span class="sxs-lookup"><span data-stu-id="b603a-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="b603a-118">Jeśli prowadzisz firmę związaną z opieką zdrowotną i świadczysz publiczną opiekę zdrowotną, a Twoim celem jest zminimalizowanie wydatków dla indywidualnych pacjentów.</span><span class="sxs-lookup"><span data-stu-id="b603a-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="b603a-119">Sposobem na to może być zmniejszenie liczby powtarzających się wizyt poprzez zapewnienie najlepszej możliwej opieki podczas jak najmniejszej liczby wizyt.</span><span class="sxs-lookup"><span data-stu-id="b603a-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="b603a-120">W tym przypadku Twoim celem jest utrzymanie częstotliwości wizyt na niskim poziomie i zminimalizowanie powtarzających się kosztów dla pacjentów.</span><span class="sxs-lookup"><span data-stu-id="b603a-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="b603a-121">Lub można zidentyfikować segmenty pacjentów, którzy mają częste wizyty i wysokie koszty powtarzające się i analizować te przypadki, aby poprawić leczenie poszczególnych osób.</span><span class="sxs-lookup"><span data-stu-id="b603a-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="b603a-122">Wymagane dane</span><span class="sxs-lookup"><span data-stu-id="b603a-122">Required data</span></span>

<span data-ttu-id="b603a-123">Propozycje są generowane na podstawie wybranych danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="b603a-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="b603a-124">Profile klientów: Wszyscy klienci lub członkowie określonego segmentu.</span><span class="sxs-lookup"><span data-stu-id="b603a-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="b603a-125">Okres czasu: Ostatni miesiąc, ostatni rok lub dowolny niestandardowy przedział czasowy.</span><span class="sxs-lookup"><span data-stu-id="b603a-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="b603a-126">Typ aktywności: zakupy, transakcje detaliczne, transakcje online, sprawy związane z obsługą klienta, subskrypcje i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="b603a-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="b603a-127">Encja w Customer Insights, który zawiera dane dotyczące aktywności: Encja UnifiedActivity lub encja dla konkretnej aktywności.</span><span class="sxs-lookup"><span data-stu-id="b603a-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="b603a-128">Wymiary do uwzględnienia: Niedawność, częstotliwość lub wymiar pieniężny, w zależności od wymagań biznesowych.</span><span class="sxs-lookup"><span data-stu-id="b603a-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="b603a-129">Generuj sugerowane segmenty</span><span class="sxs-lookup"><span data-stu-id="b603a-129">Generate suggested segments</span></span>

1. <span data-ttu-id="b603a-130">Przejdź do **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="b603a-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="b603a-131">Wybierz kartę **Sugestie (wersja zapoznawcza)**.</span><span class="sxs-lookup"><span data-stu-id="b603a-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="b603a-132">Wybierz opcję **Znajdź nowe sugestie** i wybierz opcję **Zobacz lub przewiduj zachowanie klienta**.</span><span class="sxs-lookup"><span data-stu-id="b603a-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="b603a-133">Wybierz opcję **Start**, aby uruchomić tę opcję.</span><span class="sxs-lookup"><span data-stu-id="b603a-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Pierwszy krok kreatora konfiguracji sugerowanego segmentu na podstawie aktywności.":::

1. <span data-ttu-id="b603a-135">Podaj wymagane dane wejściowe i wybierz przycisk **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="b603a-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="b603a-136">Wybierz klientów: Uwzględnij wszystkich klientów lub określony segment.</span><span class="sxs-lookup"><span data-stu-id="b603a-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="b603a-137">Wybierz aktywność: Wybierz typ działania i jednostki opisujące działanie.</span><span class="sxs-lookup"><span data-stu-id="b603a-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="b603a-138">Preferencje: Ustaw okres czasu, który ma być brany pod uwagę, czynniki dla sugestii i mapuj atrybuty.</span><span class="sxs-lookup"><span data-stu-id="b603a-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="b603a-139">Przejrzyj dane wejściowe i wybierz opcję **Uruchom** w celu uruchomienia modelu i wygenerowania sugestii.</span><span class="sxs-lookup"><span data-stu-id="b603a-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="b603a-140">W zależności od liczby profili klientów i wybranych działań, może to zająć kilka minut.</span><span class="sxs-lookup"><span data-stu-id="b603a-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="b603a-141">Po wygenerowaniu propozycji, możesz je filtrować według wymiaru lub wartości, która najbardziej Cię interesuje.</span><span class="sxs-lookup"><span data-stu-id="b603a-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="b603a-142">Wyświetl szczegóły sugerowanego segmentu</span><span class="sxs-lookup"><span data-stu-id="b603a-142">View details of a suggested segment</span></span>

<span data-ttu-id="b603a-143">Po wygenerowaniu sugestii można je znaleźć w sekcji **Sugestie** > **Sugestie (wersja zapoznawcza)** w sekcji **Sugestie oparte na aktywności**.</span><span class="sxs-lookup"><span data-stu-id="b603a-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Rozszerzony panel boczny pokazujący szczegółowe dane sugerowanego segmentu.":::

<span data-ttu-id="b603a-145">Wybierz opcję **Zobacz sugestię** dla sugerowanego segmentu, aby wyświetlić szczegółowe informacje o tym segmencie.</span><span class="sxs-lookup"><span data-stu-id="b603a-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="b603a-146">W panelu bocznym znajdują się szczegóły, takie jak zakres każdego wymiaru w porównaniu z grupą docelową.</span><span class="sxs-lookup"><span data-stu-id="b603a-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="b603a-147">Podkreślona jest również liczba potencjalnych członków w danym segmencie i odpowiadający im procent wszystkich klientów.</span><span class="sxs-lookup"><span data-stu-id="b603a-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="b603a-148">Jeśli chcesz zachować sugestię jako segment, wybierz opcję **Utwórz segment**.</span><span class="sxs-lookup"><span data-stu-id="b603a-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="b603a-149">Zapisz sugestię jako segment</span><span class="sxs-lookup"><span data-stu-id="b603a-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="b603a-150">Przejdź do **Segmenty** > **Sugestie (wersja zapoznawcza)**.</span><span class="sxs-lookup"><span data-stu-id="b603a-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="b603a-151">Wybierz segment, który chcesz zapisać.</span><span class="sxs-lookup"><span data-stu-id="b603a-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="b603a-152">W okienku bocznym wybierz pozycję **Utwórz segment**.</span><span class="sxs-lookup"><span data-stu-id="b603a-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="b603a-153">Po zapisaniu segmentu będzie on dostępny na liście segmentów na karcie **Wszystkie segmenty**. Można teraz go [odświeżyć lub usunąć, tak jak każdy inny segment](segments.md).</span><span class="sxs-lookup"><span data-stu-id="b603a-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="b603a-154">Nie można edytować szczegółów segmentu.</span><span class="sxs-lookup"><span data-stu-id="b603a-154">You can't edit the segment details.</span></span> <span data-ttu-id="b603a-155">Można jednak zmienić kryteria wejściowe sugestii i generować różne sugestie.</span><span class="sxs-lookup"><span data-stu-id="b603a-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="b603a-156">Odświeżanie i edytowanie zestawu sugestii</span><span class="sxs-lookup"><span data-stu-id="b603a-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="b603a-157">Przejdź do sekcji **Sugestie** > **Sugestie (wersja zapoznawcza)** i poszukać segmentu w sekcji **Sugestie oparte na aktywności**.</span><span class="sxs-lookup"><span data-stu-id="b603a-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="b603a-158">Wybierz opcję **Odśwież sugestie**, aby odświeżyć sugestie, zachowując skonfigurowane atrybuty.</span><span class="sxs-lookup"><span data-stu-id="b603a-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="b603a-159">Można również wybrać opcję **Edytuj sugestie** w celu zmodyfikowania skonfigurowanych atrybutów.</span><span class="sxs-lookup"><span data-stu-id="b603a-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="b603a-160">System ponownie uruchomi proces, wygeneruje sugestie dotyczące segmentu na podstawie najnowszych danych i zastąpi bieżące sugestie.</span><span class="sxs-lookup"><span data-stu-id="b603a-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
