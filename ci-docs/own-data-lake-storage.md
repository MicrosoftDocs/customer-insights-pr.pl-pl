---
title: Używanie własnego konta Azure Data Lake Storage Gen2
author: mukeshpo
description: Dowiedz się więcej o wymaganiach dotyczących używania własnego konta Azure Data Lake Storage do przechowywania danych Customer Insights.
ms.author: mukeshpo
ms.date: 06/08/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: d2ff49c324c5c5c28213f362ff330d441fcb6052
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246214"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Używanie własnego konta Azure Data Lake Storage Gen2

Dynamics 365 Customer Insights pozwala przechowywać wszystkie dane w [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction).

Zapisując dane w Data Lake Storage, zgadzasz się, że dane będą przesyłane i przechowywane w odpowiedniej lokalizacji geograficznej dla tego konta usługi Azure Storage. Aby uzyskać więcej informacji, zobacz temat [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Administratorzy usługi Customer Insights mogą [tworzyć środowiska](create-environment.md) i [określać opcję](create-environment.md#step-2-configure-data-storage) magazynowania danych w procesie.

## <a name="prerequisites-to-use-your-storage-account"></a>Wymagania wstępne dotyczące korzystania z konta magazynu

- Konta Azure Data Lake Storage muszą znajdować się w tym samym regionie azure, który został wybrany podczas tworzenia środowiska Customer Insights. Region środowiska Customer Insights możesz sprawdzić w sekcji **Administrator** > **System** > **Informacje**.
- Data Lake Storage musi być Gen2 i mieć [włączoną hierarchiczną przestrzeń nazw](/azure/storage/blobs/create-data-lake-storage-account). Konta usługi Gen1 nie są obsługiwane.
- Kontener o nazwie `customerinsights` musi istnieć na koncie magazynu. Należy ją utworzyć przed użyciem własnego magazynu danych i Data Lake Storage w funkcji Customer Insights. Administrator konfigurujący środowisko Customer Insights potrzebuje roli współautor danych obiektów blob magazynu lub właściciela danych obiektu blob magazynu na koncie magazynu lub kontenerze `customerinsights`. Aby uzyskać więcej informacji na temat przypisywania uprawnień do konta magazynu, zobacz [Tworzenie konta magazynu](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>Łączenie Customer Insights z kontem w magazynie

Podczas tworzenia nowego środowiska upewnij się, że istnieje konto Data Lake Storage i wszystkie wymagania wstępne są spełnione.

1. W kroku **Przechowywanie danych** podczas tworzenia środowiska ustaw **Zapisz dane wyjściowe** na **Azure Data Lake Storage Gen2**.
1. Wybierz sposób **podłączenia magazynu**. Można wybrać opcję opartą na zasobach i opcję uwierzytelniania opartą na subskrypcji. Aby uzyskać więcej informacji, zobacz [Łączenie z kontem Azure Data Lake Storage przy użyciu głównej usługi Azure](connect-service-principal.md).
   - W przypadku **Subskrypcja Azure** wybierz **Subskrypcja**, **Grupa zasobów** i **Konto magazynu** zawierające kontener `customerinsights`.
   - W przypadku **Klucz konta** podaj **Nazwa konta** i **Klucz konta** dla konta Data Lake Storage. Zastosowanie tej metody uwierzytelniania oznacza, że użytkownik jest informowany o tym, czy organizacja używa kluczy. Podczas obracania [należy zaktualizować konfigurację środowiska](manage-environments.md#edit-an-existing-environment) przy użyciu nowego klucza.
1. Określ, czy używać łącza Azure Private Link do łączenia się z kontem magazynu i [Tworzenia połączenia z łączem Private Link](security-overview.md#set-up-an-azure-private-link) w procesie dwuetapowym.

Po zakończeniu procesów systemowych, takich jak pozyskiwanie danych, system tworzy odpowiednie foldery na koncie magazynu. Pliki danych i pliki *model.json* są tworzone i dodawane do folderów na podstawie nazwy procesu.

W przypadku utworzenia kilku środowisk usługi Customer Insights i zapisania encji wyjściowych z tych środowisk do konta magazynu aplikacja Customer Insights utworzy oddzielne foldery dla każdego środowiska z elementem `ci_environmentID` w kontenerze.
