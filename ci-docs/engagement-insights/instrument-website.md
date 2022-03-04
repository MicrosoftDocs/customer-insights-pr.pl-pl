---
title: Dodawanie kodu do witryny
description: Sposób dodawania wstawki kodu w celu przechwytywania zdarzeń aplikacji Dynamics 365 Customer Insights w witrynie internetowej.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 99e1c04877993a9cd81912e3d400402aab06a7de
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231035"
---
# <a name="install-the-web-sdk-on-a-website"></a>Instalowanie internetowego zestawu SDK w witrynie internetowej

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

W tym artykule opisano, jak administrator instaluje internetowy zestaw narzędzi do projektowania oprogramowania (SDK) w witrynie internetowej. Zdarzenia zaczną pojawiać się w obszarze roboczym wkrótce po zakończeniu instrumentacji witryny internetowej. Aby uzyskać więcej informacji, zobacz temat [Zarządzanie środowiskami i obszarami roboczymi](manage-environments-workspaces.md). Aby zapisywać zdarzenia z aplikacji mobilnych, zobacz [omówienie zasobów dla deweloperów](developer-resources.md).


### <a name="prerequisites"></a>Wymagania wstępne

* Wymagane są uprawnienia administratora w obszarze roboczym do przechowywania danych.
* Twoja witryna sieci Web lub projekt muszą być hostowane w trybie online, aby można było wysyłać dane działań. Dane wysłane z pliku lokalnego nie będą akceptowane przez serwer.


## <a name="add-web-sdk-to-your-website"></a>Dodawanie internetowego zestawu SDK do witryny internetowej

Przejdź do **Administrowanie** > **Obszar roboczy** i wybierz **przewodnik instalacji**. Istnieją dwie opcje instalowania internetowego zestawu SDK. Pierwsza to użycie linku do pobierania, a druga to zainstalowanie pakietu menedżera pakietów węzła (NPM).

### <a name="option-1-using-the-download-link"></a>Opcja 1. Użycie linku do pobierania

1. Wybierz opcję **Kopiuj kod**, aby skopiować ten fragment kodu. Domyślnie klucz pobierania dla twojego obszaru roboczego jest osadzony we fragmencie kodu.
  :::image type="content" source="media/copy-code.png" alt-text="Zrzut ekranu strony z fragmentem kodu.":::

1. Dodaj skopiowany kod do witryny internetowej, obok <head> znacznika i przed innymi skryptami lub tagami CSS.
1. Opublikuj zaktualizowaną witrynę sieci Web i poczekaj kilka minut, aby przechwytywać przychodzący ruch sieci web.
1. Aby wyświetlić dane, wybierz obszar roboczy z przełącznika obszaru roboczego w okienku nawigacji. Następnie wybierz jeden z raportów w sekcji **Odkrywaj**.

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>Opcja 2. Użycie pakietu NPM (zalecane w przypadku aplikacji internetowych opartych na języku JavaScript)

1. Przejdź na [stronę internetową programu NPM](https://www.npmjs.com/package/engagementinsights-web) i postępuj zgodnie z instrukcjami, aby zainstalować i skonfigurować pakiet NPM internetowego zestawu SDK.
1. Opublikuj zaktualizowaną witrynę sieci Web i poczekaj kilka minut, aby przechwytywać przychodzący ruch sieci web.
1. Aby wyświetlić dane, wybierz obszar roboczy z przełącznika obszaru roboczego w okienku nawigacji. Następnie wybierz jeden z raportów w sekcji **Odkrywaj**.

## <a name="configuration-options"></a>Opcje konfiguracji

We fragmencie kodu można zmienić następujące opcje konfiguracji:

- **ingestionKey**: Klucz przejęcia używany do wysyłania zdarzeń do Twojego obszaru roboczego. Można zmienić klucz pozyskiwania, aby wysłać zdarzenia do innego obszaru roboczego. Klucz pozyskiwania jest unikatowy dla każdego obszaru roboczego.
- **autoCapture**: Określa, czy przechwytywane są odsłony stron i interakcje z witryną. Dostępne są dwie opcje:
    - **view**: Ustawione na *true*, aby zapisywać wyświetlenia stron. Wyświetlenia stron są zapisywane jako [zdarzenia](glossary.md#event) *Wyświetlenie*, podtyp [zdarzenia podstawowego](glossary.md#base-event).
    - **click**: Ustaw na *true* do przechwytywania interakcji odwiedzających na stronie internetowej. Interakcje są zapisywane jako [zdarzenia](glossary.md#event) *Zdarzenia*, podtyp [zdarzenia podstawowego](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
