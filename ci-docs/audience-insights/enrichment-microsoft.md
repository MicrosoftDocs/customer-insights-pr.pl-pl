---
title: Wzbogać profile klientów danymi firmy Microsoft
description: Użyj własnościowych danych firmy Microsoft, aby wzbogacić dane klientów o funkcje marek i zainteresowań.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6f19033236190547f68d2b91ec6b32074bf7912a
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896615"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="cec64-103">Wzbogać profile klientów dzięki koligacjom marki i zainteresowań (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="cec64-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="cec64-104">Użyj własnościowych danych firmy Microsoft, aby wzbogacić dane klientów o sympatie do marek i zainteresowania.</span><span class="sxs-lookup"><span data-stu-id="cec64-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="cec64-105">Koligacje te są określane na podstawie danych pochodzących od osób o cechach demograficznych podobnych do cech klientów.</span><span class="sxs-lookup"><span data-stu-id="cec64-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="cec64-106">Informacje te ułatwiają zrozumienie i segmentację klientów na podstawie ich koligacji z określonymi markami i zainteresowaniami.</span><span class="sxs-lookup"><span data-stu-id="cec64-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="cec64-107">W statystykach odbiorców przejdź do **Dane** > **Wzbogacanie** do [konfiguruj i wyświetl wzbogacenia](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="cec64-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="cec64-108">Aby skonfigurować wzbogacanie koligacji marki, przejdź do karty **Odkryj** i wybierz **Wzbogacaj dane** na kafelku **Marki**.</span><span class="sxs-lookup"><span data-stu-id="cec64-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="cec64-109">Aby skonfigurować wzbogacanie koligacji zainteresowań, przejdź do karty **Odkryj** i wybierz **Wzbogacaj dane** na kafelku **Zainteresowania**.</span><span class="sxs-lookup"><span data-stu-id="cec64-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cec64-110">![Kafelki Marki i Zainteresowania](media/BrandsInterest-tile-Hub.png "Kafelki Marki i Zainteresowania")</span><span class="sxs-lookup"><span data-stu-id="cec64-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="cec64-111">Jak określa się sympatie</span><span class="sxs-lookup"><span data-stu-id="cec64-111">How we determine affinities</span></span>

<span data-ttu-id="cec64-112">Microsoft korzysta z danych wyszukiwania dostępnych w trybie online w celu sympatii dla marek i zainteresowań w różnych segmentach demograficznych (zdefiniowanych według wieku, płci lub lokalizacji).</span><span class="sxs-lookup"><span data-stu-id="cec64-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="cec64-113">Wielkość wyszukiwania online dla marki lub zainteresowań określa stopień sympatii ze strony segmentu demograficznego, w porównaniu z innymi segmentami, dla tej marki lub zainteresowania.</span><span class="sxs-lookup"><span data-stu-id="cec64-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span> <span data-ttu-id="cec64-114">marka lub zainteresowania.</span><span class="sxs-lookup"><span data-stu-id="cec64-114">brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="cec64-115">Poziom sympatii i wynik</span><span class="sxs-lookup"><span data-stu-id="cec64-115">Affinity level and score</span></span>

<span data-ttu-id="cec64-116">Na każdym wzbogaconym profilu klienta podajemy dwie powiązane wartości - poziom podobieństwa i wynik podobieństwa.</span><span class="sxs-lookup"><span data-stu-id="cec64-116">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="cec64-117">Te wartości pomagają określić, jak silne jest podobieństwo segmentu demograficznego tego profilu, marki lub zainteresowań w porównaniu z innymi segmentami demograficznymi.</span><span class="sxs-lookup"><span data-stu-id="cec64-117">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="cec64-118">*Poziom sympatii* składa się z czterech poziomów, a *wynik sympatii* jest obliczany w skali 100-punktowej, mapowej na poziomy a automatycznie.</span><span class="sxs-lookup"><span data-stu-id="cec64-118">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="cec64-119">Poziom sympatii</span><span class="sxs-lookup"><span data-stu-id="cec64-119">Affinity level</span></span> |<span data-ttu-id="cec64-120">Wynik sympatii</span><span class="sxs-lookup"><span data-stu-id="cec64-120">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="cec64-121">Bardzo wysoko</span><span class="sxs-lookup"><span data-stu-id="cec64-121">Very high</span></span>     | <span data-ttu-id="cec64-122">85–100</span><span class="sxs-lookup"><span data-stu-id="cec64-122">85-100</span></span>       |
|<span data-ttu-id="cec64-123">Wysoka</span><span class="sxs-lookup"><span data-stu-id="cec64-123">High</span></span>     | <span data-ttu-id="cec64-124">70–84</span><span class="sxs-lookup"><span data-stu-id="cec64-124">70-84</span></span>        |
|<span data-ttu-id="cec64-125">Średnie</span><span class="sxs-lookup"><span data-stu-id="cec64-125">Medium</span></span>     | <span data-ttu-id="cec64-126">35–69</span><span class="sxs-lookup"><span data-stu-id="cec64-126">35-69</span></span>        |
|<span data-ttu-id="cec64-127">Niska</span><span class="sxs-lookup"><span data-stu-id="cec64-127">Low</span></span>     | <span data-ttu-id="cec64-128">1–34</span><span class="sxs-lookup"><span data-stu-id="cec64-128">1-34</span></span>        |

<span data-ttu-id="cec64-129">W zależności od stopnia szczegółowości pomiaru podobieństwa można użyć poziomu sympatii lub wyniku.</span><span class="sxs-lookup"><span data-stu-id="cec64-129">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="cec64-130">Wynik a ponadto pozwala na dokładniejsze kontrolowanie danych.</span><span class="sxs-lookup"><span data-stu-id="cec64-130">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="cec64-131">Obsługiwane kraje/regiony</span><span class="sxs-lookup"><span data-stu-id="cec64-131">Supported countries/regions</span></span>

<span data-ttu-id="cec64-132">Obecnie obsługujemy następujące opcje kraju/regionu: Australia, Kanada (angielski), Francja, Niemcy, Zjednoczone Królestwo lub Stany Zjednoczone (angielski).</span><span class="sxs-lookup"><span data-stu-id="cec64-132">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="cec64-133">Aby wybrać kraj, należy otworzyć **Wzbogacenie marek** lub **Wzbogacenie zainteresowań** a następnie wybrać **Zmień** obok **Kraj/region**.</span><span class="sxs-lookup"><span data-stu-id="cec64-133">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="cec64-134">W okienku **Ustawienia kraju/regionu** wybierz jedną z opcji i wybierz **Zastosuj**.</span><span class="sxs-lookup"><span data-stu-id="cec64-134">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="cec64-135">Implikacje dotyczące wyboru kraju</span><span class="sxs-lookup"><span data-stu-id="cec64-135">Implications related to country selection</span></span>

- <span data-ttu-id="cec64-136">Podczas [wybierania własnej marki](#define-your-brands-or-interests) system oferuje sugestie dotyczące wybranego kraju lub regionu.</span><span class="sxs-lookup"><span data-stu-id="cec64-136">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="cec64-137">[Wybierając branżę](#define-your-brands-or-interests), otrzymasz najbardziej odpowiednie marki lub zainteresowania w oparciu o wybrany kraj lub region.</span><span class="sxs-lookup"><span data-stu-id="cec64-137">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="cec64-138">Podczas [wzbogacania profilów](#refresh-enrichment) wzbogacimy wszystkie profile klientów, dla których pobierzemy dane o wybranych profilach zainteresowaniach.</span><span class="sxs-lookup"><span data-stu-id="cec64-138">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="cec64-139">Obejmuje profile, które nie znajdują się w wybranym kraju lub regionie.</span><span class="sxs-lookup"><span data-stu-id="cec64-139">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="cec64-140">Na przykład jeśli wybrano Niemcy, wzbogacimy profile zlokalizowane w Stanach Zjednoczonych, jeśli w Stanach Zjednoczonych dostępne są dane dotyczące wybranych źródeł i zainteresowań.</span><span class="sxs-lookup"><span data-stu-id="cec64-140">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="cec64-141">Konfigurowanie wzbogacenia</span><span class="sxs-lookup"><span data-stu-id="cec64-141">Configure Enrichment</span></span>

<span data-ttu-id="cec64-142">Porady pomagają w konfigurowaniu wzbogacania.</span><span class="sxs-lookup"><span data-stu-id="cec64-142">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="cec64-143">Zdefiniuj swoje marki i zainteresowania</span><span class="sxs-lookup"><span data-stu-id="cec64-143">Define your brands or interests</span></span>

<span data-ttu-id="cec64-144">Wybierz jedną z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="cec64-144">Select one of the following options:</span></span>

- <span data-ttu-id="cec64-145">**Branża**: System identyfikuje najlepsze marki lub zainteresowania istotne dla Twojej branży i wzmacnia nimi dane klientów.</span><span class="sxs-lookup"><span data-stu-id="cec64-145">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="cec64-146">**Wybierz własne**: Wybierz maksymalnie pięć elementów z listy marek lub zainteresowań, które są najbardziej interesujące dla Twojej organizacji.</span><span class="sxs-lookup"><span data-stu-id="cec64-146">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="cec64-147">Aby dodać markę lub zainteresowanie, wprowadź ją w obszarze wprowadzania, aby uzyskać sugestie na podstawie pasujących terminów.</span><span class="sxs-lookup"><span data-stu-id="cec64-147">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="cec64-148">Jeśli nie ukazujemy szukanej marki lub zainteresowania, wyślij nam opinię przy użyciu łącza **Sugeruj**.</span><span class="sxs-lookup"><span data-stu-id="cec64-148">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="cec64-149">Przejrzyj preferencje wzbogacania</span><span class="sxs-lookup"><span data-stu-id="cec64-149">Review enrichment preferences</span></span>

<span data-ttu-id="cec64-150">Przejrzyj domyślne preferencje wzbogacania i zaktualizuj je w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="cec64-150">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Zrzut ekranu okna preferencji dotyczących wzbogacenia.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="cec64-152">Wybierz encję do wzbogacenia</span><span class="sxs-lookup"><span data-stu-id="cec64-152">Select entity to enrich</span></span>

<span data-ttu-id="cec64-153">Wybierz **Obiekt wzbogacany** i wybierz zestaw danych, który chcesz wzbogacić danymi firmy z firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cec64-153">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="cec64-154">Można wybrać encję Klient, aby wzbogacić wszystkie profile klientów, lub wybierz jednostkę segmentu, aby wzbogacić tylko profile klientów zawarte w tym segmencie.</span><span class="sxs-lookup"><span data-stu-id="cec64-154">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="cec64-155">Zamapuj swoje pola</span><span class="sxs-lookup"><span data-stu-id="cec64-155">Map your fields</span></span>

<span data-ttu-id="cec64-156">Mapuj pola z ujednoliconej encji klienta, aby zdefiniować segment demograficzny, którego system ma używać do wzbogacania danych klientów.</span><span class="sxs-lookup"><span data-stu-id="cec64-156">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="cec64-157">Zamapuj kraj / region i przynajmniej atrybuty Data urodzenia lub Płeć.</span><span class="sxs-lookup"><span data-stu-id="cec64-157">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="cec64-158">Ponadto musisz zamapować co najmniej jeden z następujących atrybutów: Miejscowość (i Województwo) albo Kod pocztowy.</span><span class="sxs-lookup"><span data-stu-id="cec64-158">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="cec64-159">Wybierz **Edytuj**, aby zdefiniować mapowanie pól i wybierz **Zastosuj** po zakończeniu.</span><span class="sxs-lookup"><span data-stu-id="cec64-159">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="cec64-160">Wybierz **Zapisz**, aby zakończyć mapowanie pola.</span><span class="sxs-lookup"><span data-stu-id="cec64-160">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="cec64-161">Obsługiwane są następujące formaty i wartości, wielkość liter w przypadku wartości nie ma znaczenia:</span><span class="sxs-lookup"><span data-stu-id="cec64-161">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="cec64-162">**Data urodzenia**: Zaleca się, aby data urodzenia była konwertowana na typ DateTime podczas pozyskiwania danych.</span><span class="sxs-lookup"><span data-stu-id="cec64-162">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="cec64-163">Można też użyć ciągu w formacie [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "rrrr-mm-dd" lub "RRRR-MM-ddTHH:mm:SSZ".</span><span class="sxs-lookup"><span data-stu-id="cec64-163">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="cec64-164">**Płeć**: męska, żeńska, nieznane</span><span class="sxs-lookup"><span data-stu-id="cec64-164">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="cec64-165">**Kod pocztowy**: Pięciocyfrowe kody pocztowe dla Stanów Zjednoczonych, standardowy kod pocztowy wszędzie indziej</span><span class="sxs-lookup"><span data-stu-id="cec64-165">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="cec64-166">**Miasto**: Nazwa miasta w języku angielskim</span><span class="sxs-lookup"><span data-stu-id="cec64-166">**City**: City name in English</span></span>
- <span data-ttu-id="cec64-167">**Stan/Prowincja**: Dwuliterowy skrót dla Stanów Zjednoczonych i Kanady.</span><span class="sxs-lookup"><span data-stu-id="cec64-167">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="cec64-168">Dwuliterowy lub trzyliterowy skrót dla Australii.</span><span class="sxs-lookup"><span data-stu-id="cec64-168">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="cec64-169">Nie dotyczy Francji, Niemiec lub Wielkiej Brytanii.</span><span class="sxs-lookup"><span data-stu-id="cec64-169">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="cec64-170">**Kraj/region**:</span><span class="sxs-lookup"><span data-stu-id="cec64-170">**Country/Region**:</span></span>

  - <span data-ttu-id="cec64-171">US: Stany Zjednoczone Ameryki, Stany Zjednoczone, USA, US i Ameryka</span><span class="sxs-lookup"><span data-stu-id="cec64-171">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="cec64-172">CA: Kanada, CA</span><span class="sxs-lookup"><span data-stu-id="cec64-172">CA: Canada, CA</span></span>
  - <span data-ttu-id="cec64-173">GB: Zjednoczone Królestwo, UK, Wielka Brytania, GB, Zjednoczone Królestwo Wielkiej Brytanii i Irlandii Północnej, Zjednoczone Królestwo Wielkiej Brytanii</span><span class="sxs-lookup"><span data-stu-id="cec64-173">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="cec64-174">AU: Australia, AU, Związek Australijski</span><span class="sxs-lookup"><span data-stu-id="cec64-174">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="cec64-175">FR: Francja, FR, Republika Francuska</span><span class="sxs-lookup"><span data-stu-id="cec64-175">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="cec64-176">DE: Niemcy, niemiecki, Deutschland, Allemagne, DE, Republika Federalna Niemiec, Republika Niemiec</span><span class="sxs-lookup"><span data-stu-id="cec64-176">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="cec64-177">Przeglądanie i nazywanie wzbogacania</span><span class="sxs-lookup"><span data-stu-id="cec64-177">Review and name the enrichment</span></span>

<span data-ttu-id="cec64-178">Na koniec można przejrzeć te informacje i podać nazwę dla wzbogacania.</span><span class="sxs-lookup"><span data-stu-id="cec64-178">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Strona przeglądania i nazywania zainteresowań.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="cec64-180">Odświeżenie wzbogacenia</span><span class="sxs-lookup"><span data-stu-id="cec64-180">Refresh enrichment</span></span>

<span data-ttu-id="cec64-181">Należy uruchomić wzbogacenie po skonfigurowaniu marek, zainteresowań i mapowania pól dla demografii.</span><span class="sxs-lookup"><span data-stu-id="cec64-181">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="cec64-182">Aby rozpocząć proces, wybierz **Uruchom** na stronie konfiguracji marki lub zainteresowań.</span><span class="sxs-lookup"><span data-stu-id="cec64-182">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="cec64-183">Oprócz tego można zezwolić systemowi na automatyczne uruchamianie wzbogacenia w ramach zaplanowanego odświeżenia.</span><span class="sxs-lookup"><span data-stu-id="cec64-183">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="cec64-184">W zależności od rozmiaru danych klientów może upłynąć kilka minut, aby można było wykonać wzbogacanie systemu.</span><span class="sxs-lookup"><span data-stu-id="cec64-184">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="cec64-185">Istnieje [sześć typów stanu](system.md#status-types) zadań/procesów.</span><span class="sxs-lookup"><span data-stu-id="cec64-185">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="cec64-186">Ponadto większość procesów [zależy od innych procesów podrzędnych](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="cec64-186">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="cec64-187">Istnieje możliwość wybrania stanu procesu w celu wyświetlenia szczegółowych informacji o postępie w całym zadaniu.</span><span class="sxs-lookup"><span data-stu-id="cec64-187">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="cec64-188">Po wybraniu opcji **Zobacz szczegółowe informacje** dla jednego z zadań zadania, można znaleźć więcej informacji: czas przetwarzania, Data ostatniego przetwarzania oraz wszystkie błędy i ostrzeżenia skojarzone z zadaniem.</span><span class="sxs-lookup"><span data-stu-id="cec64-188">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="cec64-189">Wyniki wzbogacenia</span><span class="sxs-lookup"><span data-stu-id="cec64-189">Enrichment results</span></span>

<span data-ttu-id="cec64-190">Po uruchomieniu procesu wzbogacenia przejdź do **Moje wzbogacenia**, aby przejrzeć całkowitą liczbę wzbogaconych klientów i podział marek lub zainteresowań we wzbogaconych profilach klientów.</span><span class="sxs-lookup"><span data-stu-id="cec64-190">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Podgląd wyników po uruchomieniu procesu wzbogacania":::

<span data-ttu-id="cec64-192">Przejrz wzbogacone dane, zaznaczając **Przejrzyj wzbogacone dane** na wykresie.</span><span class="sxs-lookup"><span data-stu-id="cec64-192">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="cec64-193">Wzbogacone dane dla marki przechodzą do encji **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="cec64-193">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="cec64-194">Dane dotyczące zainteresowań znajdują się w encji **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="cec64-194">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="cec64-195">Te encje są również wymienione w grupie **Wzbogacanie** w **Dane** > **Encje**.</span><span class="sxs-lookup"><span data-stu-id="cec64-195">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="cec64-196">Zobacz dane dotyczące wzbogacenia na karcie klienta</span><span class="sxs-lookup"><span data-stu-id="cec64-196">See enrichment data on the customer card</span></span>

<span data-ttu-id="cec64-197">Koligacje marki i zainteresowań można również wyświetlać na kartach poszczególnych klientów.</span><span class="sxs-lookup"><span data-stu-id="cec64-197">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="cec64-198">Przejdź do **Klienci** i wybierz profil klienta.</span><span class="sxs-lookup"><span data-stu-id="cec64-198">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="cec64-199">Na karcie klienta znajdziesz wykresy dotyczące marek lub zainteresowań, z którymi ludzie z danego profilu demograficznego mogą mieć powiązania.</span><span class="sxs-lookup"><span data-stu-id="cec64-199">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Karta klienta ze wzbogaconymi danymi":::

## <a name="next-steps"></a><span data-ttu-id="cec64-201">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="cec64-201">Next steps</span></span>

<span data-ttu-id="cec64-202">Kompiluj na wierzchu wzbogaconych danych klientów.</span><span class="sxs-lookup"><span data-stu-id="cec64-202">Build on top of your enriched customer data.</span></span> <span data-ttu-id="cec64-203">Utwórz [Segmenty](segments.md), [Miary](measures.md), a nawet [eksportuj dane](export-destinations.md), aby zapewnić klientom spersonalizowane rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="cec64-203">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
