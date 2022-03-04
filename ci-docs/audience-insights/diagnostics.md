---
title: Inspekcja Dynamics 365 Customer Insights za pomocą Azure Monitor
description: Dowiedz się, jak wysyłać dzienniki do Microsoft Azure Monitor.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 2e0801c2b6af591e48a7df485a8523903c07617c
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354421"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Przekazywanie logów w Dynamics 365 Customer Insights z Azure Monitor (wersja zapoznawcza)

Dynamics 365 Customer Insights zapewnia bezpośrednią integrację z Azure Monitor. Logi zasobów Azure Monitor pozwalają monitorować i wysyłać logi do [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview) lub strumieniować je do [Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/).

W aplikacji Customer Insights są wysyłane następujące dzienniki zdarzeń:

- **Zdarzenia inspekcji**
  - **APIEvent** — umożliwia zmianę śledzenia wykonanego za pomocą interfejsu użytkownika Dynamics 365 Customer Insights.
- **Zdarzenia operacyjne**
  - **WorkflowEvent** - Przepływ pracy pozwala na skonfigurowanie [Źródła danych](data-sources.md), [unifikację](data-unification.md) i [wzbogacenie](enrichment-hub.md) oraz [eksport](export-destinations.md) danych do innych systemów. Wszystkie te kroki mogą być wykonywane pojedynczo (np. uruchomienie pojedynczego eksportu) lub w sposób zsynchronizowany (np. odświeżenie danych ze źródeł danych, które uruchamia proces unifikacji, który spowoduje pobranie dodatkowych elementów wzbogacających, a następnie wyeksportowanie danych do innego systemu). Aby uzyskać więcej informacji, zobacz [schemat WorflowEvent](#workflow-event-schema).
  - **APIEvent** — wszystkie wywołania interfejsów API do wystąpienia klienta w Dynamics 365 Customer Insights. Aby uzyskać więcej informacji, zobacz [schemat APIEvent](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Skonfiguruj ustawienia diagnostyczne

### <a name="prerequisites"></a>Wymagania wstępne

Aby skonfigurować diagnostykę w Customer Insights, muszą być spełnione następujące warunki wstępne:

- Masz aktywną [subskrypcję platformy Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- Masz uprawnienia [administratora](permissions.md#administrator) w Customer Insights.
- Masz rolę **Współautora** i **Administratora dostępu użytkownika** na zasobie docelowym w Azure. Zasobem tym może być konto Azure Storage, centrum zdarzeń platformy Azure lub obszar roboczy Azure Log Analytics. Aby uzyskać więcej informacji, przejdź do tematu [Dodawanie i usuwanie przypisań ról platformy Azure za pomocą witryny Azure Portal](/azure/role-based-access-control/role-assignments-portal).
- Spełnione są [wymagania docelowe](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) usługi Azure Storage, w centrum zdarzeń platformy Azure lub analiza dzienników Azure.
- Masz co najmniej rolę **Czytelnik** w grupie zasobów, do której należy zasób.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Skonfiguruj diagnostykę za pomocą Azure Monitor

1. W Customer Insights wybierz **System** > **Diagnostyka**, aby zobaczyć miejsca docelowe diagnostyki skonfigurowane w tej instancji.

1. Wybierz **Dodaj lokalizację docelową**.

   > [!div class="mx-imgBorder"]
   > ![Połączenie diagnostyki](media/diagnostics-pane.png "Połączenie diagnostyki")

1. Podaj nazwę w nazwie **Miejsca docelowego diagnostyki**.

1. Wybierz **Dzierżawę** subskrypcji Azure z zasobem docelowym i wybierz **Zaloguj się**.

1. Wybierz **Typ zasobu** (konto Storage, Event Hub lub analiza dzienników).

1. Wybierz **Subskrypcję** dla zasobu docelowego.

1. Wybierz **Grupa zasobów** dla zasobu docelowego.

1. Wybierz **Zasób**.

1. Potwierdź oświadczenie dotyczące **zasad ochrony poufności informacji i zgodności**.

1. Wybierz **Połącz z systemem**, aby połączyć się z zasobem docelowym. Logi zaczną pojawiać się w miejscu docelowym po 15 minutach, jeśli API jest w użyciu i generuje zdarzenia.

### <a name="remove-a-destination"></a>Usuń miejsce docelowe

1. Przejdź do **Systemu** > **Diagnostyka**.

1. Wybierz z listy miejsce docelowe diagnostyki.

1. W kolumnie **Akcje** wybierz ikonę **Usuń**.

1. Potwierdź usunięcie, aby zatrzymać przekazywanie dziennika. Zasób w subskrypcji Azure nie zostanie usunięty. Możesz wybrać link w kolumnie **Akcje**, aby otworzyć portal Azure dla wybranego zasobu i tam go usunąć.

## <a name="log-categories-and-event-schemas"></a>Kategorie dzienników i schematy zdarzeń

Obecnie wspierane są [zdarzenia API](apis.md) oraz zdarzenia przepływu pracy, przy czym obowiązują następujące kategorie i schematy.
Schemat dziennika jest zgodny z [wspólny schemat Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Kategorie

Customer Insights oferuje dwie kategorie:

- **Audyt zdarzeń**: [Zdarzenia API](#api-event-schema), aby śledzić zmiany konfiguracji w serwisie. Operacje `POST|PUT|DELETE|PATCH` należą do tej kategorii.
- **Zdarzenia operacyjne**: [zdarzenia API](#api-event-schema) lub [zdarzenia przepływu pracy](#workflow-event-schema) wygenerowane podczas korzystania z usługi.  Na przykład, żądania `GET` lub zdarzenia wykonania przepływu pracy.

## <a name="configuration-on-the-destination-resource"></a>Konfiguracja na zasobie docelowym

W zależności od tego, jaki typ zasobu wybierzesz, poniższe kroki zostaną automatycznie zastosowane:

### <a name="storage-account"></a>Storage account

Nazwa główna usługi Customer Insights otrzymuje uprawnienie **Współautor konta przechowywania** na wybranym zasobie i tworzy dwa kontenery pod wybraną przestrzenią nazw:

- `insight-logs-audit` zawierający **wydarzenia związane z audytem**
- `insight-logs-operational` zawierające **zdarzenia operacyjne**

### <a name="event-hub"></a>Centrum zdarzeń usługi Event Hubs

Nazwa główna usługi Customer Insights otrzymuje uprawnienie **Właściciel danych Azure Event Hubs** na zasobie i utworzy dwa Event Huby w wybranej przestrzeni nazw:

- `insight-logs-audit` zawierający **wydarzenia związane z audytem**
- `insight-logs-operational` zawierające **zdarzenia operacyjne**

### <a name="log-analytics"></a>Log Analytics

Zleceniodawca usługi Customer Insights otrzymuje uprawnienie **Współtwórca Log Analytics** na zasobie. Logi będą dostępne w **Dzienniki** > **Tabele** > **Zarządzanie dziennikami** na wybranym obszarze roboczym Log Analytics. Rozwiń rozwiązanie **Zarządzanie dziennikami** i zlokalizuj tabele `CIEventsAudit` oraz `CIEventsOperational`.

- `CIEventsAudit` zawierający **wydarzenia związane z audytem**
- `CIEventsOperational` zawierające **zdarzenia operacyjne**

W oknie **Kwerendy** rozwiń rozwiązanie **Inspekcja** i znajdź przykładowe kwerendy poprzez wyszukanie `CIEvents`.

## <a name="event-schemas"></a>Schematy zdarzeń

Zdarzenia API i zdarzenia przepływu pracy mają wspólną strukturę, a szczegóły, gdzie się różnią, znajdziesz w [schemacie zdarzeń API](#api-event-schema) lub [schemacie zdarzeń przepływu pracy](#workflow-event-schema).

### <a name="api-event-schema"></a>Schemat zdarzeń API

| Pole             | DataType  | Wymagane/opcjonalne | Description       | Przykład        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Sygnatura czasowa | Wymagania          | Sygnatura czasowa zdarzenia (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Wymagania          | ResourceId instancji, która wyemitowała zdarzenie         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Wymagania          | Nazwa operacji reprezentowanej przez to zdarzenie.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Wymagania          | Kategoria logiczna wydarzenia. `Operational` lub `Audit`. Wszystkie żądania HTTP POST/PUT/PATCH/DELETE są oznaczone `Audit`, wszystko inne `Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Wymagania          | Status wydarzenia. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Opcjonalnie          | Status rezultatu wydarzenia. Jeśli operacja odpowiada wywołaniu REST API, jest to kod statusu HTTP.        | `200`             |
| `durationMs`      | Długi      | Opcjonalnie          | Czas trwania operacji w milisekundach.     | `133`     |
| `callerIpAddress` | String    | Opcjonalnie          | Adres IP wywołującego, jeśli operacja odpowiada wywołaniu API pochodzącemu z publicznie dostępnego adresu IP.                                                 | `144.318.99.233`         |
| `identity`        | String    | Opcjonalnie          | Obiekt JSON opisujący tożsamość użytkownika lub aplikacji, która wykonała daną operację.       | Zobacz sekcję [Tożsamość](#identity-schema).     |  |
| `properties`      | String    | Opcjonalnie          | Obiekt JSON z większą liczbą właściwości dla danej kategorii wydarzeń.      | Zobacz sekcję [Właściwości](#api-properties-schema).    |
| `level`           | String    | Wymagania          | Poziom istotności zdarzenia.    | `Informational`, `Warning`, `Error` lub `Critical`.           |
| `uri`             | String    | Opcjonalnie          | Bezwzględny URI żądania.    |               |

#### <a name="identity-schema"></a>Schemat tożsamości

Obiekt `identity` JSON ma następującą strukturę

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Pole                         | Description                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Przypisana rola dla użytkownika lub aplikacji. Aby uzyskać więcej informacji, zobacz [uprawnienia użytkownika](permissions.md).                                     |
| `Authorization.RequiredRoles` | Role wymagane do wykonania operacji. Rola `Admin` jest uprawniona do wykonywania wszystkich operacji.                                                    |
| `Claims`                      | Twierdzenia użytkownika lub aplikacji JSON web token (JWT). Właściwości roszczeń różnią się w zależności od organizacji i konfiguracji Azure Active Directory. |

#### <a name="api-properties-schema"></a>Schemat właściwości API

[Wydarzenia API](apis.md) mają następujące właściwości.

| Pole                        | Description                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Zawsze `ApiEvent`, oznaczając zdarzenie dziennika jako zdarzenie API.                                                                 |
| `properties.userAgent`       | Agent przeglądarki wysyłający żądanie lub `unknown`.                                                                        |
| `properties.method`          | Metoda HTTP: `GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Względna ścieżka żądania.                                                                                          |
| `properties.origin`          | URI wskazujący skąd pochodzi pobieranie lub `unknown`.                                                                  |
| `properties.operationStatus` | `Success` dla kodu statusu HTTP < 400 <br> `ClientError` dla kodu statusu HTTP < 500 <br> `Error` dla stanu HTTP >= 500 |
| `properties.tenantId`        | Identyfikator organizacji                                                                                                        |
| `properties.tenantName`      | Nazwa organizacji.                                                                                              |
| `properties.callerObjectId`  | ObjectId Azure Active Directory osoby dzwoniącej.                                                                         |
| `properties.instanceId`      | `instanceId` Customer Insights                                                                                         |

### <a name="workflow-event-schema"></a>Schemat zdarzeń przepływu pracy

Przepływ pracy zawiera wiele kroków. [Źródła danych](data-sources.md), [unifikacja](data-unification.md), [wzbogacanie](enrichment-hub.md) i [eksport](export-destinations.md) danych. Wszystkie te kroki mogą być uruchamiane indywidualnie lub orkiestrowane z następującymi procesami. 

#### <a name="operation-types"></a>Rodzaje operacji

| OperationType     | Grupowy                                     |
| ----------------- | ----------------------------------------- |
| Pozyskiwanie danych         | [Źródła danych](data-sources.md)           |
| DataPreparation   | [Źródła danych](data-sources.md)           |
| Mapowanie               | [Ujednolicenie danych](data-unification.md)   |
| Match             | [Ujednolicenie danych](data-unification.md)   |
| Scalanie             | [Ujednolicenie danych](data-unification.md)   |
| ProfileStore      | [Profile klientów](customer-profiles.md) |
| Wyszukiwanie            | [Profile klientów](customer-profiles.md) |
| Aktywność          | [Działania](activities.md)                  |
| AttributeMeasures | [Segmenty i miary](segments.md)      |
| EntityMeasures    | [Segmenty i miary](segments.md)      |
| Miary          | [Segmenty i miary](segments.md)      |
| Segmentacja      | [Segmenty i miary](segments.md)      |
| Wzbogacenie        | [Wzbogacenie](enrichment-hub.md)                                          |
| Analizy      | [Przewidywania](predictions-overview.md)                                          |
| AiBuilder         | [Przewidywania](predictions-overview.md)                                          |
| Wyniki analiz          | [Przewidywania](predictions-overview.md)                                          |
| Export            | [Eksporty](export-destinations.md)                                          |
| ModelManagement   | [Przewidywania](custom-models.md)                                           |
| Relacja      | [Ujednolicenie danych](relationships.md)                                           |

#### <a name="field-description"></a>Opis pola

| Pole           | DataType  | Wymagane/opcjonalne | Description                                                                                                                                                   | Przykład                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Sygnatura czasowa | Wymagania          | Sygnatura czasowa zdarzenia (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Wymagania          | ResourceId instancji, która wyemitowała zdarzenie.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Wymagania          | Nazwa operacji reprezentowanej przez to zdarzenie. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Zobacz [Typy operacji](#operation-types), jako odnośnik. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Wymagania          | Kategoria logiczna wydarzenia. Zawsze `Operational` dla zdarzeń przepływu pracy                                                                                           | `Operational`                                                                                                                                                            | 
| `resultType`    | String    | Wymagania          | Status wydarzenia. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Długi      | Opcjonalnie          | Czas trwania operacji w milisekundach.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Opcjonalnie          | Obiekt JSON z większą liczbą właściwości dla danej kategorii wydarzeń.                                                                                        | Zobacz podrozdział [Propertie przepływu pracy](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Wymagania          | Poziom istotności zdarzenia.                                                                                                                                  | `Informational`, `Warning` lub `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Schemat właściwości przepływu pracy

Zdarzenia przepływu pracy mają następujące właściwości.

| Pole              | Workflow | Zadanie | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Tak      | Tak  | Zawsze `WorkflowEvent`, oznaczając zdarzenie jako zdarzenie przepływu pracy.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Tak      | Tak  | Identyfikator uruchomionego przepływu pracy. Wszystkie zdarzenia przepływu i zadania w ramach wykonania przepływu mają ten sam `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Tak      | Tak  | Identyfikator operacji, zobacz [Typy operacji].(#operation-types)                                                                                                                                                                                       |
| `properties.tasksCount`                      | Tak      | Nie.   | Tylko przepływ pracy. Liczba zadań, które uruchamia przepływ pracy.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Tak      | Nie.   | Opcjonalny. Tylko zdarzenia przepływu pracy. Azure Active Directory [objectId użytkownika](/azure/marketplace/find-tenant-object-id#find-user-object-id), który uruchomił przepływ pracy, zobacz także `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Tak      | Nie.   | odświeżenie `full` lub `incremental`.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Tak      | Nie.   | `OnDemand` lub `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Tak      | Nie.   | `Running` lub `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Tak      | Tak  | Sygnatura czasowa UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Tak      | Tak  | Sygnatura czasowa UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Tak      | Tak  | Sygnatura czasowa UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Tak      | Tak  | `instanceId` Customer Insights                                                                                                                                                                                                                              |  |
| `properties.identifier`                      | Nie.       | Tak  | - Dla OperationType = `Export`, identyfikatorem jest guid konfiguracji eksportu. <br> - Dla OperationType = `Enrichment`, jest to guid wzbogacenia <br> - Dla OperationType `Measures` i `Segmentation`, identyfikatorem jest nazwa podmiotu. |
| `properties.friendlyName`                    | Nie.       | Tak  | Przyjazna dla użytkownika nazwa eksportu lub podmiotu, który jest przetwarzany.                                                                                                                                                                                           |
| `properties.error`                           | Nie.       | Tak  | Opcjonalny. Komunikat o błędzie zawierający więcej szczegółów.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | Nie.       | Tak  | Opcjonalny. Tylko dla OperationType `Export`. Określa typ eksportu. Aby uzyskać więcej informacji, zobacz [przegląd miejsc docelowych eksportu](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | Nie.       | Tak  | Opcjonalny. Tylko dla OperationType `Export`. Zawiera listę skonfigurowanych encji w eksporcie.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | Nie.       | Tak  | Opcjonalny. Tylko dla OperationType `Export`. Szczegółowa wiadomość dotycząca eksportu.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | Nie.       | Tak  | Opcjonalny. Tylko dla OperationType `Segmentation`. Wskazuje całkowitą liczbę członków segmentu.                                                                                                                                                    |
