---
title: Eksportowanie Customer Insights do magazynu obiektów Azure Blob
description: Informacje o konfigurowaniu połączenia z magazynem obiektów Blob Azure.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ecacf20365e78ced8859dfa54b1b16cb923c00eb
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269205"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Łącznik dla magazynu obiektów Blob Azure (wersja zapoznawcza)

Przechowuj dane aplikacji Customer Insights w usłudze Azure Blob storage lub korzystaj z niej, aby transferować swoje dane do innych aplikacji.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Konfigurowanie łącznika dla magazynu obiektów Blob Azure

1. W analizach odbiorców przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.

1. W obszarze **Magazyn obiektów Blob Azure** wybierz **Konfiguruj**.

1. Wprowadź **Nazwę konta**, **Klucz konta** i **Kontener** dla konta magazynu obiektów Blob Azure.
    - Aby dowiedzieć się więcej o wyszukiwaniu klucza konta i nazwy konta magazynu Azure Blob, zobacz [Zarządzaj ustawieniami konta magazynu w portalu Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).
    - Aby dowiedzieć się, jak utworzyć kontener, zobacz [Tworzenie kontenera](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej rozpoznawalną nazwę.

1. Wybierz **Dalej**.

1. Zaznacz pole wyboru obok każdej encji, która ma zostać wyeksportowana do tej lokalizacji docelowej.

1. Wybierz pozycję **Zapisz**.

Eksportowane dane są przechowywane w skonfigurowanym kontenerze magazynu obiektów Blob Azure. W kontenerze są automatycznie tworzone następujące ścieżki folderów:

- Dla encji źródłowych i encji wygenerowanych przez system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Przykład: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Element model.json dla eksportowanych encji będzie przechowywany na poziomie% ExportDestinationName%
  - Przykład: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Eksportowanie danych

Możesz [eksportować dane na żądanie](export-destinations.md#export-data-on-demand). Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]