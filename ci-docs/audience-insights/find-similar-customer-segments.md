---
title: Znajdź podobnych klientów z AI
description: Znajdź segmenty podobnych klientów za pomocą sztucznej inteligencji.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 8cdec4edd599b0249fcf144b5e5c0124504e1e14
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406580"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="443db-103">Podobni klienci (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="443db-103">Similar Customers (preview)</span></span>

<span data-ttu-id="443db-104">Dzięki tej funkcji można znaleźć podobnych klientów w bazie klientów, korzystając z sztucznej inteligencji.</span><span class="sxs-lookup"><span data-stu-id="443db-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="443db-105">Aby można było korzystać z tej funkcji, musi być utworzony co najmniej jeden segment.</span><span class="sxs-lookup"><span data-stu-id="443db-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="443db-106">Rozwijanie kryteriów istniejącego segmentu ułatwia znajdowanie klientów podobnych do tego segmentu.</span><span class="sxs-lookup"><span data-stu-id="443db-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="443db-107">*Znajdź podobnych klientów* używa zautomatyzowanego narzędzia do oceniania danych i tworzenia prognoz na podstawie tych danych i w może służyć jako metoda profilowania, ponieważ ten termin jest definiowany przez Ogólne rozporządzenie o ochronie danych ("GDPR").</span><span class="sxs-lookup"><span data-stu-id="443db-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="443db-108">Korzystanie z tej funkcji przez klienta do przetwarzania danych może podlegać RODO lub innym prawom lub rozporządzeniom.</span><span class="sxs-lookup"><span data-stu-id="443db-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="443db-109">Użytkownik ma obowiązek zagwarantować, że użytkowanie Dynamics 365 Customer Insights wraz z przewidywaniami jest zgodne ze wszystkimi obowiązującymi przepisami prawnymi i wykonawczymi, w tym prawa związane z ochroną prywatności, danymi osobowymi, danymi biometrycznymi, ochroną danych i poufność informacji.</span><span class="sxs-lookup"><span data-stu-id="443db-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="443db-110">Znajdowanie podobnych klientów</span><span class="sxs-lookup"><span data-stu-id="443db-110">Finding similar customers</span></span>

1. <span data-ttu-id="443db-111">W statystykach odbiorców przejdź do **Segmenty** i wybierz segment, na którym chcesz oprzeć nowy segment.</span><span class="sxs-lookup"><span data-stu-id="443db-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="443db-112">To Twój *segment źródłowy*.</span><span class="sxs-lookup"><span data-stu-id="443db-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="443db-113">Na pasku akcji wybierz **Znajdź podobnych klientów**.</span><span class="sxs-lookup"><span data-stu-id="443db-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="443db-114">Przejrzyj sugerowaną nazwę nowego segmentu i w razie potrzeby zmodyfikuj ją.</span><span class="sxs-lookup"><span data-stu-id="443db-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="443db-115">Przejrzyj pola definiujące nowy segment.</span><span class="sxs-lookup"><span data-stu-id="443db-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="443db-116">Te pola określają podstawę, z poziomu której system ma próbować znaleźć klientów podobnych do segmentu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="443db-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="443db-117">Domyślnie system wybierze pola zalecane.</span><span class="sxs-lookup"><span data-stu-id="443db-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="443db-118">Pola, które mogą znacznie zmniejszyć wydajność modelu, są automatycznie wykluczane:</span><span class="sxs-lookup"><span data-stu-id="443db-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="443db-119">Pola o następujących typach danych: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="443db-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="443db-120">Pola z kardynalnością (liczbą elementów w polu) mniejszą niż 2 lub większą niż 30</span><span class="sxs-lookup"><span data-stu-id="443db-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="443db-121">Wybierz, jeśli chcesz uwzględnić **Wszystkich klientów** lub tylko klientów z **Określonego istniejącego segmentu** w nowym segmencie.</span><span class="sxs-lookup"><span data-stu-id="443db-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="443db-122">Wyłącz klientów w segmencie źródłowym, zaznaczając pole wyboru **Wyklucz wszystkie osoby w segmencie źródłowym**.</span><span class="sxs-lookup"><span data-stu-id="443db-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="443db-123">Domyślnie system sugeruje uwzględnienie tylko 20% wielkości odbiorców docelowych w danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="443db-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="443db-124">Edytuj ten próg zależnie od potrzeb.</span><span class="sxs-lookup"><span data-stu-id="443db-124">Edit this threshold as needed.</span></span> <span data-ttu-id="443db-125">Zwiększenie progu zmniejszy dokładność.</span><span class="sxs-lookup"><span data-stu-id="443db-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="443db-126">Wybierz **Uruchom** u dołu strony, aby rozpocząć zadanie klasyfikacji dwuelementowej (metoda uczenia maszynowego), które analizuje zestaw danych.</span><span class="sxs-lookup"><span data-stu-id="443db-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="443db-127">Wyświetl podobny segment</span><span class="sxs-lookup"><span data-stu-id="443db-127">View the similar segment</span></span>

<span data-ttu-id="443db-128">Po przetworzeniu podobnego segmentu znajdziesz nowy segment na stronie **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="443db-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="443db-129">![Segment Podobni klienci](media/expanded-segment.png "Segment Podobni klienci")</span><span class="sxs-lookup"><span data-stu-id="443db-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="443db-130">Wybierz **Widok** na pasku akcji, aby otworzyć Szczegóły segmentu.</span><span class="sxs-lookup"><span data-stu-id="443db-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="443db-131">Ten widok zawiera informacje na temat rozkładu wyniku dla [wyników podobieństwa](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="443db-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="443db-132">Wartości wyników podobieństwa są również dostępne w **Podglądzie elementów członkowskich segmentu**.</span><span class="sxs-lookup"><span data-stu-id="443db-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="443db-133">Użyj wyniku podobnego segmentu</span><span class="sxs-lookup"><span data-stu-id="443db-133">Use the output of a similar segment</span></span>

<span data-ttu-id="443db-134">Użytkownik może [pracować z danymi wyjściowymi podobnego segmentu](segments.md) tak samo jak z innymi segmentami.</span><span class="sxs-lookup"><span data-stu-id="443db-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="443db-135">Można na przykład wyeksportować segment lub utworzyć miarę.</span><span class="sxs-lookup"><span data-stu-id="443db-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="443db-136">Odśwież i edytuj podobny segment</span><span class="sxs-lookup"><span data-stu-id="443db-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="443db-137">Aby odświeżyć podobny segment, wybierz go na stronie **Segmenty** i wybierz **Odśwież** na pasku akcji.</span><span class="sxs-lookup"><span data-stu-id="443db-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="443db-138">Edytowanie podobnego segmentu spowoduje przetwarzanie danych.</span><span class="sxs-lookup"><span data-stu-id="443db-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="443db-139">Utworzony wcześniej segment jest aktualizowany odświeżonymi danymi.</span><span class="sxs-lookup"><span data-stu-id="443db-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="443db-140">Aby edytować podobny segment, wybierz go na stronie **Segmenty** i wybierz **Edytuj** na pasku akcji.</span><span class="sxs-lookup"><span data-stu-id="443db-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="443db-141">Zastosuj zmiany i wybierz **Uruchom**, aby rozpocząć przetwarzanie.</span><span class="sxs-lookup"><span data-stu-id="443db-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="443db-142">Usuń podobny segment</span><span class="sxs-lookup"><span data-stu-id="443db-142">Delete a similar segment</span></span>

<span data-ttu-id="443db-143">Wybierz segment na stronie **Segmenty** i wybierz **Usuń** na pasku akcji.</span><span class="sxs-lookup"><span data-stu-id="443db-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="443db-144">Następnie potwierdź usunięcie.</span><span class="sxs-lookup"><span data-stu-id="443db-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="443db-145">Informacje na temat wyników podobieństwa</span><span class="sxs-lookup"><span data-stu-id="443db-145">About similarity scores</span></span>

<span data-ttu-id="443db-146">Model uczenia maszynowego klasyfikacji binarnych przypisuje wyniki do klientów w podobnym segmencie.</span><span class="sxs-lookup"><span data-stu-id="443db-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="443db-147">Wynik jest uzależniony od podobieństwa do klientów w segmencie źródłowym.</span><span class="sxs-lookup"><span data-stu-id="443db-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="443db-148">Wyniki podobieństwa poniżej 0,55 są klientami, których system klasyfikuje jako *niepodobny* do klientów w segmencie źródłowym</span><span class="sxs-lookup"><span data-stu-id="443db-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="443db-149">Wyniki podobieństwa między 0,55 – 0,7 są klasyfikowane jako *nieco podobne*</span><span class="sxs-lookup"><span data-stu-id="443db-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="443db-150">Wyniki podobieństwa między 0,7 – 0,85 są klasyfikowane jako *podobne*</span><span class="sxs-lookup"><span data-stu-id="443db-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="443db-151">Wyniki podobieństwa między 0,85 – 1 to klienci, których system klasyfikuje jako *bardzo podobni*</span><span class="sxs-lookup"><span data-stu-id="443db-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="443db-152">Klienci o zbliżonych wynikach niższych niż 0,4 nie są uwzględnianiu w modelu wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="443db-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="443db-153">System nie uważa ich za wystarczająco podobnych do segmentu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="443db-153">The system doesn't consider them similar enough to the source segment.</span></span>
