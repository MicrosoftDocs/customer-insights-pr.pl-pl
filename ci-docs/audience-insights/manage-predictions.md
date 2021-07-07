---
title: Wspólne zadania dla scenariuszy przewidywania
description: Dowiedz się, jak zarządzać, rozwiązywać problemy i udoskonalać prognozy.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: dccb8dcca8f65f64973e46fed9d83034d58282e2
ms.sourcegitcommit: bcc47d15d4f0eacf008e4dbc09baac7f062b3ca8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2021
ms.locfileid: "6315891"
---
# <a name="manage-predictions"></a>Zarządzaj przewidywaniami

W tym artykule omówiono kilka zadań, które są wspólne dla większości scenariuszy predykcji.

## <a name="troubleshoot-a-failed-prediction"></a>Rozwiązywanie problemów dotyczących nieudanych przewidywań

1. Wybierz **Analizy** > **Przewidywania** i wybierz kartę **Moje przewidywania**.

1. Zaznacz wielokropek pionowy obok etykiety przewidywań, dla których chcesz wyświetlić dzienniki błędów.

1. Wybierz **Dzienniki**.

1. Przejrzyj wszystkie błędy. Istnieje kilka typów błędów, które mogą wystąpić, i opisują one jaki warunek spowodował błąd. Na przykład błąd polegający na tym, że jest zbyt mało danych, aby dokładnie przeprowadzić przewidywanie, jest zwykle rozwiązywany dzięki załadowaniu dodatkowych danych do Customer Insights.

## <a name="input-data-usability-report"></a>Raport dotyczący użyteczności danych wejściowych

Raport użyteczności danych wejściowych zapewnia skonsolidowany widok błędów i ostrzeżeń, które mogą być generowane przez Twoje przewidywania out-of-box. Podaje również zalecenia, jak poprawić wydajność modelu.

Raport jest dostępny po zakończeniu procesu szkolenia modelu. Jest on tworzony dla każdego modelu osobno, niezależnie od tego czy zakończył się sukcesem czy nie.

### <a name="view-the-input-data-usability-report"></a>Wyświetl raport użyteczności danych wejściowych

Po zakończeniu etapu szkolenia modelu out-of-box wyświetl raport:
- Wybierz grupy obok nazwy modelu i wybierz **Raport dotyczący użyteczności danych wejściowych**.
- Wybierz stan modelu, wybierz pozycję **Zobacz Raport o przydatności danych wejściowych** w okienku bocznym.
- Wybierz jeden z modeli z listy i wybierz **Raport dotyczący użyteczności danych wejściowych** na pasku poleceń.
- Otwórz stronę z wynikami modelu i wybierz **Raport dotyczący użyteczności danych wejściowych** na pasku poleceń.

### <a name="information-in-the-input-data-usability-report"></a>Informacje zawarte w raporcie o użyteczności danych wejściowych

Poniższe kolumny w raporcie zawierają informacje pomocne do poprawy danych dla modelu.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Przykład raportu użyteczności danych wejściowych zawierającego tabelę z błędami, ostrzeżeniami i zaleceniami.":::

- Nazwa: Opisowa nazwa błędu, ostrzeżenia lub zalecenia.
- Krok: Faza modelu, trenuj lub punktuj, informacje dotyczą.
- Stan: Poziom istotności informacji (błąd, ostrzeżenie, zalecenie).
- Nazwa kolumny: Kolumna w encji, która musi zostać zmodyfikowana, aby poprawić wydajność modelu.
- Nazwa encji: Nazwa encji, którą należy zmodyfikować, aby poprawić wydajność modelu.
- Szczegóły: szczegółowe informacje o błędzie, ostrzeżenie lub zalecenia.

## <a name="refresh-a-prediction"></a>Odświeżanie przewidywania

Przewidywania będą odświeżane automatycznie w oparciu o ten sam [harmonogram odświeżania danych](system.md#schedule-tab) skonfigurowany w ustawieniach. Można je również ręcznie odświeżyć.

1. Wybierz **Analizy** > **Przewidywania** i wybierz kartę **Moje przewidywania**.

1. Wybierz pionowy wielokropek obok przewidywania, które chcesz odświeżyć.

1. Wybierz **Odśwież**.

## <a name="delete-a-prediction"></a>Usuń przewidywanie

Usunięcie przewidywanie usuwa również jej encję wyjściową.

1. Wybierz **Analizy** > **Przewidywania** i wybierz kartę **Moje przewidywania**.

1. Wybierz pionowy wielokropek obok przewidywania, które chcesz usunąć.

1. Wybierz **Usuń**.
