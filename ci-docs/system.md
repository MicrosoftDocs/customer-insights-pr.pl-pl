---
title: Konfiguracja systemu
description: Informacje o ustawieniach systemu w Dynamics 365 Customer Insights.
ms.date: 04/21/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-schedule
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 0ef84d8e286d8135eb8938e72f1319925e948bed
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9050684"
---
# <a name="system-configuration"></a>Konfiguracja systemu

Aby uzyskać dostęp do konfiguracji systemu, przejdź do strony **Administrator** > **System** w celu wyświetlenia listy zadań i procesów systemowych.

Strona **System** zawiera następujące karty:
- [Status](#status-tab)
- [Harmonogram](#schedule-tab)
- [Użycie interfejsu API](#api-usage-tab)
- [Informacje](#about-tab)
- [Ogólne](#general-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Karty Ustawienia na stronie systemowej.":::

## <a name="status-tab"></a>Karta Stan

Na **karcie Stan** można śledzić postęp zadań, pozyskiwanie danych, eksportowanie danych i kilka innych ważnych procesów produktu. Przejrzyj informacje na tej karcie, aby zapewnić pełne wykonywanie aktywnych zadań i procesów.

Ta karta zawiera tabele ze statusem i informacjami o przetwarzaniu dla różnych procesów. Każda tabela śledzi **Nazwę** zadania, odpowiadającą mu encję, **Stan** ostatniego uruchomienia oraz datę **Ostatniej aktualizacji**. Szczegółowe informacje dotyczące ostatnich uruchomionych zadań można wyświetlić, wybierając nazwę zadania lub procesu. 

Wybierz stan obok zadania lub procesu w kolumnie **Stan**, aby otworzyć okienko **szczegółów postępu**.

   :::image type="content" source="media/system-progress-details.png" alt-text="Okienko szczegółów postępu systemu":::

### <a name="status-definitions"></a>Definicje stanów

W przypadku zadań i procesów system używa następujących stanów:

|Status  |Definicja  |
|---------|---------|
|Anulowane |Przed zakończeniem przetwarzanie zostało anulowane przez użytkownika.   |
|Zakończone niepowodzeniem   |Pobieranie danych zostało napotkało błędy.         |
|Błąd  |Przetwarzanie nie powiodło się.  |
|Nie rozpoczęto   |Źródło danych nie ma jeszcze pozyskanych danych lub nadal jest w trybie roboczym.         |
|Trwa przetwarzanie  |Zadanie lub proces jest w toku.  |
|Odświeżanie    |Pobieranie danych jest w toku. Aby anulować operację, można wybrać opcję **Zatrzymaj odświeżanie** w kolumnie **Czynności**. Zatrzymanie odświeżania źródła danych spowoduje przywrócenie jego ostatniego stanu odświeżania.       |
|Pominięty  |Zadanie lub proces został pominięty. Co najmniej jeden z procesów podrzędnych, od którego zależy to zadanie, zakończył się niepowodzeniem lub został pominięty.|
|Zakończone powodzeniem  |Zadanie lub proces zostało zakończony pomyślnie. W przypadku źródeł danych oznacza, że dane zostały pomyślnie pozyskane, jeśli w kolumnie **Odświeżono** zostanie podana godzina.|
|W kolejce | Przetwarzanie znajduje się w kolejce i rozpocznie się po zakończeniu wszystkich zadań i procesów. Aby uzyskać więcej informacji zobacz temat [Odświeżanie procesów](#refresh-processes).|

### <a name="refresh-processes"></a>Odświeżanie procesów

Odświeżanie zadań i procesów jest wykonywane zgodnie ze [skonfigurowanym harmonogramem](#schedule-tab). 

|Przetwarzanie  |Opis  |
|---------|---------|
|Aktywność  |Uruchamianie ręczne (pojedyncze odświeżanie). W zależności od procesu scalania. Wyniki analiz od jego przetwarzania.|
|Łączenie analizy |Uruchamianie ręczne (pojedyncze odświeżanie). Zależy od segmentów.  |
|Przygotowywanie analizy |Uruchamianie ręczne (pojedyncze odświeżanie). Zależy od segmentów.  |
|Przygotowywanie danych   |Do uruchomienia wymaga encji. Źródło danych zależy od pozyskiwania. Encje wzbogacone zależą od wzbogacania. Obiekt Klient zależy od scalania.  |
|Źródła danych   |Nie jest uzależniony od innych procesów. Dopasowanie zależy od pomyślnego zakończenia tego procesu.  |
|Wzbogacenia   |Uruchamianie ręczne (pojedyncze odświeżanie). W zależności od procesu scalania. |
|Lokalizacje docelowe eksportów |Uruchamianie ręczne (pojedyncze odświeżanie). Zależy od segmentów.  |
|Wyniki analiz |Uruchamianie ręczne (pojedyncze odświeżanie). Zależy od segmentów.  |
|Analizy   |Zależy od scalania.   |
|Dopasowywanie |Zależy od sposobu przetwarzania źródeł danych użytych w definicji dopasowania.      |
|Miary  |Uruchamianie ręczne (pojedyncze odświeżanie). W zależności od procesu scalania.  |
|Scalanie   |Zależy od pomyślnego zakończenia tego procesu dopasowywania. Segmenty, miary, wzbogacenia, wyszukiwania, działania, przewidywania i przygotowanie danych zależą od pomyślnego zakończenia procesu.   |
|Profile   |Uruchamianie ręczne (pojedyncze odświeżanie). W zależności od procesu scalania. |
|Wyszukiw.   |Uruchamianie ręczne (pojedyncze odświeżanie). W zależności od procesu scalania. |
|Segmenty  |Uruchamianie ręczne (pojedyncze odświeżanie). W zależności od procesu scalania. Wyniki analiz od jego przetwarzania.|
|Zadania systemowe   |Zależy od pomyślnego zakończenia tego procesu dopasowywania. Segmenty, miary, wzbogacenia, wyszukiwania, działania, przewidywania i przygotowanie danych zależą od pomyślnego zakończenia procesu.   |
|Użytkownika  |Uruchamianie ręczne (pojedyncze odświeżanie). Zależy od encji.  |

Wybierz stan procesu, aby wyświetlić szczegóły postępu dotyczące całego zadania, do którego należy proces. Powyższe procesy odświeżania mogą pomóc w zrozumieniu, co można zrobić w celu rozwiązania problemu z zadaniem lub procesem typu **Pominięto** lub **W kolejce**.

## <a name="schedule-tab"></a>Karta Harmonogram

Użyj karty **Harmonogram**, aby zaplanować automatyczne odświeżanie wszystkich [źródeł pobieranych danych](data-sources.md). Automatyczne odświeżanie ułatwia zagwarantowanie, że aktualizacje ze źródeł danych będą odzwierciedlone w ujednoliconych profilach klientów.

> [!NOTE]
> Źródła danych zarządzane przez odświeżanie według własnych harmonogramów. Aby zaplanować odświeżanie źródeł danych zarządzanych przez użytkownika, należy skonfigurować ustawienia odświeżania dla tego źródła danych na stronie **Źródła danych**.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Ustawienia odświeżania przepływu danych Power Platform.":::

1. Przejdź do pozycji **Administracja** > **System** i wybierz kartę **Harmonogram**.

2. Stan domyślny dla planowanego odświeżenia to **Wyłączony**. Aby włączyć zaplanowane odświeżanie, należy zmienić przełącznik na górze ekranu na opcję **Włączony**.

3. Należy wybrać kolejno pozycje **Co tydzień** (domyślne) i **Codziennie** odświeżanie. Jeśli zamierzasz zaplanować cotygodniowe odświeżenie, wybierz jeden lub kilka dni, kiedy chcesz uruchomić odświeżanie.

4. Ustaw **Strefę czasową**, a następnie użyj listy rozwijanej **Czas**, aby ustawić czas odświeżania. Kiedy skończysz, wybierz **Ustaw**. Jeśli chcesz zaplanować wiele odświeżań w ciągu jednego dnia, wybierz opcję **Dodaj inną godzinę**.

5. Wybierz pozycję **Zapisz**, aby zastosować zmiany.

## <a name="about-tab"></a>Karta Informacje

Karta **Informacje** zawiera **Wyświetlaną nazwę** organizacji, aktywny **Identyfikator środowiska**, **Region** i **Identyfikator sesji**. Jeśli masz więcej niż jedno środowisko pracy, powinieneś nadać każdemu łatwą do zidentyfikowania nazwę wyświetlaną.

## <a name="general-tab"></a>Karta Ogólne

Na karcie **Ogólne** można zmienić język i format kraju/regionu.

Aplikacja Customer Insights [obsługuje wiele języków](/dynamics365/get-started/availability). Aplikacja wykorzystuje preferencje językowe do wyświetlania elementów, takich jak menu, tekst etykiety i komunikaty systemowe w preferowanym języku.

Zaimportowane dane i informacje wprowadzone ręcznie nie są przetłumaczone.

### <a name="update-the-settings"></a>Aktualizuj ustawienia

Aby zmienić preferowany język, wybierz **Język** z listy rozwijanej.

Aby zmienić preferowany format dat, godzin i liczb, użyj listy rozwijanej **Format kraju/regionu**. W obszarze tego pola jest wyświetlany podgląd formatowania. System automatycznie zasugeruje wybór, gdy wybierzesz nowy język.

Kliknij przycisk **Zapisz** i potwierdź wybór.

## <a name="api-usage-tab"></a>Karta użycia interfejsu API

Znajdź szczegółowe informacje na temat wykorzystania interfejsu API w czasie rzeczywistym i zobacz, które zdarzenia miały miejsce w danym przedziale czasowym. Wybierz przedział czasowy w menu rozwijanym **Wybierz przedział czasowy**. 

**Użycie interfejsu API** zawiera trzy sekcje: 
- **Wywołania interfejsu API** — wykres, który wizualizuje zagregowaną liczbę wywołań interfejsu API w wybranym przedziale czasu.

- **Transfer danych** — wykres przedstawiający ilość danych przesłanych przez interfejs API w wybranym okresie.

-  **Operacje** — tabelę z wierszami dla każdej dostępnej operacji API i szczegółami użycia tych operacji. Możesz wybrać nazwę operacji, aby przejść do odwołania [do interfejsu API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Operacje, które korzystają z [pozyskiwania danych w czasie rzeczywistym](real-time-data-ingestion.md), zawierają przycisk z symbolem lornetki, który umożliwia wyświetlanie informacji o użyciu interfejsów API w czasie rzeczywistym. Wybierz przycisk, aby otworzyć panel boczny zawierający szczegóły użycia interfejsu API w czasie rzeczywistym w bieżącym środowisku.   
   Pole **Grupuj według** w okienku **Użycia interfejsu API w czasie rzeczywistym** umożliwia wybranie sposobu najlepszego prezentowania interakcji w czasie rzeczywistym. Dane można pogrupować według metody interfejsu API, kwalifikowanej nazwy encji (pobranej encji), utworzone przez (źródło zdarzenia), wyniku (powodzenie lub niepowodzenie) lub kodów błędów. Dane są dostępne jako wykres chronologiczny i jako tabela.


[!INCLUDE [footer-include](includes/footer-banner.md)]
