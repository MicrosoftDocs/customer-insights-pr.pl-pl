---
title: Eksportowanie danych Customer Insights do Azure Data Lake Storage Gen2
description: Dowiedz się, jak skonfigurować połączenie z Azure Data Lake Storage Gen2.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22eee11666752459a1750d728c4e254ab0c59e58
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947243"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>Eksportowanie listy segmentów i innych danych do usługi Azure Data Lake Storage Gen 2 (wersja zapoznawcza)

Przechowuj dane aplikacji Customer Insights na koncie usługi Data Lake Storage Gen2 lub korzystaj z niej, aby transferować swoje dane do innych aplikacji.

## <a name="known-limitations"></a>Znane ograniczenia

1. Podczas tworzenia konta magazynu dla danych typu data lake użytkownik usługi Azure Data Lake Storage Gen2 może wybrać [warstwę wydajności Standardowa lub Premium](/azure/storage/blobs/create-data-lake-storage-account). Jeśli wybierzesz warstwę wydajności Premium, jako typ konta wybierz blokowe obiekty blob typu premium.

## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>Konfigurowanie połączenia z usługą Azure Data Lake Storage Gen2

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Azure Data Lake Gen 2**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wprowadź **Nazwę konta**, **Klucz klienta** i **Kontener** dla komputera Azure Data Lake Storage Gen2.
    - Informacje o tworzeniu konta magazynu do używania z Azure Data Lake Storage Gen2 można przeczytać w temacie [Utwórz konto magazynu](/azure/storage/blobs/create-data-lake-storage-account). 
    - Aby dowiedzieć się, jak znaleźć nazwę i klucz klienta konta magazynu Azure Data Lake Gen 2, zobacz [Zarządzanie ustawieniami konta magazynu w portalu Azure Portal](/azure/storage/common/storage-account-manage).

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj eksport**, aby utworzyć nowy eksport.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi **Azure Data Lake**. Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.

1. Zaznacz pole wyboru obok każdej encji, która ma zostać wyeksportowana do tej lokalizacji docelowej.

1. Wybierz pozycję **Zapisz**.

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab).
Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).

Wyeksportowane dane są przechowywane w skonfigurowanym kontenerze magazynu Azure Data Lake Gen 2.

> [!TIP]
> Eksportowanie encji zawierających dużą ilość danych może powodować wyeksportowanie wielu plików CSV w tym samym folderze dla każdego eksportu. Podział eksportu odbywa się ze względów wydajności w celu zminimalizowania czasu jego zakończenia.

[!INCLUDE [footer-include](includes/footer-banner.md)]
