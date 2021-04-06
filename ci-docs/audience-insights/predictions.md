---
title: Uzupełnij częściowe dane za pomocą przewidywania
description: Aby wypełnić niekompletne dane klientów, należy użyć przewidywania.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3342328b9eead9bdcb8b41f119a1d0a5823001c8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595914"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="26224-103">Uzupełnij częściowe dane przy użyciu przewidywań</span><span class="sxs-lookup"><span data-stu-id="26224-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="26224-104">Przewidywania umożliwiają łatwe tworzenie prognozowanych wartości, które mogą poprawić zrozumienie klienta.</span><span class="sxs-lookup"><span data-stu-id="26224-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="26224-105">Na stronie **Analizy** > **Przewidywania** można wybrać pozycję **Moje przewidywania**, aby wyświetlić obszary, które zostały skonfigurowane w innych częściach analiz odbiorców, oraz umożliwić dalsze dostosowanie ich.</span><span class="sxs-lookup"><span data-stu-id="26224-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="26224-106">Nie można korzystać z tej funkcji, jeśli w środowisku jest używany Magazyn Azure Data Lake Gen 2.</span><span class="sxs-lookup"><span data-stu-id="26224-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="26224-107">Funkcja przewidywania używa zautomatyzowanych środków służących do oceny danych i tworzy przewidywania ich na podstawie tych danych i dlatego może służyć jako metoda profilowania, ponieważ ten termin jest określony przez Ogólne rozporządzenie o ochronie danych („RODO”).</span><span class="sxs-lookup"><span data-stu-id="26224-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="26224-108">Korzystanie z tej funkcji przez klienta do przetwarzania danych może podlegać RODO lub innym prawom lub rozporządzeniom.</span><span class="sxs-lookup"><span data-stu-id="26224-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="26224-109">Użytkownik ma obowiązek zagwarantować, że użytkowanie Dynamics 365 Customer Insights wraz z przewidywaniami jest zgodne ze wszystkimi obowiązującymi przepisami prawnymi i wykonawczymi, w tym prawa związane z ochroną prywatności, danymi osobowymi, danymi biometrycznymi, ochroną danych i poufność informacji.</span><span class="sxs-lookup"><span data-stu-id="26224-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="26224-110">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="26224-110">Prerequisites</span></span>

<span data-ttu-id="26224-111">Aby organizacja mogła korzystać z funkcji przewidywania, należy się upewnić, że są spełnione następujące wymagania wstępne:</span><span class="sxs-lookup"><span data-stu-id="26224-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="26224-112">W organizacji jest używane wystąpienie [skonfigurowane w Common Data Service](/ai-builder/build-model#prerequisites) i znajduje się on w tej samej organizacji, w której znajduje się klient Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="26224-112">Your organization has an instance [set up in the Common Data Service](/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="26224-113">Środowisko użytkownika jest dołączone do wystąpienia Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="26224-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="26224-114">W przypadku [tworzenia nowego środowiska](manage-environments.md) należy je skonfigurować w oknie dialogowym **Tworzenie środowiska** i wybrać opcję **Zaawansowane**.</span><span class="sxs-lookup"><span data-stu-id="26224-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="26224-115">Jeśli środowisko zostało już utworzone, przejdź do jego ustawień i wybierz **Zaawansowane**.</span><span class="sxs-lookup"><span data-stu-id="26224-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="26224-116">W obszarze w sekcji **Korzystanie z przewidywania** wprowadź adres URL wystąpienia Common Data Service, do którego chcesz dodać środowisko.</span><span class="sxs-lookup"><span data-stu-id="26224-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="26224-117">Tworzenie przewidywania w encji Klienta</span><span class="sxs-lookup"><span data-stu-id="26224-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="26224-118">W analizach odbiorców przejdź do **Dane** > **Encje**.</span><span class="sxs-lookup"><span data-stu-id="26224-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="26224-119">Wybierz encję **Klient**.</span><span class="sxs-lookup"><span data-stu-id="26224-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="26224-120">W encji **Klient: CustomerInsights** wybierz na karcie **Pola**.</span><span class="sxs-lookup"><span data-stu-id="26224-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="26224-121">Znajdź nazwę atrybutu, dla którego chcesz prognozować wartości, a następnie wybierz ikonę **przegląd** w kolumnie **podsumowanie**.</span><span class="sxs-lookup"><span data-stu-id="26224-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26224-122">![Ikona przegląd](media/intelligence-overviewicon.png "Ikona przegląd")</span><span class="sxs-lookup"><span data-stu-id="26224-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="26224-123">Jeśli istnieje duża liczba brakujących wartości atrybutu, wybierz **Przewiduj brakujące wartości**, aby kontynuować przewidywanie.</span><span class="sxs-lookup"><span data-stu-id="26224-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26224-124">![Status przeglądu z pokazanym przyciskiem przewidywania brakujących wartości](media/intelligence-overviewpredictmissingvalues.png "Status przeglądu z pokazanym przyciskiem przewidywania brakujących wartości")</span><span class="sxs-lookup"><span data-stu-id="26224-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="26224-125">Uzupełnij pola **Wyświetlana nazwa** i **Nazwa encji wyjściowej** dla wyników przewidywania.</span><span class="sxs-lookup"><span data-stu-id="26224-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="26224-126">Wstępnie wypełniona lista opcji będzie wskazywać miejsce, w którym można zamapować wartości na kategorię przewidywaną.</span><span class="sxs-lookup"><span data-stu-id="26224-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="26224-127">W tym przypadku tylko te opcje kategorii będą miały wartość 0 lub 1, ponieważ są one mapowane na wartość prawda/fałsz lub na dwójkową naturę przewidywania.</span><span class="sxs-lookup"><span data-stu-id="26224-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="26224-128">W kolumnie Kategoria zamapuj wartości pól, które mają być klasyfikowane jako „0”, w końcowym przewidywaniu na „0”, a pozycje, które mają być klasyfikowane jako „1”, w końcowym przewidywaniu na „1”.</span><span class="sxs-lookup"><span data-stu-id="26224-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26224-129">![Przykład przedstawiający mapowane wartości pól w kategoriach](media/intelligence-categorymapping.png "Przykład przedstawiający mapowane wartości pól w kategoriach")</span><span class="sxs-lookup"><span data-stu-id="26224-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="26224-130">Wybierz **Gotowe**, a prognoza zostanie przetworzona.</span><span class="sxs-lookup"><span data-stu-id="26224-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="26224-131">Przetwarzanie zajmie trochę czasu w zależności od rozmiaru i stopnia złożoności danych.</span><span class="sxs-lookup"><span data-stu-id="26224-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="26224-132">Wyniki będą dostępne w nowej encji na podstawie **Nazwa encji wyjściowej** utworzonego przewidywania.</span><span class="sxs-lookup"><span data-stu-id="26224-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="26224-133">Tworzenie przewidywania podczas tworzenia segmentu</span><span class="sxs-lookup"><span data-stu-id="26224-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="26224-134">Podczas tworzenia segmentu możliwe jest również przewidywanie brakujących wartości konkretnego wybranego atrybutu.</span><span class="sxs-lookup"><span data-stu-id="26224-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="26224-135">Szczególnie wtedy, gdy użytkownik szybko tworzy segment na podstawie zunifikowanej encji klienta lub encji Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="26224-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="26224-136">W ramach tego przepływu użytkownik powinien wybrać konkretny atrybut, który będzie podstawą segmentu, na przykład Zadowolenie klienta lub Kwota zakupu.</span><span class="sxs-lookup"><span data-stu-id="26224-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="26224-137">Po utworzeniu segmentu system zasugeruje metodę przewidywania brakujących wartości atrybutu.</span><span class="sxs-lookup"><span data-stu-id="26224-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="26224-138">W analizach odbiorców wybierz kolejno kafelki **Segmenty** i **Profile**.</span><span class="sxs-lookup"><span data-stu-id="26224-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="26224-139">Wybierz **Pole**, na którym ma być utworzony segment, i wybierz **operatora**, a następnie wybierz pozycję **Przejrzyj**.</span><span class="sxs-lookup"><span data-stu-id="26224-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="26224-140">Wprowadź **nazwę** i **wyświetlaną nazwę** segmentu.</span><span class="sxs-lookup"><span data-stu-id="26224-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="26224-141">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="26224-141">Select **Save**.</span></span>

5. <span data-ttu-id="26224-142">Jeśli utworzony segment zawiera niekompletne dane w polu źródłowym, można wybrać opcję przewidywania brakujących wartości.</span><span class="sxs-lookup"><span data-stu-id="26224-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26224-143">![Przycisk przewidywania](media/segments-predictoption.png "Przycisk przewidywania")</span><span class="sxs-lookup"><span data-stu-id="26224-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="26224-144">Uzupełnij pola **Wyświetlana nazwa** i **Nazwa encji wyjściowej** dla wyników przewidywania.</span><span class="sxs-lookup"><span data-stu-id="26224-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="26224-145">Wybierz **Gotowe**.</span><span class="sxs-lookup"><span data-stu-id="26224-145">Select **Done**.</span></span> <span data-ttu-id="26224-146">Przewidywanie zostanie wygenerowana wkrótce w nowej encji i będzie dostępne pod nazwą podaną dla **Nazwa encji wyjściowej**.</span><span class="sxs-lookup"><span data-stu-id="26224-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="26224-147">Zobacz przewidywanie</span><span class="sxs-lookup"><span data-stu-id="26224-147">View a prediction</span></span>

1. <span data-ttu-id="26224-148">W analizach odbiorców przejdź do **Analizy** > **Przewidywania** > **Moje przewidywania**.</span><span class="sxs-lookup"><span data-stu-id="26224-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="26224-149">Wybierz przewidywania do przeglądu.</span><span class="sxs-lookup"><span data-stu-id="26224-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="26224-150">W kolumnie **akcje** wybierz wielokropek i wybierz opcję **widok**.</span><span class="sxs-lookup"><span data-stu-id="26224-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="26224-151">W widoku przewidywania będzie widoczna liczba punktów danych.</span><span class="sxs-lookup"><span data-stu-id="26224-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="26224-152">![Strona przewidywań](media/intelligence-predictionsviewpage.png "Strona przewidywań")</span><span class="sxs-lookup"><span data-stu-id="26224-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="26224-153">**Wartości przewidywane** pokazują mapowanie utworzone podczas fazy mapowania według wartości pola do kategorii.</span><span class="sxs-lookup"><span data-stu-id="26224-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="26224-154">Są to wartości w zestawie danych, które zostały zamapowane na określoną kategorię.</span><span class="sxs-lookup"><span data-stu-id="26224-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="26224-155">-**Pola mające największy wpływ** są to czynniki w zestawie danych, które mogą mieć wpływ na wiarygodność prognozowanej wartości pola, które jest mapowane na określoną kategorię.</span><span class="sxs-lookup"><span data-stu-id="26224-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="26224-156">**Wydajność** wskazuje, jak są wykonywane przewidywania.</span><span class="sxs-lookup"><span data-stu-id="26224-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="26224-157">Aby dowiedzieć się więcej, prosimy kliknąć link.</span><span class="sxs-lookup"><span data-stu-id="26224-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="26224-158">**Podgląd** pokazuje przykłady zestawu danychów wyjściowych z przewidywania i prawdopodobieństwa lub pewność przewidywanej wartości, gdzie 0 jest niepewna, a wartość 1 jest określona jako pewna.</span><span class="sxs-lookup"><span data-stu-id="26224-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="26224-159">Aktualizuj przewidywanie</span><span class="sxs-lookup"><span data-stu-id="26224-159">Update a prediction</span></span>

1. <span data-ttu-id="26224-160">W analizach odbiorców przejdź do **Analizy** > **Przewidywania** > **Moje przewidywania**.</span><span class="sxs-lookup"><span data-stu-id="26224-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="26224-161">Wybierz sposób przewidywania, który chcesz zaktualizować, i wybierz ikonę **Aktualizuj**.</span><span class="sxs-lookup"><span data-stu-id="26224-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="26224-162">Przewidywanie będzie zaplanowane do przetworzenia.</span><span class="sxs-lookup"><span data-stu-id="26224-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="26224-163">Czas ostatniej aktualizacji jest wyświetlany w kolumnie **Zaktualizowano** na stronie **Przewidywania**.</span><span class="sxs-lookup"><span data-stu-id="26224-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="26224-164">Edytuj przewidywanie</span><span class="sxs-lookup"><span data-stu-id="26224-164">Edit a prediction</span></span>

<span data-ttu-id="26224-165">Po utworzeniu przewidywania można dostosować model w AI Builder w celu zwiększenia efektywności modelu.</span><span class="sxs-lookup"><span data-stu-id="26224-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="26224-166">W analizach odbiorców przejdź do **Analizy** > **Przewidywania** > **Moje przewidywania**.</span><span class="sxs-lookup"><span data-stu-id="26224-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="26224-167">Zaznacz przewidywanie, które chcesz edytować.</span><span class="sxs-lookup"><span data-stu-id="26224-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="26224-168">W kolumnie **akcje** wybierz wielokropek i wybierz opcję **widok**.</span><span class="sxs-lookup"><span data-stu-id="26224-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="26224-169">Wybierz **Dostosuj w aplikacji AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="26224-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="26224-170">Zaktualizuj model w konstruktorze AI Builder.</span><span class="sxs-lookup"><span data-stu-id="26224-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="26224-171">[Więcej informacji o zarządzaniu modelami w AI builder](/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="26224-171">[Learn more about managing models in the AI builder](/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="26224-172">Następne uruchomienie funkcji przewidywania będzie mieć zaktualizowany utworzony model.</span><span class="sxs-lookup"><span data-stu-id="26224-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="26224-173">Nowe modele utworzone w narzędziu AI Builder nie będą wyświetlane w statystykach odbiorców, chyba że model został utworzony na podstawie doświadczeń wymienionych powyżej.</span><span class="sxs-lookup"><span data-stu-id="26224-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="26224-174">Usuń przewidywanie</span><span class="sxs-lookup"><span data-stu-id="26224-174">Remove a prediction</span></span>

1. <span data-ttu-id="26224-175">W analizach odbiorców przejdź do **Analizy** > **Przewidywania** > **Moje przewidywania**.</span><span class="sxs-lookup"><span data-stu-id="26224-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="26224-176">Wybierz przewidywanie do usunięcia.</span><span class="sxs-lookup"><span data-stu-id="26224-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="26224-177">W kolumnie **akcje** wybierz wielokropek i wybierz opcję **usuń**.</span><span class="sxs-lookup"><span data-stu-id="26224-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="26224-178">Potwierdź usunięcie.</span><span class="sxs-lookup"><span data-stu-id="26224-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="26224-179">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="26224-179">Troubleshooting</span></span>

<span data-ttu-id="26224-180">Jeśli użytkownik nie może zakończyć procesu dołączania Common Data Service z powodu błędu, może podjąć próbę ręcznego ukończenia procesu.</span><span class="sxs-lookup"><span data-stu-id="26224-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="26224-181">Istnieją dwa znane problemy, które mogą wystąpić podczas procesu dołączania:</span><span class="sxs-lookup"><span data-stu-id="26224-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="26224-182">Rozwiązanie dodatku karty klienta nie jest zainstalowane.</span><span class="sxs-lookup"><span data-stu-id="26224-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="26224-183">Wykonaj instrukcje, aby [zainstalować i skonfigurować rozwiązanie](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="26224-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="26224-184">Nie są przyznawane uprawnienia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="26224-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="26224-185">Przejdź do [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="26224-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="26224-186">Wybierz **Środowiska**.</span><span class="sxs-lookup"><span data-stu-id="26224-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="26224-187">Wybierz wielokropek obok środowiska, do którego chcesz dodać uprawnienie i wybierz **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="26224-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="26224-188">Rozwiń **Użytkownicy + uprawnienia** i wybierz **Użytkownicy**.</span><span class="sxs-lookup"><span data-stu-id="26224-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="26224-189">Wybierz **+ Nowy** i wybierz **Użytkownik**.</span><span class="sxs-lookup"><span data-stu-id="26224-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="26224-190">Wybierz **Użytkownik aplikacji**, jeśli jeszcze nie został on wybrany i wprowadź następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="26224-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="26224-191">**Nazwa użytkownika:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="26224-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="26224-192">**Identyfikator aplikacji:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="26224-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="26224-193">**Imię:** Customer</span><span class="sxs-lookup"><span data-stu-id="26224-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="26224-194">**Nazwisko:** Insights</span><span class="sxs-lookup"><span data-stu-id="26224-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="26224-195">**Podstawowy adres e-mail:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="26224-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="26224-196">Zaznacz **Zapisz i zamknij**.</span><span class="sxs-lookup"><span data-stu-id="26224-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="26224-197">Wybierz właśnie utworzonego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="26224-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="26224-198">W górnym pasku menu wybierz **Zarządzaj rolami**.</span><span class="sxs-lookup"><span data-stu-id="26224-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="26224-199">Wybierz **Administrator systemu**, a następnie wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="26224-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]