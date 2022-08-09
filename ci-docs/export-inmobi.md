---
title: Eksportuj dane Customer Insights do InMobi
description: Dowiedz się, jak skonfigurować połączenie i eksport do InMobi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195901"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Eksportuj dane Customer Insights do InMobi (wersja zapoznawcza)

Eksportowanie list segmentów lub innych danych z wystąpienia Customer Insights do [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Wymagania wstępne

- Poświadczenia administratora i [konta InMobi](https://www.inmobi.com/).
- Nazwa [konta Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account) klucz konta. Aby znaleźć nazwę i klucz, zobacz [Zarządzanie ustawieniami konta magazynu w portalu Azure Portal](/azure/storage/common/storage-account-manage).
- [Kontener usługi Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) do eksportowania danych InMobi.
- Program InMobi utworzy bezpośrednie połączenie z magazynem Blob Storage i skonfiguruje automatyczne importowanie danych do programu InMobi. W celu zainicjowania procesu należy skontaktować się z przedstawicielem firmy InMobi.

## <a name="known-limitations"></a>Znane ograniczenia

- W przypadku usługi Azure Blob Storage wybierz [warstwę wydajności Standardowa lub Premium](/azure/storage/blobs/storage-blob-performance-tiers). Jeśli wybierzesz warstwę wydajności Premium, wybierz [jako typ konta blokowe obiekty blob typu premium](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>Skonfiguruj połączenie z usługą Azure Blob Storage

[Skonfiguruj połączenie z usługą Azure Blob Storage](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>Konfigurowanie eksportu

[Konfigurowanie eksportu](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
