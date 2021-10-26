---
title: Utwórz nowe środowisko
description: Cel środowiska i sposób tworzenia nowego.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 5e301b4ff0a7586fb143b154b773791b3bd645b7
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648130"
---
# <a name="create-a-new-environment"></a>Utwórz nowe środowisko 

## <a name="overview"></a>Omówienie

Środowisko to miejsce służące do zarządzania obszarami roboczymi i połączeniami. Sposób korzystania z środowisk zależy od organizacji i danej sprawy użycia. Można na przykład utworzyć:

- Jedno środowisko.
- Oddzielne środowiska testowe i produkcyjne.
- Oddzielne środowiska dla określonych zespołów lub działów w organizacji, które zawierają odpowiednie zdarzenia dla poszczególnych odbiorców.
- Oddzielne środowiska dla różnych oddziałów firmy na świecie.
- Połączenia z usługą Customer Insights — analiza odbiorców.

## <a name="create-a-new-environment"></a>Utwórz nowe środowisko

1. Po prawej stronie baneru głównego wybierz selektor środowiska, a następnie pozycję **+Nowy**.

   :::image type="content" source="media/environment-picker.png" alt-text="Wybierz selektor środowiska.":::

1. W okienku **Konfiguracja** wpisz **nazwę środowiska**.

1. Wybierz **typ** konta zależnie od typu planu.

1. Wybierz **Region** i wybierz **Dalej**. 

1. Wpisz **nazwę obszaru roboczego**, co umożliwia zbieranie danych dla konkretnej witryny internetowego lub aplikacji. Aby uzyskać więcej informacji, zobacz temat [Tworzenie obszaru roboczego](create-workspace.md).

1. Wybierz **Typ obszaru roboczego** (internetowy lub mobilny) do utworzenia. 

1. Wybierz opcję **Pokaż ustawienia zaawansowane**, aby włączyć lub wyłączyć te ustawienia opcjonalne:

   - Przełącz opcję **Od nieznanego do znanego** na „włączone”, aby kojarzyć zdarzeń internetowe z użytkownikami, którzy byli wcześniej uwierzytelniani. Aby uzyskać więcej informacji, zobacz temat [Rozpoznawanie zdarzeń internetowych od wcześniej uwierzytelnionych osób odwiedzających](unknown-to-known.md)
   - Przełącz opcję **Filtruj ruch botów** na „włączone” w celu usunięcia ruchu internetowego według botów dla tego obszaru roboczego. 

1. Po zakończeniu wybierz opcję **Gotowe**. 

1. Zainstaluj wstawkę kodu, aby rozpocząć odbieranie danych, a następnie wybierz opcję **Zakończ**, aby utworzyć obszar roboczy. Aby uzyskać więcej informacji, zobacz [Podstawowe informacje o zasobach dla deweloperów](developer-resources.md).

> [!NOTE]
> Teraz możesz dodawać członków i przypisywać ich poziomy uprawnień z listy **Rola**. Aby uzyskać więcej informacji, zobacz [uprawnienia i role](user-roles.md). 

Aby uzyskać więcej informacji, zobacz temat [Zarządzanie środowiskami i obszarami roboczymi](manage-environments-workspaces.md).

## <a name="work-with-your-new-environment"></a>Praca z nowym środowiskiem

- [Tworzenie obszaru roboczego](../engagement-insights/create-workspace.md) i dodawanie członków.
- [Dodawanie kodu do witryny internetowej](../engagement-insights/instrument-website.md) lub [aplikacji mobilnej](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps).
- Wyświetlanie [raportu w czasie rzeczywistym](../engagement-insights/view-reports.md) lub tworzenie [raportów niestandardowych](../engagement-insights/custom-reports.md).
- [Tworzenie zdarzeń opracowanych](../engagement-insights/refined-events.md) dla eksportu.
- [Eksportuj dane](../engagement-insights/export-events.md) do Data Lake Storage.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
