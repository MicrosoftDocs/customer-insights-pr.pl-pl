---
title: Eksperymenty usługi Azure Machine Learning
description: Użyj modeli opartych na usłudze Azure Machine Learning w Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: c166015b92596da0c6097e3d25e89579a5186ce0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267919"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="3cc65-103">Użyj modeli opartych na usłudze Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="3cc65-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="3cc65-104">Zunifikowane dane w Dynamics 365 Customer Insights są źródłem budowania modeli uczenia maszynowego, które mogą generować dodatkowe informacje o firmie.</span><span class="sxs-lookup"><span data-stu-id="3cc65-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="3cc65-105">Customer Insights integruje się z Machine Learning Studio (klasycznym) i Azure Machine Learning, aby używać własnych modeli niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="3cc65-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="3cc65-106">Zobacz, jak [Eksperymenty Machine Learning Studio (klasyczne)](machine-learning-studio-experiments.md), aby zapoznać się z przykładami eksperymentów opracowanych w Machine Learning Studio (wersja klasyczna).</span><span class="sxs-lookup"><span data-stu-id="3cc65-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="3cc65-107">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="3cc65-107">Prerequisites</span></span>

- <span data-ttu-id="3cc65-108">Dostęp do Customer Insights</span><span class="sxs-lookup"><span data-stu-id="3cc65-108">Access to Customer Insights</span></span>
- <span data-ttu-id="3cc65-109">Aktywna subskrypcja Azure Enterprise</span><span class="sxs-lookup"><span data-stu-id="3cc65-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="3cc65-110">Ujednolicone profile klientów</span><span class="sxs-lookup"><span data-stu-id="3cc65-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="3cc65-111">Konfigurowanie [eksportu encji do magazynu Azure Blob](export-azure-blob-storage.md)</span><span class="sxs-lookup"><span data-stu-id="3cc65-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="3cc65-112">Skonfiguruj obszar roboczy Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="3cc65-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="3cc65-113">Zobacz [Tworzenie obszaru roboczego Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace), aby poznać różne opcje tworzenia obszaru roboczego.</span><span class="sxs-lookup"><span data-stu-id="3cc65-113">See [create a Azure Machine Learning workspace](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="3cc65-114">Aby uzyskać najlepszą wydajność, utwórz obszar roboczy w regionie świadczenia usługi Azure, który jest geograficznie najbliższy środowiska Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3cc65-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="3cc65-115">Uzyskiwanie dostępu do obszaru roboczego za pośrednictwem [Azure Machine Learning Studio](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="3cc65-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="3cc65-116">Istnieje kilka [sposobów interakcji](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) z obszarem roboczym.</span><span class="sxs-lookup"><span data-stu-id="3cc65-116">There are several [ways to interact](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="3cc65-117">Praca z projektantem Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="3cc65-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="3cc65-118">Projektant usługi Azure Machine Learning zapewnia wizualną kanwę, w której można przeciągać i upuszczać zestawy danych i moduły, podobnie jak w usłudze Machine Learning Studio (wersja klasyczna).</span><span class="sxs-lookup"><span data-stu-id="3cc65-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="3cc65-119">Potok wsadowy utworzony przez projektanta można zintegrować z Customer Insights, jeśli są odpowiednio skonfigurowane.</span><span class="sxs-lookup"><span data-stu-id="3cc65-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="3cc65-120">Praca z Azure Machine Learning SDK</span><span class="sxs-lookup"><span data-stu-id="3cc65-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="3cc65-121">Naukowcy zajmujący się danymi i programiści sztucznej inteligencji używają [zestawu SDK usługi Azure Machine Learning](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) do tworzenia przepływów pracy uczenia maszynowego.</span><span class="sxs-lookup"><span data-stu-id="3cc65-121">Data scientists and AI developers use the [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) to build machine learning workflows.</span></span> <span data-ttu-id="3cc65-122">Obecnie modele wytrenowane przy użyciu zestawu SDK nie mogą być zintegrowane bezpośrednio z Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3cc65-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="3cc65-123">Potok wnioskowania wsadowego, który używa tego modelu, jest wymagany do integracji z Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3cc65-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="3cc65-124">Wymagania dotyczące potoku wsadowego do integracji z Customer Insights</span><span class="sxs-lookup"><span data-stu-id="3cc65-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="3cc65-125">Konfiguracja zestawu danych</span><span class="sxs-lookup"><span data-stu-id="3cc65-125">Dataset Configuration</span></span>

<span data-ttu-id="3cc65-126">Musisz utworzyć zestawy danych, aby używać danych encji z Customer Insights do potoku wnioskowania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="3cc65-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="3cc65-127">Te zestawy danych muszą zostać zarejestrowane w obszarze roboczym.</span><span class="sxs-lookup"><span data-stu-id="3cc65-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="3cc65-128">Obecnie są obsługiwane tylko [zestawy danych tabelarycznych](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) w formacie CSV.</span><span class="sxs-lookup"><span data-stu-id="3cc65-128">Currently, we only support [tabular datasets](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="3cc65-129">Zestawy danych odpowiadające danej encji muszą być parametryzowane jako parametry potoku.</span><span class="sxs-lookup"><span data-stu-id="3cc65-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="3cc65-130">Parametry zestawu danych w projektancie</span><span class="sxs-lookup"><span data-stu-id="3cc65-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="3cc65-131">W projektancie otwórz **Wybierz kolumny w zestawie danych** i wybierz polecenie **Ustaw jako parametr potoku**, gdzie jest określona nazwa parametru.</span><span class="sxs-lookup"><span data-stu-id="3cc65-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="3cc65-132">![Parametry zestawu danych w projektancie](media/intelligence-designer-dataset-parameters.png "Parametry zestawu danych w projektancie")</span><span class="sxs-lookup"><span data-stu-id="3cc65-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="3cc65-133">Parametr zestawu danych w SDK (Python)</span><span class="sxs-lookup"><span data-stu-id="3cc65-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="3cc65-134">Potok wnioskowania wsadowego</span><span class="sxs-lookup"><span data-stu-id="3cc65-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="3cc65-135">W projektancie potok szkoleniowy może służyć do tworzenia lub aktualizowania potoku wnioskowania.</span><span class="sxs-lookup"><span data-stu-id="3cc65-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="3cc65-136">Obecnie obsługiwane są tylko potoki wnioskowania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="3cc65-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="3cc65-137">Za pomocą zestawu SDK można opublikować potok do punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="3cc65-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="3cc65-138">Obecnie Customer Insights integruje się z domyślnym potokiem w punkcie końcowym potoku wsadowego w obszarze roboczym Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="3cc65-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="3cc65-139">Importuj dane potoku do Customer Insights</span><span class="sxs-lookup"><span data-stu-id="3cc65-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="3cc65-140">Projektant dostarcza [moduł eksportowania danych](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data), który umożliwia wyeksportowanie danych wyjściowych z potoku do usługi Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="3cc65-140">The designer provides the [Export Data module](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="3cc65-141">Obecnie moduł musi używać typu magazynu danych **Azure Blob Storage** i sparametryzować **Magazyn danych** i względną **Ścieżkę**.</span><span class="sxs-lookup"><span data-stu-id="3cc65-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="3cc65-142">Customer Insights zastępuje oba te parametry podczas wykonywania potoku magazynem danych i ścieżką dostępną dla produktu.</span><span class="sxs-lookup"><span data-stu-id="3cc65-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3cc65-143">![Eksportuj konfigurację modułu danych](media/intelligence-designer-importdata.png "Eksportuj konfigurację modułu danych")</span><span class="sxs-lookup"><span data-stu-id="3cc65-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="3cc65-144">Przy tworzeniu danych wyjściowych dotyczących wnioskowania przy użyciu kodu można przekazać wyniki na ścieżkę z *zarejestrowanego magazynu danych* w obszarze roboczym.</span><span class="sxs-lookup"><span data-stu-id="3cc65-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="3cc65-145">Jeśli ścieżka i magazyn danych są sparametryzowane w potoku, Customer Insights będzie mógł odczytywać i importować dane wyjściowe wnioskowania.</span><span class="sxs-lookup"><span data-stu-id="3cc65-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="3cc65-146">Obecnie obsługiwany jest tylko jeden format danych wyjściowych w formacie CSV.</span><span class="sxs-lookup"><span data-stu-id="3cc65-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="3cc65-147">Ścieżka musi zawierać katalog i nazwę pliku.</span><span class="sxs-lookup"><span data-stu-id="3cc65-147">The path must include the directory and filename.</span></span>

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```


[!INCLUDE[footer-include](../includes/footer-banner.md)]