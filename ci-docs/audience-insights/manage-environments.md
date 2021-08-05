---
title: Utwórz środowisko i zarządzaj nim.
description: Dowiedz się, jak zapisać się w usłudze i zarządzać środowiskami.
ms.date: 07/22/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 2f115269b9d07dd118ec18cc48b55de8aea9b5bb
ms.sourcegitcommit: 98267da3f3eddbdfbc89600a7f54e5e664a8f069
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2021
ms.locfileid: "6683486"
---
# <a name="manage-environments"></a>Zarządzaj środowiskami

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Przełącz środowiska

Wybierz kontrolkę **Środowiska** w prawym górnym rogu strony, aby zmienić środowiska.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Zrzut ekranu przedstawiający formant do przełączania środowisk.":::

Administratorzy mogą [tworzyć](get-started-paid.md) i zarządzać środowiskami.

## <a name="edit-an-existing-environment"></a>Edytuj istniejące środowisko

Użytkownik może edytować niektóre szczegóły istniejących środowisk.

1.  Wybierz selektor **Środowiska** w nagłówku aplikacji.

2.  Wybierz ikonę **Edytuj**.

3. W polu **Edytuj środowisko** można zaktualizować pole **Wyświetlana nazwa**, ale nie można zmienić **Regionu** lub **Typu**.

4. Jeśli w środowisku skonfigurowano przechowywanie danych w Azure Data Lake Storage, można zaktualizować **Klucz konta**. Nie można jednak zmienić **Nazwy konta** lub nazwy **Kontener**.

5. Opcjonalnie można zaktualizować połączenie oparte na kluczu konta do połączenia opartego na zasobach lub subskrypcji. Po uaktualnieniu nie można powrócić do klucza konta po aktualizacji. Aby uzyskać więcej informacji, zobacz temat [Połącz analizy odbiorców z kontem Azure Data Lake Storage Gen2 za pomocą głównej usługi platformy Azure](connect-service-principal.md). Podczas aktualizowania połączenia nie można zmieniać informacji o **Kontenerze**.

6. Opcjonalnie można podać adres URL środowiska Microsoft Dataverse w obszarze **Konfigurowanie udostępniania danych funkcji Microsoft Dataverse i włączanie dodatkowych możliwości**. Funkcje te zawierają udostępnianie danych aplikacjom i rozwiązań opartych na Microsoft Dataverse, pozyskiwanie danych z lokalnych źródeł danych lub używanie [przewidywać](predictions.md). Wybierz opcję **Włącz udostępnianie danych**, aby udostępnić dane wyjściowe usługi Customer Insights daneom wyjściowym z zarządzanego Data Lake Microsoft Dataverse.

   > [!NOTE]
   > - Udostępnianie danych za pomocą usługi Microsoft Dataverse Zarządzanego Data Lake nie jest obecnie obsługiwane w przypadku zapisywania wszystkich danych we własnym Azure Data Lake Storage.
   > - [Przewidywanie brakujących wartości w encji](predictions.md) i raportów osadzonych w usłudze Power BI w szczegółowych informacjach odbiorcy (jeśli jest włączone w danym środowisku) nie są obecnie obsługiwane po włączeniu udostępniania danych za pomocą zarządzanego data lake Microsoft Dataverse.

   Po włączeniu udostępniania danych funkcji Microsoft Dataverse zostanie rozpoczęte pełne odświeżanie źródeł danych i innych procesów. Jeśli procesy są obecnie uruchomione, nie będzie dostępna opcja włączenia udostępniania danych funkcji Microsoft Dataverse. Poczekaj na zakończenie tych procesów lub je anulować, aby włączyć udostępnianie danych. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Opcje konfiguracji umożliwiające udostępnianie danych funkcji Microsoft Dataverse.":::
   
   Podczas uruchamiania procesów, takich jak pozyskiwanie danych lub tworzenie segmentów, odpowiednie foldery zostaną utworzone na koncie magazynu określonym powyżej. W zależności od uruchomionego procesu pliki danych i pliki model.json zostaną utworzone i dodane do odpowiednich podfolderów.

## <a name="copy-the-environment-configuration"></a>Kopiowanie konfiguracji środowiska

Podczas tworzenia nowego środowiska można skopiować konfigurację z istniejącego środowiska. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Zrzut ekranu przedstawiający opcje ustawień w ustawieniach środowiska.":::

Zobaczysz listę wszystkich dostępnych środowisk w organizacji, z których można kopiować dane.

Kopiowane są następujące ustawienia konfiguracji:

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

Następujące dane *nie* są kopiowane:

- Profile klientów.
- Poświadczenia źródła danych. Konieczne będzie podanie poświadczeń dla każdego źródła danych i ręczne odświeżenie źródeł danych.
- Źródła danych z folderu Common Data Model oraz Data Lake zarządzanego przez Dataverse. Konieczne będzie ręczne utworzenie tych źródeł danych pod tą samą nazwą jak w środowisku źródłowym.

Podczas kopiowania środowiska zostanie wyświetlony komunikat z potwierdzeniem, że utworzono nowe środowisko. Wybierz **Przejdź do źródeł danych**, aby wyświetlić listę źródeł danych.

Wszystkie źródła danych ukażą stan **Wymagane poświadczenia**. Dokonaj edycji źródeł danych i wprowadź poświadczenia, aby je odświeżyć.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lista źródeł danych, które zostały skopiowane i wymagają uwierzytelniania.":::

Po odświeżeniu źródeł danych przejdź do **Dane** > **Ujednolicanie**. W tym miejscu można znaleźć ustawienia z poziomu środowiska źródłowego. Edytuj je zgodnie z wymaganiami lub wybierz **Uruchom**, aby rozpocząć proces ujednolicania danych i utworzyć zunifikowaną encję klienta.

Po zakończeniu ujednolicania danych należy przejść do **Miary** i **Segmenty**, aby je również odświeżyć.

## <a name="reset-an-existing-environment"></a>Zresetuj istniejące środowisko

Jako administrator jeśli chcesz usunąć wszystkie konfiguracje i przetworzone dane, możesz zresetować środowisko do stanu pustego.

1.  Wybierz selektor **Środowiska** w nagłówku aplikacji. 

2.  Wybierz środowisko, które chcesz zresetować, i wybierz wielokropek (**...**). 

3. Wybierz opcję **Reset**. 

4.  Aby potwierdzić usunięcie, wprowadź nazwę środowiska i wybierz pozycję **Zresetuj**.

## <a name="delete-an-existing-environment"></a>Usuń istniejące środowisko

Jako Administrator użytkownik możesz usunąć administrowane środowisko.

1.  Wybierz selektor **Środowiska** w nagłówku aplikacji.

2.  Wybierz środowisko, które chcesz zresetować, i wybierz wielokropek (**...**). 

3. Wybierz opcję **Usuń**. 

4.  Aby potwierdzić usunięcie, wprowadź nazwę środowiska i wybierz **Usuń**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
