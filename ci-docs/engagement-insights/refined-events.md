---
title: Utwórz i zmodyfikuj ulepszone zdarzenia
description: Jak tworzyć i modyfikować opracowane zdarzenia.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034787"
---
# <a name="create-and-modify-refined-events"></a>Utwórz i zmodyfikuj ulepszone zdarzenia

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


Zdarzenie to dane reprezentujące zachowanie użytkownika, takie jak działanie w witrynie sieci Web.

- Zdarzenie *podstawowe* staje się rekordem w momencie, gdy użytkownik wyświetla stronę (działanie Wyświetlanie) lub wchodzi w interakcję z treścią (działanie Akcja).
- Zdarzenie *opracowane* jest wirtualnym widokiem zdarzenia podstawowego. Zdarzenia opracowane można określać, usuwając i dodając właściwości lub filtrując zdarzenia na podstawie wartości właściwości.

Użycie zdarzeń opracowanych w celu uproszczenia zdarzenia podstawowego podczas [eksportu](export-events.md) lub usunięcia właściwości ze zdarzenia, które nie jest niezbędne do wyeksportowania lub usunięcia.

## <a name="create-refined-events"></a>Tworzenie wyrafinowanych zdarzeń

Istnieją trzy sposoby utworzenia zdarzenia opracowanego ze zdarzenia podstawowego. 

1. Przejdź do **Dane**> **Zdarzenia** i wybierz jedną z następujących opcji:
    - Wybierz opcję **Nowe zdarzenia** i wybierz opcję **Tworzenie zdarzeń opracowanych**.
    - Wybierz zdarzenie podstawowe w celu otwarcia widoku szczegółowego i z menu głównego wybierz opcję **Utwórz zdarzenia opracowane**.
    - Wybierz opcję **Więcej [...]** podczas otwierania menu skrótu dla zdarzenia podstawowego. Następnie wybierz opcję **Utwórz zdarzenia opracowane**.
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="Opcje tworzenia zdarzeń opracowanych.":::

1. W oknie dialogowym **Utwórz zdarzenie opracowane** wprowadź następujące informacje:

- Wybierz zdarzenie z listy rozwijanej **Zdarzenia podstawowe**, jeśli tworzysz nowe zdarzenie.
- Wprowadź nazwę w polu **Wyświetlana nazwa zdarzenia opracowanego**.
- Opcjonalnie można zaktualizować sugerowaną **nazwę rzeczywistą** bez używania spacji.

3. Wybierz opcję **Utwórz**, aby zastosować ustawienia.

1. W widoku szczegółowym zdarzenia opracowanego wybierz opcję **Dodaj i usuń właściwości**, aby otworzyć okienko **Edycji właściwości**. 

1. Pola wyboru zaznacz właściwości, które chcesz pokazywać, oraz te, które chcesz ukryć. 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Edytowanie właściwości zdarzeń opracowanych.":::

1. Wybierz opcję **Potwierdź**, aby zastosować wybór.

1. Wybierz **Zapisz**, aby zapisać konfigurację.

## <a name="edit-refined-events"></a>Edytowanie opracowanych zdarzeń

Można zmienić nazwę i właściwości zdarzenia.

### <a name="edit-event-name"></a>Edytuj nazwę zdarzenia

1. Przejdź do **Dane** > **Wydarzenia**. 
1. Wybierz opcję **Więcej [...]** dla wydarzenia i wybierz opcję **Edytuj nazwę**.
1. Zaktualizuj nazwę zdarzenia i wybierz opcję **Zmień nazwę**.

### <a name="edit-selected-properties"></a>Edytowanie wybranych właściwości

1. Przejdź do widoku **Dane** > **Zdarzenia** i wybierz zdarzenia opracowane, aby otworzyć widok szczegółowy.
1. Wybierz opcję **Dodaj i usuń właściwości**. 
1. Wyedytuj zaznaczenie pól wyboru.
1. Wybierz opcję **Potwierdź**, a następnie **Zapisz**, aby zastosować zmiany.

Aby uzyskać informacje na temat eksportowania zdarzeń, zobacz temat [Eksportowanie zdarzeń](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
