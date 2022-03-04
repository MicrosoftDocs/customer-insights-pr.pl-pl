---
title: Rozumienie i zarządzanie miarami
description: Dowiedz się, w jaki sposób miary pomagają analizować i odzwierciedlać wydajność biznesową.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: c46fcc3baba1d6c92c2c0fe459a62277343cc0e4
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359800"
---
# <a name="measures-overview"></a>Omówienie miar

Miary pomagają lepiej poznać zachowania klientów i wydajność biznesową. Analizują one odpowiednie wartości z [ujednoliconych profilów](data-unification.md). Na przykład, firma chce zobaczyć *całkowite wydatki na klienta*, aby zrozumieć historię zakupów poszczególnych klientów lub zmierzyć *całkowitą sprzedaż firmy*, aby zrozumieć zagregowany poziom przychodów w całej firmie.  

Miary są tworzone za [pomocą konstruktora miar](measure-builder.md), platformy zapytań o dane z różnymi operatorami i prostymi opcjami mapowania. Umożliwia filtrowanie danych, grupowanie wyników, wykrywanie [ścieżek relacji między encjami](relationships.md) i wyświetlanie podglądu danych wyjściowych. Aby efektywnie konfigurować najczęściej używane miary, można użyć [wstępnie zdefiniowanych szablonów](measure-templates.md).

Użyj konstruktora miar, aby zaplanować działania biznesowe, wykonując zapytania dotyczące danych klientów i wyodrębniając szczegółowe informacje. Na przykład utworzenie miary *całkowitych wydatków na klienta* i *całkowitego zwrotu na klienta* pomaga zidentyfikować grupę klientów z wysokimi wydatkami, ale z wysokim zwrotem. Aby dodać następne najlepsze akcje, można [utworzyć segment](segments.md) na podstawie tych działań. 

## <a name="manage-your-measures"></a>Zarządzanie miarami

Listę miar można znaleźć na stronie **Miary**.

Znajdziesz informacje o rodzaju miary, twórcy, dacie utworzenia, stanie i stanie. Po wybraniu miary z listy można wyświetlić podgląd danych wyjściowych i pobrać plik CSV.

Aby odświeżyć wszystkie miary w tym samym czasie, wybierz **Odśwież wszystko** bez wybierania określonej miary.

:::image type="content" source="media/measure-actions.png" alt-text="Akcje służące do zarządzania pojedynczymi miarami.":::

Wybierz z listy miarę dla następujących opcji:

- Wybierz nazwę miary, aby wyświetlić jej szczegóły.
- **Edytuj** konfigurację miary.
- **Odśwież** miarę na podstawie najnowszych danych.
- **Zmień nazwę** miary.
- **Usuń** miarę.
- **Aktywuj** lub **Dezaktywuj**. Nieaktywne miary nie będą odświeżane podczas [zaplanowanego odświeżania](system.md#schedule-tab).

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>Następny krok

Istniejące miary można wykorzystać do utworzenia [segmentu klienta](segments.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
