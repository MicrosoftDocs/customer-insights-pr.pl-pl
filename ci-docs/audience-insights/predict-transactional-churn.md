---
title: Przewidywanie rezygnacji z transakcji
description: Przewiduj, czy klient jest zagrożony, jeśli przestanie kupować Twoje produkty lub usługi.
ms.date: 11/12/2020
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f3cbbf99a6cecba2aab2cf85428d53e5df8346e4
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644416"
---
# <a name="transactional-churn-prediction-preview"></a><span data-ttu-id="87b48-103">Przewidywanie rezygnacji z transakcji (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="87b48-103">Transactional churn prediction (preview)</span></span>

<span data-ttu-id="87b48-104">Prognozowanie rezygnacji z transakcji pomaga przewidzieć, czy klient nie będzie już kupować Twoich produktów lub usług w danym oknie czasowym.</span><span class="sxs-lookup"><span data-stu-id="87b48-104">Transactional churn prediction helps predict if a customer will no longer purchase your products or services in a given time window.</span></span> <span data-ttu-id="87b48-105">Nowe przewidywania mogą być tworzone w **Analizy** > **Przewidywania**.</span><span class="sxs-lookup"><span data-stu-id="87b48-105">You can create new churn predictions on **Intelligence** > **Predictions**.</span></span> <span data-ttu-id="87b48-106">Wybierz **Moje przewidywania**, aby wyświetlić inne utworzone przewidywania.</span><span class="sxs-lookup"><span data-stu-id="87b48-106">Select **My predictions** to see other predictions that you've created.</span></span>

> [!TIP]
> <span data-ttu-id="87b48-107">Wypróbuj samouczek, aby uzyskać translacyjne przewidywanie rezygnacji z przykładowych danych: [Przykładowy przewodnik dotyczący prognozowania rezygnacji z transakcji (wersja zapoznawcza)](sample-guide-predict-transactional-churn.md).</span><span class="sxs-lookup"><span data-stu-id="87b48-107">Try the tutorial for a translactional churn prediction using sample data: [Transactional churn prediction (preview) sample guide](sample-guide-predict-transactional-churn.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="87b48-108">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="87b48-108">Prerequisites</span></span>

- <span data-ttu-id="87b48-109">Co najmniej [Uprawnienia współautora](permissions.md) w Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="87b48-109">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="87b48-110">Wiedza biznesowa, pozwalająca zrozumieć co rezygnacja oznacza dla Twojej działalności.</span><span class="sxs-lookup"><span data-stu-id="87b48-110">Business knowledge to understand what churn means for your business.</span></span> <span data-ttu-id="87b48-111">Obsługujemy definicje rezygnacji na podstawie czasu, co oznacza, że klient odszedł po okresie braku zakupów.</span><span class="sxs-lookup"><span data-stu-id="87b48-111">We support time-based churn definitions, meaning a customer is considered to have churned after a period of no purchases.</span></span>
- <span data-ttu-id="87b48-112">Dane o transakcjach/zakupach oraz ich historii:</span><span class="sxs-lookup"><span data-stu-id="87b48-112">Data about your transactions/purchases and their history:</span></span>
    - <span data-ttu-id="87b48-113">Identyfikatory transakcji w celu rozróżnienia zakupionych/transakcji.</span><span class="sxs-lookup"><span data-stu-id="87b48-113">Transaction identifiers to distinguish purchases/transactions.</span></span>
    - <span data-ttu-id="87b48-114">Identyfikatory klientów, aby odpowiadały transakcjom klientów.</span><span class="sxs-lookup"><span data-stu-id="87b48-114">Customer identifiers to match transactions to your customers.</span></span>
    - <span data-ttu-id="87b48-115">Daty zdarzeń transakcji, które określają daty, w których doszło do transakcji.</span><span class="sxs-lookup"><span data-stu-id="87b48-115">Transaction event dates, which define the dates the transaction occurred on.</span></span>
    - <span data-ttu-id="87b48-116">Schemat danych semantycznych dla operacji zakupu/transakcji wymaga następujących informacji:</span><span class="sxs-lookup"><span data-stu-id="87b48-116">The semantic data schema for purchases/transactions requires the following information:</span></span>
        - <span data-ttu-id="87b48-117">**Identyfikator transakcji:** unikatowy identyfikator zakupu lub transakcji.</span><span class="sxs-lookup"><span data-stu-id="87b48-117">**Transaction ID:** A unique identifier of a purchase or transaction.</span></span>
        - <span data-ttu-id="87b48-118">**Data transakcji:** Data zakupu lub transakcji.</span><span class="sxs-lookup"><span data-stu-id="87b48-118">**Transaction Date:** The date of the purchase or transaction.</span></span>
        - <span data-ttu-id="87b48-119">**Wartość transakcji:** Kwota waluty/wartości liczbowej transakcji/pozycji.</span><span class="sxs-lookup"><span data-stu-id="87b48-119">**Value of the transaction:** The currency/numerical value amount of the transaction/item.</span></span>
        - <span data-ttu-id="87b48-120">(Opcjonalnie) **Unikatowy identyfikator produktu:** Identyfikator zakupionego produktu lub usługi, jeśli dane są na poziomie pozycji wiersza.</span><span class="sxs-lookup"><span data-stu-id="87b48-120">(Optional) **Unique product ID:** The ID of the product or service purchased if your data is at a line item level.</span></span>
        - <span data-ttu-id="87b48-121">(Opcjonalnie) **Czy ta transakcja była zwrotem:** pole typu prawda/fałsz, które określa, czy transakcja była zwrotna, czy nie.</span><span class="sxs-lookup"><span data-stu-id="87b48-121">(Optional) **Whether this transaction was a return:** A true/false field that identifies if the transaction was a return or not.</span></span> <span data-ttu-id="87b48-122">Jeśli **Wartość transakcji** jest ujemna, Microsoft będzie również używać tych informacji do wywnioskowania, że nastąpił zwrot.</span><span class="sxs-lookup"><span data-stu-id="87b48-122">If the **Value of the transaction** is negative, we will also use this information to infer a return.</span></span>
- <span data-ttu-id="87b48-123">(Opcjonalnie) Dane o działaniach klientów:</span><span class="sxs-lookup"><span data-stu-id="87b48-123">(Optional) Data about customer activities:</span></span>
    - <span data-ttu-id="87b48-124">Identyfikatory działań w celu wyróżnienia działań tego samego typu.</span><span class="sxs-lookup"><span data-stu-id="87b48-124">Activity identifiers to distinguish activities of the same type.</span></span>
    - <span data-ttu-id="87b48-125">Identyfikatory klientów, umożliwiające mapowanie działań do klientów.</span><span class="sxs-lookup"><span data-stu-id="87b48-125">Customer identifiers to map activities to your customers.</span></span>
    - <span data-ttu-id="87b48-126">Informacje o działaniu zawierające nazwę i datę działania.</span><span class="sxs-lookup"><span data-stu-id="87b48-126">Activity information containing the name and date of the activity.</span></span>
    - <span data-ttu-id="87b48-127">Schemat danych semantycznych dla działań klientów zawiera:</span><span class="sxs-lookup"><span data-stu-id="87b48-127">The semantic data schema for customer activities includes:</span></span>
        - <span data-ttu-id="87b48-128">**Klucz podstawowy:** Unikatowy identyfikator działania.</span><span class="sxs-lookup"><span data-stu-id="87b48-128">**Primary key:** A unique identifier for an activity.</span></span> <span data-ttu-id="87b48-129">Na przykład wizyta w witrynie internetowej lub zapis użytkowania pokazujący, że klient wypróbował próbkę Twojego produktu.</span><span class="sxs-lookup"><span data-stu-id="87b48-129">For example, a website visit or a usage record showing the customer tried a sample of your product.</span></span>
        - <span data-ttu-id="87b48-130">**Sygnatura czasowa:** Data i godzina zdarzenia identyfikowanego przez klucz podstawowy.</span><span class="sxs-lookup"><span data-stu-id="87b48-130">**Timestamp:** The date and time of the event identified by the primary key.</span></span>
        - <span data-ttu-id="87b48-131">**Zdarzenie:** Określ nazwę zdarzenia, które chcesz użyć.</span><span class="sxs-lookup"><span data-stu-id="87b48-131">**Event:** The name of the event you want to use.</span></span> <span data-ttu-id="87b48-132">Na przykład pole o nazwie „UserAction” w sklepie spożywczym może być kuponem używanym przez klienta.</span><span class="sxs-lookup"><span data-stu-id="87b48-132">For example, a field called "UserAction" in a grocery store might be a coupon use by the customer.</span></span>
        - <span data-ttu-id="87b48-133">**Szczegóły:** Szczegółowe informacje o zdarzeniu.</span><span class="sxs-lookup"><span data-stu-id="87b48-133">**Details:** Detailed information about the event.</span></span> <span data-ttu-id="87b48-134">Na przykład pole o nazwie „CouponValue” w sklepie spożywczym może zawierać walutę kuponu.</span><span class="sxs-lookup"><span data-stu-id="87b48-134">For example, a field called "CouponValue" in a grocery store might be the currency value of the coupon.</span></span>

## <a name="create-a-transactional-churn-prediction"></a><span data-ttu-id="87b48-135">Utwórz prognozę rezygnacji z transakcji</span><span class="sxs-lookup"><span data-stu-id="87b48-135">Create a transactional churn prediction</span></span>

1. <span data-ttu-id="87b48-136">W Customer Insights przejdź do **Analizy** > **Przewidywania**.</span><span class="sxs-lookup"><span data-stu-id="87b48-136">In Customer Insights, go to **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="87b48-137">Wybierz kafelek **Model rezygnacji klientów (wersja zapoznawcza)** i wybierz opcję **Użyj tego modelu**.</span><span class="sxs-lookup"><span data-stu-id="87b48-137">Select the **Customer churn model (preview)** tile and select **Use this model**.</span></span>
   
1. <span data-ttu-id="87b48-138">W okienku **Model rezygnacji klientów** wybierz opcję **Transakcyjne** i wybierz pozycję **Rozpocznij**.</span><span class="sxs-lookup"><span data-stu-id="87b48-138">In the **Customer churn model** pane, choose **Transactional** and select **Get started**.</span></span>

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Zrzut ekranu z wybraną opcją transakcyjną w okienku modelu rezygnacji klientów.":::

### <a name="name-model"></a><span data-ttu-id="87b48-140">Nadaj nazwę modelowi</span><span class="sxs-lookup"><span data-stu-id="87b48-140">Name model</span></span>

1. <span data-ttu-id="87b48-141">Podaj nazwę modelu odróżniającą go od innych modeli.</span><span class="sxs-lookup"><span data-stu-id="87b48-141">Provide a name for the model to distinguish it from other models.</span></span>

1. <span data-ttu-id="87b48-142">Podaj nazwę encji wyjściowej używając wyłącznie liter i cyfr, bez żadnych spacji.</span><span class="sxs-lookup"><span data-stu-id="87b48-142">Provide a name for the output entity using letters and numbers only, without any spaces.</span></span> <span data-ttu-id="87b48-143">To jest nazwa, której będzie używać encja modelowa.</span><span class="sxs-lookup"><span data-stu-id="87b48-143">That's the name that the model entity will use.</span></span> 

1. <span data-ttu-id="87b48-144">Wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="87b48-144">Select **Next**.</span></span>

### <a name="define-customer-churn"></a><span data-ttu-id="87b48-145">Definiuj rezygnację klienta</span><span class="sxs-lookup"><span data-stu-id="87b48-145">Define customer churn</span></span>

1. <span data-ttu-id="87b48-146">Ustaw przedział dni na prognozowanie rezygnacji w polu **Zidentyfikuj klientów, którzy mogą odejść w następnym**.</span><span class="sxs-lookup"><span data-stu-id="87b48-146">Set a window of days to predict churn for in the **Identify customers who may churn in the next** field.</span></span> <span data-ttu-id="87b48-147">Na przykład prognozuj ryzyko odejścia klientów w ciągu najbliższych 90 dni, aby dostosować się do działań marketingowych dotyczących utrzymania klientów.</span><span class="sxs-lookup"><span data-stu-id="87b48-147">For example, predict the risk of churn for your customers over the next 90 days to align to your marketing retention efforts.</span></span> <span data-ttu-id="87b48-148">Przewidywanie ryzyka odejścia na dłuższy lub krótszy okres może utrudnić uwzględnienie czynników w profilu ryzyka odejścia, ale zależy to od konkretnych wymagań biznesowych.</span><span class="sxs-lookup"><span data-stu-id="87b48-148">Predicting churn risk for a longer or shorter period of time can make it more difficult to address the factors in your churn risk profile, but it depends on your specific business requirements.</span></span> 
   >[!TIP]
   > <span data-ttu-id="87b48-149">W dowolnym momencie możesz wybrać **Zapisz i zamknij**, aby zapisać przewidywanie jako wersję roboczą.</span><span class="sxs-lookup"><span data-stu-id="87b48-149">You can select **Save and close** at any time to save the prediction as a draft.</span></span> <span data-ttu-id="87b48-150">Aby kontynuować, należy znaleźć przewidywanie w wersji roboczej na karcie **Moje przewidywania**.</span><span class="sxs-lookup"><span data-stu-id="87b48-150">You'll find the draft prediction in the **My predictions** tab to continue.</span></span>

1. <span data-ttu-id="87b48-151">Wprowadź liczbę dni do zdefiniowania rezygnacji w polu **Klient odszedł, jeśli nie dokonał zakupów w:**.</span><span class="sxs-lookup"><span data-stu-id="87b48-151">Enter the number of days to define churn in the **A customer has churned if they've made no purchases in:** field.</span></span> <span data-ttu-id="87b48-152">Na przykład, jeśli klient nie dokonał zakupów w ciągu ostatnich 30 dni, może zostać uznany za klienta, który zrezygnował, w przypadku Twojej firmy.</span><span class="sxs-lookup"><span data-stu-id="87b48-152">For example, if a customer has made no purchases in the last 30 days, they might be considered as churned for your business.</span></span> 

1. <span data-ttu-id="87b48-153">Wybierz **Dalej**, aby kontynuować</span><span class="sxs-lookup"><span data-stu-id="87b48-153">Select **Next** to continue</span></span>

### <a name="add-required-data"></a><span data-ttu-id="87b48-154">Dodaj wymagane dane</span><span class="sxs-lookup"><span data-stu-id="87b48-154">Add required data</span></span>

1. <span data-ttu-id="87b48-155">Wybierz opcję **Dodaj dane** do **Historii zakupu** i wybierz encję, która dostarcza informacje historyczne dotyczące transakcji i zakupu, jak to opisano w sekcji [wymagania wstępne](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="87b48-155">Select **Add data** for **Purchase history** and choose the entity that provides the transaction/purchase history information as described in the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="87b48-156">Zmapuj pola semantyczne na atrybuty w encji historii zakupu i wybierz przycisk **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="87b48-156">Map the semantic fields to attributes within your purchase history entity and select **Next**.</span></span> <span data-ttu-id="87b48-157">Aby zapoznać się z opisami pól, należy zapoznać się z [wymaganiami wstępnymi](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="87b48-157">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="Mapowanie pól semantycznych encji zakupu.":::

1. <span data-ttu-id="87b48-159">Jeśli poniższe pola nie są wypełnione, skonfiguruj relację z encji historii zakupu do encji klient.</span><span class="sxs-lookup"><span data-stu-id="87b48-159">If the fields below aren't populated, configure the relationship from your purchase history entity to the Customer entity.</span></span>
    1. <span data-ttu-id="87b48-160">Wybierz **Encja historii zakupów**.</span><span class="sxs-lookup"><span data-stu-id="87b48-160">Select the **Purchase history entity**.</span></span>
    1. <span data-ttu-id="87b48-161">Wybierz **Pole**, które identyfikuje klienta w encji historii zakupu.</span><span class="sxs-lookup"><span data-stu-id="87b48-161">Select the **Field** that identifies the customer in the purchase history entity.</span></span> <span data-ttu-id="87b48-162">Musi ono być powiązane z podstawowym identyfikatorem klienta encji Klient.</span><span class="sxs-lookup"><span data-stu-id="87b48-162">It needs to relate to the primary customer ID of your Customer entity.</span></span>
    1. <span data-ttu-id="87b48-163">Wybierz **encję Klient** pasującą do podstawowej encji klienta.</span><span class="sxs-lookup"><span data-stu-id="87b48-163">Select the **Customer entity** that matches your primary customer entity.</span></span>
    1. <span data-ttu-id="87b48-164">Wprowadź nazwę, która opisuje relację.</span><span class="sxs-lookup"><span data-stu-id="87b48-164">Enter a name that describes the relationship.</span></span>

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="Strona historii zakupów pokazująca tworzenie relacji z klientem.":::
   
1. <span data-ttu-id="87b48-166">Wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="87b48-166">Select **Next**.</span></span>

1. <span data-ttu-id="87b48-167">Możesz też wybrać pozycję **Dodaj dane** do **Działań klienta**.</span><span class="sxs-lookup"><span data-stu-id="87b48-167">Optionally, select **Add data** for **Customer activities**.</span></span> <span data-ttu-id="87b48-168">Wybierz encję, która dostarcza informacje o działaniu klienta w sposób opisany w sekcji wymagania wstępne.</span><span class="sxs-lookup"><span data-stu-id="87b48-168">Choose the entity that provides the customer activity information as described in the prerequisites.</span></span>

1. <span data-ttu-id="87b48-169">Zmapuj pola semantyczne na atrybuty w encji działań klienta i wybierz przycisk **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="87b48-169">Map the semantic fields to attributes within your customer activity entity and select **Next**.</span></span> <span data-ttu-id="87b48-170">Aby zapoznać się z opisami pól, należy zapoznać się z [wymaganiami wstępnymi](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="87b48-170">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="87b48-171">Wybierz typ działania odpowiadający typowi działania klienta, które konfigurujesz.</span><span class="sxs-lookup"><span data-stu-id="87b48-171">Select an activity type that matches to the type of customer activity you're configuring.</span></span> <span data-ttu-id="87b48-172">Wybierz opcję **Utwórz nowy** i wybierz dostępny typ działania lub utwórz nowy typ.</span><span class="sxs-lookup"><span data-stu-id="87b48-172">Select **Create new** and choose an available activity type or create a new type.</span></span>

1. <span data-ttu-id="87b48-173">Należy skonfigurować relację od encji działania klienta do encji Klient.</span><span class="sxs-lookup"><span data-stu-id="87b48-173">You'll need to configure the relationship from your customer activity entity to the Customer entity.</span></span>
    1. <span data-ttu-id="87b48-174">Wybierz pole, które identyfikuje klienta w tabeli aktywności klientów.</span><span class="sxs-lookup"><span data-stu-id="87b48-174">Select the field that identifies the customer in the customer activity table.</span></span> <span data-ttu-id="87b48-175">Może być bezpośrednio powiązany z głównym identyfikatorem klienta encji klienta.</span><span class="sxs-lookup"><span data-stu-id="87b48-175">It can be directly related to the primary customer ID of your Customer entity.</span></span>
    1. <span data-ttu-id="87b48-176">Wybierz encję Klient pasującą do podstawowej encji Klient</span><span class="sxs-lookup"><span data-stu-id="87b48-176">Select the Customer entity that matches your primary Customer entity</span></span>
    1. <span data-ttu-id="87b48-177">Wprowadź nazwę, która opisuje relację.</span><span class="sxs-lookup"><span data-stu-id="87b48-177">Enter a name that describes the relationship.</span></span>

1. <span data-ttu-id="87b48-178">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="87b48-178">Select **Save**.</span></span>

1. <span data-ttu-id="87b48-179">Jeśli istnieją inne działania dotyczące klientów, które mają zostać uwzględnione, powtórz te kroki.</span><span class="sxs-lookup"><span data-stu-id="87b48-179">If you have any other customer activities you would like to include, repeat the steps above.</span></span>

1. <span data-ttu-id="87b48-180">Wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="87b48-180">Select **Next**.</span></span>

### <a name="set-schedule-and-review-configuration"></a><span data-ttu-id="87b48-181">Konfigurowanie harmonogramu i przeglądu konfiguracji</span><span class="sxs-lookup"><span data-stu-id="87b48-181">Set schedule and review configuration</span></span>

1. <span data-ttu-id="87b48-182">Ustaw częstotliwość ponownego uczenia modelu.</span><span class="sxs-lookup"><span data-stu-id="87b48-182">Set a frequency to retrain your model.</span></span> <span data-ttu-id="87b48-183">To ustawienie jest ważne, aby zaktualizować dokładność prognoz w miarę pozyskiwania nowych danych.</span><span class="sxs-lookup"><span data-stu-id="87b48-183">This setting is important to update the accuracy of predictions as new data is ingested.</span></span> <span data-ttu-id="87b48-184">Większość firm może przeprowadzać ponowne szkolenia raz w miesiącu i uzyskać dobrą dokładność przewidywań.</span><span class="sxs-lookup"><span data-stu-id="87b48-184">Most businesses can retrain once per month and get a good accuracy for their prediction.</span></span>

1. <span data-ttu-id="87b48-185">Wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="87b48-185">Select **Next**.</span></span>

1. <span data-ttu-id="87b48-186">Przejrzyj konfigurację prognozy.</span><span class="sxs-lookup"><span data-stu-id="87b48-186">Review the configuration of the prediction.</span></span> <span data-ttu-id="87b48-187">Aby wrócić do poprzednich kroków, można wybrać opcję **Edycji** pod pokazaną wartością.</span><span class="sxs-lookup"><span data-stu-id="87b48-187">You can go back to prior steps by selecting **Edit** under the shown value.</span></span> <span data-ttu-id="87b48-188">Można też wybrać krok konfiguracji ze wskaźnika postępu.</span><span class="sxs-lookup"><span data-stu-id="87b48-188">Or you can select a configuration step from the progress indicator.</span></span>

1. <span data-ttu-id="87b48-189">Jeśli wszystkie wartości są poprawnie skonfigurowane, wybierz **Zapisz i uruchom**, aby rozpocząć proces przewidywania.</span><span class="sxs-lookup"><span data-stu-id="87b48-189">If all values are configured correctly, select **Save and run** to begin the prediction process.</span></span> <span data-ttu-id="87b48-190">Na karcie **Moje przewidywania** można sprawdzić stan przewidywań.</span><span class="sxs-lookup"><span data-stu-id="87b48-190">On the **My predictions** tab, you can see the status of your predictions.</span></span> <span data-ttu-id="87b48-191">Przeprowadzanie procesu może potrwać kilka godzin, w zależności od ilości danych użytych w przewidywaniu.</span><span class="sxs-lookup"><span data-stu-id="87b48-191">The process may take several hours to complete depending on the amount of data used in the prediction.</span></span>

## <a name="review-a-prediction-status-and-results"></a><span data-ttu-id="87b48-192">Przejrzyj stan przewidywania i wyniki</span><span class="sxs-lookup"><span data-stu-id="87b48-192">Review a prediction status and results</span></span>

1. <span data-ttu-id="87b48-193">Wybierz **Analizy** > **Przewidywania** i wybierz kartę **Moje przewidywania**.</span><span class="sxs-lookup"><span data-stu-id="87b48-193">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="87b48-194">Wybierz przewidywania do przeglądu.</span><span class="sxs-lookup"><span data-stu-id="87b48-194">Select the prediction you want to review.</span></span>
   - <span data-ttu-id="87b48-195">**Nazwa przewidywania:** Nazwa przewidywania podana podczas jej tworzenia..</span><span class="sxs-lookup"><span data-stu-id="87b48-195">**Prediction name:** Name of the prediction provided when creating it.</span></span>
   - <span data-ttu-id="87b48-196">**Typ przewidywania:** typ modelu używanego przez przewidywanie</span><span class="sxs-lookup"><span data-stu-id="87b48-196">**Prediction type:** Type of model used for the prediction</span></span>
   - <span data-ttu-id="87b48-197">**Encja wyjściowa:** Nazwa encji, w której mają być przechowywane wyniki przewidywania.</span><span class="sxs-lookup"><span data-stu-id="87b48-197">**Output entity:** Name of the entity to store the output of the prediction.</span></span> <span data-ttu-id="87b48-198">Encję o tej nazwie można znaleźć w **Dane** > **Encje**.</span><span class="sxs-lookup"><span data-stu-id="87b48-198">You can find an entity with this name on **Data** > **Entities**.</span></span>
   - <span data-ttu-id="87b48-199">**Przewidywane pole:** To pole jest wypełniane tylko w przypadku niektórych typów przewidywań i nie jest używane w przewidywaniu rezygnacji.</span><span class="sxs-lookup"><span data-stu-id="87b48-199">**Predicted field:** This field is populated only for some types of predictions, and isn't used in churn prediction.</span></span>
   - <span data-ttu-id="87b48-200">**Stan:** Stan przebiegu przewidywania.</span><span class="sxs-lookup"><span data-stu-id="87b48-200">**Status:** Status of the prediction run.</span></span>
        - <span data-ttu-id="87b48-201">**W kolejce:** Przewidywanie oczekuje na uruchomienie innych procesów.</span><span class="sxs-lookup"><span data-stu-id="87b48-201">**Queued:** Prediction is waiting for other processes to run.</span></span>
        - <span data-ttu-id="87b48-202">**Odświeżanie:** przewidywanie jest obecnie uruchomione w celu wyprodukowania wyników, które będą przepływać na encję wyjściową.</span><span class="sxs-lookup"><span data-stu-id="87b48-202">**Refreshing:** Prediction is currently running to produce results that will flow into the output entity.</span></span>
        - <span data-ttu-id="87b48-203">**Niepowodzenie:** uruchomienie przewidywanie zakończyło się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="87b48-203">**Failed:** Prediction run has failed.</span></span> <span data-ttu-id="87b48-204">Aby uzyskać więcej informacji, [przejrzyj dzienniki](#troubleshoot-a-failed-prediction).</span><span class="sxs-lookup"><span data-stu-id="87b48-204">[Review the logs](#troubleshoot-a-failed-prediction) for more details.</span></span>
        - <span data-ttu-id="87b48-205">**Zakończono pomyślnie:** przewidywanie zakończyło się sukcesem.</span><span class="sxs-lookup"><span data-stu-id="87b48-205">**Succeeded:** Prediction has succeeded.</span></span> <span data-ttu-id="87b48-206">Wybierz **Widok** pod pionowymi wielokropkami, aby przejrzeć przewidywanie</span><span class="sxs-lookup"><span data-stu-id="87b48-206">Select **View** under the vertical ellipses to review the prediction</span></span>
   - <span data-ttu-id="87b48-207">**Edytowano:** Data konfiguracji dla przewidywania została zmieniona.</span><span class="sxs-lookup"><span data-stu-id="87b48-207">**Edited:** The date the configuration for the prediction was changed.</span></span>
   - <span data-ttu-id="87b48-208">**Ostatnie odświeżenie:** Data odświeżonych wyników przewidywania w encji wyjściowej.</span><span class="sxs-lookup"><span data-stu-id="87b48-208">**Last refreshed:** The date the prediction refreshed results in the output entity.</span></span>

1. <span data-ttu-id="87b48-209">Zaznacz pionowy wielokropek obok przewidywania, dla którego chcesz przejrzeć wyniki, i wybierz **Widok**.</span><span class="sxs-lookup"><span data-stu-id="87b48-209">Select the vertical ellipses next to the prediction you want to review results for and select **View**.</span></span>

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Wyświetl kontrolkę, aby zobaczyć wyniki prognozy.":::   

1. <span data-ttu-id="87b48-211">Na stronie wyników wyszukiwania znajdują się trzy podstawowe sekcje danych:</span><span class="sxs-lookup"><span data-stu-id="87b48-211">There are three primary sections of data within the results page:</span></span>
    1. <span data-ttu-id="87b48-212">**Wydajność modelu szkoleniowego:** A, B i C są możliwymi wynikami.</span><span class="sxs-lookup"><span data-stu-id="87b48-212">**Training model performance:** A, B, or C are possible scores.</span></span> <span data-ttu-id="87b48-213">Ten wynik wskazuje wydajność przewidywania i może pomóc w podjęciu decyzji w zakresie korzystania z wyników przechowywanych w encji wyjściowej.</span><span class="sxs-lookup"><span data-stu-id="87b48-213">This score indicates the performance of the prediction, and can help you make the decision to use the results stored in the output entity.</span></span> <span data-ttu-id="87b48-214">Wyniki są określane na podstawie następujących reguł:</span><span class="sxs-lookup"><span data-stu-id="87b48-214">Scores are determined based on the following rules:</span></span>
         
         - <span data-ttu-id="87b48-215">**A** kiedy model dokładnie przewidział co najmniej 50% wszystkich prognoz, a odsetek trafnych prognoz dla klientów, którzy zrezygnowali, jest większy od wskaźnika bazowego o co najmniej 10%.</span><span class="sxs-lookup"><span data-stu-id="87b48-215">**A** when the model accurately predicted at least 50% of the total predictions, and when the percentage of accurate predictions for customers who churned is greater than the baseline rate by at least 10%.</span></span>
            
         - <span data-ttu-id="87b48-216">**B** kiedy model dokładnie przewidział co najmniej 50% wszystkich prognoz, a odsetek trafnych prognoz dla klientów, którzy zrezygnowali, jest do 10% większy niż poziom bazowy.</span><span class="sxs-lookup"><span data-stu-id="87b48-216">**B** when the model accurately predicted at least 50% of the total predictions, and when the percentage of accurate predictions for customers who churned is up to 10% greater than the baseline.</span></span>
            
         - <span data-ttu-id="87b48-217">**C** kiedy model dokładnie przewidział mniej niż 50% wszystkich prognoz lub odsetek trafnych prognoz dla klientów, którzy zrezygnowali, jest do 10% mniejszsy niż poziom bazowy.</span><span class="sxs-lookup"><span data-stu-id="87b48-217">**C** when the model accurately predicted less 50% of the total predictions, or when the percentage of accurate predictions for customers who churned is less than the baseline.</span></span>
               
         - <span data-ttu-id="87b48-218">**Linia bazowa** przyjmuje dane wejściowe w oknie czasowym prognozy dla modelu (na przykład jeden rok), a model tworzy różne ułamki czasu, dzieląc je przez 2, aż osiągnie jeden miesiąc lub mniej.</span><span class="sxs-lookup"><span data-stu-id="87b48-218">**Baseline** takes the prediction time window input for the model (for example, one year) and the model creates different fractions of time by dividing it by 2 until it reaches one month or less.</span></span> <span data-ttu-id="87b48-219">Wykorzystuje te ułamki do stworzenia reguły biznesowej dla klientów, którzy nie dokonali zakupów w tym przedziale czasowym.</span><span class="sxs-lookup"><span data-stu-id="87b48-219">It uses these fractions to create a business rule for customers who have not purchased in this time frame.</span></span> <span data-ttu-id="87b48-220">Tych klientów uważa się za utraconych.</span><span class="sxs-lookup"><span data-stu-id="87b48-220">These customers are considered as churned.</span></span> <span data-ttu-id="87b48-221">Jako model bazowy wybrano regułę biznesową opartą na czasie z największą zdolnością przewidywania, kto prawdopodobnie odejdzie.</span><span class="sxs-lookup"><span data-stu-id="87b48-221">The time-based business rule with the highest ability to predict who is likely to churn is chosen as baseline model.</span></span>
            
    1. <span data-ttu-id="87b48-222">**Prawdopodobieństwo rezygnacji (liczba klientów):** Grupy klientów na podstawie ich przewidywanego ryzyka rezygnacji.</span><span class="sxs-lookup"><span data-stu-id="87b48-222">**Likelihood to churn (number of customers):** Groups of customers based on their predicted risk of churn.</span></span> <span data-ttu-id="87b48-223">Te dane mogą pomóc później, jeśli chcesz utworzyć segment klientów z dużym ryzykiem rezygnacji.</span><span class="sxs-lookup"><span data-stu-id="87b48-223">This data can help you later if you want to create a segment of customers with high churn risk.</span></span> <span data-ttu-id="87b48-224">Takie segmenty ułatwiają zrozumienie tego, w którym miejscu powinien się znaleźć próg dla członkostwa w segmencie.</span><span class="sxs-lookup"><span data-stu-id="87b48-224">Such segments help to understand where your cutoff should be for segment membership.</span></span>
       
    1. <span data-ttu-id="87b48-225">**Czynniki mające największy wpływ:** Istnieje wiele czynników branych pod uwagę podczas tworzenia przewidywania.</span><span class="sxs-lookup"><span data-stu-id="87b48-225">**Most influential factors:** There are many factors that are taken into account when creating your prediction.</span></span> <span data-ttu-id="87b48-226">Każdy z czynników ma swoją wagę obliczoną dla zagregowanych prognoz tworzonych przez model.</span><span class="sxs-lookup"><span data-stu-id="87b48-226">Each of the factors has its importance calculated for the aggregated predictions a model creates.</span></span> <span data-ttu-id="87b48-227">Tych czynników można użyć w celu sprawdzenia poprawności wyników przewidywania.</span><span class="sxs-lookup"><span data-stu-id="87b48-227">You can use these factors to help validate your prediction results.</span></span> <span data-ttu-id="87b48-228">Można też użyć tych informacji później, aby [utworzyć segmenty](segments.md), które mogą wpłynąć na ryzyko rezygnacji dla klientów.</span><span class="sxs-lookup"><span data-stu-id="87b48-228">Or you can use this information later to [create segments](segments.md) that could help influence churn risk for customers.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="87b48-229">Rozwiązywanie problemów dotyczących nieudanych przewidywań</span><span class="sxs-lookup"><span data-stu-id="87b48-229">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="87b48-230">Wybierz **Analizy** > **Przewidywania** i wybierz kartę **Moje przewidywania**.</span><span class="sxs-lookup"><span data-stu-id="87b48-230">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="87b48-231">Zaznacz wielokropek pionowy obok etykiety przewidywań, dla których chcesz wyświetlić dzienniki błędów.</span><span class="sxs-lookup"><span data-stu-id="87b48-231">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="87b48-232">Wybierz **Dzienniki**.</span><span class="sxs-lookup"><span data-stu-id="87b48-232">Select **Logs**.</span></span>

1. <span data-ttu-id="87b48-233">Przejrzyj wszystkie błędy.</span><span class="sxs-lookup"><span data-stu-id="87b48-233">Review all the errors.</span></span> <span data-ttu-id="87b48-234">Istnieje kilka typów błędów, które mogą wystąpić, i opisują one jaki warunek spowodował błąd.</span><span class="sxs-lookup"><span data-stu-id="87b48-234">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="87b48-235">Na przykład błąd polegający na tym, że jest zbyt mało danych, aby dokładnie przeprowadzić przewidywanie, jest zwykle rozwiązywany dzięki załadowaniu dodatkowych danych do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="87b48-235">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="87b48-236">Odświeżanie przewidywania</span><span class="sxs-lookup"><span data-stu-id="87b48-236">Refresh a prediction</span></span>

<span data-ttu-id="87b48-237">Przewidywania będą odświeżane automatycznie w oparciu o ten sam [harmonogram odświeżania danych](system.md#schedule-tab) skonfigurowany w ustawieniach.</span><span class="sxs-lookup"><span data-stu-id="87b48-237">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="87b48-238">Można je również ręcznie odświeżyć.</span><span class="sxs-lookup"><span data-stu-id="87b48-238">You can refresh them manually too.</span></span>

1. <span data-ttu-id="87b48-239">Wybierz **Analizy** > **Przewidywania** i wybierz kartę **Moje przewidywania**.</span><span class="sxs-lookup"><span data-stu-id="87b48-239">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="87b48-240">Wybierz pionowy wielokropek obok przewidywania, które chcesz odświeżyć.</span><span class="sxs-lookup"><span data-stu-id="87b48-240">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="87b48-241">Wybierz **Odśwież**.</span><span class="sxs-lookup"><span data-stu-id="87b48-241">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="87b48-242">Usuń przewidywanie</span><span class="sxs-lookup"><span data-stu-id="87b48-242">Delete a prediction</span></span>

<span data-ttu-id="87b48-243">Usunięcie przewidywanie usuwa również jej encję wyjściową.</span><span class="sxs-lookup"><span data-stu-id="87b48-243">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="87b48-244">Wybierz **Analizy** > **Przewidywania** i wybierz kartę **Moje przewidywania**.</span><span class="sxs-lookup"><span data-stu-id="87b48-244">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="87b48-245">Wybierz pionowy wielokropek obok przewidywania, które chcesz usunąć.</span><span class="sxs-lookup"><span data-stu-id="87b48-245">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="87b48-246">Wybierz **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="87b48-246">Select **Delete**.</span></span>