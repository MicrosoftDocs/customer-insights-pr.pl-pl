---
title: Eksportowanie danych z usługi Customer Insights
description: Zarządzaj eksportami do udostępniania danych.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016649"
---
# <a name="exports-preview-overview"></a>Omówienie eksportów (wersja zapoznawcza)

Na stronie **Eksporty** widać wszystkie skonfigurowane eksporty. Eksporty udostępniają konkretne dane różnym aplikacjom. Mogą one zawierać profile klientów lub encje, schematy i szczegóły mapowania. Każdy eksport wymaga [połączenia, skonfigurowanego przez administratora, do zarządzania uwierzytelnianiem i dostępem](connections.md).

Przejdź do strony **Dane** > **Eksporty**, aby wyświetlić stronę eksportów. Wszystkie role użytkowników mają dostęp do wyświetlania skonfigurowanych eksportów. Użycie pola wyszukiwania na pasku poleceń w celu znalezienia eksportów według ich nazwy, nazwy połączenia lub typu połączenia.

## <a name="set-up-a-new-export"></a>Konfiguracja nowego eksportu

Aby skonfigurować lub edytować eksport, potrzebne są dostępne dla użytkownika połączenia. Połączenia zależą od [roli użytkownika](permissions.md):
- Administratorzy mają dostęp do wszystkich połączeń. Mogą oni także tworzyć nowe połączenia podczas konfigurowania eksportu.
- Współautorzy mogą mieć dostęp do określonych połączeń. Zależą od administratorów, którzy muszą konfigurować i udostępniać połączenia. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Wyświetlający mogą tylko wyświetlać istniejące eksporty, ale nie mogą ich tworzyć.

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj eksport**, aby utworzyć nowe miejsce docelowe eksportu.

1. W okienku **Konfigurowanie eksportu** wybierz połączenie, które ma być użyte. [Połączenia](connections.md) są zarządzane przez administratorów. 

1. Podaj wymagane szczegóły i wybierz opcję **Zapisz**, aby utworzyć eksport.

### <a name="edit-an-export"></a>Edytuj eksport

1. Wybierz pionowy wielokropek dla lokalizacji docelowej eksportu, którą chcesz edytować.

1. Z menu rozwijanego wybierz polecenie **Edytuj**.

1. Zmień wartości, które chcesz zaktualizować i wybierz **Zapisz**.

## <a name="view-exports-and-export-details"></a>Wyświetlanie eksportów i szczegółów eksportów

Po utworzeniu miejsc docelowych eksportu są one wyświetlane w **Dane** > **Eksporty**. Wszyscy użytkownicy mogą zobaczyć, które dane są udostępniane oraz ich najaktualniejszy stan.

1. Przejdź do **Dane** > **Eksporty**.

1. Użytkownicy bez uprawnień do edytowania mogą wybrać opcję **Wyświetl** zamiast opcji **Edytuj**, zobacz szczegółowe informacje o eksportowaniu.

1. W tym okienku bocznym jest pokazana konfiguracja tego eksportu. Bez uprawnień do edycji nie można zmienić wartości. Wybierz opcję **Zamknij**, aby powrócić do strony eksportowania.

## <a name="run-exports-on-demand"></a>Uruchamianie eksportów na żądanie

Po skonfigurowaniu eksportu będzie on uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab), o ile posiada działające połączenie.

Aby wyeksportować dane bez oczekiwania na zaplanowane odświeżenie, przejdź do strony **Dane** > **Eksporty**. Dostępne są dwie opcje:

- Aby uruchomić wszystkie eksporty, wybierz polecenie **Uruchom wszystkie** na pasku poleceń. 
- Aby uruchomić pojedynczy eksport, wybierz wielokropek (...) dla elementu listy, a następnie wybierz opcję **Uruchom**.

## <a name="remove-an-export"></a>Usuwanie eksportu

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz pionowy wielokropek dla eksportu, który chcesz usunąć.

1. Wybierz **Usuń** z menu rozwijanego.

1. Potwierdź usuwanie, zaznaczając pole **Usuń** na ekranie potwierdzenia.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
