---
title: Dane aplikacji Customer Insights w Microsoft Dataverse
description: Korzystanie z encji funkcji Customer Insights jako tabel w Microsoft Dataverse.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: bbbbf2a7f5edb81ee75f6e33988cd4721134b6e7
ms.sourcegitcommit: 0363559a1af7ae16da2a96b09d6a4a8a53a8cbb8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547639"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Praca z danymi aplikacji Customer Insights w Microsoft Dataverse

Customer Insights udostępnia opcję udostępniania encji wyjściowych w [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Integracja ta umożliwia łatwe współdzielenie danych i tworzenie własnych rozwiązań dzięki podejściu low code / no code. [Encje wyjściowe](#output-entities) są dostępne jako tabele w środowisku Dataverse. Możesz wykorzystać te dane w dowolnej innej aplikacji opartej na tabelach Dataverse. Tabele te umożliwiają takie scenariusze jak zautomatyzowane przepływy pracy dzięki Power Automate czy budowanie aplikacji za pomocą Power Apps. Obecna implementacja wspiera głównie wyszukiwanie, gdzie dane z dostępnych jednostek Customer Insights mogą zostać pobrane dla danego identyfikatora klienta.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Dołączanie środowiska Dataverse do aplikacji Customer Insights

**Istniejąca organizacja**

Administratorzy mogą skonfigurować Customer Insights tak, aby [używał istniejącego środowiska Dataverse](create-environment.md) podczas tworzenia środowiska Customer Insights. Podając adres URL do środowiska Dataverse, dołącza się do ich nowego środowiska wyników analiz odbiorców. Środowiska Customer Insights i Dataverse muszą być hostowane w tym samym regionie. 

Jeśli nie chcesz korzystać z istniejącego środowiska Dataverse, system tworzy nowe środowisko dla danych Customer Insights w Twojej dzierżawie. 

> [!NOTE]
> Jeśli Twoja organizacja korzysta już z Dataverse w swojej dzierżawie, ważne jest, aby pamiętać, że [tworzenie środowiska Dataverse jest kontrolowane przez administratora](/power-platform/admin/control-environment-creation). Na przykład, jeśli konfigurujesz nowe środowisko statystyk odbiorców na swoim koncie organizacji, a administrator wyłączył tworzenie środowisk próbnych Dataverse dla wszystkich z wyjątkiem administratorów, nie możesz utworzyć nowego środowiska próbnego.
> 
> Środowiska próbne Dataverse utworzone w usłudze Customer Insights mają 3 GB pamięci masowej, która nie jest wliczana do całkowitej pojemności przysługującej dzierżawcy. Płatne subskrypcje uzyskują uprawnienie Dataverse w wysokości 15 GB na bazę danych i 20 GB na przechowywanie plików.

**Nowa organizacja**

Jeśli podczas zakładania Customer Insights tworzysz nową organizację, system automatycznie tworzy dla ciebie nowe środowisko Dataverse w twojej organizacji.

## <a name="output-entities"></a>Encje wyjściowe

Niektóre encje wyjściowe z odbiorcy danych są dostępne jako tabele w tabeli w Dataverse. Poniższe sekcje opisują oczekiwany schemat tych tabel.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Wzbogacenie](#enrichment)
- [Przewidywanie](#prediction)
- [Członkostwo segmentu](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Ta tabela zawiera ujednolicony profil klienta z funkcji Customer Insights. Schemat ujednoliconego profilu klienta zależy od jednostek i atrybutów używanych w procesie scalania. Schemat profilu klienta zazwyczaj zawiera podzbiór atrybutów z [definicji Common Data Model klienta CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Tabela AlternateKey zawiera klucze encji, które brały udział w procesie ujednolicania.

|Column  |Pisz  |Opis  |
|---------|---------|---------|
|DataSourceName    |String         | Nazwa źródła danych. Na przykład: `datasource5`        |
|EntityName        | String        | Nazwa encji używanej w analizie odbiorców. Na przykład: `contact1`        |
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

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| Identyfikator klienta        | String       | Identyfikator profilu klienta        |
| SegmentProvider      | String       | Aplikacja, która publikuje segmenty. Domyślnie: Wyniki analiz odbiorców         |
| SegmentMembershipType | String       | Typ klienta, w tym rekordzie członkostwa segmentu. Obsługuje wiele typów, takich jak Klient, Kontakt lub Konto. Domyślnie: Klient  |
| Segmenty       | Ciąg JSON  | Lista unikatowych segmentów, których członkiem jest profil klienta      |
| msdynci_identifier  | String   | Unikatowy identyfikator rekordu członkostwa segmentu. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | Identyfikator GUID      | Deterministyczny identyfikator GUID wygenerowany z poziomu `msdynci_identifier`          |
