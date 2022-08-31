---
title: Używanie własnego konta Azure Data Lake Storage Gen2
author: mukeshpo
description: Dowiedz się więcej o wymaganiach dotyczących używania własnego konta Azure Data Lake Storage do przechowywania danych Customer Insights.
ms.author: mukeshpo
ms.date: 08/15/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 5e4b9348f06d4e5e10b4499ad86b38c9d52da1f5
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304394"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Używanie własnego konta Azure Data Lake Storage Gen2

Dynamics 365 Customer Insights pozwala przechowywać wszystkie dane w [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction). Zapisując dane w Data Lake Storage, zgadzasz się, że dane będą przesyłane i przechowywane w odpowiedniej lokalizacji geograficznej dla tego konta usługi Azure Storage. Aby uzyskać więcej informacji, zobacz temat [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Administratorzy usługi Customer Insights mogą [tworzyć środowiska](create-environment.md) i [określać opcję](create-environment.md#step-2-configure-data-storage) magazynowania danych w procesie.

## <a name="prerequisites"></a>Wymagania wstępne

- Konta Azure Data Lake Storage muszą znajdować się w tym samym regionie azure, który został wybrany podczas tworzenia środowiska Customer Insights. Aby poznać region usługi dla środowiska, przejdź do **Administrator** > **System** > **Informacje** w Customer Insights.
- Konto Data Lake Storage musi być Gen2. Konta magazynu usługi Azure Data Lake Gen1 nie są obsługiwane.
- Konto magazynu Azure Data Lake Storage musi mieć [włączoną hierarchiczną przestrzeń nazw](/azure/storage/blobs/data-lake-storage-namespace).
- Kontener o nazwie `customerinsights` musi istnieć na koncie magazynu. Należy ją utworzyć przed użyciem własnego magazynu danych i Data Lake Storage w funkcji Customer Insights.
- Administrator konfigurujący środowisko Customer Insights potrzebuje roli współautor danych obiektów blob magazynu lub właściciela danych obiektu blob magazynu na koncie magazynu lub kontenerze `customerinsights`. Aby uzyskać więcej informacji na temat przypisywania uprawnień do konta magazynu, zobacz [Tworzenie konta magazynu](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>Łączenie Customer Insights z kontem w magazynie

Podczas tworzenia nowego środowiska upewnij się, że istnieje konto Data Lake Storage i wszystkie wymagania wstępne są spełnione.

1. W kroku **Przechowywanie danych** podczas tworzenia środowiska ustaw **Zapisz dane wyjściowe** na **Azure Data Lake Storage Gen2**.
1. Wybierz sposób **podłączenia magazynu**. Można wybrać opcję opartą na zasobach i opcję uwierzytelniania opartą na subskrypcji. Aby uzyskać więcej informacji, zobacz [Łączenie z kontem Azure Data Lake Storage przy użyciu głównej usługi Azure](connect-service-principal.md).
   - W przypadku **Subskrypcja Azure** wybierz **Subskrypcja**, **Grupa zasobów** i **Konto magazynu** zawierające kontener `customerinsights`.
   - W przypadku **Klucz konta** podaj **Nazwa konta** i **Klucz konta** dla konta Data Lake Storage. Zastosowanie tej metody uwierzytelniania oznacza, że użytkownik jest informowany o tym, czy organizacja używa kluczy. Podczas obracania [należy zaktualizować konfigurację środowiska](manage-environments.md#edit-an-existing-environment) przy użyciu nowego klucza.
1. Określ, czy używać łącza Azure Private Link do łączenia się z kontem magazynu i [Tworzenia połączenia z łączem Private Link](security-overview.md#set-up-an-azure-private-link).

Po zakończeniu procesów systemowych, takich jak pozyskiwanie danych, system tworzy odpowiednie foldery na koncie magazynu. Pliki danych i pliki model.json są tworzone i dodawane do folderów na podstawie nazwy procesu.

W przypadku utworzenia kilku środowisk usługi Customer Insights i zapisania encji wyjściowych z tych środowisk do konta magazynu aplikacja Customer Insights utworzy oddzielne foldery dla każdego środowiska z elementem `ci_environmentID` w kontenerze.
