---
title: Eksportowanie danych do magazynu Azure Blob Storage (wersja zapoznawcza)
description: Dowiedz się, jak skonfigurować połączenie i eksport do magazynu Blob Storage.
ms.date: 06/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 059c8364ca0f3740bc0e4ffeeeba94246c9e5696
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055503"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Eksportowanie danych do magazynu Azure Blob Storage (wersja zapoznawcza)

Przechowuj dane aplikacji Customer Insights w usłudze Blob Storage lub korzystaj z niej, aby przenosić swoje dane do innych aplikacji.

## <a name="known-limitations"></a>Znane ograniczenia

1. W przypadku usługi Azure Blob Storage można wybrać [warstwę wydajności Standardowa lub Premium](/azure/storage/blobs/storage-blob-performance-tiers). Jeśli wybierzesz warstwę wydajności Premium, wybierz [jako typ konta blokowe obiekty blob typu premium](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-blob-storage"></a>Skonfiguruj połączenie z usługą Blob Storage

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Azure Blob Storage**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wprowadź **Nazwę konta**, **Klucz klienta** i **Kontener** dla konta Blob Storage.
    - Aby dowiedzieć się, jak znaleźć nazwę i klucz klienta konta Blob Storage, zobacz [Zarządzanie ustawieniami konta magazynu w portalu Azure Portal](/azure/storage/common/storage-account-manage).
    - Aby dowiedzieć się, jak utworzyć kontener, zobacz [Tworzenie kontenera](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Aby zakończyć połączenie, wybierz **Zapisz**. 

## <a name="configure-an-export"></a>Konfigurowanie eksportu

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

> [!IMPORTANT]
> Jeśli włączone jest ustawienie usuwania nietrwałego dla konta usługi Azure Blob Storage, eksportowanie zakończy się niepowodzeniem. Wyłącz usuwanie nietrwałe, aby wyeksportować dane do obiektów blob. Aby uzyskać więcej informacji, zobacz [Włączanie usuwania nietrwałego obiektu blob](/azure/storage/blobs/soft-delete-blob-enable)

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Azure Blob Storage. Jeśli nie widzisz tej nazwy sekcji, to znaczy, że nie masz dostępu do żadnych połączeń tego typu.

1. Zaznacz pole wyboru obok każdej encji, która ma zostać wyeksportowana do tej lokalizacji docelowej.

1. Wybierz pozycję **Zapisz**.

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab).

Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).

Wyeksportowane dane są przechowywane w skonfigurowanym kontenerze Blob Storage. W kontenerze są automatycznie tworzone następujące ścieżki folderów:

- Dla encji źródłowych i encji wygenerowanych przez system:   
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - Przykład: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
  
  > [!TIP]
  > Eksportowanie encji zawierających dużą ilość danych może powodować wyeksportowanie wielu plików CSV w tym samym folderze dla każdego eksportu. Podział eksportu odbywa się ze względów wydajności w celu zminimalizowania czasu jego zakończenia.

- Element model.json dla eksportowanych encji będzie na poziomie %ExportDestinationName%.  
  - Przykład: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE [footer-include](includes/footer-banner.md)]
