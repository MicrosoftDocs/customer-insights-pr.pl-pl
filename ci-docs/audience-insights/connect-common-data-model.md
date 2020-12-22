---
title: Połącz dane Common Data Model z kontem Azure Data Lake
description: Pracuj z danymi Common Data Model przy użyciu usługi Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643471"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Połącz z folderem Common Data Model za pomocą Azure Data Lake Account

Ten artykuł zawiera informacje na temat pozyskiwania danych z folderu Common Data Model przy użyciu konta Azure Data Lake Storage Gen2.

## <a name="important-considerations"></a>Ważne uwagi

- Dane w usłudze Azure Data Lake muszą być zgodne ze standardem Common Data Model. W tym momencie inne formaty nie są obsługiwane.

- Pozyskiwanie danych obsługuje wyłącznie konta magazynu Azure Data Lake *Gen2*. Nie można używać kont magazynu Azure Data Lake Gen1 do pozyskiwania danych.

- Aby uwierzytelnić się przy użyciu głównej usługi platformy Azure, upewnij się, że jest ona skonfigurowana w dzierżawie. Aby uzyskać więcej informacji, zobacz temat [Połącz analizy odbiorców z kontem Azure Data Lake Storage Gen2 za pomocą głównej usługi platformy Azure](connect-service-principal.md).

- Usługa Azure Data Lake, z którą chcesz się łączyć i pozyskiwać dane, musi znajdować się w tym samym regionie Azure, co środowisko Dynamics 365 Customer Insights. Połączenia z folderem Common Data Model z data lake w innym regionie świadczenia usługi Azure nie są obsługiwane. Aby sprawdzić, jaki jest obszar Azure środowiska, przejdź do **Administrator** > **System** > **Informacje** w analizach odbiorców.

- Dane przechowywane w usługach online mogą być przechowywane w innej lokalizacji niż ta, w której dane są przetwarzane lub przechowywane w Dynamics 365 Customer Insights. Importując lub łącząc się z danymi w usługach online, użytkownik zgadza się, że dane mogą być przenoszone do programu Dynamics 365 Customer Insights i przechowywane w nim. [Dowiedz się więcej w Centrum zaufania firmy Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-model-folder"></a>Połącz z folderem modelu Common Data Model

1. W analizach odbiorców przejdź do **Dane** > **Źródła danych**.

1. Wybierz **Dodaj źródła danych**.

1. Wybierz opcję **Połącz z folderem Common Data Model**, wprowadź **Nazwę** źródła danych i wybierz przycisk **Dalej**.

1. Można wybrać między opcją opartą na zasobach a opcją opartą na subskrypcji na potrzeby uwierzytelniania. Aby uzyskać więcej informacji, zobacz temat [Połącz analizy odbiorców z kontem Azure Data Lake Storage Gen2 za pomocą głównej usługi platformy Azure](connect-service-principal.md). Wprowadź informacje o **Kontenerze** i wybierz opcję **Dalej**.
   > [!div class="mx-imgBorder"]
   > ![Okno dialogowe, w którym można wprowadzić szczegółowe dane dotyczące połączenia z Azure Data Lake](media/enter-new-storage-details.png)

1. W oknie dialogowym **Wybierz folder Common Data Model** wybierz plik model.json w celu zaimportowania danych z programu i wybierz przycisk **Dalej**.
   > [!NOTE]
   > Żaden plik model.json powiązany z innym źródłem danych w środowisku nie zostanie wyświetlony na liście.

1. Otrzymasz listę dostępnych encji w wybranym pliku model.json. Możesz przeanalizować i wybrać z listy dostępnych encji i wybrać **Zapisz**. Wszystkie wybrane encje zostaną pozyskane z nowego źródła danych.
   > [!div class="mx-imgBorder"]
   > ![Okno dialogowe pokazujące listę encji z pliku model.json](media/review-entities.png)

8. Określ, dla których encji danych chcesz włączyć profilowanie danych i wybierz **Zapisz**. Dzięki profilowaniu danych można korzystać z analiz i innych możliwości. Możesz wybrać całą encję, która wybiera wszystkie atrybuty z encji lub wybrane atrybuty. Domyślnie żadne encje nie są włączone do profilowania danych.
   > [!div class="mx-imgBorder"]
   > ![Okno dialogowe pokazujące Profilowanie danych](media/dataprofiling-entities.png)

9. Po zapisaniu wybranych opcji zostanie otwarta strona **Źródła danych**. Łącze do folderu Common Data Model powinno być teraz widoczne jako źródło danych.

> [!NOTE]
> Plik typu model.json może mieć skojarzenie tylko jedno źródło danych w tym samym środowisku. Jednak ten sam plik model.json może być używany dla źródeł danych w wielu środowiskach.

## <a name="edit-a-common-data-model-folder-data-source"></a>Edytowanie źródła danych folderu Common Data Model

Możesz zaktualizować klucz dostępu dla konta magazynu zawierającego folder Common Data Model. Użytkownik może również zmienić plik model.json. Aby połączyć się z innym kontenerem z konta magazynu lub zmienić nazwę konta, [utwórz nowe połączenie źródła danych](#connect-to-a-common-data-model-folder).

1. W analizach odbiorców przejdź do **Dane** > **Źródła danych**.

2. Kliknij wielokropek obok źródła danych, który chcesz zaktualizować.

3. Wybierz opcję **Edytuj** z listy.

4. Opcjonalnie zaktualizuj **Klucz dostępu** i wybierz **Dalej**.

   ![Dialog pozwalający edytować i aktualizować klucz dostępu dla istniejącego źródła danych](media/edit-access-key.png)

5. Opcjonalnie można zaktualizować połączenie z klucza konta do połączenia opartego na zasobach lub subskrypcji. Aby uzyskać więcej informacji, zobacz temat [Połącz analizy odbiorców z kontem Azure Data Lake Storage Gen2 za pomocą głównej usługi platformy Azure](connect-service-principal.md). Podczas aktualizowania połączenia nie można zmieniać informacji o **Kontenerze**.
   > [!div class="mx-imgBorder"]
   > ![Okno dialogowe, w którym można wprowadzić szczegółowe dane dotyczące połączenia z Azure Data Lake](media/enter-existing-storage-details.png)

6. Opcjonalnie wybierz inny plik model.json z innym zestawem encji z kontenera.

7. Można też wybrać dodatkowe encje do pobrania. Jeśli nie ma zależności, można również usunąć wszystkie wybrane encje.

   > [!IMPORTANT]
   > Jeśli istnieją zależności między istniejącym plikiem model.json a zestawem encji, zostanie wyświetlony komunikat o błędzie i nie będzie można wybrać innego pliku model.json. Usuń te zależności przed zmodyfikowaniem pliku model.json lub utwórz nowe źródło danych za pomocą pliku typu model.json, którego chcesz użyć, aby zapobiec usuwaniu zależności.

8. Opcjonalnie możesz wybrać dodatkowe atrybuty lub encje, aby włączyć profilowanie danych lub wyłączyć już wybrane.   
