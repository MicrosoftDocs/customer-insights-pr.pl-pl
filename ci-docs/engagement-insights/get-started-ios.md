---
title: Rozpoczynanie pracy z iOS SDK
description: Dowiedz się, jak wdrażać i personalizować SDK iOS
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: de8291fc429ae6433301a47bfdf9a3271b1b77294fd58448c7aa6bd0783edc97
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036886"
---
# <a name="get-started-with-the-ios-sdk"></a>Rozpoczynanie pracy z SDK iOS

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ten przewodnik przeprowadzi Cię przez proces instrumentacji aplikacji iOS za pomocą zestawu SDK aplikacji Wyniki analiz interakcji Dynamics 365 Customer Insights. Zaczniesz widzieć wydarzenia w swoim portalu w ciągu pięciu minut lub szybciej.

## <a name="configuration-options"></a>Opcje konfiguracji

Do SDK można przekazać następujące opcje konfiguracji za pośrednictwem dostępnego pliku `EIConfig.plist`:

- **ingestionKey**: Klucz przekazywania jest używany do wysyłania zdarzeń do Twojego projektu.
- **autocollectAction**: wartość logiczna włączania lub wyłączania automatycznej instrumentacji zdarzenia akcji.
- **autocollectView**: wartość logiczna włączania lub wyłączania automatycznej instrumentacji zdarzenia wyświetlenia.
- **endpointUrl**: adres URL punktu końcowego, pod który będą kierowane zdarzenia.

## <a name="prerequisites"></a>Wymagania wstępne

- Xcode wersja 9+
- iOS w wersji 8.2+
- Klucz przekazywania (zobacz poniżej, aby uzyskać instrukcje dotyczące uzyskiwania)

## <a name="integrate-the-sdk-into-your-application"></a>Integrowanie SDK w aplikacji

Rozpocznij proces, wybierając przestrzeń roboczą, platformę mobilną iOS i pobierając pakiet SDK.

- Aby wybrać obszar roboczy, użyj przełącznika w lewym okienku nawigacji.

- Jeśli nie masz istniejącego obszaru roboczego, wybierz opcję **Nowy obszar roboczy** i wykonaj kroki tworzenia [nowego obszaru](create-workspace.md).

## <a name="configure-the-sdk"></a>Skonfigurowanie SDK

Po pobraniu SDK, możesz pracować z nim w Xcode, aby włączyć i zdefiniować zdarzenia.

1. Po utworzeniu obszaru roboczego przejdź do **Administracja** > **Obszar roboczy** i wybierz **przewodnik instalacji**.

1. Pobierz [SDK iOS analizy interakcji](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip) i umieść plik `EIObjC.xcframework` w folderze `Frameworks`.

1. Jeśli folder `Frameworks` nie istnieje, utwórz go w folderze projektu.

## <a name="enable-auto-instrumentation"></a>Włączanie automatycznej instrumentacji
 
Można łatwo włączyć automatyczną instrumentację bez pisania kodu. Podczas realizacji projektu są automatycznie śledzone zdarzenia `view` i `action` przy użyciu skonfigurowanego klucza przekazywania. 

1. Zaktualizuj i dołącz podany plik `EIConfig.plist` w folderze katalogu projektów dla następujących pól:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = TAK
    - autocollectAction = TAK

2. Następnie w programie Xcode dodaj plik `EIConfig.plist` do projektu. 



Aby wyłączyć auto-instrumentację, zaktualizuj następujące pola w dołączonym pliku `EIConfig.plist` w katalogu projektu. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Implementowanie niestandardowych zdarzeń

1. Otwórz projekt w Xcode i przejdź do ustawień **Ogólnych**. 
1. Dodaj element `EIObjC.xcframework` do projektu w sekcji „Frameworks, Libraries and Embedded Content” (Frameworks, Biblioteki i treści osadzone).

1. Zaimportuj plik nagłówka struktury w pliku AppDelegate.m, używając następującej wstawki:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Inicjalizuj analizę interakcji SDK z poziomu aplikacji: didFinishLaunchingWithOptions.
1. Skopiuj wstawkę XML z **Przewodnika po instalacji**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Śledź zdarzenie:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Ustaw szczegóły użytkownika dla Twojego wydarzenia

Zestaw SDK umożliwia definiowanie informacji o użytkowniku, które mogą być wysyłane przy każdym zdarzeniu. Informacje o użytkowniku można określić, wywołując `setUser:(nonnull EIUser *)user` w interfejsie API na poziomie SDK.

Określenie szczegółów użytkownika na poziomie `Analytics` oznacza, że wszystkie telemetrie będą zawierały te informacje. Jednakże, jeśli określisz na poziomie zdarzenia poprzez wywołanie API `setUser:(nonnull EIUser *)user` na obiekcie EIEvent, tylko to konkretne zdarzenie będzie zawierało informacje.

Klasa danych `EIUser` zawiera następujące właściwości ciągu NSString:

- **localId**: identyfikator lokalny użytkownika.
- **authId**: uwierzytelniony identyfikator użytkownika.
- **authType**: typ uwierzytelniania używany do uzyskania uwierzytelnionego identyfikatora użytkownika.
- **name**: Nazwa użytkownika.
- **email**: Adres e-mail użytkownika.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
