---
title: Rozpoczynanie pracy z SDK Android
description: Dowiedz się, jak wdrażać i personalizować SDK Android
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 77e63929bbcc7ecff34a3839af525b76ec3c7f21173ddc5f8f2d69f11c25c441
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036931"
---
# <a name="get-started-with-the-android-sdk"></a>Rozpoczynanie pracy z SDK Android

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ten przewodnik przeprowadzi Cię przez proces instrumentacji aplikacji Android za pomocą zestawu SDK aplikacji Wyniki analiz interakcji Dynamics 365 Customer Insights. Zaczniesz widzieć wydarzenia w swoim portalu w ciągu pięciu minut lub szybciej.

## <a name="configuration-options"></a>Opcje konfiguracji
Następujące opcje konfiguracyjne mogą być przekazane do SDK:

- **ingestionKey**: Klucz przekazywania jest używany do wysyłania zdarzeń do twojego obszaru roboczego.

## <a name="prerequisites"></a>Wymagania wstępne

- Android Studio

- Minimalny poziom interfejsu API Android: 16 (Jelly Bean)

- Klucz przekazywania (zobacz poniżej, aby uzyskać instrukcje dotyczące uzyskiwania)

## <a name="step-1-integrate-the-sdk-into-your-application"></a>Krok 1. Integrowanie SDK w aplikacji
Rozpocznij proces, wybierając przestrzeń roboczą, platformę mobilną Android i pobierając pakiet SDK Android.

- Aby wybrać obszar roboczy, użyj przełącznika w lewym okienku nawigacji.

- Jeśli nie masz istniejącego obszaru roboczego, wybierz opcję **Nowy obszar roboczy** i wykonaj kroki tworzenia [nowego obszaru](create-workspace.md).

## <a name="step-2-configure-the-sdk"></a>Krok 2. Skonfigurowanie SDK

1. Po utworzeniu obszaru roboczego przejdź do **Administracja** > **Obszar roboczy** i wybierz **przewodnik instalacji**. 

1. Pobierz [zestaw SDK Android analizy odbiorców](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) i umieść plik `eiandroidsdk-debug.aar` w folderze `libs`.

1. Otwórz plik `build.gradle` na poziomie projektu i dodaj wymienione poniżej wstawki:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

1. Skonfiguruj konfigurację zestawu SDK analizy odbiorców za pośrednictwem pliku `AndroidManifest.xml` znajdującego się w folderze `manifests`. 
1. Skopiuj wstawkę XML z **Przewodnika po instalacji**. Pole `Your-Ingestion-Key` powinno być wypełniane automatycznie.

   > [!NOTE]
   > Nie ma potrzeby zastępowania sekcji `${applicationId}`. Jest wypełniane automatycznie.
   

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Włącz lub wyłącz automatyczne przechwytywanie zdarzeń `View`, ustawiając w powyższym polu `autoCapture` wartość `true` lub `false`.

1. (Opcjonalnie) Inne konfiguracje obejmują ustawienie adresu URL kolektora punktów końcowych. Można je dodać w obszarze metadanych klucza pozyskiwania w `AndroidManifest.xml`:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="step-3-initialize-the-sdk-from-mainactivity"></a>Krok 3. Zainicjuj zestaw SDK z poziomu działania MainActivity 

Po zainicjalizowaniu SDK, można pracować ze zdarzeniami i ich właściwościami w środowisku MainActivity.

    
Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Ustawienie właściwości dla wszystkich zdarzeń (opcjonalne)
    
Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

Dla właściwości zdarzenia kontekstowego obsługiwane są następujące typy:
- String
- Data
- Liczba rzeczywista
- Długi
- Boolean
- UUID

### <a name="track-an-event"></a>Śledź zdarzenie

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

### <a name="set-user-details-for-your-event-optional"></a>Ustaw szczegóły użytkownika dla Twojego wydarzenia (opcjonalnie)

Zestaw SDK umożliwia definiowanie informacji o użytkowniku, które mogą być wysyłane przy każdym zdarzeniu. Informacje o użytkowniku można określić, wywołując `setUser(user: User)` w interfejsie API na poziomie `Analytics`.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

Klasa danych `User` zawiera następujące właściwości ciągu:

- **localId**: identyfikator lokalny użytkownika.
- **authId**: uwierzytelniony identyfikator użytkownika.
- **authType**: typ uwierzytelniania używany do uwierzytelniania identyfikatora użytkownika.
- **name**: Nazwa użytkownika.
- **email**: Adres e-mail użytkownika.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
