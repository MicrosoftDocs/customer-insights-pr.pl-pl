---
title: Utwórz miary na podstawie szablonów
description: Zdefiniuj miary przy użyciu szablonów do najczęściej występujących spraw.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 6dc7fce78d10ba91de4b2abf54c6c6ab1c919d3a
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170786"
---
# <a name="create-measures-from-templates"></a>Utwórz miary na podstawie szablonów

Do ich utworzenia miar można użyć wstępnie zdefiniowanych szablonów najczęściej stosowanych [miar](measures.md). Szablony są budowane na podstawie zamapowanych danych z encji *Ujednolicone działanie*. Należy więc upewnić się, że skonfigurowano [działania klientów](activities.md) przed utworzeniem miary na podstawie szablonu.

Szablony miar są obsługiwane tylko w środowiskach dla **poszczególnych klientów**. Aby utworzyć miary niestandardowe lub utworzyć miary B-do-B, zobacz [Korzystanie z konstruktora miar](measure-builder.md).

Dostępne szablony miar:
- Średnia wartość transakcji (ATV)
- Łączna wartość transakcji
- Średni przychód dzienny
- Średni przychód miesięczny
- Średni przychód roczny
- Liczba transakcji
- Zdobyte punkty lojalnościowe
- Zrealizowane punkty lojalnościowe
- Saldo punktów lojalnościowych
- Okres istnienia aktywnego klienta
- Czas trwania uczestnictwa w programie lojalnościowym
- Czas od ostatniego zakupu

## <a name="build-a-new-measure-using-a-template"></a>Tworzenie nowej miary przy użyciu szablonu

1. Przejdź do **Miar**.

1. Wybierz **Nowy** i wybierz **Wybierz szablon**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Zrzut ekranu menu rozwijanego podczas tworzenia nowej miary z wyróżnieniem szablonu.":::

1. Znajdź szablon odpowiedni do potrzeb i wybierz opcję **Wybierz szablon**.

1. Przejrzyj wymagane dane i wybierz pozycję **Rozpocznij**, jeśli masz już wszystkie dane.

1. Wybierz **Edytuj szczegóły** obok nazwy miary. Podaj nazwę miary. Opcjonalnie dodaj [etykiety](work-with-tags-columns.md#manage-tags) do miary.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Okno dialogowe Edytuj szczegóły.":::

1. Wybierz pozycję **Gotowe**.

1. W sekcji **Ustawianie okresu czasu** zdefiniuj horyzont czasowy danych, które mają być użyte. Określ, czy nowa miara ma obejmować cały zestaw danych, wybierając opcję **Ogółem** lub jeśli chcesz skupić się na **określonym okresie**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Zrzut ekranu przedstawiający sekcję okresu podczas konfigurowania miary z szablonu.":::

1. W następnej sekcji wybierz pozycję **Dodaj dane**, aby wybrać działania i zmapować odpowiednie dane z encji *Ujednolicone działanie*.

    1. Krok 1 z 2: w obszarze **Typ działania** wybierz typ encji, której chcesz użyć. W przypadku **Działań** wybierz encje, które chcesz zamapować, a następnie wybierz **Dalej**.
    1. Krok 2 z 2: wybierz atrybut z encji *Ujednolicone działanie* dla składnika wymaganego przez formułę. Na przykład w przypadku Średniej wartości transakcji jest to atrybut reprezentujący wartość Transakcji. W przypadku **Znacznika czasu działania** wybierz atrybut z encji *Ujednolicone działanie* reprezentujący datę i godzinę działania.
    1. Wybierz pozycję **Zapisz**.

    Po pomyślnym mapowaniu danych można zobaczyć stan jako **Zakończone** oraz nazwę zmapowanych działań i atrybutów.

1. Wybierz opcję **Uruchom**, aby obliczyć wyniki miary. Wybierz opcję **Zapisz wersję roboczą**, jeśli chcesz zachować bieżącą konfigurację i uruchomić miarę później. Wyświetla się strona **Miary**.

## <a name="next-step"></a>Następny krok

Istniejące miary można wykorzystać do utworzenia [segmentu klienta](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
