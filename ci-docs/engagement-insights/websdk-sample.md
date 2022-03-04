---
title: Uruchamianie przykładowego zestawu SDK sieci Web
description: Dowiedz się, jak spersonalizować i uruchomić przykładowy zestaw SDK sieci Web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a50a10db784ec7c1943c94e74000713309787e5c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225344"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Uruchamianie przykładowego zestawu SDK sieci Web w Dynamics 365 Customer Insights w celu obsługi funkcji analizy interakcji

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Biblioteka zestawu sieciowego SDK analizy interakcji to biblioteka w języku JavaScript z przykładowym kodem, który można wykorzystać w witrynie sieci Web.

## <a name="prerequisites"></a>Wymagania wstępne

- Zainstaluj [kod Visual Studio](https://code.visualstudio.com/).
- [Zainstaluj rozszerzenie Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) w Visual Studio Code i zapoznaj się ze sposobem uruchamiania programu Live Server.
- Musisz mieć obszar roboczy [wyników analiz interakcji](create-workspace.md).

## <a name="run-sample"></a>Uruchom próbkę

1. [Pobieranie próbki sieciowego SDK](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Rozpakuj plik skompresowany `ei_websdk_sample.zip`.

1. Otwórz rozpakowany folder w Visual Studio Code.

1. Przejdź do portalu wyników analiz interakcji dla swojego obszaru roboczego. Wybierz opcję **Administracja** > **Obszar roboczy** i **Podręcznik instalacji**. Wykonaj pierwszą opcję i wybierz opcję **Kopiuj kod**, aby skopiować wstawkę kodu JavaScript.

1. W pliku `ei_websdk_sample.html` wklej wstawkę kodu właśnie skopiowaną w tym wierszu:

   - <-- WKLEJ WSTAWKĘ KODU JAVASCRIPT Z PORTALU WYNIKÓW ANALIZ INTERAKCJI TUTAJ, PONIŻEJ TEGO WIERSZA -->

1. Otwórz plik `ei_websdk_sample.html`, używając funkcji Live Server w Visual Studio Code, wybierając menu **Przejdź do Live** na pasku stanu.

1. Po otwarciu strony zdarzenie widoku powinno być wysyłane automatycznie. Kliknięcie dowolnego przycisku na stronie spowoduje wysłanie zdarzeń akcji. Przycisk **Śledź zdarzenia** spowoduje również wysłanie zdarzeń niestandardowych. Wybór przycisku **Przejdź do Bing** spowoduje wysłanie zdarzenia akcji przed przejściem do witryny Bing.

1. Zwróć uwagę na zdarzenia przepływowe podczas przechodzenia do obszaru roboczego. Ten obszar roboczy jest skojarzony z kluczem pozyskiwania wprowadzonym w kroku 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
