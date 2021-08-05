---
title: Eksportowanie danych z usługi Customer Insights
description: Zarządzaj eksportami do udostępniania danych.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 47bdcc5bb38587063e4414377568943f868107a3
ms.sourcegitcommit: b78c9680b213204e6b0ed47f0147205083f6a98f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "6539356"
---
# <a name="exports-preview-overview"></a>Omówienie eksportów (wersja zapoznawcza)

Na stronie **Eksporty** widać wszystkie skonfigurowane eksporty. Eksporty udostępniają konkretne dane różnym aplikacjom. Mogą one zawierać profile klientów lub encje, schematy i szczegóły mapowania. Każdy eksport wymaga [połączenia, skonfigurowanego przez administratora, do zarządzania uwierzytelnianiem i dostępem](connections.md).

Przejdź do strony **Dane** > **Eksporty**, aby wyświetlić stronę eksportów. Wszystkie role użytkowników mogą przeglądać skonfigurowane eksporty. Użyj pola wyszukiwania na pasku poleceń, aby znaleźć eksporty według ich nazwy, nazwy połączenia lub typu połączenia.

## <a name="set-up-a-new-export"></a>Konfiguracja nowego eksportu

Aby skonfigurować lub edytować eksport, potrzebne są dostępne dla użytkownika połączenia. Połączenia zależą od [roli użytkownika](permissions.md):
- Administratorzy mają dostęp do wszystkich połączeń. Mogą oni także tworzyć nowe połączenia podczas konfigurowania eksportu.
- Współautorzy mogą mieć dostęp do określonych połączeń. Zależą od administratorów, którzy muszą konfigurować i udostępniać połączenia. Na liście eksportowania są wyświetlani współautorzy, niezależnie od tego, czy mogą edytować lub wyświetlać tylko eksport w kolumnie **Uprawnienia użytkownika**. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Wyświetlający mogą tylko wyświetlać istniejące eksporty, ale nie mogą ich tworzyć.

### <a name="define-a-new-export"></a>Definiowanie nowego eksportu

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj eksport**, aby utworzyć nowy eksport.

1. W okienku **Konfigurowanie eksportu** wybierz połączenie, które ma być użyte. [Połączenia](connections.md) są zarządzane przez administratorów. 

1. Podaj wymagane szczegóły i wybierz opcję **Zapisz**, aby utworzyć eksport.

### <a name="define-a-new-export-based-on-an-existing-export"></a>Definiowanie nowego eksportu na podstawie istniejącego eksportu

1. Przejdź do **Dane** > **Eksporty**.

1. Na liście eksportów wybierz eksport, który chcesz zduplikować.

1. Wybierz opcję **Utwórz duplikat** na pasku poleceń, aby otworzyć okienko **Konfigurowanie eksportu** ze szczegółami wybranego eksportu.

1. Przejrzyj i dostosuj eksport i wybierz opcję **Zapisz**, aby utworzyć nowy eksport.

### <a name="edit-an-export"></a>Edytuj eksport

1. Przejdź do **Dane** > **Eksporty**.

1. Na liście eksportów wybierz eksport, który chcesz edytować.

1. Na pasku poleceń wybierz **Edytuj**.

1. Zmień wartości, które chcesz zaktualizować i wybierz **Zapisz**.

## <a name="view-exports-and-export-details"></a>Wyświetlanie eksportów i szczegółów eksportów

Po utworzeniu miejsc docelowych eksportu są one wyświetlane w **Dane** > **Eksporty**. Wszyscy użytkownicy mogą zobaczyć, które dane są udostępniane oraz ich najaktualniejszy stan.

1. Przejdź do **Dane** > **Eksporty**.

1. Użytkownicy bez edytowania uprawnień wybrać opcję **Wyświetl** zamiast opcji **Edycja**, aby wyświetlić szczegóły eksportowania.

1. W okienku bocznym jest pokazana konfiguracja eksportu. Bez uprawnień do edycji nie można zmienić wartości. Wybierz opcję **Zamknij**, aby powrócić do strony eksportowania.

## <a name="schedule-and-run-exports"></a>Zaplanuj i uruchom eksport

Każdy skonfigurowany eksport ma harmonogram odświeżania. Podczas odświeżania system szuka nowych lub zaktualizowanych danych do uwzględnienia w eksporcie. Domyślnie eksport jest uruchamiany w ramach każdego [zaplanowanego odświeżania systemu](system.md#schedule-tab). Można dostosować harmonogram odświeżania lub wyłączyć go, aby eksporty były wykonywane ręcznie.

Harmonogramy eksportu zależą od stanu środowiska. Jeśli istnieją aktualizacje dotyczące [zależności](system.md#refresh-policies) po uruchomieniu zaplanowanego eksportu, system najpierw je uzupełni, a następnie uruchomi eksport. W ostatniej kolumnie **Odświeżony** eksport można zobaczyć, kiedy został ostatnio odświeżony eksport.

### <a name="schedule-exports"></a>Harmonogram wywozu

Można zdefiniować niestandardowe harmonogramy odświeżania dla pojedynczego eksportu lub kilku eksportów jednocześnie. Aktualnie zdefiniowany harmonogram jest wymieniony w kolumnie **Harmonogram** na liście eksportu. Uprawnienia do zmiany harmonogramu są takie same jak w przypadku [edytowania i definiowania eksportów](export-destinations.md#set-up-a-new-export). 

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz eksport, który chcesz zaplanować.

1. Na pasku poleceń wybierz **Zaplanuj**.

1. W okienku **Zaplanuj eksport** ustaw **Zaplanuj uruchomienie** na wartość **Wł.**, aby automatycznie uruchamiać eksportowanie. Ustaw wartość **Wyłącz**, aby odświeżyć go ręcznie.

1. W przypadku automatycznie odświeżanego eksportu wybierz wartość **Cykl** i określ jej szczegóły. Zdefiniowany czas ma zastosowanie do wszystkich przypadków nawrotu. To czas, w którym eksportowanie powinno rozpocząć odświeżanie.

1. Zastosuj i aktywuj zmiany, wybierając przycisk **Zapisz**.

Podczas edytowania harmonogramu dla kilku eksportów należy dokonać wyboru w obszarze **Zachowaj lub zastępowanie harmonogramów**:
- **Zachowaj poszczególne harmonogramy**: Zachowaj poprzednio zdefiniowany harmonogram dla wybranych eksportów i tylko je wyłączaj lub włączaj.
- **Zdefiniuj nowy harmonogram dla wszystkich wybranych eksportów**: zastąp istniejące harmonogramy wybranych eksportów.

### <a name="run-exports-on-demand"></a>Uruchamianie eksportów na żądanie

Aby wyeksportować dane bez oczekiwania na zaplanowane odświeżenie, przejdź do strony **Dane** > **Eksporty**.

- Aby uruchomić wszystkie eksporty, wybierz polecenie **Uruchom wszystkie** na pasku poleceń. Ta akcja uruchomi tylko eksporty, które mają aktywny harmonogram.
- Aby uruchomić pojedynczy eksport, wybierz go z listy i wybierz przycisk **Uruchom** na pasku poleceń. Tak można uruchomić eksport bez aktywnego harmonogramu. 

## <a name="remove-an-export"></a>Usuwanie eksportu

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz eksport, który chcesz usunąć.

1. Na pasku poleceń wybierz **Usuń**.

1. Potwierdź usuwanie, zaznaczając pole **Usuń** na ekranie potwierdzenia.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
