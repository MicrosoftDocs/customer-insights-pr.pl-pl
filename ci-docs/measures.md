---
title: Omówienie miar
description: Dowiedz się, w jaki sposób miary pomagają analizować i odzwierciedlać wydajność biznesową.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: 880c06bffcfa269151d96cb4c597eed4832fc61b
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081705"
---
# <a name="measures-overview"></a>Omówienie miar

Miary pomagają lepiej poznać zachowania klientów i wydajność biznesową. Analizują one odpowiednie wartości z [ujednoliconych profilów](data-unification.md). Na przykład, firma chce zobaczyć *całkowite wydatki na klienta*, aby zrozumieć historię zakupów poszczególnych klientów lub zmierzyć *całkowitą sprzedaż firmy*, aby zrozumieć zagregowany poziom przychodów w całej firmie.  

Miary są tworzone za [pomocą konstruktora miar](measure-builder.md), platformy zapytań o dane z różnymi operatorami i prostymi opcjami mapowania. Umożliwia filtrowanie danych, grupowanie wyników, wykrywanie [ścieżek relacji między encjami](relationships.md) i wyświetlanie podglądu danych wyjściowych. Aby efektywnie konfigurować najczęściej używane miary, można użyć [wstępnie zdefiniowanych szablonów](measure-templates.md).

Użyj konstruktora miar, aby zaplanować działania biznesowe, wykonując zapytania dotyczące danych klientów i wyodrębniając szczegółowe informacje. Na przykład utworzenie miary *całkowitych wydatków na klienta* i *całkowitego zwrotu na klienta* pomaga zidentyfikować grupę klientów z wysokimi wydatkami, ale z wysokim zwrotem. Aby dodać następne najlepsze akcje, można [utworzyć segment](segments.md) na podstawie tych działań.

## <a name="manage-your-measures"></a>Zarządzanie miarami

Listę miar można znaleźć na stronie **Miary**.

Znajdziesz informacje o rodzaju miary, twórcy, dacie utworzenia, stanie i stanie. Po wybraniu miary z listy można wyświetlić podgląd danych wyjściowych i pobrać plik CSV.

:::image type="content" source="media/measures-actions.png" alt-text="Akcje służące do zarządzania pojedynczymi miarami."lightbox="media/measures-actions.png":::

Po zaznaczeniu segmentu dostępne są następujące miary:

- **Edytuj** konfigurację miary.
- **Duplikuj** miarę. Można od razu edytować jego właściwości lub po prostu zapisać duplikat.
- **Odśwież** miarę na podstawie najnowszych danych. Aby odświeżyć wszystkie miary w tym samym czasie, wybierz wszystkie miary, a następnie **Odśwież**.
- **Zmień nazwę** miary.
- **Aktywuj** lub **Dezaktywuj**. Nieaktywne miary nie będą odświeżane podczas [zaplanowanego odświeżania](system.md#schedule-tab).
- **Otaguj**, aby [zarządzać etykietami](work-with-tags-columns.md#manage-tags) dla segmentu.
- **Usuń** miarę.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-step"></a>Następny krok

Istniejące miary można wykorzystać do utworzenia [segmentu klienta](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
