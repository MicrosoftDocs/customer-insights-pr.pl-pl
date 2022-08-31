---
title: Praca z danymi aplikacji Customer Insights w Microsoft Dataverse
description: Dowiedz się, jak połączyć Customer Insights i Microsoft Dataverse i zrozumieć encje wyjściowe, które są eksportowane do Dataverse.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 0d536259f310b41fe12922baeebdc4569937db08
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303842"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Praca z danymi aplikacji Customer Insights w Microsoft Dataverse

Customer Insights udostępnia opcję udostępniania encji wyjściowych w [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Integracja ta umożliwia łatwe współdzielenie danych i tworzenie własnych rozwiązań dzięki podejściu low code / no code. [Encje wyjściowe](#output-entities) są dostępne jako tabele w środowisku Dataverse. Możesz wykorzystać te dane w dowolnej innej aplikacji opartej na tabelach Dataverse. Tabele te umożliwiają takie scenariusze jak zautomatyzowane przepływy pracy dzięki Power Automate czy budowanie aplikacji za pomocą Power Apps.

Połączenie ze środowiskiem Dataverse umożliwia również [pozyskiwanie danych z lokalnych źródeł danych za pomocą przepływów danych Power Platform i bram](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Wymagania wstępne

- Środowiska Customer Insights i Dataverse muszą być hostowane w tym samym regionie.
- Rola administratora globalnego skonfigurowana w środowisku Dataverse. Sprawdź, czy to [środowisko Dataverse jest powiązane](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) z określonymi grupami zabezpieczeń i upewnij się, że dodane do tych grup zabezpieczeń.
- Żadne inne środowisko Customer Insights nie jest już powiązane ze środowiskiem Dataverse, z którym chcesz się połączyć. Dowiedz się, [jak usunąć istniejące połączenie ze środowiskiem Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).
- Środowisko Microsoft Dataverse połączone z jednym kontem magazynu, jeśli skonfigurujesz środowisko do [korzystania z usługi Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Pojemność magazynu uprawnienia Dataverse

Subskrypcja usługi Customer Insights umożliwia nadsyłanie dodatkowej wydajności dla istniejącej istniejącej [wydajności magazynu Dataverse w organizacji](/power-platform/admin/capacity-storage). Dodana pojemność zależy od liczby profili, z których korzysta Twoja subskrypcja.

**Przykład:**

Zakładając, że otrzymasz 15 GB miejsca na bazę danych i 20 GB miejsca na pliki na 100 000 profili klientów. Jeśli Twoja subskrypcja obejmuje 300 000 profili klientów, łączna pojemność magazynu wynosi 45 GB (3 x 15 GB) magazynu bazy danych i 60 GB magazynu plików (3 x 20 GB). Podobnie, jeśli masz subskrypcję B-do-B z 30 000 kont, łączna pojemność magazynu wynosi 45 GB (3 x 15 GB) magazynu bazy danych i 60 GB magazynu plików (3 x 20 GB).

Pojemność dziennika nie jest przyrostowa i stała dla Twojej organizacji.

Aby uzyskać więcej informacji na temat szczegółowych uprawnień dyspozycyjności, zobacz [Przewodnik po licencjonowaniu Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Łączenie środowiska Dataverse z usługą Customer Insights

Krok **Microsoft Dataverse** pozwala połączyć Customer Insights ze środowiskiem Dataverse podczas [tworzenia środowiska Customer Insights](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="udostępnianie danych z włączoną automatycznie obsługą Microsoft Dataverse dla nowych środowisk.":::

1. Podaj adres URL do swojego środowiska Dataverse lub pozostaw puste, aby utworzyć go dla siebie.

   > [!NOTE]
   > Po ustanowieniu połączenia między usługą Customer Insights a Dataverse, nie zmieniaj nazwy organizacji dla środowiska Dataverse. Nazwa organizacji jest używana w adresie URL Dataverse, a zmieniona nazwa przerwie połączenie z usługą Customer Insights.

   [Administratorzy Power Platform mogą kontrolować, kto może tworzyć nowe środowiska Dataverse](/power-platform/admin/control-environment-creation). Jeśli próbujesz skonfigurować nowe środowisko Customer Insights i nie możesz, administrator mógł wyłączyć tworzenie środowisk Dataverse dla wszystkich oprócz administratorów.

1. Jeśli używasz własnego konta Data Lake Storage:
   1. Wybierz opcję **Włącz udostępnianie danych** w Dataverse.
   1. Wpisz **Identyfikator uprawnień**. Aby uzyskać identyfikator uprawnienia, [włącz udostępnianie danych za pomocą Dataverse z własnej usługi Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Włącz udostępnianie danych za pomocą Dataverse z własnej usługi Azure Data Lake Storage (wersja zapoznawcza)

W [Twoje własne konto Azure Data Lake Storage](own-data-lake-storage.md) sprawdź, czy użytkownik konfigurujący środowisko Customer Insights ma co najmniej **Uprawnienia do odczytu obiektów blob magazynu** w usłudze `customerinsights` kontener na koncie magazynu.

### <a name="limitations"></a>Ograniczenia

- Istnieje mapowanie jeden do jednego między organizacją Dataverse a kontem usługi Azure Data Lake Storage. Organizacja Dataverse jest połączona z kontem magazynu, nie może się połączyć z innym kontem magazynu. To ograniczenie uniemożliwia Dataverse wypełnianie wielu kont magazynu.
- Udostępnianie danych nie będzie działać, jeśli do uzyskania dostępu do konta usługi Azure Data Lake Storage jest potrzebna konfiguracja łącza prywatnego platformy Azure, ponieważ znajduje się ono za zaporą. Dataverse obecnie nie obsługuje połączenia z prywatnymi punktami końcowymi za pośrednictwem łącza prywatnego.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Konfigurowanie grup zabezpieczeń dla Azure Data Lake Storage

1. W subskrypcji Azure utwórz dwie grupy zabezpieczeń — jedną grupę zabezpieczeń **Czytelnik** i jedną grupę zabezpieczeń **współautor** i ustaw usługę Microsoft Dataverse jako właściciela obu grup zabezpieczeń.

1. Zarządzaj listą kontroli dostępu (ACL) dla konteneru `customerinsights` w ramach konta magazynu za pośrednictwem tych grup zabezpieczeń.
   1. Dodaj usługę Microsoft Dataverse i dowolne aplikacje biznesowe oparte na Dataverse, takie jak Dynamics 365 Marketing, do grupy zabezpieczeń **Czytelnik** z uprawnieniami **tylko do odczytu**.
   1. Dodaj *tylko* aplikację Customers Insights do grupy zabezpieczeń **współautor**, aby udzielić zarówno uprawnień do **odczytu i zapisu** do pisania profilów i analiz.

### <a name="set-up-powershell"></a>Konfigurowanie PowerShell

Skonfiguruj program PowerShell do wykonywania skryptów programu PowerShell.

1. Zainstaluj najnowszą wersję [programu Azure Active Directory PowerShell dla programu Graph](/powershell/azure/active-directory/install-adv2).
   1. Na komputerze wybierz klawisz Windows i wyszukaj program **Windows PowerShell** i wybierz opcję **Uruchom jako Administrator**.
   1. W wyświetlonym oknie PowerShell wprowadź polecenie `Install-Module AzureAD`.

1. Zaimportuj trzy moduły.
   1. W oknie PowerShell wpisz `Install-Module -Name Az.Accounts` i postępuj zgodnie z instrukcjami.
   1. Powtórz dla `Install-Module -Name Az.Resources` i `Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>Wykonywanie skryptów programu PowerShell i uzyskiwanie identyfikatora uprawnień

1. Pobierz dwa skrypty programu PowerShell, które trzeba uruchomić, ze strony [repo GitHub](https://github.com/trin-msft/byol) inżyniera.
   - `CreateSecurityGroups.ps1`: Wymaga uprawnień administratora dzierżawy.
   - `ByolSetup.ps1`: wymaga uprawnień Właściciel danych obiektów blob magazynu na poziomie konta magazynu/konteneru. Skrypt ten spowoduje utworzenie uprawnień dla użytkownika. Przypisanie roli można usunąć ręcznie po pomyślnym uruchomieniu skryptu.

1. Wykonaj `CreateSecurityGroups.ps1` w programie Windows PowerShell, podając identyfikator subskrypcji Azure zawierający identyfikator Azure Data Lake Storage. Otwórz skrypt PowerShell w edytorze, aby przejrzeć dodatkowe informacje i zaimplementowaną logikę.

   Ten skrypt tworzy dwie grupy zabezpieczeń w subskrypcji Azure: jedną dla grupy Czytelnik, a drugą dla współautor klienta. Microsoft Dataverse jest właścicielem obu tych grup zabezpieczeń.

1. Zapisz obie wartości identyfikatorów grup zabezpieczeń wygenerowanych przez ten skrypt, bo użyjemy ich w skrypcie `ByolSetup.ps1`.

   > [!NOTE]
   > W dzierżawie można wyłączyć tworzenie grupy zabezpieczeń. W takim przypadku jest potrzebna konfiguracja ręczna, a administrator Azure AD będzie musiał włączyć [tworzenie grupy zabezpieczeń](/azure/active-directory/enterprise-users/groups-self-service-management).

1. Wykonaj `ByolSetup.ps1` w programie Windows PowerShell, podając identyfikator subskrypcji platformy Azure zawierający nazwę usługi Azure Data Lake Storage, nazwę konta magazynu, nazwę grupy zasobów oraz wartości identyfikatorów grupy zabezpieczeń czytelnik i współautor. Otwórz skrypt PowerShell w edytorze, aby przejrzeć dodatkowe informacje i zaimplementowaną logikę.

   Ten skrypt dodaje wymaganą kontrolę dostępu opartą na tole dla usługi Microsoft Dataverse i dowolnych aplikacji biznesowych opartych na Dataverse. Aktualizuje również Listę kontroli dostępu (ACL) w kontenerze `customerinsights` dla grup zabezpieczeń utworzonych za pomocą skryptu `CreateSecurityGroups.ps1`. Grupa współautor będzie mieć uprawnienie *rwx*, a grupa Czytelnicy będzie mieć tylko uprawnienie *r-x*.

1. Skopiuj ciąg wyjściowy, który wygląda jak: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Wprowadź ciąg wyjściowy skopiowany z powyższej strony do pola **Identyfikator uprawnień** w kroku konfiguracji środowiska dla ustawienia Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opcje konfiguracji umożliwiające udostępnianie danych z własnej usługi Azure Data Lake Storage za pomocą Microsoft Dataverse.":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Usuń istniejące połączenie ze środowiskiem Dataverse

Podczas łączenia się ze środowiskiem Dataverse komunikat o błędzie **Ta organizacja CDS jest już połączona z inną instancją Customer Insights** oznacza, że środowisko Dataverse jest już używane w środowisku Customer Insights. Możesz usunąć istniejące połączenie jako administrator globalny w środowisku Dataverse. Wypełnienie zmian może zająć kilka godzin.

1. Przejdź do [Power Apps](https://make.powerapps.com).
1. Wybierz środowisko z selektora środowiska.
1. Przejdź na stronę **Rozwiązania**.
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

| Column            | Type        | opis                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| Identyfikator klienta        | String      | Identyfikator profilu klienta                                                                      |
| ActivityId        | String      | Wewnętrzny identyfikator działania klienta (klucz podstawowy)                                       |
| SourceEntityName  | String      | Nazwa encji źródłowej                                                                |
| SourceActivityId  | String      | Klucz podstawowy encji źródłowej                                                       |
| ActivityType      | String      | Typ działania (rodzaj działania) lub nazwa działania niestandardowego                                        |
| ActivityTimeStamp | DATETIME    | Sygnatura czasowa działania                                                                      |
| Nazwa             | String      | Tytuł lub nazwa działalności                                                               |
| opis       | String      | Opis działania                                                                     |
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

| Column               | Type        | opis                                          |
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


[!INCLUDE [footer-include](includes/footer-banner.md)]
