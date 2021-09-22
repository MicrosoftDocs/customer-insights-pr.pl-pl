---
title: Przykład SDK Android
description: Przykładowy projekt, aby dowiedzieć się więcej o zestawie SDK Android
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ba51961bc7f9555d7dba5b6a21c8636011438d75cba87bc132b896841c467a33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035839"
---
# <a name="run-the-android-sdk-sample"></a>Uruchom próbkę SDK w Android

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ten przykładowy projekt Android ułatwia zrozumienie działania zestawu SDK w aplikacji. Nie będzie trzeba pisać kodu. Wystarczy dodać swój klucz pozyskiwania i od razu możesz zobaczyć zdarzenia w swoim obszarze roboczym.

## <a name="prerequisites"></a>Wymagania wstępne

- [Android Studio](https://developer.android.com/studio)
- [Klucz pozyskiwania](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Pobieranie przykładu SDK Android

1. [Pobierz przykładowe SDK zaangażowania w Android](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Rozpakuj plik skompresowany `ei-android-sample.zip`.
1. Otwórz rozpakowany folder w Android Studio.
1. W pliku `AndroidManifest.xml` zastąp ciąg `"Your-Ingestion-Key"` swoim kluczem pozyskiwania z przestrzeni roboczej z analizy zaangażowania **Administracja** > **Obszar roboczy** > **Przewodnik instalacji**. 

   > [!NOTE]
   > Nie ma potrzeby zastępowania sekcji `${applicationId}`. Jest wypełniane automatycznie.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Aby rozpocząć projekt demonstracyjny, wybierz pozycję **Uruchom**.
1. Wyświetl zdarzenia w swoim obszarze roboczym.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
