---
title: Eksportowanie danych Customer Insights do Azure Data Lake Storage Gen2
description: Dowiedz się, jak skonfigurować połączenie z Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760064"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a>Skonfiguruj połączenie z usługą Azure Data Lake Storage Gen2 (wersja zapoznawcza)

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
