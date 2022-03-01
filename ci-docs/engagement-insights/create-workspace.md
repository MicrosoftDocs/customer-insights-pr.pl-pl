---
title: Utwórz nowy obszar roboczy
description: Cel obszaru roboczego i sposób tworzenia nowego.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 816f948331a06794c15000eb779f93cc7fdda202
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645323"
---
# <a name="create-a-new-workspace-and-add-members"></a>Tworzenie nowego obszaru roboczego i dodawanie członków

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Obszar roboczy to sposób wyświetlania działań użytkownika w czasie rzeczywistym w celu lepszego zrozumienia odbiorcy. W tym miejscu można przechowywać zdarzenia i raporty oraz zarządzać nimi.

Podczas tworzenia obszaru roboczego wybierasz typ danych, na których chcesz się skupić. W każdej chwili możesz dodać innych użytkowników lub członków do istniejącego obszaru roboczego. 

## <a name="create-a-new-workspace"></a>Utwórz nowy obszar roboczy

Proces tworzenia przestrzeni roboczej obejmuje ustawienie *środowiska* do organizacji przestrzeni roboczej. Środowisko to miejsce mogące zawierać jeden lub więcej obszarów roboczych. Środowisko pozwala zarządzać obszarami roboczymi i połączeniami z funkcją analizy odbiorców w Customer Insights.

1. Wybierz pozycję **Nowy** z przełącznika obszarów roboczych.

   :::image type="content" source="media/new-workspace.png" alt-text="Strona Customer Insights z objaśnieniami w okienku nawigacji i opisem.":::

1. W okienku **Obszar roboczy** wprowadź **nazwę obszaru roboczego**.

   :::image type="content" source="media/workspace-name.png" alt-text="Wpisywanie nazwy obszaru roboczego.":::

1. Wybierz typ platformy (internetowa lub mobilna) do mierzenia.

1. Wybierz opcję **Pokaż ustawienia zaawansowane**, aby włączyć lub wyłączyć te ustawienia opcjonalne:

   - Przełącz opcję **Od nieznanego do znanego** na „włączone”, aby kojarzyć zdarzeń internetowe z użytkownikami, którzy byli wcześniej uwierzytelniani. Aby uzyskać więcej informacji, zobacz temat [Rozpoznawanie zdarzeń internetowych od wcześniej uwierzytelnionych osób odwiedzających](unknown-to-known.md)
   - Przełącz opcję **Filtruj ruch botów** na „włączone” w celu usunięcia ruchu internetowego według botów dla tego obszaru roboczego. 

1. Po zakończeniu wybierz opcję **Gotowe**. 

1. Zainstaluj wstawkę kodu, aby rozpocząć odbieranie danych, a następnie wybierz opcję **Zakończ**, aby utworzyć obszar roboczy. Aby uzyskać więcej informacji, zobacz [Podstawowe informacje o zasobach dla deweloperów](developer-resources.md).

> [!NOTE]
> Teraz możesz dodawać członków i przypisywać ich poziomy uprawnień z listy **Rola**. Aby uzyskać więcej informacji, zobacz [uprawnienia i role](user-roles.md). 

Aby uzyskać więcej informacji, zobacz temat [Zarządzanie środowiskami i obszarami roboczymi](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
