---
title: Omówienie eksportów (wersja zapoznawcza)
description: Zarządzaj eksportami do udostępniania danych.
ms.date: 07/25/2022
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
ms.openlocfilehash: fd234aff9021ded76d8226bf2f15e035cf75e7db
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245340"
---
# <a name="exports-preview-overview"></a>Omówienie eksportów (wersja zapoznawcza)

 Eksporty umożliwiają udostępnianie określonych danych różnym aplikacjom. Mogą one zawierać profile klientów, encje, schematy i szczegóły mapowania. Każdy eksport wymaga [połączenia, skonfigurowanego przez administratora, do zarządzania uwierzytelnianiem i dostępem](connections.md). Na stronie **Eksporty** widać wszystkie skonfigurowane eksporty.

## <a name="export-types"></a>Typy eksportów

Istnieją dwa główne typy eksportów:  

- **Eksportowanie danych wyjściowych** umożliwia wyeksportowanie dowolnego typu encji dostępnych w aplikacji Customer Insights. Encje wybrane do wyeksportowania są eksportowane ze wszystkimi polami danych, metadanymi, schematami i szczegółami mapowania.
- **Eksporty segmentów** umożliwiają eksportowanie encji segmentów z aplikacji Customer Insights. Segmenty reprezentują listę profilów klientów. Podczas konfigurowania eksportu należy wybrać uwzględnione pola danych, w zależności od systemu docelowego, do którego są eksportowane dane.

### <a name="export-segments"></a>Eksportowanie segmentów

**Eksportowanie segmentów w środowiskach dla kont biznesowych (B2B) lub indywidualnych konsumentów (B2C)**  
W większości przypadków opcja eksportu obsługuje oba typy środowisk. Eksportowanie segmentów do różnych systemów docelowych ma specyficzne wymagania. 

**Eksporty segmentów w środowiskach dla konsumentów indywidualnych (B2C)**  
- Segmenty w kontekście środowisk indywidualnych klientów są wbudowane w encji *ujednoliconego profilu klienta*. Każdy segment spełniający wymagania systemów docelowych (na przykład adres e-mail) może zostać wyeksportowany.

**Środowiska eksportowania segmentów dla kont biznesowych (B2B)**  
- Segmenty w kontekście środowisk kont biznesowych są wbudowane w encji *klienta*. Aby wyeksportować segmenty kont w stanie takim, jak są, system docelowy musi obsługiwać czyste segmenty klientów. Ta opcja ma miejsce w przypadku serwisu [LinkedIn](export-linkedin-ads.md), gdy podczas definiowania eksportu zostanie wybrania opcja **firma**.
- Wszystkie inne systemy docelowe wymagają pól z encji kontaktu. Aby segmenty klientów mogą pobierać dane z kontaktów pokrewnych, definicja segmentu musi mieć atrybuty projektu encji kontaktu. Dowiedz się więcej o [konfigurowaniu segmentów i atrybutów projektu](segment-builder.md).

**Limity dotyczące eksportów segmentu**  
- Docelowe systemy innych firm mogą ograniczyć liczbę profilów klientów, które można eksportować. 
- W przypadku poszczególnych klientów po wybraniu segmentu eksportu zobaczysz rzeczywistą liczbę elementów członkowskich segmentu. Pojawi się ostrzeżenie, jeśli segment jest zbyt duży. 
- W przypadku kont biznesowych zobaczysz liczbę kont w segmencie; jednak liczba kontaktów, które mogą być projektowane, nie jest pokazywana. W niektórych przypadkach może to doprowadzić do tego, że wyeksportowany segment będzie zawierać więcej profilów klientów niż jest w stanie zaakceptować system docelowy. Jeśli limity systemu docelowego zostaną przekroczone, eksport zostanie pominięty.

## <a name="set-up-a-new-export"></a>Konfiguracja nowego eksportu

Aby skonfigurować lub edytować eksport, potrzebujesz odpowiednich połączeń. Połączenia zależą od [roli użytkownika](permissions.md):
- **Administratorzy** mają dostęp do wszystkich połączeń. Mogą oni także tworzyć nowe połączenia podczas konfigurowania eksportu.
- **Współautorzy** mogą mieć dostęp do określonych połączeń. Zależą od administratorów, którzy muszą konfigurować i udostępniać połączenia. Na liście eksportowania są wyświetlani współautorzy, niezależnie od tego, czy mogą edytować lub wyświetlać tylko eksport w kolumnie **Uprawnienia użytkownika**. Aby uzyskać więcej informacji, przejdź do tematu [Zezwalanie współautorom na używanie połączenia do eksportów](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Osoby przeglądające** mogą tylko wyświetlać istniejące raporty — a nie je tworzyć.

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj eksport**, aby utworzyć nowy eksport.

1. W okienku **Konfigurowanie eksportu** wybierz [połączenie](connections.md), które ma być użyte.

1. Podaj wymagane szczegóły i wybierz opcję **Zapisz**, aby utworzyć eksport. Aby uzyskać wymagane szczegóły, przejrzyj dokumentację Customer Insights dotyczącą konkretnego eksportu.

## <a name="manage-existing-exports"></a>Zarządzaj istniejącymi eksportami

Przejdź do **Dane** > **Eksporty**, aby wyświetlić eksporty, ich nazwę połączenia, typ połączenia i stan. Wszystkie role użytkowników mogą przeglądać skonfigurowane eksporty. Możesz posortować listę eksportów według dowolnej kolumny lub skorzystać z pola wyszukiwania, aby znaleźć eksport, którym chcesz zarządzać.

Wybierz eksport, aby wyświetlić dostępne akcje.

:::image type="content" source="media/exports_showmore.png" alt-text="Strona eksportu":::

- **Wyświet** lub **Edytuj** eksport. Użytkownicy bez edytowania uprawnień wybrać opcję **Wyświetl** zamiast opcji **Edycja**, aby wyświetlić szczegóły eksportowania.
- **Uruchom** eksport, aby wyeksportować najnowsze dane.
- **Utwórz duplikat** eksportu.
- **[Zaplanuj](#schedule-and-run-exports)** eksport.
- **Odłącz połączenie**, aby usunąć połączenie dla tego eksportu. Usunięcie połączenia nie powoduje usunięcia połączenia, ale powoduje dezaktywowanie eksportu. W kolumnie **Używane połączenie** jest wyświetlane brak połączenia.
- **Usuwanie** eksportu.

## <a name="schedule-and-run-exports"></a>Zaplanuj i uruchom eksport

Każdy skonfigurowany eksport ma harmonogram odświeżania. Podczas odświeżania system szuka nowych lub zaktualizowanych danych do uwzględnienia w eksporcie. Domyślnie eksport jest uruchamiany w ramach każdego [zaplanowanego odświeżania systemu](schedule-refresh.md). Można dostosować harmonogram odświeżania lub wyłączyć go, aby eksporty były wykonywane ręcznie.

Harmonogramy eksportu zależą od stanu środowiska. Jeśli istnieją aktualizacje dotyczące [zależności](system.md#refresh-processes) po uruchomieniu zaplanowanego eksportu, system najpierw je uzupełni, a następnie uruchomi eksport. Kolumna **Odświeżony** pokazuje, kiedy ostatnio odświeżono eksport.

### <a name="schedule-exports"></a>Harmonogram wywozu

Można zdefiniować niestandardowe harmonogramy odświeżania dla pojedynczego eksportu lub kilku eksportów jednocześnie. Aktualnie zdefiniowany harmonogram jest wymieniony w kolumnie **Harmonogram** na liście eksportu. Uprawnienia do zmiany harmonogramu są takie same jak w przypadku [edytowania i definiowania eksportów](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz eksport, który chcesz zaplanować.

1. Wybierz **Harmonogram**.

1. W okienku **Zaplanuj eksport** ustaw **Zaplanuj uruchomienie** na wartość **Wł.**, aby automatycznie uruchamiać eksportowanie. Ustaw wartość **Wyłącz**, aby odświeżyć go ręcznie.

1. W przypadku automatycznie odświeżanego eksportu wybierz wartość **Cykl** i określ jej szczegóły. Zdefiniowany czas ma zastosowanie do wszystkich przypadków nawrotu. To czas, w którym eksportowanie powinno rozpocząć odświeżanie.

1. Wybierz pozycję **Zapisz**.

Podczas edytowania harmonogramu dla kilku eksportów należy dokonać wyboru w obszarze **Zachowaj lub zastępowanie harmonogramów**:

- **Zachowaj poszczególne harmonogramy**: Zachowaj poprzednio zdefiniowany harmonogram dla wybranych eksportów i tylko je wyłączaj lub włączaj.
- **Zdefiniuj nowy harmonogram dla wszystkich wybranych eksportów**: zastąp istniejące harmonogramy wybranych eksportów.

### <a name="run-exports-on-demand"></a>Uruchamianie eksportów na żądanie

Aby wyeksportować dane bez oczekiwania na zaplanowane odświeżenie, przejdź do strony **Dane** > **Eksporty**.

- Aby uruchomić wszystkie eksporty, wybierz polecenie **Uruchom wszystkie** na pasku poleceń. Uruchamiane są tylko eksporty z aktywnym harmonogramem. Aby uruchomić nie aktywny eksport, uruchom pojedynczy eksport.
- Aby uruchomić pojedynczy eksport, wybierz go z listy i wybierz przycisk **Uruchom** na pasku poleceń.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
