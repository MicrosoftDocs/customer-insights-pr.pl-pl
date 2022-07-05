---
title: Eksportuj dane Customer Insights do InMobi
description: Dowiedz się, jak skonfigurować połączenie i eksport do InMobi.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9056548"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Eksportowanie listy segmentów i innych danych do InMobi (wersja zapoznawcza)

Eksportowanie list segmentów lub innych danych z wystąpienia Customer Insights do [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Wymagania wstępne

1. Użytkownik ma poświadczenia administratora i [konta InMobi](https://www.inmobi.com/).
1. Masz nazwę konta Azure Blob Storage i odpowiedni klucz konta. Aby uzyskać więcej informacji, przejrzyj temat [Zarządzanie ustawieniami konta magazynu w portalu Azure](/azure/storage/common/storage-account-manage). Na koncie magazynu jest kontener w celu eksportowania danych do InMobi. Aby uzyskać więcej informacji, zobacz temat [Tworzenie kontenera](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. Program InMobi utworzy bezpośrednie połączenie z magazynem Blob Storage i skonfiguruje automatyczne importowanie danych do programu InMobi. W celu zainicjowania procesu należy skontaktować się z przedstawicielem firmy InMobi.

## <a name="known-limitations"></a>Znane ograniczenia

1. W przypadku usługi Azure Blob Storage można wybrać [warstwę wydajności Standardowa lub Premium](/azure/storage/blobs/storage-blob-performance-tiers). Jeśli wybierzesz warstwę wydajności Premium, wybierz [jako typ konta blokowe obiekty blob typu premium](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Konfigurowanie połączenia z magazynem Azure Blob Storage i konfigurowanie eksportu

1. Postępuj zgodnie z instrukcjami, aby [skonfigurować połączenie z magazynem Azure Blob Storage](export-azure-blob-storage.md).
2. Postępuj zgodnie z podanym instrukcjami , aby [skonfigurować eksport](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
