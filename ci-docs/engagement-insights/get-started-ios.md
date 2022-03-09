---
title: Rozpoczynanie pracy z iOS SDK
description: Dowiedz się, jak wdrażać i personalizować SDK iOS
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 09/15/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e4d0555d2fc377fae62ff5db64c032fcebcb04
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226228"
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

- Po utworzeniu obszaru roboczego przejdź do **Administracja** > **Obszar roboczy** i wybierz **przewodnik instalacji**.

## <a name="configure-the-sdk"></a>Skonfigurowanie SDK

Po pobraniu SDK, możesz pracować z nim w Xcode, aby włączyć i zdefiniować zdarzenia. Istnieją dwa sposoby wykonania tej czynności

### <a name="option-1-using-cocoapods-recommended"></a>Opcja 1. Użycie CocoaPods (zalecane)
CocoaPods to menedżer zależności dla projektów Swift i Objective-C Cocoa. Jego użycie ułatwia integrację zestawu SDK szczegółowych informacji o zaangażowaniu dla systemu iOS. CocoaPods umożliwia również uaktualnienie do najnowszej wersji zestawu SDK szczegółowych informacji o zaangażowaniu. Oto sposób integrowania zestawu SDK szczegółowych informacji o zaangażowaniu z programem CocoaPods w projekcie Xcode. 

1. Zainstaluj program CocoaPods. 

1. Utwórz nowy plik o nazwie Podfile w katalogu głównym projektu i dodaj do niego następujące instrukcje. Zastąp YOUR_TARGET_PROJECT_NAME nazwą projektu Xcode. 
```objectivec
platform :ios, '9.0'  

 target '${YOUR_TARGET_PROJECT_NAME}' do 

     use_frameworks!   

     pod 'EIObjC.framework.debug' 

     pod 'EIObjC.framework.release' 

 end 
```
Powyższy zestaw zasobników zawiera wersje debugowania i wydania zestawu SDK. Wybierz jedną z najlepszych opcji projektu.

1. Zainstaluj zasobnik, wykonując następujące polecenie:  `pod install --repo-update `

### <a name="option-2-using-download-link"></a>Opcja 2. Użycie linku do pobierania

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
