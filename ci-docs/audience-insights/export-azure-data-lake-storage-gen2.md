---
title: Eksportowanie danych Customer Insights do Azure Data Lake Storage Gen2
description: Dowiedz się, jak skonfigurować połączenie z Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477192"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Łącznik dla usługi  Azure Data Lake Storage Gen2 (wersja zapoznawcza)

Przechowuj dane aplikacji Customer Insights w usłudze Azure Data Lake Storage Gen2 lub korzystaj z niej, aby transferować swoje dane do innych aplikacji.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Konfigurowanie łącznika dla Azure Data Lake Storage Gen2

1. W analizach odbiorców przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.

1. W **Azure Data Lake Storage Gen2** wybierz **Konfiguruj**.

1. W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej rozpoznawalną nazwę.

1. Wprowadź **Nazwę konta**, **Klucz klienta** i **Kontener** dla komputera Azure Data Lake Storage Gen2.
    - Informacje o tworzeniu konta magazynu do używania z Azure Data Lake Storage Gen2 można przeczytać w temacie [Utwórz konto magazynu](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account). 
    - Aby dowiedzieć się więcej o tym, jak znaleźć nazwę konta magazynu Azure Data Lake Gen2 i klucz konta, zobacz [Zarządzaj ustawieniami konta magazynu w Azure Portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).

1. Wybierz **Dalej**.

1. Zaznacz pole wyboru obok każdej encji, która ma zostać wyeksportowana do tej lokalizacji docelowej.

1. Wybierz pozycję **Zapisz**.

## <a name="export-the-data"></a>Eksportowanie danych

Możesz [eksportować dane na żądanie](export-destinations.md#export-data-on-demand). Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab).
