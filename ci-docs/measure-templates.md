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
ms.openlocfilehash: f6bcdfc45a49c36f22d6ebc6e919f43b27f899d8
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051697"
---
# <a name="create-measures-from-templates"></a>Utwórz miary na podstawie szablonów

Do ich utworzenia miar można użyć wstępnie zdefiniowanych szablonów najczęściej stosowanych [miar](measures.md). Szczegółowe opisy szablonów i działanie z przewodnikiem mogą ułatwić efektywne tworzenie miar. Szablony są budowane na podstawie zamapowanych danych z encji *Ujednolicone działanie*. Należy więc upewnić się, że skonfigurowano [działania klientów](activities.md) przed utworzeniem miary na podstawie szablonu.

Aby utworzyć miary niestandardowe, zobacz temat [Korzystanie z konstruktora miar do tworzenia miar od podstaw](measure-builder.md).

# <a name="individual-consumers-b-to-c"></a>[Klienci indywidualni (B2C)](#tab/b2c)

Dostępne szablony miar: 
- Średnia wartość transakcji (ATV)
- Łączna wartość transakcji
- Średni przychód dzienny
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

    1. Krok 1 z 2: w obszarze **Typ działania** wybierz typ encji, której chcesz użyć. W przypadku **Działań** wybierz encje, które chcesz zamapować.
    1. Krok 2 z 2: wybierz atrybut z encji *Ujednolicone działanie* dla składnika wymaganego przez formułę. Na przykład w przypadku Średniej wartości transakcji jest to atrybut reprezentujący wartość Transakcji. W przypadku **Znacznika czasu działania** wybierz atrybut z encji Ujednolicone działanie reprezentujący datę i godzinę działania.
   
1. Po pomyślnym mapowaniu danych można zobaczyć stan jako **Zakończone** oraz nazwę zamapowanych działań i atrybutów.

1. Teraz można wybrać opcję **Uruchom**, aby obliczyć wyniki miary. Aby uściślić go później, wybierz opcję **Zapisz kopię roboczą**.

# <a name="business-accounts-b-to-b"></a>[Klienci biznesowi (B2B)](#tab/b2b)

Ta funkcja jest dostępna tylko dla działań utworzonych w środowiskach, w których klienci indywidualni są podstawowymi odbiorcami docelowymi.

---
