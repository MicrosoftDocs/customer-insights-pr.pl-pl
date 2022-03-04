---
title: Uruchom próbkę SDK w iOS
description: Przykładowy projekt, aby dowiedzieć się więcej o zestawie SDK iOS
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bbe4ba648952a8081af4c8f2610276809fa5efeb
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232855"
---
# <a name="run-the-ios-sdk-sample"></a>Uruchom próbkę SDK w iOS

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ten przykładowy projekt iOS ułatwia zrozumienie działania zestawu SDK w aplikacji. Nie będzie trzeba pisać kodu. Wystarczy dodać swój klucz pozyskiwania i od razu możesz zobaczyć zdarzenia w swoim obszarze roboczym.

## <a name="prerequisites"></a>Wymagania wstępne

- [Xcode wersja 9+](https://developer.apple.com/xcode/downloads/)
- [Klucz pozyskiwania](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>Pobieranie przykładu SDK iOS

1. [Pobierz przykładowe SDK analizy interakcji w iOS](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. Rozpakuj plik skompresowany `ei-ios-sample.zip`.
1. Otwórz przykładowy projekt aplikacji w programie Xcode.
1. W pliku `EIConfig.plist` zastąp ciąg `“YOUR-INGESTION-KEY”` w polu `ingestionKey` swoim kluczem pozyskiwania z przestrzeni roboczej z analizy interakcji **Administracja** > **Obszar roboczy** > **Przewodnik instalacji**.
1. Aby rozpocząć projekt demonstracyjny, wybierz pozycję **Uruchom**.
1. Wyświetl zdarzenia w swoim obszarze roboczym.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
