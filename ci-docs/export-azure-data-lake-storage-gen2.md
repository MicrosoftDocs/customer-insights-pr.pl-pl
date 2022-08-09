---
title: Eksportowanie danych do usługi Azure Data Lake Storage Gen2 (wersja zapoznawcza)
description: Dowiedz się, jak skonfigurować połączenie z Azure Data Lake Storage Gen2.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196453"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Eksportowanie danych do usługi Azure Data Lake Storage Gen2 (wersja zapoznawcza)

Przechowuj dane aplikacji Customer Insights na koncie usługi Data Lake Storage Gen2 lub korzystaj z niej, aby transferować swoje dane do innych aplikacji.

## <a name="prerequisites"></a>Wymagania wstępne

- [Konto magazynu, aby używać Azure Data Lake Gen 2](/azure/storage/blobs/create-data-lake-storage-account). Aby znaleźć nazwę i klucz konta magazynu, zobacz [Zarządzanie ustawieniami konta magazynu w portalu Azure Portal](/azure/storage/common/storage-account-manage).
- [Kontener Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Znane ograniczenia

- W przypadku Azure Data Lake Storage Gen2 można wybrać [warstwę wydajności Standardowa lub Premium](/azure/storage/blobs/create-data-lake-storage-account). Jeśli wybierzesz warstwę wydajności Premium, wybierz [jako typ konta blokowe obiekty blob typu premium](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Konfigurowanie połączenia z usługą Azure Data Lake Storage Gen2

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz pozycję **Azure Data Lake Gen 2**.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Domyślnie – tylko administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wprowadź **Nazwę konta**, **Klucz klienta** i **Kontener** dla komputera Azure Data Lake Storage Gen2.

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz opcję **Dodaj eksport**.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Azure Data Lake. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wpisz nazwę eksportu.

1. Wprowadź nazwę folderu magazynu obiektów Azure Data Lake Storage Gen2.

1. Zaznacz pole wyboru obok każdej encji, która ma zostać wyeksportowana do tej lokalizacji docelowej.

1. Wybierz pozycję **Zapisz**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Wyeksportowane dane są przechowywane w skonfigurowanym kontenerze magazynu Azure Data Lake Gen 2.

> [!TIP]
> Eksportowanie encji zawierających dużą ilość danych może powodować wyeksportowanie wielu plików CSV w tym samym folderze dla każdego eksportu. Podział eksportu odbywa się ze względów wydajności w celu zminimalizowania czasu jego zakończenia.

[!INCLUDE [footer-include](includes/footer-banner.md)]
