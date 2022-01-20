---
title: Rozpoczynanie pracy z SDK Android
description: Dowiedz się, jak wdrażać i personalizować SDK Android
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 10/19/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 71ec4841303bd17d3f605547be8d6032c58a7b21
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977588"
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

## <a name="integrate-the-sdk-into-your-application"></a>Integrowanie SDK w aplikacji
Rozpocznij proces, wybierając przestrzeń roboczą, platformę mobilną Android i pobierając pakiet SDK Android.

- Aby wybrać obszar roboczy, użyj przełącznika w lewym okienku nawigacji.

- Jeśli nie masz istniejącego obszaru roboczego, wybierz opcję **Nowy obszar roboczy** i wykonaj kroki tworzenia [nowego obszaru](create-workspace.md).

- Po utworzeniu obszaru roboczego przejdź do **Administracja** > **Obszar roboczy** i wybierz **przewodnik instalacji**.

## <a name="configure-the-sdk"></a>Skonfigurowanie SDK

Po pobraniu zestawu SDK możesz pracować z nim w Android Studio, aby włączyć i zdefiniować zdarzenia. Istnieją dwa sposoby wykonania tej czynności:
### <a name="option-1-use-jitpack-recommended"></a>Opcja 1: instalacja repozytorium JitPack (zalecana)
1. Dodaj repozytorium JitPack do katalogu głównego `build.gradle`:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. Dodaj zależność:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:v1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-use-download-link"></a>Opcja 2: użycie linku pobierania
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

## <a name="enable-auto-instrumentation"></a>Włączanie automatycznej instrumentacji

1. Dodaj uprawnienie do sieci i Internetu w pliku `AndroidManifest.xml` umieszczonym w folderze `manifests`.
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```

1. Skonfiguruj konfigurację zestawu SDK szczegółowych informacji o odbiorcach za pośrednictwem pliku `AndroidManifest.xml`.

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

   >[!NOTE]
   >Zdarzenia `Action` należy dodać ręcznie.

1. (Opcjonalnie) Inne konfiguracje obejmują ustawienie adresu URL kolektora punktów końcowych. Można je dodać w obszarze metadanych klucza pozyskiwania w `AndroidManifest.xml`.

   ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
   ```

## <a name="implement-custom-events"></a>Implementowanie niestandardowych zdarzeń

Po zainicjowaniu zestawu SDK można pracować ze zdarzeniami i ich właściwościami w środowisku `MainActivity`.


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

## <a name="set-user-details-for-your-event-optional"></a>Ustaw szczegóły użytkownika dla Twojego wydarzenia (opcjonalnie)

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
