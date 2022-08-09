---
title: Eksportowanie danych do magazynu Azure Blob Storage (wersja zapoznawcza)
description: Dowiedz się, jak skonfigurować połączenie i eksport do magazynu Blob Storage.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195717"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Eksportowanie danych do magazynu Azure Blob Storage (wersja zapoznawcza)

Przechowuj dane aplikacji Customer Insights w usłudze Blob Storage lub korzystaj z niej, aby przenosić swoje dane do innych aplikacji.

## <a name="prerequisites"></a>Wymagania wstępne

- Nazwa [konta Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account) klucz konta. Aby znaleźć nazwę i klucz, zobacz [Zarządzanie ustawieniami konta magazynu w portalu Azure Portal](/azure/storage/common/storage-account-manage).
- [Kontener Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Znane ograniczenia

- W przypadku usługi Azure Blob Storage wybierz [warstwę wydajności Standardowa lub Premium](/azure/storage/blobs/storage-blob-performance-tiers). Jeśli wybierzesz warstwę wydajności Premium, wybierz [jako typ konta blokowe obiekty blob typu premium](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>Skonfiguruj połączenie z usługą Blob Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz pozycję **Azure Blob Storage**.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Domyślnie – tylko administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wprowadź **Nazwę konta**, **Klucz klienta** i **Kontener** dla konta Blob Storage.

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

Aby skonfigurować ten eksport, należy mieć [uprawnienia](export-destinations.md#set-up-a-new-export) do tego typu połączenia.

> [!IMPORTANT]
> Jeśli włączone jest ustawienie [usuwania nietrwałego](/azure/storage/blobs/soft-delete-blob-enable) dla konta usługi Azure Blob Storage, eksportowanie zakończy się niepowodzeniem. Wyłącz usuwanie nietrwałe, aby wyeksportować dane do obiektów blob.

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz opcję **Dodaj eksport**.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Azure Blob Storage. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wpisz nazwę eksportu.

1. Wprowadź nazwę folderu magazynu obiektów blob.

1. Zaznacz pole wyboru obok każdej encji, która ma zostać wyeksportowana do tej lokalizacji docelowej.

1. Wybierz pozycję **Zapisz**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Wyeksportowane dane są przechowywane w skonfigurowanym kontenerze Blob Storage. W kontenerze są automatycznie tworzone następujące ścieżki folderów:

- Dla encji źródłowych i encji wygenerowanych przez system:   
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Przykład: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > Eksportowanie encji zawierających dużą ilość danych może powodować wyeksportowanie wielu plików CSV w tym samym folderze dla każdego eksportu. Podział eksportu odbywa się ze względów wydajności w celu zminimalizowania czasu jego zakończenia.

- Element model.json dla eksportowanych encji znajduje się na poziomie *%ExportDestinationName%*.  
  
  Przykład: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
