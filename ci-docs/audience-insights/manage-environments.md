---
title: Utwórz środowisko i zarządzaj nim.
description: Dowiedz się, jak zapisać się w usłudze i zarządzać środowiskami.
ms.date: 03/26/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8cc1401251ed7c45c598bd4a8fb33a9709fabbc8
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887999"
---
# <a name="manage-environments"></a>Zarządzaj środowiskami

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

W tym artykule wyjaśniono, jak utworzyć nową organizację i zastrzec bezpieczeństwo środowiska.

## <a name="sign-up-and-create-an-organization"></a>Tworzenie konta i organizacja

1. Przejdź do witryny internetowej [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).

2. Wybierz **Rozpocznij**.

3. Wybierz preferowany scenariusz zapisywania i wybierz odpowiednie łącze.

4. Zaakceptuj warunki, a następnie wybierz **Dalej**, aby rozpocząć tworzenie organizacji.

5. Po utworzeniu środowiska nastąpi przekierowanie do [Customer Insights](https://home.ci.ai.dynamics.com).

6. Użyj środowiska pokazowego, aby eksplorować aplikację, lub utwórz nowe środowisko, wykonując kroki opisane w następnej sekcji.

7. Po określeniu ustawień środowiska wybierz **Utwórz**.

8. Po pomyślnym utworzeniu środowiska użytkownik zostanie zalogowany.

## <a name="create-an-environment-in-an-existing-organization"></a>Tworzenie środowiska w istniejącej organizacji

Istnieją dwa sposoby utworzenia nowego środowiska. Można określić zupełnie nową konfigurację lub skopiować niektóre ustawienia konfiguracji z istniejącego środowiska.

> [!NOTE]
> Organizacje mogą utworzyć *dwa* środowiska dla każdej licencji usługi Customer Insights. Jeśli organizacja kupuje więcej niż jedną licencję, [skontaktuj się z zespołem pomocy technicznej](https://go.microsoft.com/fwlink/?linkid=2079641) w celu zwiększenia liczby dostępnych środowisk. Aby uzyskać więcej informacji dotyczących pojemności i wydajności dodatku, pobierz [Przewodnik licencjonowania usługi Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Aby utworzyć nowe środowisko:

1. Wybierz selektor **Środowiska** w nagłówku aplikacji.

1. Wybierz **Nowy**.

   > [!div class="mx-imgBorder"]
   > ![Ustawienia środowiska](media/environment-settings-dialog.png)

1. W oknie dialogowym **Tworzenie nowego środowiska** wybierz **Nowe środowisko**.

   Jeśli chcesz [kopiować dane z bieżącego środowiska](#considerations-for-copy-configuration-preview), wybierz **Kopiowanie z istniejącego środowiska**. Zobaczysz listę wszystkich dostępnych środowisk w organizacji, z których można kopiować dane.

1. Podaj następujące szczegóły:
   - **Nazwa**: Nazwa tego środowiska. To pole jest już wypełnione, jeśli skopiowano istniejące środowisko, ale można to zmienić.
   - **Region**: Region, w którym usługa jest wdrażana i hostowana.
   - **Wpisz**: Wybierz, czy chcesz utworzyć środowisko produkcyjne, czy też piaskownicę.

1. Opcjonalnie możesz wybrać **Ustawienia zaawansowane**:

   - **Zapisz wszystkie dane do**: Określa miejsce, w którym mają być przechowywane dane wyjściowe uzyskane na podstawie danych dotyczących klienta. Dostępne będą dwie opcje: **Magazyn Customer Insights** (usługa Azure Data Lake zarządzana przez zespół Customer Insights) i **Azure Data Lake Storage Gen2** (Twój własny Azure Data Lake Storage). Domyślnie jest zaznaczona opcja magazyn Customer Insights.

   > [!NOTE]
   > Zapisując dane w usłudze Azure Data Lake Storage, zgadzasz się na przenoszenie danych do lokalizacji geograficznej odpowiedniej dla danego konta usługi Azure Storage i przechowywanie ich w tej lokalizacji, która może być inna niż lokalizacja, w której są przechowywane dane w Dynamics 365 Customer Insights. [Więcej informacji znajduje się w centrum zaufania Microsoft.](https://www.microsoft.com/trust-center)
   >
   > Obecnie pozyskiwane encje są zawsze przechowywane w data lake obsługiwanym przez Customer Insights..
   > Obsługujemy tylko konta magazynu Azure Data Lake Gen2 z tego samego regionu Azure, który został wybrany podczas tworzenia środowiska.
   > Obsługujemy tylko konta magazynów włączone przez Hierarchiczny Obszar Nazw (HNS) Azure Data Lake Gen2.

   - W przypadku opcji Azure Data Lake Storage Gen2 można wybrać między opcją opartą na zasobach a opcją opartą na subskrypcji na potrzeby uwierzytelniania. Aby uzyskać więcej informacji, zobacz temat [Połącz analizy odbiorców z kontem Azure Data Lake Storage Gen2 za pomocą głównej usługi platformy Azure](connect-service-principal.md). Nazwa **Kontenera** nie może zostać zmieniona i będzie mieć wartość „customerinsights”.
   
   - Jeśli chcesz używać [przewidywań](predictions.md), skonfiguruj udostępnianie danych w aplikacjach i rozwiązaniach na podstawie funkcji Microsoft Dataverse lub włącz pozyskiwanie danych z lokalnych źródeł danych, podaj adres URL środowiska Microsoft Dataverse w obszarze **Konfigurowanie udostępniania danych funkcji Microsoft Dataverse i włączanie dodatkowych funkcji**. Wybierz opcję **Włącz udostępnianie danych**, aby udostępnić dane wyjściowe usługi Customer Insights daneom wyjściowym z zarządzanego Data Lake Microsoft Dataverse.

     > [!NOTE]
     > - Udostępnianie danych za pomocą usługi Microsoft Dataverse Zarządzanego Data Lake nie jest obecnie obsługiwane w przypadku zapisywania wszystkich danych we własnym Azure Data Lake Storage.
     > - [Przewidywanie brakujących wartości w encji](predictions.md) nie są obecnie obsługiwane, jeśli w przypadku włączenia udostępniania danych w Microsoft Dataverse zarządzane są Data Lake.

     > [!div class="mx-imgBorder"]
     > ![Opcje konfiguracji umożliwiające udostępnianie danych z Microsoft Dataverse](media/datasharing-with-DataverseMDL.png)

   Podczas uruchamiania procesów, takich jak pozyskiwanie danych lub tworzenie segmentów, odpowiednie foldery zostaną utworzone na koncie magazynu określonym powyżej. Pliki danych i pliki model.json zostaną utworzone i dodane do odpowiednich podfolderów na podstawie uruchamianego procesu.

   Jeśli utworzysz wiele środowisk Customer Insights i zdecydujesz się zapisać encje wyjściowe z tych środowisk na koncie magazynu, dla każdego środowiska zostaną utworzone osobne foldery z ci_<environmentid> w kontenerze.

### <a name="considerations-for-copy-configuration-preview"></a>Rozważania dotyczące konfiguracji kopiowania (wersja zapoznawcza)

Kopiowane są następujące ustawienia konfiguracji:

- Konfiguracja funkcji
- Importowanie/importowanie źródeł danych
- Konfiguracja ujednolicania danych (mapowanie, dopasowywanie, scalanie)
- Segmenty
- Miary
- Relacje
- Działania
- Wyszukiwanie i indeks filtrów
- Lokalizacje docelowe eksportu
- Zaplanowane odświeżanie
- Wzbogacenia
- Zarządzanie modelem
- Przypisania ról

Poniższe ustawienia *nie są* kopiowane:

- Profile klientów.
- Poświadczenia źródła danych. Konieczne będzie podanie poświadczeń dla każdego źródła danych i ręczne odświeżenie źródeł danych.
- Źródła danych z folderu Common Data Model i zarządzanego repozytorium danych typu lake Common Data Service. Konieczne będzie ręczne utworzenie tych źródeł danych pod tą samą nazwą jak w środowisku źródłowym.

Podczas kopiowania środowiska zostanie wyświetlony komunikat z potwierdzeniem, że utworzono nowe środowisko. Wybierz **Przejdź do źródeł danych**, aby wyświetlić listę źródeł danych.

Wszystkie źródła danych ukażą stan **Wymagane poświadczenia**. Dokonaj edycji źródeł danych i wprowadź poświadczenia, aby je odświeżyć.

> [!div class="mx-imgBorder"]
> ![Skopiowane źródła danych](media/data-sources-copied.png)

Po odświeżeniu źródeł danych przejdź do **Dane** > **Ujednolicanie**. W tym miejscu można znaleźć ustawienia z poziomu środowiska źródłowego. Edytuj je zgodnie z wymaganiami lub wybierz **Uruchom**, aby rozpocząć proces ujednolicania danych i utworzyć zunifikowaną encję klienta.

Po zakończeniu ujednolicania danych należy przejść do **Miary** i **Segmenty**, aby je również odświeżyć.

## <a name="edit-an-existing-environment"></a>Edytuj istniejące środowisko

Użytkownik może edytować niektóre szczegóły istniejących środowisk.

1.  Wybierz selektor **Środowiska** w nagłówku aplikacji.

2.  Wybierz ikonę **Edytuj**.

3. W polu **Edytuj środowisko** można zaktualizować pole **Wyświetlana nazwa**, ale nie można zmienić **Regionu** lub **Typu**.

4. Jeśli środowisko jest skonfigurowane do przechowywania danych w Azure Data Lake Storage Gen2, można zaktualizować **Klucz konta**. Nie można jednak zmienić **Nazwy konta** lub nazwy **Kontener**.

5. Opcjonalnie można zaktualizować połączenie oparte na kluczu konta do połączenia opartego na zasobach lub subskrypcji. Po uaktualnieniu nie można powrócić do klucza konta po aktualizacji. Aby uzyskać więcej informacji, zobacz temat [Połącz analizy odbiorców z kontem Azure Data Lake Storage Gen2 za pomocą głównej usługi platformy Azure](connect-service-principal.md). Podczas aktualizowania połączenia nie można zmieniać informacji o **Kontenerze**.

6. Opcjonalnie można podać adres URL środowiska Microsoft Dataverse w obszarze **Konfigurowanie udostępniania danych funkcji Microsoft Dataverse i włączanie dodatkowych możliwości**. Funkcje te zawierają udostępnianie danych aplikacjom i rozwiązań opartych na Microsoft Dataverse, pozyskiwanie danych z lokalnych źródeł danych lub używanie [przewidywać](predictions.md). Wybierz opcję **Włącz udostępnianie danych**, aby udostępnić dane wyjściowe usługi Customer Insights daneom wyjściowym z zarządzanego Data Lake Microsoft Dataverse.

   > [!NOTE]
   > - Udostępnianie danych za pomocą usługi Microsoft Dataverse Zarządzanego Data Lake nie jest obecnie obsługiwane w przypadku zapisywania wszystkich danych we własnym Azure Data Lake Storage.
   > - [Przewidywanie brakujących wartości w encji](predictions.md) nie jest obecnie obsługiwane, jeśli włączone zostało udostępnianie danych zarządzanemu Data Lake Microsoft Dataverse.

   Po włączeniu udostępniania danych funkcji Microsoft Dataverse zostanie wyzwolone pełne odświeżanie źródeł danych i innych procesów. Jeśli procesy są obecnie uruchomione i są w kolejce, nie będzie dostępna opcja włączenia udostępniania danych funkcji Microsoft Dataverse. Można poczekać na zakończenie tych procesów lub je anulować, aby włączyć udostępnianie danych. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Opcje konfiguracji umożliwiające udostępnianie danych funkcji Microsoft Dataverse.":::
   
   Podczas uruchamiania procesów, takich jak pozyskiwanie danych lub tworzenie segmentów, odpowiednie foldery zostaną utworzone na koncie magazynu określonym powyżej. W zależności od uruchomionego procesu pliki danych i pliki model.json zostaną utworzone i dodane do odpowiednich podfolderów.

## <a name="reset-an-existing-environment"></a>Zresetuj istniejące środowisko

Jako administrator jeśli chcesz usunąć wszystkie konfiguracje i przetworzone dane, możesz zresetować środowisko do stanu pustego.

1.  Wybierz selektor **Środowiska** w nagłówku aplikacji. 

2.  Wybierz środowisko, które chcesz zresetować, i wybierz wielokropek **...**. 

3. Wybierz opcję **Reset**. 

4.  Aby potwierdzić usunięcie, wprowadź nazwę środowiska i wybierz pozycję **Zresetuj**.

## <a name="delete-an-existing-environment-available-only-for-admins"></a>Usuwanie istniejącego środowiska (dostępnego tylko dla administratorów)

Jako Administrator użytkownik możesz usunąć administrowane środowisko.

1.  Wybierz selektor **Środowiska** w nagłówku aplikacji.

2.  Wybierz środowisko, które chcesz zresetować, i wybierz wielokropek **...**. 

3. Wybierz opcję **Usuń**. 

4.  Aby potwierdzić usunięcie, wprowadź nazwę środowiska i wybierz **Usuń**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
