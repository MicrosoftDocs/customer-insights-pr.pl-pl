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
ms.openlocfilehash: ead57ccbdcaf9f86ee54d1f15de71a63f2e1081b
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170856"
---
# <a name="measures-overview"></a>Omówienie miar

Miary pomagają lepiej poznać zachowania klientów i wydajność biznesową. Analizują one odpowiednie wartości z [ujednoliconych profilów](data-unification.md). Na przykład, firma chce zobaczyć *całkowite wydatki na klienta*, aby zrozumieć historię zakupów poszczególnych klientów lub zmierzyć *całkowitą sprzedaż firmy*, aby zrozumieć zagregowany poziom przychodów w całej firmie.

Twórz miary, aby planować działania biznesowe, wysyłając zapytania do danych klientów i wydobywając spostrzeżenia. Na przykład utworzenie miary *całkowitych wydatków na klienta* i *całkowitego zwrotu na klienta* pomaga zidentyfikować grupę klientów z wysokimi wydatkami, ale z wysokim zwrotem. Następnie aby dodać następne najlepsze akcje, można [utworzyć segment](segments.md) na podstawie tych działań.

## <a name="create-a-measure"></a>Utwórz miarę

Wybierz sposób tworzenia miary na podstawie grupy docelowej.

# <a name="individual-consumers-b-to-c"></a>[Klienci indywidualni (B2C)](#tab/b2c)

- Konstruktor miar od podstaw: [twórz własne](measure-builder.md).
- Z powszechnie stosowanych miar: [Użyj predefiniowanych szablonów](measure-templates.md).

# <a name="business-accounts-b-to-b"></a>[Klienci biznesowi (B2B)](#tab/b2b)

Konstruktor miar od podstaw: [twórz własne](measure-builder.md).

---

## <a name="manage-existing-measures"></a>Zarządzaj istniejącymi środkami

Przejdź do strony **Miary**, aby wyświetlić utworzone miary, ich status, typ miary i czas ostatniego odświeżenia danych. Listę miar można posortować według dowolnej kolumny lub użyć pola wyszukiwania, aby znaleźć miarę, którą chcesz zarządzać.

Wybierz obok miary, aby wyświetlić dostępne działania. Wybierz nazwę taktu, aby wyświetlić podgląd danych wyjściowych i pobrać plik CSV.

:::image type="content" source="media/measures-actions.png" alt-text="Akcje służące do zarządzania pojedynczymi miarami."lightbox="media/measures-actions.png":::

- **Edytuj** miara, aby zmienić jego właściwości.
- **Odśwież** miara, aby uwzględnić najnowsze dane.
- **Zmień nazwę** miary.
- **Aktywuj** lub **Dezaktywuj** miara. Nieaktywne miary nie zostaną odświeżone podczas [zaplanowanego odświeżenia](system.md#schedule-tab), a segment nieaktywne mają **Stan** wyświetlany jako **Pominięty**, co oznacza, że nie wystąpiła jeszcze próba odświeżenia.
- **Otaguj**, aby [zarządzać etykietami](work-with-tags-columns.md#manage-tags) dla miary.
- **Usuń** miarę.
- **Kolumny** w [celu dostosowania wyświetlanych kolumn](work-with-tags-columns.md#customize-columns).
- **Filtruj**, aby [filtrować etykiety](work-with-tags-columns.md#filter-on-tags).
- **Wyszukaj nazwę**, aby wyszukać według nazwy miary.

## <a name="refresh-measures"></a>Odświeżanie miar

Miary mogą być odświeżane w harmonogramie automatycznym lub ręcznie odświeżane na żądanie. Aby ręcznie odświeżyć jedno lub więcej miar, wybierz je i wybierz opcję **Odśwież**. Aby [zaplanować automatyczne odświeżanie](system.md#schedule-tab), przejdź do strony **Administrator** > **System** > **Harmonogram**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
