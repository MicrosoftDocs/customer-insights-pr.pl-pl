---
title: Zaawansowane scenariusze sieciowego SDK
description: Zaawansowane scenariusze, które należy rozważyć podczas instrumentowania witryny sieci Web za pomocą zestawu SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 11/12/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7455d276035bfaf1f8a93d0e3b0b0884353a4010715c05d1d696309f7eb4b233
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036341"
---
# <a name="advanced-web-sdk-instrumentation"></a>Zaawansowane instrumentowanie zestawu SDK sieci Web

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ten artykuł zawiera przewodnik po zaawansowanych scenariuszach, które można rozważyć przy [instrumentowaniu witryny sieci Web](instrument-website.md) przy użyciu SDK analizy odbiorców w Dynamics 365 Customer Insights.

## <a name="setting-user-details-for-your-event"></a>Ustawianie szczegółów zdarzenia przez użytkownika

Zestaw SDK umożliwia definiowanie informacji o użytkowniku, które mogą być wysyłane przy każdym zdarzeniu. Można określić szczegóły użytkownika we właściwości o nazwie `user` (oczekiwane dane dla tej właściwości to obiekt `IUser`), podobnie jak w przypadku `src`, `name` i `cfg` we fragmencie kodu konfiguracji.

Obiekt `IUser` zawiera następujące właściwości ciągu:

- **localId**: identyfikator lokalny użytkownika.
- **authId**: uwierzytelniony identyfikator użytkownika.
- **authType**: typ uwierzytelniania używany do uzyskania uwierzytelnionego identyfikatora użytkownika.
- **name**: Nazwa użytkownika.
- **email**: Adres e-mail użytkownika.
    
W następującym przykładzie przedstawiono fragment kodu wysyłania informacji o użytkowniku. Gdy funkcja jest oznaczana przez *, zastąp ją implementacją wywołującą te wartości:  

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
    name:"myproject",      
    cfg:{ 
      ingestionKey:<paste your ingestion key>", 
      autoCapture:{ 
        view:true, 
        click:true 
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

Informacje o użytkowniku można również określać, wywołując interfejs API `setUser(user: IUser)` w zestawie SDK. Dane telemetryczne wysyłane po wywołaniu `setUser API` będą zawierać informacje o użytkowniku.

## <a name="adding-custom-properties-for-each-event"></a>Dodawanie właściwości niestandardowych dla każdego zdarzenia

Zestaw SDK umożliwia zdefiniowanie niestandardowych właściwości, które mogą być wysyłane przy każdym zdarzeniu. Można określić właściwości niestandardowe jako obiekt zawierający parę klucz-wartość (może to być wartość typu `string | number | boolean`). Obiekt można dodać we właściwości o nazwie `props`, podobnie jak w `src`, `name`, i `cfg` we fragmencie kodu konfiguracji. 

W następującym przykładzie przedstawiono fragment kodu wysyłania właściwości niestandardowych:

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
    name:"myproject",      
    cfg:{ 
      ingestionKey:<paste your ingestion key>", 
      autoCapture:{ 
        view:true, 
        click:true 
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

Można również określać właściwości niestandardowe pojedynczo, wywołując interfejs API `setProperty(name: string, value: string | number | boolean)` w zestawie SDK.

## <a name="sending-custom-events"></a>Przesyłaj zdarzenia niestandardowe

Do wysyłania niestandardowych zdarzeń można użyć zestawu SDK. Należy podać nazwę zdarzenia i właściwości, które mają być wysyłane razem ze zdarzeniem.

W następującym przykładzie przedstawiono fragment kodu śledzenia wydarzeń niestandardowych: „NAZWA” w kluczu `name` we fragmencie konfiguracji. Jest to również nazwa zmiennej w obiekcie okna, w którym jest ładowany zestaw SDK.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]