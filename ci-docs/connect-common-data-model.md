---
title: Połącz dane Common Data Model z kontem Azure Data Lake
description: Pracuj z danymi Common Data Model przy użyciu usługi Azure Data Lake Storage.
ms.date: 01/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: eeb6b9d97be5f9c0b9f6cbd6dbc6985559a1cd9d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646844"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Połącz z folderem Common Data Model za pomocą Azure Data Lake Account

W tym artykule przedstawiono informacje na temat sposobu pobierania danych z Dynamics 365 Customer Insights do folderu Common Data Model przy użyciu konta Azure Data Lake Storage Gen2.

## <a name="important-considerations"></a>Ważne uwagi

- Dane w usłudze Azure Data Lake muszą być zgodne ze standardem Common Data Model. W tym momencie inne formaty nie są obsługiwane.

- Pozyskiwanie danych obsługuje wyłącznie konta magazynu Azure Data Lake *Gen2*. Nie można używać kont magazynu Azure Data Lake Gen1 do pozyskiwania danych.

- Konto magazynu Azure Data Lake Storage musi mieć [włączoną hierarchiczną przestrzeń nazw](/azure/storage/blobs/data-lake-storage-namespace).

- Aby uwierzytelnić się przy użyciu głównej usługi platformy Azure, upewnij się, że jest ona skonfigurowana w dzierżawie. Aby uzyskać więcej informacji, zobacz [Łączenie z kontem Azure Data Lake Storage Gen2 przy użyciu głównej usługi Azure](connect-service-principal.md).

- Usługa Azure Data Lake, z którą chcesz się łączyć i pozyskiwać dane, musi znajdować się w tym samym regionie Azure, co środowisko Dynamics 365 Customer Insights. Połączenia z folderem Common Data Model z data lake w innym regionie świadczenia usługi Azure nie są obsługiwane. Aby poznać region usługi Azure dla środowiska, przejdź do **Administrator** > **System** > **Informacje** w Customer Insights.

- Dane przechowywane w usługach online mogą być przechowywane w innej lokalizacji niż ta, w której dane są przetwarzane lub przechowywane w Dynamics 365 Customer Insights. Importując lub łącząc się z danymi w usługach online, użytkownik zgadza się, że dane mogą być przenoszone do programu Dynamics 365 Customer Insights i przechowywane w nim. [Dowiedz się więcej w Centrum zaufania firmy Microsoft](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-common-data-model-folder"></a>Połącz z folderem modelu Common Data Model

1. Przejdź do **Dane** > **Źródła danych**.

1. Wybierz **Dodaj źródła danych**.

1. Wybierz **Azure data lake storage**, wprowadź **Nazwę** źródła danych, a następnie wybierz **Następny**.

   - Jeśli zostaniesz o to poproszony, wybierz jeden z przykładowych zestawów danych, który dotyczy Twojej branży, a następnie wybierz **Dalej**. 

1. Można wybrać między opcją opartą na zasobach a opcją opartą na subskrypcji na potrzeby uwierzytelniania. Aby uzyskać więcej informacji, zobacz [Łączenie z kontem Azure Data Lake Storage Gen2 przy użyciu głównej usługi Azure](connect-service-principal.md). Wpisz **Adres serwera**, wybierz **Zaloguj się**, a następnie wybierz **Następny**.
   > [!div class="mx-imgBorder"]
   > ![Okno dialogowe umożliwiające wprowadzenie nowych szczegółów połączenia dla usługi Azure Data Lake.](media/enter-new-storage-details.png)
   > [!NOTE]
   > Potrzebujesz jednej z następujących ról do kontenera lub konta magazynu, o którym mowa powyżej, aby móc nawiązać połączenie i utworzyć źródło danych:
   >  - Czytnik danych Storage Blob
   >  - Właściciel danych Storage Blob
   >  - Współautor danych w usłudze Blob Storage

1. W oknie dialogowym **Wybierz folder Common Data Model** wybierz plik model.json lub manifest.json w celu zaimportowania danych z programu i wybierz przycisk **Dalej**.
   > [!NOTE]
   > Żaden plik model.json lub manifest.json powiązany z innym źródłem danych w środowisku nie zostanie wyświetlony na liście.

1. Zobaczysz listę dostępnych encji w wybranym pliku model.json lub manifest.json. Przejrzyj i wybierz z listy dostępnych podmiotów, a następnie wybierz **Zapisz**. Wszystkie wybrane encje zostaną pozyskane z nowego źródła danych.
   > [!div class="mx-imgBorder"]
   > ![Okno dialogowe pokazujące listę encji z pliku model.json.](media/review-entities.png)

8. Określ, dla których encji danych chcesz włączyć profilowanie danych, następnie wybierz **Zapisz**. Dzięki profilowaniu danych można korzystać z analiz i innych możliwości. Możesz wybrać całą encję, która wybiera wszystkie atrybuty z encji lub wybrane atrybuty. Domyślnie żadne encje nie są włączone do profilowania danych.
   > [!div class="mx-imgBorder"]
   > ![Okno dialogowe pokazujące Profilowanie danych.](media/dataprofiling-entities.png)

9. Po zapisaniu wybranych opcji zostanie otwarta strona **Źródła danych**. Łącze do folderu Common Data Model powinno być teraz widoczne jako źródło danych.

> [!NOTE]
> Plik typu model.json lub manifest.json może mieć skojarzenie tylko jedno źródło danych w tym samym środowisku. Jednak ten sam plik model.json lub manifest.json może być używany dla źródeł danych w wielu środowiskach.

## <a name="edit-a-common-data-model-folder-data-source"></a>Edytowanie źródła danych folderu Common Data Model

Możesz zaktualizować klucz dostępu dla konta magazynu zawierającego folder Common Data Model. Można również zmienić plik model.json lub manifest.json. Aby połączyć się z innym kontenerem z konta magazynu lub zmienić nazwę konta, [utwórz nowe połączenie źródła danych](#connect-to-a-common-data-model-folder).

1. Przejdź do **Dane** > **Źródła danych**.

2. Kliknij wielokropek obok źródła danych, który chcesz zaktualizować.

3. Wybierz opcję **Edytuj** z listy.

4. Opcjonalnie zaktualizuj **Klucz dostępu** i wybierz **Dalej**.

   ![Dialog pozwalający edytować i aktualizować klucz dostępu dla istniejącego źródła danych.](media/edit-access-key.png)

5. Opcjonalnie można zaktualizować połączenie z klucza konta do połączenia opartego na zasobach lub subskrypcji. Aby uzyskać więcej informacji, zobacz [Łączenie z kontem Azure Data Lake Storage Gen2 przy użyciu głównej usługi Azure](connect-service-principal.md). Podczas aktualizowania połączenia nie można zmieniać informacji o **Kontenerze**.
   > [!div class="mx-imgBorder"]

   > ![Okno dialogowe wprowadzania szczegółów połączenia dla danych Azure Data Lake do istniejącego konta magazynu.](media/enter-existing-storage-details.png)

   > [!NOTE]
   > Potrzebujesz jednej z następujących ról do kontenera lub konta magazynu, o którym mowa powyżej, aby móc nawiązać połączenie i utworzyć źródło danych:
   >  - Czytnik danych Storage Blob
   >  - Właściciel danych Storage Blob
   >  - Współautor danych w usłudze Blob Storage


6. Opcjonalnie wybierz inny plik model.json lub manifest.json z innym zestawem jednostek z kontenera.

7. Można też wybrać dodatkowe encje do pobrania. Jeśli nie ma zależności, można również usunąć wszystkie wybrane encje.

   > [!IMPORTANT]
   > Jeśli istnieją zależności między istniejącym plikiem model.json lub manifest.json a zestawem jednostek, zostanie wyświetlony komunikat o błędzie i nie będzie można wybrać innego pliku model.json lub manifest.json. Usuń te zależności przed zmianą pliku model.json lub manifest.json lub utwórz nowe źródło danych z plikiem model.json lub manifest.json, którego chcesz użyć, aby uniknąć usuwania zależności.

8. Opcjonalnie możesz wybrać dodatkowe atrybuty lub encje, aby włączyć profilowanie danych lub wyłączyć już wybrane.   


[!INCLUDE [footer-include](includes/footer-banner.md)]
