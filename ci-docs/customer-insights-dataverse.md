---
title: Praca z danymi aplikacji Customer Insights w Microsoft Dataverse
description: Dowiedz się, jak połączyć Customer Insights i Microsoft Dataverse i zrozumieć encje wyjściowe, które są eksportowane do Dataverse.
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 3848e143bc7cb2f345bc698a274b92148ef00669
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833689"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Praca z danymi aplikacji Customer Insights w Microsoft Dataverse

Customer Insights zapewnia opcję udostępnienia encji wyjściowych jako [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Integracja ta umożliwia łatwe współdzielenie danych i tworzenie własnych rozwiązań dzięki podejściu low code / no code. [Encje wyjściowe](#output-entities) są dostępne jako tabele w środowisku Dataverse. Możesz wykorzystać te dane w dowolnej innej aplikacji opartej na tabelach Dataverse. Tabele te umożliwiają takie scenariusze jak zautomatyzowane przepływy pracy dzięki Power Automate czy budowanie aplikacji za pomocą Power Apps.

Połączenie ze środowiskiem Dataverse umożliwia również [pozyskiwanie danych z lokalnych źródeł danych za pomocą przepływów danych Power Platform i bram](data-sources.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Wymagania wstępne

- Środowiska Customer Insights i Dataverse muszą być hostowane w tym samym regionie.
- Użytkownik musi mieć rolę Administrator globalny w środowisku Dataverse. Sprawdź, czy to [środowisko Dataverse jest powiązane](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) z określonymi grupami zabezpieczeń i upewnij się, że dodane do tych grup zabezpieczeń.
- Żadne inne środowisko Customer Insights nie jest już powiązane ze środowiskiem Dataverse, z którym chcesz się połączyć. Dowiedz się, [jak usunąć istniejące połączenie ze środowiskiem Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).
- Środowisko Microsoft Dataverse może łączyć się tylko z jednym kontem magazynu. Stosuje się ją tylko wtedy, gdy środowisko jest konfigurowane do [używania przez użytkownika Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Łączenie środowiska Dataverse z usługą Customer Insights

Krok **Microsoft Dataverse** pozwala połączyć Customer Insights ze środowiskiem Dataverse podczas [tworzenia środowiska Customer Insights](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="udostępnianie danych z włączoną automatycznie obsługą Microsoft Dataverse dla nowych środowisk sieci.":::

Administratorzy mogą skonfigurować usługę Customer Insights w celu połączenia istniejącego środowiska Dataverse. Podając adres URL do środowiska Dataverse, dołączasz do nowego środowiska Customer Insights.

Jeśli nie chcesz korzystać z istniejącego środowiska Dataverse, system tworzy nowe środowisko dla danych Customer Insights w Twojej dzierżawie. [Administratorzy Power Platform mogą kontrolować, kto może tworzyć środowiska](/power-platform/admin/control-environment-creation). Gdy konfigurujesz nowe środowisko Customer Insights, a administrator wyłączył tworzenie środowisk Dataverse dla wszystkich z wyjątkiem administratorów, możesz nie być w stanie utworzyć nowego środowiska.

**Włącz udostępnianie danych** z Dataverse, zaznaczając pole wyboru udostępniania danych.

Jeśli używasz własnego konta Data Lake Storage, musisz mieć **także identyfikator uprawnień**. Aby uzyskać więcej informacji, jak uzyskać identyfikator uprawnienia, przejrzyj następującą sekcję.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Włącz udostępnianie danych za pomocą Dataverse z własnej usługi Azure Data Lake Storage (wersja zapoznawcza)

Włączenie udostępniania danych w Microsoft Dataverse, gdy Twoje środowisko [używa własnego konta Azure Data Lake Storage](own-data-lake-storage.md) wymaga dodatkowej konfiguracji. Użytkownik konfigurujący środowisko Customer Insights musi mieć co najmniej uprawnienia **Storage Blob Data Reader** w kontenerze *CustomerInsights* na koncie Azure Data Lake Storage.

1. W subskrypcji Azure utwórz dwie grupy zabezpieczeń — jedną grupę zabezpieczeń **Czytelnik** i jedną grupę zabezpieczeń **współautor** i ustaw usługę Microsoft Dataverse jako właściciela obu grup zabezpieczeń.
2. Zarządzaj listą kontroli dostępu (ACL) dla konteneru CustomerInsights w ramach konta magazynu za pośrednictwem tych grup zabezpieczeń. Dodaj usługę Microsoft Dataverse i dowolne aplikacje biznesowe oparte na Dataverse, takie jak Dynamics 365 Marketing, do grupy zabezpieczeń **Czytelnik** z uprawnieniami **tylko do odczytu**. Dodaj *tylko* aplikację Customers Insights do grupy zabezpieczeń **współautor**, aby udzielić zarówno uprawnień do **odczytu i zapisu** do pisania profilów i analiz.

### <a name="limitations"></a>Ograniczenia

Podczas korzystania z Dataverse z własnym kontem Azure Data Lake Storage istnieją dwa ograniczenia:

- Istnieje mapowanie jeden do jednego między organizacją Dataverse a kontem usługi Azure Data Lake Storage. Organizacja Dataverse jest połączona z kontem magazynu, nie może się połączyć z innym kontem magazynu. To ograniczenie zapobiega temu, że Dataverse nie wypełnia wielu kont magazynu.
- Udostępnianie danych nie będzie działać, jeśli do uzyskania dostępu do konta usługi Azure Data Lake Storage jest potrzebna konfiguracja łącza prywatnego platformy Azure, ponieważ znajduje się ono za zaporą. Dataverse obecnie nie obsługuje połączenia z prywatnymi punktami końcowymi za pośrednictwem łącza prywatnego.

### <a name="set-up-powershell"></a>Konfigurowanie PowerShell

Aby wykonać skrypty PowerShell, musisz najpierw odpowiednio skonfigurować PowerShell.

1. Zainstaluj najnowszą wersję [programu Azure Active Directory PowerShell dla programu Graph](/powershell/azure/active-directory/install-adv2).
   1. Na komputerze wybierz klawisz Windows i wyszukaj program **Windows PowerShell** i wybierz opcję **Uruchom jako Administrator**.
   1. W wyświetlonym oknie PowerShell wprowadź polecenie `Install-Module AzureAD`.
2. Zaimportuj trzy moduły.
    1. W oknie PowerShell wpisz `Install-Module -Name Az.Accounts` i postępuj zgodnie z instrukcjami.
    1. Powtórz dla `Install-Module -Name Az.Resources` i `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Kroki konfiguracji

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
        - Skopiuj ciąg wyjściowy po pomyślnym uruchomieniu skryptu. Ciąg wyjściowy wygląda następująco: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Wprowadź ciąg wyjściowy skopiowany z powyższej strony do pola **Identyfikator uprawnień** w kroku konfiguracji środowiska dla ustawienia Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opcje konfiguracji umożliwiające udostępnianie danych z własnej usługi Azure Data Lake Storage za pomocą Microsoft Dataverse.":::

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

Jeśli usuwanie połączenia kończy się niepowodzeniem z powodu zależności, należy również usunąć zależności. Aby uzyskać więcej informacji, zobacz [Usuwanie zależności](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Encje wyjściowe

Niektóre encje wyjściowe z Customer Insights są dostępne jako tabele w Dataverse. Poniższe sekcje opisują oczekiwany schemat tych tabel.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Wzbogacenie](#enrichment)
- [Przewidywanie](#prediction)
- [Członkostwo segmentu](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Ta tabela zawiera ujednolicony profil klienta z funkcji Customer Insights. Schemat ujednoliconego profilu klienta zależy od encji i atrybutów używanych w procesie ujednolicania danych. Schemat profilu klienta zazwyczaj zawiera podzbiór atrybutów z [definicji Common Data Model klienta CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Tabela AlternateKey zawiera klucze encji, które brały udział w procesie ujednolicania.

|Column  |Pisz  |Opis  |
|---------|---------|---------|
|DataSourceName    |String         | Nazwa źródła danych. Na przykład: `datasource5`        |
|EntityName        | String        | Nazwa encji w Customer Insights. Na przykład: `contact1`        |
|AlternateValue    |String         |Alternatywny identyfikator mapowany na identyfikator klienta. Przykład: `cntid_1078`         |
|KeyRing           | Tekst wielowierszowy        | Wartość JSON  </br> Przykład: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|Identyfikator klienta         | String        | Identyfikator ujednoliconego profilu klienta.         |
|AlternateKeyId     | Identyfikator GUID         |  AlternateKey ( identyfikator GUID) oparty na msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Przykład: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Ta tabela zawiera działania według użytkowników dostępnych w aplikacji Customer Insights.

| Column            | Pisz        | Opis                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| Identyfikator klienta        | String      | Identyfikator profilu klienta                                                                      |
| ActivityId        | String      | Wewnętrzny identyfikator działania klienta (klucz podstawowy)                                       |
| SourceEntityName  | String      | Nazwa encji źródłowej                                                                |
| SourceActivityId  | String      | Klucz podstawowy encji źródłowej                                                       |
| ActivityType      | String      | Typ działania (rodzaj działania) lub nazwa działania niestandardowego                                        |
| ActivityTimeStamp | DATETIME    | Sygnatura czasowa działania                                                                      |
| Stanowisko             | String      | Tytuł lub nazwa działalności                                                               |
| Opis       | String      | Opis działania                                                                     |
| Adres URL               | String      | Łącze do zewnętrznego adresu URL specyficznego dla działania                                         |
| SemanticData      | Ciąg JSON | Zawiera listę par klucz-wartość dla pól mapowania semantycznego specyficznych dla rodzaju działalności |
| RangeIndex        | String      | Unix timestamp używany do sortowania osi czasu aktywności i efektywnych zapytań o zakres |
| mydynci_unifiedactivityid   | Identyfikator GUID | Wewnętrzny identyfikator działania klienta (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Ta tabela zawiera dane wyjściowe działań opartych na atrybutach klienta.

| Column             | Pisz             | Opis                 |
|--------------------|------------------|-----------------------------|
| Identyfikator klienta         | String           | Identyfikator profilu klienta        |
| Miary           | Ciąg JSON      | Zawiera listę par kluczy wartości dla nazwy i wartości miary dla danego klienta | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | Identyfikator GUID      | Identyfikator profilu klienta |


### <a name="enrichment"></a>Wzbogacenie

Ta tabela zawiera wynik procesu wzbogacania.

| Column               | Pisz             |  Opis                                          |
|----------------------|------------------|------------------------------------------------------|
| Identyfikator klienta           | String           | Identyfikator profilu klienta                                 |
| EnrichmentProvider   | String           | Nazwa dostawcy wzbogacenia                                  |
| EnrichmentType       | String           | Typ wzbogacenia                                      |
| Wartości               | Ciąg JSON      | Lista atrybutów, których wzbogacenie jest wykonywane |
| msdynci_enrichmentid | Identyfikator GUID             | Różnych identyfikatorów GUID wygenerowanych na podstawie msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Przewidywanie

Ta tabela zawiera dane wyjściowe prognoz modelu.

| Column               | Pisz        | Opis                                          |
|----------------------|-------------|------------------------------------------------------|
| Identyfikator klienta           | String      | Identyfikator profilu klienta                                  |
| ModelProvider        | String      | Nazwa dostawcy modelu                                      |
| Model                | String      | Nazwa modelu                                                |
| Wartości               | Ciąg JSON | Lista atrybutów wytwarzanych przez model |
| msdynci_predictionid | Identyfikator GUID        | Różnych identyfikatorów GUID wygenerowanych na podstawie msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Członkostwo segmentu

Ta tabela zawiera informacje o członkostwie segmentu profilów klientów.

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| Identyfikator klienta        | String       | Identyfikator profilu klienta        |
| SegmentProvider      | String       | Aplikacja, która publikuje segmenty.      |
| SegmentMembershipType | String       | Typ klienta, w tym rekordzie członkostwa segmentu. Obsługuje wiele typów, takich jak Klient, Kontakt lub Konto. Domyślnie: Klient  |
| Segmenty       | Ciąg JSON  | Lista unikatowych segmentów, których członkiem jest profil klienta      |
| msdynci_identifier  | String   | Unikatowy identyfikator rekordu członkostwa segmentu. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | Identyfikator GUID      | Deterministyczny identyfikator GUID wygenerowany z poziomu `msdynci_identifier`          |

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
