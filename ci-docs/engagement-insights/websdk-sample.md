---
title: Uruchamianie przykładowego zestawu SDK sieci Web
description: Dowiedz się, jak spersonalizować i uruchomić przykładowy zestaw SDK sieci Web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036616"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Uruchamianie przykładowego zestawu SDK sieci Web w Dynamics 365 Customer Insights w celu obsługi funkcji analizy interakcji

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Biblioteka zestawu sieciowego SDK analizy interakcji to biblioteka w języku JavaScript z przykładowym kodem, który można wykorzystać w witrynie sieci Web.

## <a name="prerequisites"></a>Wymagania wstępne

- Zainstaluj [kod Visual Studio](https://code.visualstudio.com/).
- [Zainstaluj rozszerzenie Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) w Visual Studio Code i zapoznaj się ze sposobem uruchamiania programu Live Server.
- Musisz posiadać [klucz pozyskiwania](instrument-website.md).

## <a name="run-sample"></a>Uruchom próbkę

1. [Pobieranie próbki sieciowego SDK](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Rozpakuj plik skompresowany `ei_websdk_sample.zip`.

1. Otwórz rozpakowany folder w Visual Studio Code.

1. W pliku `ei_websdk_sample.html` zastąp ciąg „INGESTION_KEY” kluczem pozyskania z portalu funkcji analizy interakcji, a następnie ciągiem „NAME” z nazwą globalną, której ma używać zestaw SDK. Upewnij się, że wszystkie wystąpienia zostaną zastąpione.

1. Otwórz plik `ei_websdk_sample.html`, używając funkcji Live Server w Visual Studio Code, wybierając menu **Przejdź do Live** na pasku stanu.

1. Po otwarciu strony zdarzenie widoku powinno być wysyłane automatycznie. Kliknięcie dowolnego przycisku na stronie spowoduje wysłanie zdarzeń akcji. Przycisk **Śledź zdarzenia** spowoduje również wysłanie zdarzeń niestandardowych. Wybór przycisku **Przejdź do Bing** spowoduje wysłanie zdarzenia akcji przed przejściem do witryny Bing.

1. Zwróć uwagę na zdarzenia przepływowe podczas przechodzenia do obszaru roboczego. Ten obszar roboczy jest skojarzony z kluczem pozyskiwania wprowadzonym w kroku 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]