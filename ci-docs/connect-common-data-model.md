---
title: Połącz z folderem Common Data Model za pomocą Azure Data Lake Account
description: Pracuj z danymi Common Data Model przy użyciu usługi Azure Data Lake Storage.
ms.date: 05/30/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: b1cdcb46df17d722ad49d361ae4c7ab34c83eeb1
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081306"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Tworzenie połączenia z danymi w programie Azure Data Lake Storage

Pozyskiwanie danych do Dynamics 365 Customer Insights przy użyciu konta Azure Data Lake Storage Gen2. Pozyskiwanie danych może być pełna lub stopniowe.

## <a name="prerequisites"></a>Wymagania wstępne

- Pozyskiwanie danych obsługuje tylko konta Azure Data Lake Storage *Gen2*. Nie można używać kont magazynu Data Lake Storage Gen1 do pozyskiwania danych.

- Konto usługi Azure Data Lake Storage musi mieć [włączone hierarchiczne obszary nazw](/azure/storage/blobs/data-lake-storage-namespace). Dane muszą być przechowywane w hierarchicznym formacie folderów definiującym folder główny, który ma podfoldery dla każdej encji. Podfoldery mogą mieć pełne dane lub stopniowe foldery danych.

- Aby uwierzytelnić się przy użyciu głównej usługi platformy Azure, upewnij się, że jest ona skonfigurowana w dzierżawie. Aby uzyskać więcej informacji, zobacz [Łączenie z kontem Azure Data Lake Storage Gen2 przy użyciu głównej usługi Azure](connect-service-principal.md).

- Usługa Azure Data Lake Storage, którą chcesz połączyć i z której chcesz pozyskiwać dane musi znajdować się w tym samym regionie Azure, co środowisko Dynamics 365 Customer Insights. Połączenia z folderem Common Data Model z data lake w innym regionie świadczenia usługi Azure nie są obsługiwane. Aby poznać region usługi Azure dla środowiska, przejdź do **Administrator** > **System** > **Informacje** w Customer Insights.

- Dane przechowywane w usługach online mogą być przechowywane w innej lokalizacji niż ta, w której dane są przetwarzane lub przechowywane w Dynamics 365 Customer Insights. Importując lub łącząc się z danymi w usługach online, użytkownik zgadza się, że dane mogą być przenoszone do programu Dynamics 365 Customer Insights i przechowywane w nim. [Dowiedz się więcej w Centrum zaufania firmy Microsoft](https://www.microsoft.com/trust-center).

- Aby uzyskać dostęp do konta magazynu, główna usługa Customer Insights musi mieć jedną z następujących ról. Aby uzyskać więcej informacji, zobacz [Nadaj uprawnienia usłudze głównej w celu uzyskania dostępu do konta magazynu](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account).
  - Czytnik danych Storage Blob
  - Właściciel danych Storage Blob
  - Współautor danych w usłudze Blob Storage

- Dane w magazynie Data Lake Storage powinny być zgodne ze standardem Common Data Model dla przechowywania danych oraz mają wspólny model danych reprezentujący schemat plików danych (*.csv lub *.parquet). W manifeście muszą być podane szczegółowe informacje o encjach, takie jak kolumny encji i typy danych, a także o lokalizacji i typie pliku danych. Aby uzyskać więcej informacji, zobacz [Manifest Common Data Model](/common-data-model/sdk/manifest). Jeśli ten manifest nie istnieje, administratorzy z dostępem właściciela danych obiektów blob magazynu lub współautora danych obiektów blob magazynu mogą zdefiniować schemat podczas pozyskiwania danych.

## <a name="connect-to-azure-data-lake-storage"></a>Nawiązywanie połączenia z rozwiązaniem Azure Data Lake Storage

1. Przejdź do **Dane** > **Źródła danych**.

1. Wybierz **Dodaj źródła danych**.

1. Wybierz **Azure data lake storage**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Okno dialogowe, w którym można wprowadzić szczegółowe dane dotyczące połączenia z Azure Data Lake." lightbox="media/data_sources_ADLS.png":::

1. Wprowadź **Nazwa** dla źródła danych i opcjonalnie **Opis**. Nazwa w sposób unikatowy określa źródło danych, do których odwołuje się w procesach w dół i nie można jej zmienić.

1. Wybierz jedną z następujących opcji **Połącz używanie magazynu**. Aby uzyskać więcej informacji, zobacz [Łączenie Customer Insights z kontem Azure Data Lake Storage Gen2 przy użyciu głównej usługi Azure](connect-service-principal.md).

   - **Zasób Azure**: Wprowadź **Identyfikator zasobu**. Opcjonalnie, jeśli chcesz uzyskać dane z konta magazynu za pośrednictwem łącza Azure Private Link, wybierz opcję **Włącz łącze prywatne**. Aby uzyskać więcej informacji, zobacz [Łącza Private Links](security-overview.md#private-links-tab).
   - **Subskrypcja Azure**: wybierz **Subskrypcję**, a następnie konto **Grupa zasobów** i **Konto magazynu**. Opcjonalnie, jeśli chcesz uzyskać dane z konta magazynu za pośrednictwem łącza Azure Private Link, wybierz opcję **Włącz łącze prywatne**. Aby uzyskać więcej informacji, zobacz [Łącza Private Links](security-overview.md#private-links-tab).
  
   > [!NOTE]
   > Potrzebujesz jednej z następujących ról w kontenerze lub koncie magazynu do utworzenia źródła danych:
   >
   >  - Czytnik danych obiektów blob magazynu wystarcza do odczytywania z konta magazynu i pozyskiwania danych do usługi Customer Insights. 
   >  - Współautor lub właściciel obiektów blob magazynu jest wymagany, jeśli chcesz edytować pliki manifestu bezpośrednio w Customer Insights.  
  
1. Wybierz nazwę **Kontener** zawierającą dane i schemat (plik model.json lub manifest.json), z których chcesz zaimportować dane, i wybierz przycisk **Dalej**.
   > [!NOTE]
   > Żaden plik model.json lub manifest.json powiązany z innym źródłem danych w środowisku nie zostanie wyświetlony na liście. Jednak ten sam plik model.json lub manifest.json może być używany dla źródeł danych w wielu środowiskach.

1. Aby utworzyć nowy schemat, przejdź do [Tworzenie nowego pliku schematu](#create-a-new-schema-file).

1. Aby użyć istniejącego schematu, przejdź do folderu zawierającego plik model.json lub manifest.cdm.json. Plik można wyszukać w katalogu.

1. Wybierz plik json, a następnie wybierz **Dalej**. Wyświetla się lista dostępnych encji.

   :::image type="content" source="media/review-entities.png" alt-text="Okno dialogowe listy encji do wybrania":::

1. Wybierz encje, które chcesz uwzględnić.

   :::image type="content" source="media/ADLS_required.png" alt-text="Okno dialogowe przedstawiające wymaganie dla klucza podstawowego":::

   > [!TIP]
   > Aby edytować encje w interfejsie edycji JSON, zaznacz opcję **Pokaż więcej** > **Edytuj plik schematu**. Wprowadź zmiany i wybierz **Zapisz**.

1. W przypadku wybranych encji, które wymagają pozyskiwania, opcja **Wymagane** jest wyświetlana w obszarze **Odświeżanie przyrostowe**. Aby uzyskać informacje o tych encjach, zobacz [Konfigurowanie odświeżania przyrostowego źródeł danych platformy Azure Data](incremental-refresh-data-sources.md).

1. W przypadku wybranych encji, których klucz podstawowy nie został zdefiniowany, opcja **Wymagane** jest wyświetlana w obszarze **Klucz podstawowy**. Dla każdej z tych encji:
   1. Wybierz **Wymagane**. Zostanie wyświetlony panel **Edytowanie encji**.
   1. Wybierz **Klucz podstawowy**. Klucz podstawowy jest atrybutem unikalnym dla danej encji. Aby atrybut był prawidłowym kluczem podstawowym, nie może zawierać zduplikowanych wartości, brakujących wartości ani wartości null. Atrybuty typu ciąg, liczba całkowita i GUID są obsługiwane jako klucze podstawowe.
   1. Opcjonalnie można zmienić wzorzec partycji.
   1. Wybierz **Zamknij**, by zapisać i zamknąć panel.

1. Wybierz liczbę **Atrybutów** dla każdej dołączonej encji. Zostanie wyświetlona strona **Zarządzanie atrybutami**.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Okno dialogowe do wybrania profilowania danych.":::

   1. Tworzenie nowych atrybutów, edytowanie lub usuwanie istniejących atrybutów. Można zmienić nazwę, format danych lub dodać typ semantyczny.
   1. Aby włączyć analizy i inne funkcje, wybierz **Profilowanie danych** dla całej encji lub dla określonych atrybutów. Domyślnie żadne encje nie są włączone do profilowania danych.
   1. Wybierz pozycję **Gotowe**.

1. Wybierz pozycję **Zapisz**. Zostanie otwarta strona **Źródła danych** z nowymi źródło danych **Odświeżania**.

### <a name="create-a-new-schema-file"></a>Utwórz nowy plik schematu

1. Wybierz **Nowy plik schematu**.

1. Wprowadź nazwę dla pliku i wybierz **Zapisz**.

1. Wybierz **Nowa encja**. Zostanie wyświetlony panel **Nowa encja**.

1. Wprowadź nazwę encji i wybierz **Lokalizację plików danych**.
   - **Wiele plików .csv lub .parquet**: przejdź do folderu głównego, wybierz typ wzorca i wprowadź wyrażenie.
   - **Pojedyncze pliki .csv lub .parquet**: przejdź do pliku .csv lub .parquet i go zaznacz.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Okno dialogowe tworzenia nowej encji, w którym wyróżniona jest lokalizacja plików danych.":::

1. Wybierz pozycję **Zapisz**.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Okno dialogowe definiowania lub automatycznego generowania atrybutów.":::

1. Wybierz **określ atrybuty**, by ręcznie dodać atrybuty, lub wybierz opcję **automatycznego generowania atrybutów**. Aby zdefiniować atrybuty, wprowadź nazwę, wybierz format danych i opcjonalny typ semantyczny. Do automatycznego generowania atrybutów:

   1. Po automatycznym wygenerowaniu atrybutów wybierz opcję **Przejrzyj atrybuty**. Zostanie wyświetlona strona **Zarządzanie atrybutami**.

   1. Upewnij się, że format danych dla każdego atrybutu jest poprawny.

   1. Aby włączyć analizy i inne funkcje, wybierz **Profilowanie danych** dla całej encji lub dla określonych atrybutów. Domyślnie żadne encje nie są włączone do profilowania danych.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Okno dialogowe do wybrania profilowania danych.":::

   1. Wybierz pozycję **Gotowe**. Zostanie wyświetlona strona **Wybierz encje**.

1. W razie potrzeby kontynuuj dodawanie encji i atrybutów.

1. Po dodaniu wszystkich encji wybierz opcję **Uwzględnij**, aby uwzględnić encje w pozyskiwaniu źródła danych.

   :::image type="content" source="media/ADLS_required.png" alt-text="Okno dialogowe przedstawiające wymaganie dla klucza podstawowego":::

1. W przypadku wybranych encji, które wymagają pozyskiwania, opcja **Wymagane** jest wyświetlana w obszarze **Odświeżanie przyrostowe**. Aby uzyskać informacje o tych encjach, zobacz [Konfigurowanie odświeżania przyrostowego źródeł danych platformy Azure Data](incremental-refresh-data-sources.md).

1. W przypadku wybranych encji, których klucz podstawowy nie został zdefiniowany, opcja **Wymagane** jest wyświetlana w obszarze **Klucz podstawowy**. Dla każdej z tych encji:
   1. Wybierz **Wymagane**. Zostanie wyświetlony panel **Edytowanie encji**.
   1. Wybierz **Klucz podstawowy**. Klucz podstawowy jest atrybutem unikalnym dla danej encji. Aby atrybut był prawidłowym kluczem podstawowym, nie może zawierać zduplikowanych wartości, brakujących wartości ani wartości null. Atrybuty typu ciąg, liczba całkowita i GUID są obsługiwane jako klucze podstawowe.
   1. Opcjonalnie można zmienić wzorzec partycji.
   1. Wybierz **Zamknij**, by zapisać i zamknąć panel.

1. Wybierz pozycję **Zapisz**. Zostanie otwarta strona **Źródła danych** z nowymi źródło danych **Odświeżania**.


## <a name="edit-an-azure-data-lake-storage-data-source"></a>Edytuj źródło danych Azure Data Lake Storage

Możesz zaktualizować za pomocą opcji *Połącz z kontem magazynu, używając*. Aby uzyskać więcej informacji, zobacz [Łączenie Customer Insights z kontem Azure Data Lake Storage Gen2 przy użyciu głównej usługi Azure](connect-service-principal.md). Aby połączyć się z innym kontenerem z konta magazynu lub zmienić nazwę konta, [utwórz nowe połączenie źródła danych](#connect-to-azure-data-lake-storage).

1. Przejdź do **Dane** > **Źródła danych**.

1. Obok źródła danych, które chcesz zaktualizować, wybierz **Edytuj**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Okno dialogowe do edytowania źródła danych Azure Data Lake.":::

1. Zmień którekolwiek z poniższych informacji:

   - **opis**
   - **Podłącz magazyn przy użyciu** i informacje o połączeniu. Podczas aktualizowania połączenia nie można zmieniać informacji o **Kontenerze**.
      > [!NOTE]
      > Do konta lub kontenera magazynu musi być przypisana jedna z następujących ról:
        > - Czytnik danych Storage Blob
        > - Właściciel danych Storage Blob
        > - Współautor danych w usłudze Blob Storage

   - Jeśli chcesz uzyskać dane z konta magazynu za pośrednictwem łącza Azure Private Link, wybierz opcję **Włącz łącze prywatne**. Aby uzyskać więcej informacji, zobacz [Łącza Private Links](security-overview.md#private-links-tab).

1. Wybierz **Dalej**.
1. Zmień dowolną z następujących czynności:
   - Przejdź do innego pliku model.json lub manifest.json z innym zestawem obiektów z kontenera.
   - Aby dodać kolejne encje do pozyskania, wybierz opcję **Nowa encja**.
   - Aby usunąć wszystkie już zaznaczone encje, jeśli brak zależności, zaznacz encję i **Usuń**.
      > [!IMPORTANT]
      > Jeśli istnieją zależności między istniejącym plikiem model.json lub manifest.json a zestawem jednostek, zostanie wyświetlony komunikat o błędzie i nie będzie można wybrać innego pliku model.json lub manifest.json. Usuń te zależności przed zmianą pliku model.json lub manifest.json lub utwórz nowe źródło danych z plikiem model.json lub manifest.json, którego chcesz użyć, aby uniknąć usuwania zależności.
   - Aby zmienić lokalizację pliku danych lub klucz podstawowy, wybierz opcję **Edytuj**.
   - Aby zmienić dane pozyskiwania przyrostowego, zobacz [Konfigurowanie odświeżania przyrostowego źródła danych platformy Azure Data Lake](incremental-refresh-data-sources.md)

1. Wybierz **Atrybuty,** które chcesz dodać lub zmienić, albo w celu włączenia funkcji profilowania danych. Następnie wybierz **Gotowe**.

1. Kliknij przycisk **Zapisz**, aby zastosować zmiany i wrócić do strony **Źródła danych**.
