---
title: Eksportowanie danych Customer Insights do Azure Data Lake Storage Gen2
description: Dowiedz się, jak skonfigurować połączenie z Azure Data Lake Storage Gen2.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 934c396559d4c4be8e640917d2265805753eb62d
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/06/2021
ms.locfileid: "7605916"
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

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab). Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand). 

Wyeksportowane dane są przechowywane w skonfigurowanym kontenerze magazynu Azure Data Lake Gen 2. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
