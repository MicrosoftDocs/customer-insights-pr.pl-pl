---
title: Użyj modeli opartych na usłudze Azure Machine Learning
description: Użyj modeli opartych na usłudze Azure Machine Learning w Dynamics 365 Customer Insights.
ms.date: 09/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8d9c9324ea4840b585b9af1a58d505ccaea6f18e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609838"
---
# <a name="use-azure-machine-learning-based-models"></a>Użyj modeli opartych na usłudze Azure Machine Learning

Zunifikowane dane w Dynamics 365 Customer Insights są źródłem budowania modeli uczenia maszynowego, które mogą generować dodatkowe informacje o firmie. Customer Insights integruje się z platformą Uczenie maszynowe Azure w celu korzystania z własnych modeli niestandardowych.

## <a name="prerequisites"></a>Wymagania wstępne

- Dostęp do Customer Insights
- Aktywna subskrypcja Azure Enterprise
- [Ujednolicone profile klientów](data-unification.md)
- Konfigurowanie [eksportu encji do magazynu Azure Blob](export-azure-blob-storage.md)

## <a name="set-up-azure-machine-learning-workspace"></a>Skonfiguruj obszar roboczy Azure Machine Learning

1. Zobacz [Tworzenie obszaru roboczego Azure Machine Learning](/azure/machine-learning/concept-workspace#-create-a-workspace), aby poznać różne opcje tworzenia obszaru roboczego. Aby uzyskać najlepszą wydajność, utwórz obszar roboczy w regionie świadczenia usługi Azure, który jest geograficznie najbliższy środowiska Customer Insights.

1. Uzyskiwanie dostępu do obszaru roboczego za pośrednictwem [Azure Machine Learning Studio](https://ml.azure.com/). Istnieje kilka [sposobów interakcji](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) z obszarem roboczym.

## <a name="work-with-azure-machine-learning-designer"></a>Praca z projektantem Azure Machine Learning

Projektant Azure Machine Learning dostarcza wizualną kanwę, na której możesz przeciągać i upuszczać zestawy danych i moduły. Potok wsadowy utworzony przez projektanta można zintegrować z Customer Insights, jeśli są odpowiednio skonfigurowane. 

## <a name="working-with-azure-machine-learning-sdk"></a>Praca z Azure Machine Learning SDK

Naukowcy zajmujący się danymi i programiści sztucznej inteligencji używają [zestawu SDK usługi Azure Machine Learning](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) do tworzenia przepływów pracy uczenia maszynowego. Obecnie modele wytrenowane przy użyciu zestawu SDK nie mogą być zintegrowane bezpośrednio z Customer Insights. Potok wnioskowania wsadowego, który używa tego modelu, jest wymagany do integracji z Customer Insights.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Wymagania dotyczące potoku wsadowego do integracji z Customer Insights

### <a name="dataset-configuration"></a>Konfiguracja zestawu danych

Utwórz zestawy danych, aby używać danych encji z Customer Insights dla potoku wnioskowania wsadowego. Zarejestruj te zestawy danych w obszarze roboczym. Obecnie są obsługiwane tylko [zestawy danych tabelarycznych](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) w formacie CSV. Parametryzuj zestawy danych odpowiadające danej encji jako parametry potoku.

- Parametry zestawu danych w projektancie

  W projektancie otwórz **Wybierz kolumny w zestawie danych** i wybierz polecenie **Ustaw jako parametr potoku**, gdzie jest określona nazwa parametru.

  :::image type="content" source="media/intelligence-designer-dataset-parameters.png" alt-text="Parametry zestawu danych w projektancie.":::

- Parametr zestawu danych w SDK (Python)

   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Potok wnioskowania wsadowego
  
- W projektancie użyj potoku szkoleniowego do tworzenia lub aktualizowania potoku wnioskowania. Obecnie obsługiwane są tylko potoki wnioskowania wsadowego.

- Za pomocą zestawu SDK opublikuj potok do punktu końcowego. Obecnie Customer Insights integruje się z domyślnym potokiem w punkcie końcowym potoku wsadowego w obszarze roboczym Machine Learning.

   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Importuj dane potoku do Customer Insights

- Projektant dostarcza [moduł eksportowania danych](/azure/machine-learning/algorithm-module-reference/export-data), który umożliwia wyeksportowanie danych wyjściowych z potoku do usługi Azure Storage. Obecnie moduł musi używać typu magazynu danych **Azure Blob Storage** i sparametryzować **Magazyn danych** i względną **Ścieżkę**. Customer Insights zastępuje oba te parametry podczas wykonywania potoku magazynem danych i ścieżką dostępną dla produktu.

  :::image type="content" source="media/intelligence-designer-importdata.png" alt-text="Eksportuj konfigurację modułu danych.":::

- Przy tworzeniu danych wyjściowych dotyczących wnioskowania przy użyciu kodu można przekazać wyniki na ścieżkę z *zarejestrowanego magazynu danych* w obszarze roboczym. Jeśli ścieżka i magazyn danych są sparametryzowane w potoku, Customer Insights będzie mógł odczytywać i importować dane wyjściowe wnioskowania. Obecnie obsługiwany jest tylko jeden format danych wyjściowych w formacie CSV. Ścieżka musi zawierać katalog i nazwę pliku.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]