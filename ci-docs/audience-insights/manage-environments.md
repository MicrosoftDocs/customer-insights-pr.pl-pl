---
title: Utwórz środowisko i zarządzaj nim.
description: Dowiedz się, jak zapisać się w usłudze i zarządzać środowiskami.
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: ba29bcd173e615e544bd10e69043f310c009eb47
ms.sourcegitcommit: ae02ac950810242e2505d7d371b80210dc8a0777
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/29/2022
ms.locfileid: "8492017"
---
# <a name="manage-environments"></a>Zarządzaj środowiskami

## <a name="switch-environments"></a>Przełącz środowiska

Wybierz kontrolkę **Środowiska** w prawym górnym rogu strony, aby zmienić środowiska.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Zrzut ekranu przedstawiający formant do przełączania środowisk.":::

Administratorzy mogą [tworzyć](create-environment.md) i zarządzać środowiskami.

## <a name="edit-an-existing-environment"></a>Edytuj istniejące środowisko

Użytkownik może edytować niektóre szczegóły istniejących środowisk.

1.  Wybierz selektor **Środowiska** w nagłówku aplikacji.

2.  Wybierz ikonę **Edytuj**.

3. W polu **Edytuj środowisko** można zaktualizować ustawienia środowiska.

Aby uzyskać więcej informacji o ustawieniach środowiska, zobacz temat [Tworzenie nowego środowiska](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Nawiązywanie połączenia z usługą Microsoft Dataverse
   
Krok **Microsoft Dataverse** umożliwia połączenie aplikacji Customer Insights ze środowiskiem Dataverse. 

Udostępnij własne środowisko Microsoft Dataverse w celu udostępniania danych (profilów i analiz) aplikacjom biznesowym opartym usługach Dataverse, jak Dynamics 365 Marketing lub aplikacje oparte na modelu w usłudze Power Apps.

Aby używać [gotowych modeli przewidywania](predictions-overview.md#out-of-box-models), skonfiguruj udostępnianie danych w funkcji Dataverse. Można też włączyć pozyskiwanie danych z lokalnych źródeł danych, udostępniając adres URL środowiska funkcji Microsoft Dataverse, którym administruje Twoja organizacja.

Włączenie udostępniania danych za pomocą Microsoft Dataverse poprzez zaznaczenie pola wyboru udostępniania danych spowoduje jednorazowe pełne odświeżenie źródeł danych i wszystkich innych procesów.

> [!IMPORTANT]
> 1. Customer Insights i Dataverse muszą znajdować się w tym samym regionie, aby umożliwić wymianę danych.
> 1. Użytkownik musi mieć rolę Administrator globalny w środowisku Dataverse. Sprawdź, czy to [środowisko Dataverse jest skojarzone](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) z określonymi grupami zabezpieczeń i upewnij się, że użytkownik został dodany do tych grup zabezpieczeń.
> 1. Żadne istniejące środowisko Customer Insights nie jest już powiązane z tym środowiskiem Dataverse. Dowiedz się, [jak usunąć istniejące połączenie ze środowiskiem Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Opcje konfiguracji umożliwiające udostępnianie danych funkcji Microsoft Dataverse.":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Włącz udostępnianie danych za pomocą Dataverse z własnej usługi Azure Data Lake Storage (wersja zapoznawcza)

Jeśli Twoje środowisko jest skonfigurowane do używania własnej usługi Azure Data Lake Storage do przechowywania danych Customer Insights, włączenie udostępniania danych za pomocą Microsoft Dataverse wymaga dodatkowej konfiguracji.

1. W subskrypcji Azure utwórz dwie grupy zabezpieczeń — jedną grupę zabezpieczeń **Czytelnik** i jedną grupę zabezpieczeń **współautor** i ustaw usługę Microsoft Dataverse jako właściciela obu grup zabezpieczeń.
2. Zarządzaj listą kontroli dostępu (ACL) dla konteneru CustomerInsights w ramach konta magazynu za pośrednictwem tych grup zabezpieczeń. Dodaj usługę Microsoft Dataverse i dowolne aplikacje biznesowe oparte na Dataverse, takie jak Dynamics 365 Marketing, do grupy zabezpieczeń **Czytelnik** z uprawnieniami **tylko do odczytu**. Dodaj *tylko* aplikację Customers Insights do grupy zabezpieczeń **współautor**, aby udzielić zarówno uprawnień do **odczytu i zapisu** do pisania profilów i analiz.
   
#### <a name="prerequisites"></a>Wymagania wstępne

Aby wykonać skrypty programu PowerShell, należy zaimportować trzy poniższe moduły. 

1. Zainstaluj najnowszą wersję [programu Azure Active Directory PowerShell dla programu Graph](/powershell/azure/active-directory/install-adv2).
   1. Na komputerze wybierz klawisz Windows i wyszukaj program **Windows PowerShell** i wybierz opcję **Uruchom jako Administrator**.
   1. W wyświetlonym oknie PowerShell wprowadź polecenie `Install-Module AzureAD`.
2. Zaimportuj trzy moduły.
    1. W oknie PowerShell wpisz `Install-Module -Name Az.Accounts` i postępuj zgodnie z instrukcjami. 
    1. Powtórz dla `Install-Module -Name Az.Resources` i `Install-Module -Name Az.Storage`.

#### <a name="configuration-steps"></a>Kroki konfiguracji

1. Pobierz dwa skrypty programu PowerShell, które trzeba uruchomić, ze strony [repo GitHub](https://github.com/trin-msft/byol) inżyniera.
    1. `CreateSecurityGroups.ps1`
       - Aby uruchomić ten skrypt PowerShell, potrzebujesz uprawnień *administratora dzierżawy*. 
       - Ten skrypt programu PowerShell tworzy dwie grupy zabezpieczeń w ramach subskrypcji platformy Azure. Jeden dla grupy Czytelnik, a drugi dla grupy współautor i uczyni usługę Microsoft Dataverse jako właścicielem dla obu tych grup zabezpieczeń.
       - Wykonaj ten skrypt programu PowerShell w programie Windows PowerShell, podając identyfikator subskrypcji Azure zawierający identyfikator Azure Data Lake Storage. Otwórz skrypt PowerShell w edytorze, aby przejrzeć dodatkowe informacje i zaimplementowaną logikę.
       - Zapisz obie wartości identyfikatorów grup zabezpieczeń wygenerowanych przez ten skrypt, ponieważ użyjemy ich w skrypcie `ByolSetup.ps1`.
       
        > [!NOTE]
        > W dzierżawie można wyłączyć tworzenie grupy zabezpieczeń. W takim przypadku jest potrzebna konfiguracja ręczna, a administrator Azure AD będzie musiał włączyć [tworzenie grupy zabezpieczeń](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Aby uruchomić ten skrypt, potrzebujesz uprawnień *Właściciel danych obiektów blob magazynu* na poziomie konta magazynu/kontenera. W przeciwnym razie ten skrypt utworzy go dla Ciebie. Przypisanie roli można usunąć ręcznie po pomyślnym uruchomieniu skryptu.
        - Ten skrypt programu PowerShell dodaje wymaganą kontrolę dostępu opartą na tole (RBAC) dla usługi Microsoft Dataverse i dowolnych aplikacji biznesowych opartych na Dataverse. Aktualizuje również Listę kontroli dostępu (ACL) w kontenerze CustomerInsights dla grup zabezpieczeń utworzonych za pomocą skryptu `CreateSecurityGroups.ps1`. Grupa współautor będzie mieć uprawnienie *rwx*, a grupa Czytelnicy będzie mieć tylko uprawnienie *r-x*.
        - Wykonaj ten skrypt programu PowerShell w programie Windows PowerShell, podając identyfikator subskrypcji platformy Azure zawierający nazwę usługi Azure Data Lake Storage, nazwę konta magazynu, nazwę grupy zasobów oraz wartości identyfikatorów grupy zabezpieczeń czytelnik i współautor. Otwórz skrypt PowerShell w edytorze, aby przejrzeć dodatkowe informacje i zaimplementowaną logikę.
        - Skopiuj ciąg wyjściowy po pomyślnym uruchomieniu skryptu. Ciąg wyjściowy wygląda następująco: `https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. Wprowadź ciąg wyjściowy skopiowany z powyższej strony do pola **Identyfikator uprawnień** w kroku konfiguracji środowiska dla ustawienia Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opcje konfiguracji umożliwiające udostępnianie danych z własnej usługi Azure Data Lake Storage za pomocą Microsoft Dataverse.":::

Aplikacja Customer Insights nie obsługuje następujących scenariuszy udostępniania danych:
- W przypadku włączenia udostępniania usłudze Dataverse, nie będzie można [tworzyć przewidywanych lub brakujących wartości w encji](predictions.md).
- Jeśli włączysz udostępnianie danych za pomocą Dataverse, nie będziesz mieć możliwości przeglądania żadnych opcjonalnych raportów PowerBI Embedded w swoim środowisku Customer Insights.

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Usuń istniejące połączenie ze środowiskiem Dataverse

Podczas łączenia się ze środowiskiem Dataverse komunikat o błędzie **Ta organizacja CDS jest już połączona z inną instancją Customer Insights** oznacza, że środowisko Dataverse jest już używane w środowisku Customer Insights. Możesz usunąć istniejące połączenie jako administrator globalny w środowisku Dataverse. Wypełnienie zmian może zająć kilka godzin.

1. Przejdź do [Power Apps](https://make.powerapps.com).
1. Wybierz środowisko z selektora środowiska.
1. Przejdź na stronę **Rozwiązania**
1. Odinstaluj lub usuń rozwiązanie o nazwie **Dodatek karta klienta Dynamics 365 Customer Insights (wersja zapoznawcza)**.

LUB 

1. Otwórz swoje środowisko Dataverse.
1. Wybierz kolejno pozycje **Ustawienia zaawansowane** > **Rozwiązania**.
1. Odinstaluj rozwiązanie **CustomerInsightsCustomerCard**.

## <a name="copy-the-environment-configuration"></a>Kopiowanie konfiguracji środowiska

Jako administrator możesz skopiować konfigurację z istniejącego środowiska podczas tworzenia nowego. 

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

## <a name="set-up-a-copied-environment"></a>Skonfiguruj skopiowane środowisko

Podczas kopiowania konfiguracji środowiska następujące dane *nie* są kopiowane:

- Profile klientów.
- Poświadczenia źródła danych. Konieczne będzie podanie poświadczeń dla każdego źródła danych i ręczne odświeżenie źródeł danych.
- Źródła danych z folderu Common Data Model i danych data lake zarządzanych przez Dataverse. Konieczne będzie ręczne utworzenie tych źródeł danych pod tą samą nazwą jak w środowisku źródłowym.
- Sekrety połączeń używane do eksportowania i wzbogacania. Musisz ponownie uwierzytelnić połączenia, a następnie ponownie aktywować wzbogacanie i eksporty. 

Podczas kopiowania środowiska zostanie wyświetlony komunikat z potwierdzeniem, że utworzono nowe środowisko. Wybierz **Przejdź do źródeł danych**, aby wyświetlić listę źródeł danych.

Wszystkie źródła danych ukażą stan **Wymagane poświadczenia**. Dokonaj edycji źródeł danych i wprowadź poświadczenia, aby je odświeżyć.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lista źródeł danych, które zostały skopiowane i wymagają uwierzytelniania.":::

Po odświeżeniu źródeł danych przejdź do **Dane** > **Ujednolicanie**. W tym miejscu można znaleźć ustawienia z poziomu środowiska źródłowego. Edytuj je zgodnie z wymaganiami lub wybierz **Uruchom**, aby rozpocząć proces ujednolicania danych i utworzyć zunifikowaną encję klienta.

Po zakończeniu ujednolicania danych należy przejść do **Miary** i **Segmenty**, aby je również odświeżyć.

Zanim ponownie aktywujesz eksporty i wzbogacenia, przejdź do **Administrator** > **Połączenia**, aby ponownie uwierzytelnić połączenia w nowym środowisku.

## <a name="change-the-owner-of-an-environment"></a>Zmień właściciela środowiska

Podczas gdy kilku użytkowników może mieć uprawnienia administratora w Customer Insights, tylko jeden użytkownik jest właścicielem środowiska. Domyślnie to administrator tworzy środowisko na początku. Jako administrator środowiska możesz przydzielić prawo własności innemu użytkownikowi z uprawnieniami administratora.

1. Wybierz selektor **Środowiska** w nagłówku aplikacji.

1. Wybierz ikonę **Edytuj**.

1. W polu **Edytowanie środowiska** przejdź do kroku **Podstawowe informacje**.

1. W polu **Zmień właściciela środowiska** wybierz nowego właściciela środowiska.  

1. Wybierz **Przeglądaj i zakończ**, a następnie **Uaktualnij**, aby zastosować zmiany. 

## <a name="claim-ownership-of-an-environment"></a>Zastrzeż sobie prawo do własności środowiska

Jeśli właściciel środowiska opuści organizację lub jego konto użytkownika zostanie usunięte, środowisko nie będzie miało właściciela. Użytkownik z uprawnieniami administratora może odebrać prawo własności i stać się nowym właścicielem. Mogą oni nadal być właścicielami środowiska lub [zmienić właściciela na innego administratora](#change-the-owner-of-an-environment). 

Aby zastrzec sobie prawo własności, wybierz **Przejmij własność**, który pojawia się na górze każdej strony w Customer Insights, gdy pierwotny właściciel opuścił organizację.

## <a name="reset-an-existing-environment"></a>Zresetuj istniejące środowisko

Jako właściciel środowiska możesz zresetować środowisko do stanu pustego, jeśli chcesz usunąć wszystkie konfiguracje i usunąć wprowadzone dane.

1.  Wybierz selektor **Środowiska** w nagłówku aplikacji. 

2.  Wybierz środowisko, które chcesz zresetować, i wybierz wielokropek (**...**). 

3. Wybierz opcję **Reset**. 

4.  Aby potwierdzić usunięcie, wprowadź nazwę środowiska i wybierz pozycję **Zresetuj**.

## <a name="delete-an-existing-environment"></a>Usuń istniejące środowisko

Jako właściciel środowiska możesz usunąć środowisko, którym administrujesz.

1.  Wybierz selektor **Środowiska** w nagłówku aplikacji.

2.  Wybierz środowisko, które chcesz zresetować, i wybierz wielokropek (**...**). 

3. Wybierz opcję **Usuń**. 

4.  Aby potwierdzić usunięcie, wprowadź nazwę środowiska i wybierz **Usuń**.

> [!NOTE]
> Usunięcie środowiska nie powoduje usunięcia skojarzenia ze środowiskiem Dataverse. Dowiedz się, [jak usunąć istniejące połączenie ze środowiskiem Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
