---
title: Przykłady OData dla interfejsów API Dynamics 365 Customer Insights
description: Powszechnie używane przykłady wykorzystania Open Data Protocol (OData) do zadawania pytań Customer Insights API w celu przeglądania danych.
ms.date: 05/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: cdadd72bfe4272d8d83d923baaa6fd40d008473b
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808474"
---
# <a name="odata-query-examples"></a>Przykłady zapytań OData

Open Data Protocol (OData) jest protokołem dostępu do danych zbudowanym na podstawowych protokołach, takich jak HTTP. Wykorzystuje powszechnie akceptowane metodologie, takie jak REST dla sieci. Istnieją różne rodzaje bibliotek i narzędzi, które mogą być używane do korzystania z usług OData.

Ten artykuł zawiera listę często poszukiwanych przykładowych zapytań, które pomogą Ci w budowaniu własnych implementacji opartych na [Customer Insights API](apis.md).

Musisz zmodyfikować próbki zapytań, aby działały na docelowych środowiskach: 

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}` gdzie {instanceId} jest identyfikatorem GUID środowiska Customer Insights, które chcesz przeszukać. Operacja [ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) pozwala ci znaleźć {InstanceId}, do których masz dostęp.
- {CID}: GUID zunifikowanego rekordu klienta. Przykład: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: Identyfikator klucza głównego rekordu klienta w źródle danych. Przykład: `CNTID_1002`
- {DSname}: Ciąg znaków z nazwą jednostki źródła danych, które jest wprowadzane do Customer Insights. Przykład: `Website_contacts`.
- {SegmentName}: Ciąg znaków zawierający nazwę wyjściową segmentu w Customer Insights. Przykład: `Male_under_40`.

## <a name="customer"></a>kliencie

Poniższa tabela zawiera zestaw przykładowych zapytań dla encji *Klient*.

|Typ zapytania |Przykład  | Uwaga  |
|---------|---------|---------|
|Identyfikator pojedynczego klienta     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Klucz alternatywny    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Alternatywne klucze są przechowywane w zunifikowanej jednostce klienta       |
|Zaznacz   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|Za    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Klucz alternatywny + In   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Wyszukiwanie  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Zwraca 10 najlepszych wyników dla wyszukiwanego ciągu znaków      |
|Członkostwo segmentu  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Zwraca zadaną liczbę wierszy z encji segmentacji.      |

## <a name="unified-activity"></a>Ujednolicona aktywność

Poniższa tabela zawiera zestaw przykładowych zapytań dla encji *Ujednolicona aktywność*.

|Typ zapytania |Przykład  | Uwaga  |
|---------|---------|---------|
|Aktywność CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Listy działań dla określonego profilu klienta |
|Ramy czasowe działania    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Aktywność profilu klienta w określonym przedziale czasu       |
|Typ działania    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Aktywność według nazwy wyświetlanej     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Sortowanie działań    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Sortuj aktywności rosnąco lub malejąco       |
|Aktywność poszerzona o członkostwo w segmencie  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Inne przykłady

Poniższa tabela zawiera zestaw przykładowych zapytań dla innych encji.

|Typ zapytania |Przykład  | Uwaga  |
|---------|---------|---------|
|Miary CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Wzbogacone marki CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Wzbogacone interesy CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|In-Clause + Rozwiń     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>Nie są obsługiwane zapytania OData

Następujące zapytania nie są obsługiwane przez usługę Customer Insights:

- `$filter` do encji źródłowych, które są wgrane. Zapytania $filter można uruchamiać tylko na encjach systemowych utworzonych przez usługę Customer Insights.
- `$expand` z zapytania `$search`. Przykład: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` z `$select`, tylko jeśli wybrano podzbiór atrybutów. Przykład: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` wzbogacona marka lub powiązania zainteresowań dla danego klienta. Przykład: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Zapytania przewidywanie encji wyjściowych modelu za klucz alternatywny. Przykład: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
