---
title: Niestandardowe modele Uczenie maszynowe | Microsoft Docs
description: Praca z modelami niestandardowymi z Uczenie maszynowe Azure w Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668916"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="19d08-103">Niestandardowe modele Uczenie maszynowe</span><span class="sxs-lookup"><span data-stu-id="19d08-103">Custom machine learning models</span></span>

<span data-ttu-id="19d08-104">**Analizy** > **Modele niestandardowe** umożliwia zarządzanie przepływami pracy na podstawie modeli Uczenie maszynowe platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="19d08-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="19d08-105">Przepływy pracy pomagają wybrać dane, z których chcesz generować szczegółowe informacje, i odwzorować wyniki na ujednolicone dane klientów.</span><span class="sxs-lookup"><span data-stu-id="19d08-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="19d08-106">Aby uzyskać więcej informacji na temat budowania niestandardowych modeli ML, zobacz [Korzystanie z modeli opartych na Azure Machine Learning](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="19d08-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="19d08-107">Odopowiedzialne AI</span><span class="sxs-lookup"><span data-stu-id="19d08-107">Responsible AI</span></span>

<span data-ttu-id="19d08-108">Przewidywania umożliwiają zwiększanie komfortu obsługi klienta, poprawianie funkcji biznesowych i strumienia przychodów.</span><span class="sxs-lookup"><span data-stu-id="19d08-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="19d08-109">Stanowczo zaleca się, aby zrównoważyć wartość przewidywanie w stosunku do oddziaływania i skutków, które można wprowadzić w sposób etyczny.</span><span class="sxs-lookup"><span data-stu-id="19d08-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="19d08-110">Dowiedz się więcej o tym, jak firma Microsoft [zajmuje się odpowiedzialną sztuczną inteligencją](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="19d08-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="19d08-111">Użytkownik może również zapoznać się [z technikami i procesami dotyczącymi odpowiedzialności za uczenie maszynowe](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) dotyczące usługi Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="19d08-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="19d08-112">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="19d08-112">Prerequisites</span></span>

- <span data-ttu-id="19d08-113">Obecnie ta funkcja obsługuje usługi sieci Web opublikowane za pośrednictwem potoków wsadowych usługi [Machine Learning Studio (klasyczna)](https://studio.azureml.net) i [Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="19d08-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="19d08-114">Aby korzystać z tej funkcji, potrzebujesz konta magazynu Azure Data Lake Gen2 skojarzonego z wystąpieniem usługi Azure Studio.</span><span class="sxs-lookup"><span data-stu-id="19d08-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="19d08-115">Aby uzyskać więcej informacji, zobacz [Tworzenie konta magazynu Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="19d08-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="19d08-116">Dodaj nowy przepływ pracy</span><span class="sxs-lookup"><span data-stu-id="19d08-116">Add a new workflow</span></span>

1. <span data-ttu-id="19d08-117">Przejdź do **Analizy** > **Niestandardowe modele** i wybierz **Nowy przepływ pracy**.</span><span class="sxs-lookup"><span data-stu-id="19d08-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="19d08-118">W polu **Nazwa** nadaj modelowi niestandardowemu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="19d08-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="19d08-119">![Zrzut ekranu okienka Nowy przepływ pracy](media/new-workflowv2.png "Zrzut ekranu okienka Nowy przepływ pracy")</span><span class="sxs-lookup"><span data-stu-id="19d08-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="19d08-120">Wybierz organizację zawierającą usługę sieci Web w **Dzierżawa zawierająca usługę sieci Web**.</span><span class="sxs-lookup"><span data-stu-id="19d08-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="19d08-121">Jeśli subskrypcja Uczenie maszynowe Azure znajduje się w innej dzierżawie niż usługa Customer Insights, wybierz **Zaloguj się**, używając swoich poświadczeń dla wybranej organizacji.</span><span class="sxs-lookup"><span data-stu-id="19d08-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="19d08-122">Wybierz **Obszary robocze** skojarzone z daną usługą sieci Web.</span><span class="sxs-lookup"><span data-stu-id="19d08-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="19d08-123">Na liście znajdują się dwie sekcje, jedna dla Azure Machine Learning w wersji 1 (Machine Learning Studio (klasyczna)) i Azure Machine Learning w wersji 2 (Azure Machine Learning).</span><span class="sxs-lookup"><span data-stu-id="19d08-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="19d08-124">Jeśli nie masz pewności, który obszar roboczy jest odpowiedni dla Twojej usługi internetowej Machine Learning Studio (klasycznej), wybierz opcję **Dowolny**.</span><span class="sxs-lookup"><span data-stu-id="19d08-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="19d08-125">Wybierz usługę sieciową Machine Learning Studio (klasyczną) lub potok Azure Machine Learning na liście rozwijanej **Uslugi sieci Web, która zawiera model**.</span><span class="sxs-lookup"><span data-stu-id="19d08-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="19d08-126">Następnie wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="19d08-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="19d08-127">Więcej informacji o [publikowaniu usługi sieci Web w Machine Learning Studio (klasyczny)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="19d08-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="19d08-128">Dowiedz się więcej o [publikowaniu potoku w usłudze Azure Machine Learning przy użyciu projektanta](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) lub [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="19d08-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> 
     > [!NOTE]
     > <span data-ttu-id="19d08-129">Potok musi zostać opublikowany w [punkcie końcowym potoku](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="19d08-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="19d08-130">Dla **Dane wejściowe usług sieci Web**, wybierz pasującą **Encję** z analiz odbiorców i wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="19d08-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="19d08-131">![Konfiguruj przepływ pracy](media/intelligence-screen2-updated.png "Konfiguruj przepływ pracy")</span><span class="sxs-lookup"><span data-stu-id="19d08-131">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="19d08-132">W kroku **Parametry wyjściowe modelu** ustaw następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="19d08-132">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="19d08-133">Machine Learning Studio (klasyczna)</span><span class="sxs-lookup"><span data-stu-id="19d08-133">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="19d08-134">Wprowadź nazwę **Encji wyjściowej**, do którego ma zostać wlany wyniki usługi sieci Web.</span><span class="sxs-lookup"><span data-stu-id="19d08-134">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="19d08-135">Uczenie maszynowe Azure</span><span class="sxs-lookup"><span data-stu-id="19d08-135">Azure Machine Learning</span></span>
      1. <span data-ttu-id="19d08-136">Wprowadź nazwę **Encji wyjściowej**, do którego ma zostać wlany wyniki strumienia.</span><span class="sxs-lookup"><span data-stu-id="19d08-136">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="19d08-137">Z listy rozwijanej wybierz **Nazwę parametru magazynu danych wyjściowych** potoku wsadowego.</span><span class="sxs-lookup"><span data-stu-id="19d08-137">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="19d08-138">Z listy rozwijanej wybierz **Nazwę parametru ścieżki danych wyjściowych** potoku wsadowego.</span><span class="sxs-lookup"><span data-stu-id="19d08-138">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="19d08-139">![Panel parametrów wyjściowych modelu](media/intelligence-screen3-outputparameters.png "Panel parametrów wyjściowych modelu")</span><span class="sxs-lookup"><span data-stu-id="19d08-139">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="19d08-140">Wybierz pasujący atrybut z listy rozwijanej **Identyfikator klienta w wynikach**, która identyfikuje klientów, i wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="19d08-140">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="19d08-141">![Powiązanie wyników z okienkiem Dane klient](media/intelligence-screen4-relatetocustomer.png "Powiązanie wyników z okienkiem Dane klient")</span><span class="sxs-lookup"><span data-stu-id="19d08-141">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="19d08-142">Zostanie wyświetlony ekran **Zapisany przepływ pracy** ze szczegółowymi informacjami na temat przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="19d08-142">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="19d08-143">Jeśli skonfigurowano przepływ pracy dla potoku Azure Machine Learning, szczegółowe informacje o odbiorcach zostaną dołączone do obszaru roboczego zawierającego potok.</span><span class="sxs-lookup"><span data-stu-id="19d08-143">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="19d08-144">Usługa analizy odbiorców będzie mieć rolę **Współautora** w obszarze roboczym Azure.</span><span class="sxs-lookup"><span data-stu-id="19d08-144">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="19d08-145">Wybierz **Gotowe**.</span><span class="sxs-lookup"><span data-stu-id="19d08-145">Select **Done**.</span></span>

1. <span data-ttu-id="19d08-146">Można teraz uruchomić przepływ pracy ze strony **Modele niestandardowe**.</span><span class="sxs-lookup"><span data-stu-id="19d08-146">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="19d08-147">Edytuj przepływ pracy</span><span class="sxs-lookup"><span data-stu-id="19d08-147">Edit a workflow</span></span>

1. <span data-ttu-id="19d08-148">Na stronie **Modele niestandardowe** wybierz wielokropek pionowy w kolumnie **Akcje** obok utworzonego uprzednio przepływu pracy i wybierz **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="19d08-148">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="19d08-149">Można zaktualizować rozpoznawalną nazwę przepływu pracy w polu **Wyświetlana nazwa**, ale nie można zmienić skonfigurowanej usługi sieci web ani potoku.</span><span class="sxs-lookup"><span data-stu-id="19d08-149">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="19d08-150">Wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="19d08-150">Select **Next**.</span></span>

1. <span data-ttu-id="19d08-151">Dla **Dane wejściowe usług sieci Web**, można aktualizować pasującą **Encję** z analiz odbiorców.</span><span class="sxs-lookup"><span data-stu-id="19d08-151">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="19d08-152">Następnie wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="19d08-152">Then, select **Next**.</span></span>

1. <span data-ttu-id="19d08-153">W kroku **Parametry wyjściowe modelu** ustaw następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="19d08-153">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="19d08-154">Machine Learning Studio (klasyczna)</span><span class="sxs-lookup"><span data-stu-id="19d08-154">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="19d08-155">Wprowadź nazwę **Encji wyjściowej**, do którego ma zostać wlany wyniki usługi sieci Web.</span><span class="sxs-lookup"><span data-stu-id="19d08-155">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="19d08-156">Uczenie maszynowe Azure</span><span class="sxs-lookup"><span data-stu-id="19d08-156">Azure Machine Learning</span></span>
      1. <span data-ttu-id="19d08-157">Wprowadź nazwę **Encji wyjściowej**, do którego ma zostać wlany wyniki strumienia.</span><span class="sxs-lookup"><span data-stu-id="19d08-157">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="19d08-158">Wybierz **Nazwa parametru magazynu danych wyjściowych** dla planowanego strumienia testowego.</span><span class="sxs-lookup"><span data-stu-id="19d08-158">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="19d08-159">Wybierz **Nazwa parametru ścieżki danych wyjściowych** dla planowanego strumienia testowego.</span><span class="sxs-lookup"><span data-stu-id="19d08-159">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="19d08-160">Wybierz pasujący atrybut z listy rozwijanej **Identyfikator klienta w wynikach**, która identyfikuje klientów, i wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="19d08-160">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="19d08-161">Musisz wybrać atrybut z danych wyjściowych wnioskowania o wartościach podobnych do kolumny Identyfikator klienta encji Klient.</span><span class="sxs-lookup"><span data-stu-id="19d08-161">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="19d08-162">Jeśli nie masz takiej kolumny w swoim zbiorze danych, wybierz atrybut, który jednoznacznie identyfikuje wiersz.</span><span class="sxs-lookup"><span data-stu-id="19d08-162">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="19d08-163">Uruchamianie przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="19d08-163">Run a workflow</span></span>

1. <span data-ttu-id="19d08-164">Na stronie **Modele niestandardowe**, wybierz wielokropek pionowy w kolumnie **Akcje** obok utworzonego uprzednio przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="19d08-164">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="19d08-165">Wybierz **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="19d08-165">Select **Run**.</span></span>

<span data-ttu-id="19d08-166">Przepływ pracy jest również uruchamiany automatycznie przy każdym planowanym odświeżeniu.</span><span class="sxs-lookup"><span data-stu-id="19d08-166">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="19d08-167">Dowiedz się więcej na temat [konfigurowania zaplanowanego odświeżania](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="19d08-167">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="19d08-168">Usuń przepływ pracy</span><span class="sxs-lookup"><span data-stu-id="19d08-168">Delete a workflow</span></span>

1. <span data-ttu-id="19d08-169">Na stronie **Modele niestandardowe**, wybierz wielokropek pionowy w kolumnie **Akcje** obok utworzonego uprzednio przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="19d08-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="19d08-170">Wybierz **Usuń** i potwierdź usunięcie.</span><span class="sxs-lookup"><span data-stu-id="19d08-170">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="19d08-171">Przepływ pracy zostanie usunięty.</span><span class="sxs-lookup"><span data-stu-id="19d08-171">Your workflow will be deleted.</span></span> <span data-ttu-id="19d08-172">[Encja](entities.md) utworzona w momencie utworzenia przepływu pracy pozostanie i będzie można ją wyświetlać na stronie **Encje**.</span><span class="sxs-lookup"><span data-stu-id="19d08-172">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>
