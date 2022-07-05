---
title: Omówienie eksportów (wersja zapoznawcza)
description: Zarządzaj eksportami do udostępniania danych.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- ci-connections
- customerInsights
ms.openlocfilehash: d983e84e713003610eb27dc9b3f911b62b01d522
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081605"
---
# <a name="exports-preview-overview"></a>Omówienie eksportów (wersja zapoznawcza)

Na stronie **Eksporty** widać wszystkie skonfigurowane eksporty. Eksporty udostępniają konkretne dane różnym aplikacjom. Mogą one zawierać profile klientów, encje, schematy i szczegóły mapowania. Każdy eksport wymaga [połączenia, skonfigurowanego przez administratora, do zarządzania uwierzytelnianiem i dostępem](connections.md).

Przejdź do strony **Dane** > **Eksporty**, aby wyświetlić stronę eksportów. Wszystkie role użytkowników mogą przeglądać skonfigurowane eksporty. Użyj pola wyszukiwania na pasku poleceń, aby znaleźć eksporty według ich nazwy, nazwy połączenia lub typu połączenia.

## <a name="export-types"></a>Typy eksportów

Istnieją dwa główne typy eksportów:  

- **Eksportowanie danych wyjściowych** umożliwia wyeksportowanie dowolnego typu encji dostępnych w aplikacji Customer Insights. Encje wybrane do wyeksportowania są eksportowane ze wszystkimi polami danych, metadanymi, schematami i szczegółami mapowania. 
- **Eksporty segmentów** umożliwiają eksportowanie encji segmentów z aplikacji Customer Insights. Segmenty reprezentują listę profilów klientów. Podczas konfigurowania eksportu należy wybrać uwzględnione pola danych, w zależności od systemu docelowego, do którego są eksportowane dane. 

### <a name="export-segments"></a>Eksportowanie segmentów

**Eksportowanie segmentów w środowiskach dla kont biznesowych (B2B) lub indywidualnych konsumentów (B2C)**  
W większości przypadków opcja eksportu obsługuje oba typy środowisk. Eksportowanie segmentów do różnych systemów docelowych ma specyficzne wymagania. Generalnie rzecz biorąc, element członkowski segmentu, profil klienta, zawiera informacje kontaktowe. Tak się zwykle dzieje w przypadku segmentów opartych na indywidualnych konsumentach (B2C), ale nie musi to być prawda w przypadku segmentów opartych na kontach biznesowych (B2B). 

**Środowiska eksportowania segmentów dla kont biznesowych (B2B)**  
- Segmenty w kontekście środowisk kont biznesowych są wbudowane w encji *klienta*. Aby wyeksportować segmenty kont w stanie takim, jak są, system docelowy musi obsługiwać czyste segmenty klientów. Ta opcja ma miejsce w przypadku serwisu [LinkedIn](export-linkedin-ads.md), gdy podczas definiowania eksportu zostanie wybrania opcja **firma**.
- Wszystkie inne systemy docelowe wymagają pól z encji kontaktu. Aby segmenty klientów mogą pobierać dane z kontaktów pokrewnych, definicja segmentu musi mieć atrybuty projektu encji kontaktu. Dowiedz się więcej o [konfigurowaniu segmentów i atrybutów projektu](segment-builder.md).

**Eksporty segmentów w środowiskach dla konsumentów indywidualnych (B2C)**  
- Segmenty w kontekście środowisk indywidualnych klientów są wbudowane w encji *ujednoliconego profilu klienta*. Każdy segment spełniający wymagania systemów docelowych (na przykład adres e-mail) może zostać wyeksportowany.

**Limity dotyczące eksportów segmentu**  
- Docelowe systemy innych firm mogą ograniczyć liczbę profilów klientów, które można eksportować. 
- W przypadku poszczególnych klientów po wybraniu segmentu eksportu zobaczysz rzeczywistą liczbę elementów członkowskich segmentu. Pojawi się ostrzeżenie, jeśli segment jest zbyt duży. 
- W przypadku kont biznesowych zobaczysz liczbę kont w segmencie; jednak liczba kontaktów, które mogą być projektowane, nie jest pokazywana. W niektórych przypadkach może to doprowadzić do tego, że wyeksportowany segment będzie zawierać więcej profilów klientów niż jest w stanie zaakceptować system docelowy. Przekroczenie limitów wyników w systemach docelowych spowoduje pominięcie eksportu. 

## <a name="set-up-a-new-export"></a>Konfiguracja nowego eksportu  
Aby skonfigurować lub edytować eksport, potrzebne są dostępne dla użytkownika połączenia. Połączenia zależą od [roli użytkownika](permissions.md):
- **Administratorzy** mają dostęp do wszystkich połączeń. Mogą oni także tworzyć nowe połączenia podczas konfigurowania eksportu.
- **Współautorzy** mogą mieć dostęp do określonych połączeń. Zależą od administratorów, którzy muszą konfigurować i udostępniać połączenia. Na liście eksportowania są wyświetlani współautorzy, niezależnie od tego, czy mogą edytować lub wyświetlać tylko eksport w kolumnie **Uprawnienia użytkownika**. Aby uzyskać więcej informacji, przejdź do tematu [Zezwalanie współautorom na używanie połączenia do eksportów](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Osoby przeglądające** mogą tylko wyświetlać istniejące raporty — a nie je tworzyć.

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

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Harmonogramy eksportu zależą od stanu środowiska. Jeśli istnieją aktualizacje dotyczące [zależności](system.md#refresh-processes) po uruchomieniu zaplanowanego eksportu, system najpierw je uzupełni, a następnie uruchomi eksport. W ostatniej kolumnie **Odświeżony** eksport można zobaczyć, kiedy został ostatnio odświeżony eksport.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]
