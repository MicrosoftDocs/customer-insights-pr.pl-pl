---
title: Raporty niestandardowe — informacje
description: Dowiedz się, jak tworzyć raporty niestandardowe.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 3fa801bfc8b0aee65c21b90de2423a3d5d5e4e26
ms.sourcegitcommit: d9965f4bfc09391698a34042f6b44367e53819e3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2021
ms.locfileid: "7582890"
---
# <a name="create-and-edit-custom-reports"></a>Twórz i edytuj raporty niestandardowe

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Oprócz gotowych raportów (OOB) możesz utworzyć raport niestandardowy zawierający wizualizacje typu wykres i tabela, który ułatwi Ci zrozumienie zachowania użytkowników. Ten artykuł wyjaśnia, jak utworzyć raport zawierający potrzebne dane przy użyciu wizualizacji tabel i wykresów. Aby uzyskać informacje na temat raportów OOB, zobacz temat [Wyświetlanie raportów](view-reports.md).

## <a name="create-a-custom-report"></a>Tworzenie raportu niestandardowego

1. Przejdź do opcji **Analizowanie** > **Niestandardowe**, aby uzyskać dostęp do niestandardowej listy raportów.

1. Wybierz opcję **Nowy raport**, aby rozpocząć tworzenie raportu niestandardowego.

   :::image type="content" source="media/new-custom-report.png" alt-text="Nowe raporty niestandardowe.":::

1. Wybierz typ raportu, który chcesz utworzyć:

    - Wybranie opcji **Dodaj wizualizację** na pasku poleceń umożliwia utworzenie domyślnej wizualizacji tabeli.
    - Można też wybrać wizualizację kolumnową, słupkową, liniową, obszarową, kołową, pączkową lub tabelaryczną w okienku **edytora raportów**.

1. W sekcji **Dane** w okienku **edytora wizualizacji** wybierz jedną z dostępnych opcji (na przykład widoki stron) z listy rozwijanej **Metryki**. Można również dodać opcję **Wymiary** (na przykład kraj), które będą wyświetlane w wizualizacjach. Aby uzyskać więcej informacji, zobacz tematy [Wyświetlanie i tworzenie metryk](metrics.md) oraz [Wyświetlanie i tworzenie wymiarów](dimensions.md).

   :::image type="content" source="media/page-views.png" alt-text="Wybierz metrykę dla swojego raportu.":::

1. Zaznacz sekcję **Projekt** w okienku **edytora wizualizacji**, aby dodać **tekst tytułu** oraz włączyć lub wyłączyć opcję **Tytuł**.  Można również zmienić typ wizualizacji, wybierając inny wykres, na przykład **wykres kołowy**.

1. Aby zmienić rozmiar i położenie wizualizacji:
   - Wybierz wizualizację, a następnie przeciągnij jedną z nich, aby dostosować jej rozmiar.
   - Wybierz wizualizację i przenieś ją w nowe miejsce. Aby zmienić położenie, można również użyć strzałek.
1. Wybierz **Dodaj wizualizację** na pasku poleceń, aby dodać kolejną wizualizację.
1. Po dodaniu wizualizacji do raportu wybierz polecenie **Zapisz** na pasku poleceń.

1. Podaj nazwę raportu niestandardowego i wybierz opcję **Zapisz**, aby go utworzyć.
 
## <a name="filter-a-custom-report"></a>Filtrowanie raportu niestandardowego

W celu skoncentrowania się na zakresie dat lub wartości można wybrać horyzont czasowy lub zakres dat w raporcie niestandardowym.

Aby wybrać horyzont czasowy, w prawym górnym rogu widoku raportu wybierz wartość z listy rozwijanej raportu. Można również wybrać **Stały zakres dat*.

:::image type="content" source="media/filter-time-date-range.png" alt-text="Filtruj według czasu lub zakresów dat.":::

W przypadku większości raportów wybierz opcję **+ Dodaj warunek**, aby wybrać wymiar lub segment w celu filtrowania raportu. Aby uzyskać więcej informacji, zobacz temat [Wyświetlanie i tworzenie segmentów](segments.md).

## <a name="edit-a-custom-report"></a>Edytuj raport niestandardowy

1. Przejdź do opcji **Analizowanie** > **Niestandardowe**, aby uzyskać dostęp do niestandardowej listy raportów.

1. Z listy niestandardowych raportów wybierz pozycję **Więcej [..]** 

1. Wybierz opcję **Edytuj nazwę**, aby zmienić nazwę raportu.

1. Wybierz nazwę raportu i użyj opcji **+ Dodaj wizualizację** i **Edytuj**, aby dodać, usunąć, zmienić położenie lub rozmiary wizualizacji.

1. Aby zmienić właściwości wizualizacji, wybierz wizualizację, wybierz opcję **...**, a następnie opcję **Edytuj wizualizację**.

   :::image type="content" source="media/edit-visual-control.png" alt-text="Edytowanie właściwości wykresu dla raportów niestandardowych.":::

1. Po zakończeniu edycji raportu wybierz opcję **Zapisz**, aby zastosować zmiany. 

## <a name="delete-a-custom-report"></a>Usuwanie raportu niestandardowego

1. Przejdź do opcji **Analizowanie** > **Niestandardowe**, aby uzyskać dostęp do niestandardowej listy raportów.

1. Z listy niestandardowych raportów wybierz pozycję **...**

1. Wybierz pozycję **Usuń**, aby usunąć raport.

1. Potwierdź usunięcie, aby trwale usunąć raport.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
