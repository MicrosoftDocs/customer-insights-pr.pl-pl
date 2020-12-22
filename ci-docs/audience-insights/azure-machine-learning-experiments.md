---
title: Eksperymenty usługi Azure Machine Learning
description: Użyj modeli opartych na usłudze Azure Machine Learning w Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: 6f00d3202dc29d810bdd218d06c7d04e551846e8
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668782"
---
# <a name="use-azure-machine-learning-based-models"></a>Użyj modeli opartych na usłudze Azure Machine Learning

Zunifikowane dane w Dynamics 365 Customer Insights są źródłem budowania modeli uczenia maszynowego, które mogą generować dodatkowe informacje o firmie. Customer Insights integruje się z Machine Learning Studio (klasycznym) i Azure Machine Learning, aby używać własnych modeli niestandardowych. Zobacz, jak [Eksperymenty Machine Learning Studio (klasyczne)](machine-learning-studio-experiments.md), aby zapoznać się z przykładami eksperymentów opracowanych w Machine Learning Studio (wersja klasyczna). 

## <a name="prerequisites"></a>Wymagania wstępne

- Dostęp do Customer Insights
- Aktywna subskrypcja Azure Enterprise
- [Ujednolicone profile klientów](data-unification.md)
- Konfigurowanie [eksportu encji do magazynu Azure Blob](export-azure-blob-storage.md)

## <a name="set-up-azure-machine-learning-workspace"></a>Skonfiguruj obszar roboczy Azure Machine Learning

1. Zobacz [Tworzenie obszaru roboczego Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace), aby poznać różne opcje tworzenia obszaru roboczego. Aby uzyskać najlepszą wydajność, utwórz obszar roboczy w regionie świadczenia usługi Azure, który jest geograficznie najbliższy środowiska Customer Insights.

1. Uzyskiwanie dostępu do obszaru roboczego za pośrednictwem [Azure Machine Learning Studio](https://ml.azure.com/). Istnieje kilka [sposobów interakcji](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) z obszarem roboczym.

## <a name="work-with-azure-machine-learning-designer"></a>Praca z projektantem Azure Machine Learning

Projektant usługi Azure Machine Learning zapewnia wizualną kanwę, w której można przeciągać i upuszczać zestawy danych i moduły, podobnie jak w usłudze Machine Learning Studio (wersja klasyczna). Potok wsadowy utworzony przez projektanta można zintegrować z Customer Insights, jeśli są odpowiednio skonfigurowane. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Praca z Azure Machine Learning SDK

Naukowcy zajmujący się danymi i programiści sztucznej inteligencji używają [zestawu SDK usługi Azure Machine Learning](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) do tworzenia przepływów pracy uczenia maszynowego. Obecnie modele wytrenowane przy użyciu zestawu SDK nie mogą być zintegrowane bezpośrednio z Customer Insights. Potok wnioskowania wsadowego, który używa tego modelu, jest wymagany do integracji z Customer Insights.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Wymagania dotyczące potoku wsadowego do integracji z Customer Insights

### <a name="dataset-configuration"></a>Konfiguracja zestawu danych

Musisz utworzyć zestawy danych, aby używać danych encji z Customer Insights do potoku wnioskowania wsadowego. Te zestawy danych muszą zostać zarejestrowane w obszarze roboczym. Obecnie są obsługiwane tylko [zestawy danych tabelarycznych](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) w formacie CSV. Zestawy danych odpowiadające danej encji muszą być parametryzowane jako parametry potoku.
   
* Parametry zestawu danych w projektancie
   
     W projektancie otwórz **Wybierz kolumny w zestawie danych** i wybierz polecenie **Ustaw jako parametr potoku**, gdzie jest określona nazwa parametru.

     > [!div class="mx-imgBorder"]
     > ![Parametry zestawu danych w projektancie](media/intelligence-designer-dataset-parameters.png "Parametry zestawu danych w projektancie")
   
* Parametr zestawu danych w SDK (Python)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Potok wnioskowania wsadowego
  
* W projektancie potok szkoleniowy może służyć do tworzenia lub aktualizowania potoku wnioskowania. Obecnie obsługiwane są tylko potoki wnioskowania wsadowego.

* Za pomocą zestawu SDK można opublikować potok do punktu końcowego. Obecnie Customer Insights integruje się z domyślnym potokiem w punkcie końcowym potoku wsadowego w obszarze roboczym Machine Learning.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Importuj dane potoku do Customer Insights

* Projektant dostarcza [moduł eksportowania danych](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data), który umożliwia wyeksportowanie danych wyjściowych z potoku do usługi Azure Storage. Obecnie moduł musi używać typu magazynu danych **Azure Blob Storage** i sparametryzować **Magazyn danych** i względną **Ścieżkę**. Customer Insights zastępuje oba te parametry podczas wykonywania potoku magazynem danych i ścieżką dostępną dla produktu.
   > [!div class="mx-imgBorder"]
   > ![Eksportuj konfigurację modułu danych](media/intelligence-designer-importdata.png "Eksportuj konfigurację modułu danych")
   
* Przy tworzeniu danych wyjściowych dotyczących wnioskowania przy użyciu kodu można przekazać wyniki na ścieżkę z *zarejestrowanego magazynu danych* w obszarze roboczym. Jeśli ścieżka i magazyn danych są sparametryzowane w potoku, Customer Insights będzie mógł odczytywać i importować dane wyjściowe wnioskowania. Obecnie obsługiwany jest tylko jeden format danych wyjściowych w formacie CSV. Ścieżka musi zawierać katalog i nazwę pliku.

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