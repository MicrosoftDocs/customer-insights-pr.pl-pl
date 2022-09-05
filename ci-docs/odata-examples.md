---
title: Przykłady zapytań OData dla interfejsów API usługi Customer Insights
description: Powszechnie używane przykłady wykorzystania Open Data Protocol (OData) do zadawania pytań Customer Insights API w celu przeglądania danych.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 26e56a3bab01ba55284a52e72efbcbfbaadaad6f
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387215"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>Przykłady zapytań OData dla interfejsów API usługi Customer Insights

Open Data Protocol (OData) jest protokołem dostępu do danych zbudowanym na podstawowych protokołach, takich jak HTTP. Wykorzystuje powszechnie akceptowane metodologie, takie jak REST dla sieci. Istnieją różne rodzaje bibliotek i narzędzi, które mogą być używane do korzystania z usług OData.

Aby pomóc Ci w tworzeniu własnych implementacji opartych na [Interfejsach API Customer Insights](apis.md), przejrzyj często zadawane przykładowe zapytania.

Musisz zmodyfikować próbki zapytań, aby działały na docelowych środowiskach:

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}/data` gdzie {instanceId} jest identyfikatorem GUID środowiska Customer Insights, które chcesz przeszukać. Operacja [ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) pozwala ci znaleźć {InstanceId}, do których masz dostęp.
- {CID}: GUID zunifikowanego rekordu klienta. Przykład: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: Identyfikator klucza głównego rekordu klienta w źródle danych. Przykład: `CNTID_1002`
- {DSname}: Ciąg znaków z nazwą jednostki źródła danych, które jest wprowadzane do Customer Insights. Przykład: `Website_contacts`.
- {SegmentName}: Ciąg znaków zawierający nazwę wyjściową segmentu w Customer Insights. Przykład: `Male_under_40`.

## <a name="customer"></a>kliencie

Przykładowe zapytania dotyczące *encji* Klient.

|Typ zapytania |Przykład  | Uwaga  |
|---------|---------|---------|
|Identyfikator pojedynczego klienta     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Klucz alternatywny    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Alternatywne klucze są przechowywane w zunifikowanej jednostce klienta       |
|Zaznacz   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|Za    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Klucz alternatywny + In   | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Wyszukiwanie  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Zwraca 10 najlepszych wyników dla wyszukiwanego ciągu znaków      |
|Członkostwo segmentu  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Zwraca zadaną liczbę wierszy z encji segmentacji.      |
|Członkostwo w segmentach dla klienta | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'&IsMemberOfSegment('{SegmentName}')`     | Zwraca profil klienta, jeśli użytkownik należy do danego segmentu     |

## <a name="unified-activity"></a>Ujednolicona aktywność

Przykładowe zapytania dotyczące encji *UnifiedActivity*.

|Typ zapytania |Przykład  | Uwaga  |
|---------|---------|---------|
|Aktywność CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Listy działań dla określonego profilu klienta |
|Ramy czasowe działania    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Aktywność profilu klienta w określonym przedziale czasu       |
|Typ działania    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Aktywność według nazwy wyświetlanej     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Sortowanie działań    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Sortuj aktywności rosnąco lub malejąco       |
|Aktywność poszerzona o członkostwo w segmencie  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Inne przykłady

Przykładowe zapytania dotyczące innych encji.

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