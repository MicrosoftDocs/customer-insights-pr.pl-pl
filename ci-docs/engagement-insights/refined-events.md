---
title: Tworzenie i modyfikowanie zdarzeń
description: Jak tworzyć i modyfikować zdarzenia.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: dbafa2231daa82c34ee2ec8292111575e95af675
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228216"
---
# <a name="create-and-modify-events"></a>Tworzenie i modyfikowanie zdarzeń

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Zdarzenie to dane reprezentujące zachowanie użytkownika, takie jak działanie w witrynie sieci Web.

- Zdarzenie *podstawowe* staje się rekordem w momencie, gdy użytkownik wyświetla stronę (działanie Wyświetlanie) lub wchodzi w interakcję z treścią (działanie Akcja).
- Zdarzenie *opracowane* jest wirtualnym widokiem zdarzenia podstawowego. Zdarzenia opracowane można określać, usuwając i dodając właściwości lub filtrując zdarzenia na podstawie wartości właściwości.

## <a name="prerequisites"></a>Wymagania wstępne

Aby pobrać zdarzenia, połącz najpierw dane ze swojej witryny internetowej z aplikacją Wyniki analiz interakcji, używając prostej wstawki kodu. Aby uzyskać więcej informacji, zobacz temat [Instalowanie internetowego zestawu SDK w witrynie internetowej](instrument-website.md).

 :::image type="content" source="media/new-events-connect-data.png" alt-text="Połącz najpierw swoje dane.":::

## <a name="create-refined-events"></a>Utwórz ulepszone zdarzenia

Użycie zdarzeń opracowanych w celu uproszczenia zdarzenia podstawowego podczas [eksportu](export-events.md) lub usunięcia właściwości ze zdarzenia, które nie jest niezbędne do wyeksportowania lub usunięcia.

> [!NOTE]
> Po dodaniu internetowego zestawu SDK w witrynie internetowej można wyświetlać zdarzenia podstawowe i tworzyć zdarzenia ulepszone. 

Aby wyświetlić zdarzenia podstawowe:

1. Przejdź do **Dane** lewym okienku nawigacji.

1. Wybierz pozycję **Zdarzenia**, aby wyświetlić listę wszystkich zdarzeń w obszarze roboczym.

    :::image type="content" source="media/data-events.png" alt-text="Wyświetl zdarzenia.":::

Aby utworzyć zdarzenie ulepszone na podstawie zdarzenia podstawowego: 

1. Przejdź do obszaru **Dane** > **Zdarzenia** i wybierz **+ Nowe zdarzenia** w górnej części ekranu.

1. W sesji dialogowej **Nowe zdarzenie** wybierz opcję **Utwórz zdarzenia ulepszone**, a następnie wybierz opcję **Dalej**.
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="Kreator nowych zdarzeń.":::
     
1. W sesji dialogowej **Nowe zdarzenia** wprowadź następujące informacje:

   - Wybierz zdarzenie z listy rozwijanej **Zdarzenia podstawowe**.
   - Wprowadź nazwę w polu **Wyświetlana nazwa zdarzenia opracowanego**.
   - Opcjonalnie można zaktualizować sugerowaną **nazwę rzeczywistą** bez używania spacji.

1. Wybierz opcję **Utwórz**, aby zastosować ustawienia.

Zdarzenie ulepszone zostanie teraz wyświetlone na liście **Zdarzenia**.

### <a name="edit-event-name"></a>Edytuj nazwę zdarzenia

Można zmienić nazwę i właściwości zdarzenia podstawowego lub zdarzenia ulepszonego.

1. Przejdź do **Dane** > **Wydarzenia**. 

1. Wybierz opcję **Więcej [...]** dla wydarzenia i wybierz opcję **Edytuj nazwę**.
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="Opcje tworzenia zdarzeń opracowanych.":::

3. Zaktualizuj nazwę zdarzenia i wybierz opcję **Zmień nazwę**.

### <a name="view-the-details-of-a-refined-event"></a>Wyświetl szczegółowe informacje o zdarzeniu ulepszonym:

1. Z listy **Zdarzenia** wybierz zdarzenie podstawowe lub ulepszone. 

1. Wybierz opcję **Dodaj lub usuń właściwości** u góry ekranu, aby otworzyć okienko **Edytuj właściwości**. 

     :::image type="content" source="media/add-remove-properties.png" alt-text="Dodaj lub usuń właściwości.":::

1. Pola wyboru zaznacz właściwości, które chcesz pokazywać, oraz te, które chcesz ukryć. 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Edytowanie właściwości zdarzeń opracowanych.":::

1. Wybierz opcję **Potwierdź**, aby zastosować wybór, a następnie wybierz opcję **Zapisz**.


### <a name="edit-selected-properties-for-a-refined-event"></a>Edytowanie wybranych właściwości zdarzenia ulepszonego

1. Przejdź do widoku **Dane** > **Zdarzenia** i wybierz zdarzenia opracowane, aby otworzyć widok szczegółowy.
1. Wybierz opcję **Dodaj i usuń właściwości**. 
1. Wyedytuj zaznaczenie pól wyboru.
1. Wybierz opcję **Potwierdź**, a następnie **Zapisz**, aby zastosować zmiany.

Aby uzyskać informacje na temat eksportowania zdarzeń, zobacz temat [Eksportowanie zdarzeń](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
