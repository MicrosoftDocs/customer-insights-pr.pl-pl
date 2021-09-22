---
title: Dodawanie kodu do witryny
description: Sposób dodawania fragmentu kodu w celu przechwytywania zdarzeń w witrynie sieci Web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035107"
---
# <a name="install-the-code-snippet-on-a-website"></a>Instalowanie fragmentu kodu do witryny sieci Web

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

W tym artykule opisano jak administrator instaluje fragment kodu w witrynie sieci Web. Zdarzenia w obszarze roboczym zaczną być widoczne wkrótce po dodaniu skryptu do witryny sieci Web. Aby uzyskać więcej informacji, zobacz temat [Zarządzanie środowiskami i obszarami roboczymi](manage-environments-workspaces.md). Aby zapisywać zdarzenia z aplikacji mobilnych, zobacz [omówienie zasobów dla deweloperów](developer-resources.md).


### <a name="prerequisites"></a>Wymagania wstępne

* Wymagane są uprawnienia administratora w obszarze roboczym do przechowywania danych.
* Twoja witryna sieci Web lub projekt muszą być hostowane w trybie online, aby można było wysyłać dane działań. Dane wysłane z pliku lokalnego nie będą akceptowane przez serwer.


## <a name="add-code-to-your-website"></a>Dodawanie kodu do witryny
1.  Przejdź do **Administrowanie** > **Obszar roboczy** i wybierz **przewodnik instalacji**.
1. Wybierz opcję **Kopiuj kod**, aby skopiować ten fragment kodu. Domyślnie klucz pobierania dla twojego obszaru roboczego jest osadzony we fragmencie kodu.
:::image type="content" source="media/copy-code.png" alt-text="Zrzut ekranu strony z fragmentem kodu.":::
3. Dodaj skopiowany fragment kodu do witryny sieci Web, obok <head> znacznika i przed innymi skryptami lub tagami CSS.
4.  Opublikuj zaktualizowaną witrynę sieci Web i poczekaj kilka minut, aby przechwytywać przychodzący ruch sieci web.
5.  Aby wyświetlić dane, wybierz obszar roboczy z przełącznika obszaru roboczego w okienku nawigacji. Następnie wybierz jeden z raportów w sekcji **Odkrywaj**.

## <a name="configuration-options"></a>Opcje konfiguracji

We fragmencie kodu można zmienić następujące opcje konfiguracji:

- **ingestionKey**: Klucz przejęcia używany do wysyłania zdarzeń do Twojego obszaru roboczego. Można zmienić klucz pozyskiwania, aby wysłać zdarzenia do innego obszaru roboczego. Klucz pozyskiwania jest unikatowy dla każdego obszaru roboczego. 
- **autoCapture**: Określa, czy przechwytywane są odsłony stron i interakcje z witryną. Dostępne są dwie opcje:
    - **view**: Ustawione na *true*, aby zapisywać wyświetlenia stron. Wyświetlenia stron są zapisywane jako [zdarzenia](glossary.md#event) *Wyświetlenie*, podtyp [zdarzenia podstawowego](glossary.md#base-event).
    - **click**: Ustaw na *true* do przechwytywania interakcji odwiedzających na stronie internetowej. Interakcje są zapisywane jako [zdarzenia](glossary.md#event) *Zdarzenia*, podtyp [zdarzenia podstawowego](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
