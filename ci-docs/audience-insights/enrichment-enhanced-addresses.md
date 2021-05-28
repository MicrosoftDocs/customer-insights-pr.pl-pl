---
title: Wzbogacanie rozszerzonych adresów
description: Wzbogacaj i normalizuj informacje adresowe z profili klientów za pomocą modeli firmy Microsoft.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965591"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="bc88c-103">Wzbogacenie profili klientów za pomocą ulepszonych adresów</span><span class="sxs-lookup"><span data-stu-id="bc88c-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="bc88c-104">Adresy w Twoich danych mogą być nieustrukturyzowane, niekompletne lub nieprawidłowe.</span><span class="sxs-lookup"><span data-stu-id="bc88c-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="bc88c-105">Użyj modeli firmy Microsoft do normalizacji i wzbogacenia adresów do [formatu Common Data Model](/common-data-model/schema/core/applicationcommon/address) w celu lepszej dokładności i głębszej analizy.</span><span class="sxs-lookup"><span data-stu-id="bc88c-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="bc88c-106">Jak wzbogacamy adresy</span><span class="sxs-lookup"><span data-stu-id="bc88c-106">How we enhance addresses</span></span>

<span data-ttu-id="bc88c-107">Nasz model jest procesem dwuetapowym, który wzbogaca adres.</span><span class="sxs-lookup"><span data-stu-id="bc88c-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="bc88c-108">Najpierw analizuje adres, aby zidentyfikować jego składniki i umieszcza je w formacie ustrukturyzowanym.</span><span class="sxs-lookup"><span data-stu-id="bc88c-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="bc88c-109">Następnie używamy sztucznej inteligencji do poprawienia, ukończenia i ustandardyzowania wartości adresu.</span><span class="sxs-lookup"><span data-stu-id="bc88c-109">Then, we use artificial intelligence to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="bc88c-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="bc88c-110">Example</span></span>

<span data-ttu-id="bc88c-111">Informacje o adresie mogą mieć format niestandardowy i zawierać błędy pisowni.</span><span class="sxs-lookup"><span data-stu-id="bc88c-111">Address information might be in a non-standard format and contain spelling errors.</span></span> <span data-ttu-id="bc88c-112">Model może rozwiązać te problemy i utworzyć spójne adresy w ujednoliconych profilach klientów.</span><span class="sxs-lookup"><span data-stu-id="bc88c-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="bc88c-113">Ograniczenia</span><span class="sxs-lookup"><span data-stu-id="bc88c-113">Limitations</span></span>

<span data-ttu-id="bc88c-114">Funkcja ulepszania adresów współpracuje tylko z wartościami, które już istnieją w sprawdzanych danych adresów.</span><span class="sxs-lookup"><span data-stu-id="bc88c-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="bc88c-115">Model nie potrafi:</span><span class="sxs-lookup"><span data-stu-id="bc88c-115">The model doesn't:</span></span> 

1. <span data-ttu-id="bc88c-116">Zweryfikować, czy adres jest poprawny.</span><span class="sxs-lookup"><span data-stu-id="bc88c-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="bc88c-117">Sprawdzić, czy któraś z wartości, na przykład kodów pocztowy lub nazwa ulicy, jest prawidłowa.</span><span class="sxs-lookup"><span data-stu-id="bc88c-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="bc88c-118">Zmienić wartości, które nie są przez niego rozpoznawane.</span><span class="sxs-lookup"><span data-stu-id="bc88c-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="bc88c-119">W modelu do poprawiania adresów są używane techniki oparte na uczeniu maszynowym.</span><span class="sxs-lookup"><span data-stu-id="bc88c-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="bc88c-120">Stosujemy wysoki próg ufności, gdy model zmienia wartość wejściową, jak w przypadku każdego modelu opartego na ML, ale 100% dokładność nie jest gwarantowana.</span><span class="sxs-lookup"><span data-stu-id="bc88c-120">While we apply a high confidence threshold for when the model changes an input value, as with any ML-based model, 100% accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="bc88c-121">Obsługiwane kraje lub regiony</span><span class="sxs-lookup"><span data-stu-id="bc88c-121">Supported countries or regions</span></span>

<span data-ttu-id="bc88c-122">Obecnie oferujemy wzbogacenie adresów w tych krajach lub regionach:</span><span class="sxs-lookup"><span data-stu-id="bc88c-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="bc88c-123">Australia</span><span class="sxs-lookup"><span data-stu-id="bc88c-123">Australia</span></span>
- <span data-ttu-id="bc88c-124">Kanada</span><span class="sxs-lookup"><span data-stu-id="bc88c-124">Canada</span></span>
- <span data-ttu-id="bc88c-125">Zjednoczone Królestwo</span><span class="sxs-lookup"><span data-stu-id="bc88c-125">United Kingdom</span></span>
- <span data-ttu-id="bc88c-126">Stany Zjednoczone</span><span class="sxs-lookup"><span data-stu-id="bc88c-126">United States</span></span>

<span data-ttu-id="bc88c-127">Adresy muszą zawierać wartość kraju/regionu.</span><span class="sxs-lookup"><span data-stu-id="bc88c-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="bc88c-128">Nie są przetwarzane adresy krajów lub regionów, które nie są obsługiwane, ani adresy, które nie mają podanego kraju lub regionu.</span><span class="sxs-lookup"><span data-stu-id="bc88c-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="bc88c-129">Konfiguracja wzbogacania</span><span class="sxs-lookup"><span data-stu-id="bc88c-129">Configure the enrichment</span></span>

1. <span data-ttu-id="bc88c-130">Przejdź do **Dane** > **Wzbogacanie**.</span><span class="sxs-lookup"><span data-stu-id="bc88c-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="bc88c-131">Wybierz opcję **Wzbogać dane** na kafelku **Ulepszone adresy**.</span><span class="sxs-lookup"><span data-stu-id="bc88c-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Zrzut ekranu kafelka Ulepszone adresy.":::

1. <span data-ttu-id="bc88c-133">Wybierz **Zestaw danych klienta** i wybierz encję zawierającą adresy, które chcesz wzbogacić.</span><span class="sxs-lookup"><span data-stu-id="bc88c-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="bc88c-134">Można wybrać encję *Klient*, aby wzbogacić adresy we wszystkich profilach klientów lub wybrać encję segmentu, która wzbogaci adresy tylko w profilach klientów zawartych w tym segmencie.</span><span class="sxs-lookup"><span data-stu-id="bc88c-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="bc88c-135">Wybierz sposób formatowania adresów w Twoich zestawach danych.</span><span class="sxs-lookup"><span data-stu-id="bc88c-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="bc88c-136">Wybierz **Adres z pojedynczym atrybutem**, jeśli adresy w Twoich danych zawierają tylko jedno pole.</span><span class="sxs-lookup"><span data-stu-id="bc88c-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="bc88c-137">Wybierz **Adres z wieloma atrybutami**, jeśli adresy w Twoich danych zawierają więcej niż jedno pole.</span><span class="sxs-lookup"><span data-stu-id="bc88c-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="bc88c-138">Kraj/Region to pole obowiązkowe — zarówno w przypadku adresu o pojedynczym atrybucie, jak i adresu z wieloma atrybutami.</span><span class="sxs-lookup"><span data-stu-id="bc88c-138">Country/Region is mandatory in both single-attribute and multiple-attribute address.</span></span> <span data-ttu-id="bc88c-139">Adresy nie zawierające prawidłowych lub obsługiwanych wartości kraju/regionu nie zostaną wzbogacone</span><span class="sxs-lookup"><span data-stu-id="bc88c-139">Addresses that don't contain valid or supported country/region values won't be enriched</span></span>

1.  <span data-ttu-id="bc88c-140">Zamapuj pola adresu z ujednoliconej encji klienta.</span><span class="sxs-lookup"><span data-stu-id="bc88c-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Strona ulepszonego mapowania pola adresu.":::

1. <span data-ttu-id="bc88c-142">Wybierz **Dalej**, by zakończyć mapowanie pól.</span><span class="sxs-lookup"><span data-stu-id="bc88c-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="bc88c-143">Podaj nazwę dla wzbogacania oraz encję wyjściową.</span><span class="sxs-lookup"><span data-stu-id="bc88c-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="bc88c-144">Wybierz opcję **Zapisz wzbogacenie** po przejrzeniu wybranych opcji.</span><span class="sxs-lookup"><span data-stu-id="bc88c-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="bc88c-145">Wyniki wzbogacenia</span><span class="sxs-lookup"><span data-stu-id="bc88c-145">Enrichment results</span></span>

<span data-ttu-id="bc88c-146">Aby rozpocząć proces wzbogacania, wybierz **Uruchom** na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="bc88c-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="bc88c-147">Można również zezwolić, aby system automatycznie uruchamiał wzbogacenie w ramach [zaplanowanego odświeżenia](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bc88c-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bc88c-148">Czas przetwarzania zależy od rozmiaru danych klienta.</span><span class="sxs-lookup"><span data-stu-id="bc88c-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="bc88c-149">Po zakończeniu procesu wzbogacania można przejrzeć dane nowo wzbogacone profile klientów w **Moje wzbogacenia**.</span><span class="sxs-lookup"><span data-stu-id="bc88c-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="bc88c-150">Ponadto znajdziesz tam czas ostatniej aktualizacji i liczbę wzbogaconych profilów.</span><span class="sxs-lookup"><span data-stu-id="bc88c-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="bc88c-151">Aby uzyskać dostęp do szczegółowego widoku poszczególnych wzbogaconych profilów, należy zaznaczyć **Wyświetl wzbogacone dane**.</span><span class="sxs-lookup"><span data-stu-id="bc88c-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bc88c-152">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="bc88c-152">Next steps</span></span>

<span data-ttu-id="bc88c-153">Kompiluj na wierzchu wzbogaconych danych klientów.</span><span class="sxs-lookup"><span data-stu-id="bc88c-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="bc88c-154">Utwórz [segmenty](segments.md), [miary](measures.md), a nawet [eksportuj dane](export-destinations.md), aby zapewnić klientom spersonalizowane rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="bc88c-154">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
