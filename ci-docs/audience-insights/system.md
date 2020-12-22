---
title: Konfiguracja systemu w statystykach odbiorców
description: Dowiedz się o ustawieniach systemu w możliwości analiz odbiorców w Dynamics 365 Customer Insights.
ms.date: 06/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: 7dd72e6512cd87ac70235d21667399298408db21
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406592"
---
# <a name="system-configuration"></a><span data-ttu-id="6e48a-103">Konfiguracja systemu</span><span class="sxs-lookup"><span data-stu-id="6e48a-103">System configuration</span></span>

<span data-ttu-id="6e48a-104">Strona **System** zawiera cztery karty: **Stan**, **Harmonogram**, **Informacje** i **Ogólne**.</span><span class="sxs-lookup"><span data-stu-id="6e48a-104">The **System** page includes four tabs: **Status**, **Schedule**, **About**, and **General**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6e48a-105">![Strona systemowa](media/system-tabs.png "Strona systemowa")</span><span class="sxs-lookup"><span data-stu-id="6e48a-105">![System page](media/system-tabs.png "System page")</span></span>

## <a name="status-tab"></a><span data-ttu-id="6e48a-106">Karta Stan</span><span class="sxs-lookup"><span data-stu-id="6e48a-106">Status tab</span></span>

<span data-ttu-id="6e48a-107">**Karta Stan** umożliwia śledzenie postępu przyjmowania danych, eksportu danych, i kilka ważnych procesów produktu.</span><span class="sxs-lookup"><span data-stu-id="6e48a-107">The **Status tab** lets you track the progress of data ingestion, data exports, and several important product processes.</span></span> <span data-ttu-id="6e48a-108">Przejrzyj informacje na tej karcie, aby zapewnić kompletność aktywnych procesów.</span><span class="sxs-lookup"><span data-stu-id="6e48a-108">Review the information on this tab to ensure the completeness of active processes.</span></span>

<span data-ttu-id="6e48a-109">Na tej karcie są zawarte tabele stanu dla **Źródeł danych**, **Procesów systemowych** i **Przygotowywania danych**.</span><span class="sxs-lookup"><span data-stu-id="6e48a-109">This tab includes status tables for **Data sources**, **System processes**, and **Data preparation**.</span></span> <span data-ttu-id="6e48a-110">Każda tabela śledzi **Nazwę** zadania, odpowiadającą mu encję, **Stan** ostatniego uruchomienia oraz datę **Ostatniej aktualizacji**.</span><span class="sxs-lookup"><span data-stu-id="6e48a-110">Each table tracks the **Name** of the task and its corresponding entity, the **Status** of its most recent run, and when it was **Last updated**.</span></span>

<span data-ttu-id="6e48a-111">Wyświetl szczegółowe informacje na temat kilku ostatnich uruchomień zadania wybierajac jego nazwę.</span><span class="sxs-lookup"><span data-stu-id="6e48a-111">View the details of the tasks' last several runs by selecting its name.</span></span>

### <a name="status-types"></a><span data-ttu-id="6e48a-112">Typy stanu</span><span class="sxs-lookup"><span data-stu-id="6e48a-112">Status types</span></span>

<span data-ttu-id="6e48a-113">Istnieje sześć typów stanu zadań.</span><span class="sxs-lookup"><span data-stu-id="6e48a-113">There are six types of status for tasks.</span></span> <span data-ttu-id="6e48a-114">Poniższe typy stanów są również widoczne na stronach *Dopasuj*, *Scal*, *Źródła danych*, *Segmenty*, *Miary*, *Wzbogacenie*, *Działania* i *Przewidywania*:</span><span class="sxs-lookup"><span data-stu-id="6e48a-114">The following status types also show on the *Match*, *Merge*, *Data sources*, *Segments*, *Measures*, *Enrichment*, *Activities*, and *Predictions* pages:</span></span>

- <span data-ttu-id="6e48a-115">**Przetwarzanie:** Zadanie jest w toku.</span><span class="sxs-lookup"><span data-stu-id="6e48a-115">**Processing:** Task is in progress.</span></span> <span data-ttu-id="6e48a-116">Stan może zmienić się na Powodzenie lub Niepowodzenie.</span><span class="sxs-lookup"><span data-stu-id="6e48a-116">The status can change to Successful or Failure.</span></span>
- <span data-ttu-id="6e48a-117">**Powodzenie:** Zadanie zostało ukończone pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="6e48a-117">**Successful:** Task completed successfully.</span></span>
- <span data-ttu-id="6e48a-118">**Pominięto:** Zadanie zostało pominięte.</span><span class="sxs-lookup"><span data-stu-id="6e48a-118">**Skipped:** Task got skipped.</span></span> <span data-ttu-id="6e48a-119">Co najmniej jeden z procesów podrzędnych, od którego zależy to zadanie, zakończył się niepowodzeniem lub został pominięty.</span><span class="sxs-lookup"><span data-stu-id="6e48a-119">One or more of the downstream processes this task depends on are failing or got skipped.</span></span>
- <span data-ttu-id="6e48a-120">**Niepowodzenie:** Przetwarzanie zadania nie powiodło się.</span><span class="sxs-lookup"><span data-stu-id="6e48a-120">**Failure:** Processing  of the task has failed.</span></span>
- <span data-ttu-id="6e48a-121">**Anulowano:** Przetwarzanie zostało anulowane przez użytkownika przed jego zakończeniem.</span><span class="sxs-lookup"><span data-stu-id="6e48a-121">**Canceled:** Processing was canceled by the user before it finished.</span></span>
- <span data-ttu-id="6e48a-122">**W kolejce:** Przetwarzanie jest kolejkowane i uruchomi się po zakończeniu wszystkich zadań podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="6e48a-122">**Queued:** Processing is queued and will start once all the downstream tasks are completed.</span></span> <span data-ttu-id="6e48a-123">Aby uzyskać więcej informacji, zobacz [Zasady odświeżania](#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="6e48a-123">For more information, see [Refresh policies](#refresh-policies).</span></span>

### <a name="refresh-policies"></a><span data-ttu-id="6e48a-124">Zasady odświeżania</span><span class="sxs-lookup"><span data-stu-id="6e48a-124">Refresh policies</span></span>

<span data-ttu-id="6e48a-125">Ta lista przedstawia zasady odświeżania dla każdego z głównych procesów:</span><span class="sxs-lookup"><span data-stu-id="6e48a-125">This list shows the refresh policies for each of the main processes:</span></span>

- <span data-ttu-id="6e48a-126">**Źródła danych:** Działają zgodnie ze [skonfigurowanym harmonogramem](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6e48a-126">**Data sources:** Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="6e48a-127">Nie jest uzależniony od innych procesów.</span><span class="sxs-lookup"><span data-stu-id="6e48a-127">Doesn't depend on any other process.</span></span> <span data-ttu-id="6e48a-128">Dopasowanie zależy od pomyślnego zakończenia tego procesu.</span><span class="sxs-lookup"><span data-stu-id="6e48a-128">Match depends on the successful completion of this process.</span></span>
- <span data-ttu-id="6e48a-129">**Dopasowanie:** Działa zgodnie ze [skonfigurowanym harmonogramem](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6e48a-129">**Match:** Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="6e48a-130">Zależy od sposobu przetwarzania źródeł danych użytych w definicji dopasowania.</span><span class="sxs-lookup"><span data-stu-id="6e48a-130">Depends on the processing of the data sources used in the match definition.</span></span> <span data-ttu-id="6e48a-131">Scalanie zależy od pomyślnego zakończenia tego procesu.</span><span class="sxs-lookup"><span data-stu-id="6e48a-131">Merge depends on the successful completion of this process.</span></span>
- <span data-ttu-id="6e48a-132">**Scalanie:** Działa zgodnie ze [skonfigurowanym harmonogramem](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6e48a-132">**Merge**: Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="6e48a-133">Zależy od pomyślnego zakończenia tego procesu dopasowywania.</span><span class="sxs-lookup"><span data-stu-id="6e48a-133">Depends on the completion of the match process.</span></span> <span data-ttu-id="6e48a-134">Segmenty, miary, wzbogacenia, wyszukiwania, działania, przewidywania i przygotowanie danych zależą od pomyślnego zakończenia procesu.</span><span class="sxs-lookup"><span data-stu-id="6e48a-134">Segments, measures, enrichment, search, activities, predictions, and data preparation depend on the successful completion of this process.</span></span>
- <span data-ttu-id="6e48a-135">**Segmenty**: Ręczne uruchamiane (jednorazowe odświeżanie) i zgodnie ze [skonfigurowanym harmonogramem](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6e48a-135">**Segments**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="6e48a-136">Zależy od procesu Scalanie.</span><span class="sxs-lookup"><span data-stu-id="6e48a-136">Depends on Merge.</span></span> <span data-ttu-id="6e48a-137">Wyniki analiz od jego przetwarzania.</span><span class="sxs-lookup"><span data-stu-id="6e48a-137">Insights depend on its processing.</span></span>
- <span data-ttu-id="6e48a-138">**Miary**: Ręczne uruchamiane (jednorazowe odświeżanie) i zgodnie ze [skonfigurowanym harmonogramem](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6e48a-138">**Measures**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="6e48a-139">Zależy od procesu Scalanie.</span><span class="sxs-lookup"><span data-stu-id="6e48a-139">Depends on Merge.</span></span>
- <span data-ttu-id="6e48a-140">**Działania**: Ręczne uruchamiane (jednorazowe odświeżanie) i zgodnie ze [skonfigurowanym harmonogramem](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6e48a-140">**Activities**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="6e48a-141">Zależy od procesu Scalanie.</span><span class="sxs-lookup"><span data-stu-id="6e48a-141">Depends on Merge.</span></span>
- <span data-ttu-id="6e48a-142">**Wzbogacanie**: Ręczne uruchamiane (jednorazowe odświeżanie) i zgodnie ze [skonfigurowanym harmonogramem](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6e48a-142">**Enrichment**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="6e48a-143">Zależy od procesu Scalanie.</span><span class="sxs-lookup"><span data-stu-id="6e48a-143">Depends on Merge.</span></span>
- <span data-ttu-id="6e48a-144">**Wyszukaj**: Ręczne uruchamiane (jednorazowe odświeżanie) i zgodnie ze [skonfigurowanym harmonogramem](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6e48a-144">**Search**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="6e48a-145">Zależy od procesu Scalanie.</span><span class="sxs-lookup"><span data-stu-id="6e48a-145">Depends on Merge.</span></span>
- <span data-ttu-id="6e48a-146">**Przygotowanie danych:** Działa zgodnie ze [skonfigurowanym harmonogramem](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6e48a-146">**Data preparation**: Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="6e48a-147">Zależy od procesu Scalanie.</span><span class="sxs-lookup"><span data-stu-id="6e48a-147">Depends on Merge.</span></span>
- <span data-ttu-id="6e48a-148">**Wyniki analiz**: Ręczne uruchamiane (jednorazowe odświeżanie) i zgodnie ze [skonfigurowanym harmonogramem](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6e48a-148">**Insights**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="6e48a-149">Zależy od segmentów.</span><span class="sxs-lookup"><span data-stu-id="6e48a-149">Depends on Segments.</span></span>

<span data-ttu-id="6e48a-150">Wybierz stan zadania, aby zobaczyć szczegółowe informacje o postępie w całego zadania.</span><span class="sxs-lookup"><span data-stu-id="6e48a-150">Select the status of a task to see the progress details of the entire job it was in.</span></span> <span data-ttu-id="6e48a-151">Powyższe zasady odświeżenia mogą pomóc w zrozumieniu, które można zrobić, aby zająć się zadaniem **Pominięte** lub **W kolejce**.</span><span class="sxs-lookup"><span data-stu-id="6e48a-151">The refresh policies above can help to understand what you can do to address a **Skipped** or **Queued** task.</span></span>

## <a name="schedule-tab"></a><span data-ttu-id="6e48a-152">Karta Harmonogram</span><span class="sxs-lookup"><span data-stu-id="6e48a-152">Schedule tab</span></span>

<span data-ttu-id="6e48a-153">Użyj karty **Harmonogram**, aby zaplanować automatyczne odświeżanie wszystkich [źródeł pobieranych danych](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="6e48a-153">Use the **Schedule** tab to schedule automatic refreshes of all your [ingested data sources](data-sources.md).</span></span> <span data-ttu-id="6e48a-154">Automatyczne odświeżanie ułatwia zagwarantowanie, że aktualizacje ze źródeł danych będą odzwierciedlone w ujednoliconych profilach klientów.</span><span class="sxs-lookup"><span data-stu-id="6e48a-154">Automatic refreshes help ensure that updates from your data sources are reflected in your unified customer profiles.</span></span>

1. <span data-ttu-id="6e48a-155">W analizach odbiorców wybierz **Administrator** > **System** i wybierz kartę **Harmonogram**.</span><span class="sxs-lookup"><span data-stu-id="6e48a-155">In audience insights, go to **Admin** > **System** and select the **Schedule** tab.</span></span>

2. <span data-ttu-id="6e48a-156">Stan domyślny dla planowanego odświeżenia to **Wyłączony**.</span><span class="sxs-lookup"><span data-stu-id="6e48a-156">The default state for the scheduled refresh is **Off**.</span></span> <span data-ttu-id="6e48a-157">Aby włączyć zaplanowane odświeżanie, należy zmienić przełącznik na górze ekranu na opcję **Włączony**.</span><span class="sxs-lookup"><span data-stu-id="6e48a-157">To enable scheduled refreshes, change the toggle at the top of the screen to **On**.</span></span>

3. <span data-ttu-id="6e48a-158">Należy wybrać kolejno pozycje **Co tydzień** (domyślne) i **Codziennie** odświeżanie.</span><span class="sxs-lookup"><span data-stu-id="6e48a-158">Choose between **Weekly** (default) and **Daily** refreshes.</span></span> <span data-ttu-id="6e48a-159">Jeśli zamierzasz zaplanować cotygodniowe odświeżenie, wybierz jeden lub kilka dni, kiedy chcesz uruchomić odświeżanie.</span><span class="sxs-lookup"><span data-stu-id="6e48a-159">If you intend to schedule weekly refreshes, select one or more days on which you want to run the refresh.</span></span>

4. <span data-ttu-id="6e48a-160">Ustaw **Strefę czasową**, a następnie użyj listy rozwijanej **Czas**, aby ustawić czas odświeżania.</span><span class="sxs-lookup"><span data-stu-id="6e48a-160">Set your **Time zone**, then use the **Time** dropdown to set your refresh timing.</span></span> <span data-ttu-id="6e48a-161">Kiedy skończysz, wybierz **Ustaw**.</span><span class="sxs-lookup"><span data-stu-id="6e48a-161">When you're finished, select **Set**.</span></span> <span data-ttu-id="6e48a-162">Jeśli chcesz zaplanować wiele odświeżań w ciągu jednego dnia, wybierz opcję **Dodaj inną godzinę**.</span><span class="sxs-lookup"><span data-stu-id="6e48a-162">If you'd like to schedule multiple refreshes in a single day, select **Add another time**.</span></span>

5. <span data-ttu-id="6e48a-163">Wybierz pozycję **Zapisz**, aby zastosować zmiany.</span><span class="sxs-lookup"><span data-stu-id="6e48a-163">Select **Save** to apply your changes.</span></span>

## <a name="about-tab"></a><span data-ttu-id="6e48a-164">Karta Informacje</span><span class="sxs-lookup"><span data-stu-id="6e48a-164">About tab</span></span>

<span data-ttu-id="6e48a-165">Karta **Informacje** zawiera **Wyświetlaną nazwę** organizacji, aktywny **Identyfikator środowiska**, **Region** i **Identyfikator sesji**.</span><span class="sxs-lookup"><span data-stu-id="6e48a-165">The **About** tab contains your organization's **Display name**, the active **Environment ID**, the **Region**, and your **Session ID**.</span></span> <span data-ttu-id="6e48a-166">Jeśli masz więcej niż jedno środowisko pracy, powinieneś nadać każdemu łatwą do zidentyfikowania nazwę wyświetlaną.</span><span class="sxs-lookup"><span data-stu-id="6e48a-166">If you have more than one work environment, you should give each an easily identifiable display name.</span></span>

## <a name="general-tab"></a><span data-ttu-id="6e48a-167">Karta Ogólne</span><span class="sxs-lookup"><span data-stu-id="6e48a-167">General tab</span></span>

<span data-ttu-id="6e48a-168">Na karcie **Ogólne** są dostępne dwie opcje, **Język** i **Format kraju/regionu**.</span><span class="sxs-lookup"><span data-stu-id="6e48a-168">There are two options on the **General** tab, **Language** and **Country/Region format**.</span></span>

<span data-ttu-id="6e48a-169">Aplikacja [obsługuje szereg języków](supported-languages.md).</span><span class="sxs-lookup"><span data-stu-id="6e48a-169">The app [supports a number of languages](supported-languages.md).</span></span> <span data-ttu-id="6e48a-170">Aby zmienić preferowany język, wybierz **Język** z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="6e48a-170">To change your preferred language, choose a **Language** from the dropdown.</span></span>

<span data-ttu-id="6e48a-171">Aby zmienić preferowany format dat, godzin i liczb, użyj listy rozwijanej **Format kraju/regionu**.</span><span class="sxs-lookup"><span data-stu-id="6e48a-171">To change your preferred formatting for dates, time, and numbers, use the **Country/Region format** dropdown.</span></span> <span data-ttu-id="6e48a-172">W obszarze tego pola jest wyświetlany podgląd formatowania.</span><span class="sxs-lookup"><span data-stu-id="6e48a-172">A formatting preview is displayed under this field.</span></span> <span data-ttu-id="6e48a-173">System automatycznie zasugeruje wybór, gdy wybierzesz nowy język.</span><span class="sxs-lookup"><span data-stu-id="6e48a-173">The system will automatically suggest a selection when you choose a new language.</span></span>

<span data-ttu-id="6e48a-174">Kliknij przycisk **Zapisz** i potwierdź wybór.</span><span class="sxs-lookup"><span data-stu-id="6e48a-174">Select **Save** to confirm your selections.</span></span>

## <a name="api-usage-tab"></a><span data-ttu-id="6e48a-175">Karta użycia interfejsu API</span><span class="sxs-lookup"><span data-stu-id="6e48a-175">API usage tab</span></span>

<span data-ttu-id="6e48a-176">Zapoznaj się ze szczegółowymi informacjami o wykorzystaniu interfejsów API w czasie rzeczywistym i zobacz, jakie zdarzenia wystąpiły w danym zakresie czasu.</span><span class="sxs-lookup"><span data-stu-id="6e48a-176">Find details about the real-time API usage and see which events happened in a given time range.</span></span> <span data-ttu-id="6e48a-177">Aby uzyskać więcej informacji, zobacz [Pozyskiwanie danych w czasie rzeczywistym](real-time-data-ingestion.md).</span><span class="sxs-lookup"><span data-stu-id="6e48a-177">For more information, see [Real-time data ingestion](real-time-data-ingestion.md).</span></span>