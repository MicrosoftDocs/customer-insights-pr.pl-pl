---
title: Konfiguracja systemu w statystykach odbiorców
description: Dowiedz się o ustawieniach systemu w możliwości analiz odbiorców w Dynamics 365 Customer Insights.
ms.date: 02/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2af8728009b4f1d53ebc2557bab8c79537a0dc5dda54477493ab1ad16f3f9a8a
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035929"
---
# <a name="system-configuration"></a>Konfiguracja systemu

Strona **System** zawiera następujące karty:
- [Status](#status-tab)
- [Harmonogram](#schedule-tab)
- [Użycie interfejsu API](#api-usage-tab)
- [Informacje](#about-tab)
- [Ogólne](#general-tab)

> [!div class="mx-imgBorder"]
> ![Strona systemowa.](media/system-tabs.png "Strona systemowa")

## <a name="status-tab"></a>Karta Stan

Na **Karta Stan** można śledzić postęp przetwarzania danych, eksportowania danych i wielu innych ważnych procesów produktu. Przejrzyj informacje na tej karcie, aby zapewnić kompletność aktywnych procesów.

Ta karta zawiera tabele ze statusem i informacjami o przetwarzaniu dla różnych procesów. Każda tabela śledzi **Nazwę** zadania, odpowiadającą mu encję, **Stan** ostatniego uruchomienia oraz datę **Ostatniej aktualizacji**.

Wyświetl szczegółowe informacje na temat kilku ostatnich uruchomień zadania wybierajac jego nazwę.

### <a name="status-types"></a>Typy stanu

Istnieje sześć typów stanu zadań. Poniższe typy stanów są również widoczne na stronach *Dopasuj*, *Scal*, *Źródła danych*, *Segmenty*, *Miary*, *Wzbogacenie*, *Działania* i *Przewidywania*:

- **Przetwarzanie:** Zadanie jest w toku. Stan może zmienić się na Powodzenie lub Niepowodzenie.
- **Powodzenie:** Zadanie zostało ukończone pomyślnie.
- **Pominięto:** Zadanie zostało pominięte. Co najmniej jeden z procesów podrzędnych, od którego zależy to zadanie, zakończył się niepowodzeniem lub został pominięty.
- **Niepowodzenie:** Przetwarzanie zadania nie powiodło się.
- **Anulowano:** Przetwarzanie zostało anulowane przez użytkownika przed jego zakończeniem.
- **Kolejka**: przetwarzanie jest ustawiane w kolejce i rozpoczyna się po zakończeniu wszystkich zadań. Aby uzyskać więcej informacji, zobacz [Zasady odświeżania](#refresh-policies).

### <a name="refresh-policies"></a>Zasady odświeżania

Ta lista przedstawia zasady odświeżania dla każdego z głównych procesów:

- **Źródła danych:** Działają zgodnie ze [skonfigurowanym harmonogramem](#schedule-tab). Nie jest uzależniony od innych procesów. Dopasowanie zależy od pomyślnego zakończenia tego procesu.
- **Dopasowanie:** Działa zgodnie ze [skonfigurowanym harmonogramem](#schedule-tab). Zależy od sposobu przetwarzania źródeł danych użytych w definicji dopasowania. Scalanie zależy od pomyślnego zakończenia tego procesu.
- **Scalanie:** Działa zgodnie ze [skonfigurowanym harmonogramem](#schedule-tab). Zależy od pomyślnego zakończenia tego procesu dopasowywania. Segmenty, miary, wzbogacenia, wyszukiwania, działania, przewidywania i przygotowanie danych zależą od pomyślnego zakończenia procesu.
- **Segmenty**: Ręczne uruchamiane (jednorazowe odświeżanie) i zgodnie ze [skonfigurowanym harmonogramem](#schedule-tab). Zależy od procesu Scalanie. Wyniki analiz od jego przetwarzania.
- **Miary**: Ręczne uruchamiane (jednorazowe odświeżanie) i zgodnie ze [skonfigurowanym harmonogramem](#schedule-tab). Zależy od procesu Scalanie.
- **Działania**: Ręczne uruchamiane (jednorazowe odświeżanie) i zgodnie ze [skonfigurowanym harmonogramem](#schedule-tab). Zależy od procesu Scalanie.
- **Wzbogacanie**: Ręczne uruchamiane (jednorazowe odświeżanie) i zgodnie ze [skonfigurowanym harmonogramem](#schedule-tab). Zależy od procesu Scalanie.
- **Wyszukaj**: Ręczne uruchamiane (jednorazowe odświeżanie) i zgodnie ze [skonfigurowanym harmonogramem](#schedule-tab). Zależy od procesu Scalanie.
- **Przygotowanie danych:** Działa zgodnie ze [skonfigurowanym harmonogramem](#schedule-tab). Zależy od procesu Scalanie.
- **Wyniki analiz**: Ręczne uruchamiane (jednorazowe odświeżanie) i zgodnie ze [skonfigurowanym harmonogramem](#schedule-tab). Zależy od segmentów.

Wybierz stan zadania, aby zobaczyć szczegółowe informacje o postępie w całego zadania. Powyższe zasady odświeżenia mogą pomóc w zrozumieniu, które można zrobić, aby zająć się zadaniem **Pominięte** lub **W kolejce**.

## <a name="schedule-tab"></a>Karta Harmonogram

Użyj karty **Harmonogram**, aby zaplanować automatyczne odświeżanie wszystkich [źródeł pobieranych danych](data-sources.md). Automatyczne odświeżanie ułatwia zagwarantowanie, że aktualizacje ze źródeł danych będą odzwierciedlone w ujednoliconych profilach klientów.

1. W analizach odbiorców wybierz **Administrator** > **System** i wybierz kartę **Harmonogram**.

2. Stan domyślny dla planowanego odświeżenia to **Wyłączony**. Aby włączyć zaplanowane odświeżanie, należy zmienić przełącznik na górze ekranu na opcję **Włączony**.

3. Należy wybrać kolejno pozycje **Co tydzień** (domyślne) i **Codziennie** odświeżanie. Jeśli zamierzasz zaplanować cotygodniowe odświeżenie, wybierz jeden lub kilka dni, kiedy chcesz uruchomić odświeżanie.

4. Ustaw **Strefę czasową**, a następnie użyj listy rozwijanej **Czas**, aby ustawić czas odświeżania. Kiedy skończysz, wybierz **Ustaw**. Jeśli chcesz zaplanować wiele odświeżań w ciągu jednego dnia, wybierz opcję **Dodaj inną godzinę**.

5. Wybierz pozycję **Zapisz**, aby zastosować zmiany.

## <a name="about-tab"></a>Karta Informacje

Karta **Informacje** zawiera **Wyświetlaną nazwę** organizacji, aktywny **Identyfikator środowiska**, **Region** i **Identyfikator sesji**. Jeśli masz więcej niż jedno środowisko pracy, powinieneś nadać każdemu łatwą do zidentyfikowania nazwę wyświetlaną.

## <a name="general-tab"></a>Karta Ogólne

Na karcie **Ogólne** są dostępne dwie opcje, **Język** i **Format kraju/regionu**.

Aplikacja [obsługuje szereg języków](supported-languages.md). Aby zmienić preferowany język, wybierz **Język** z listy rozwijanej.

Aby zmienić preferowany format dat, godzin i liczb, użyj listy rozwijanej **Format kraju/regionu**. W obszarze tego pola jest wyświetlany podgląd formatowania. System automatycznie zasugeruje wybór, gdy wybierzesz nowy język.

Kliknij przycisk **Zapisz** i potwierdź wybór.

## <a name="api-usage-tab"></a>Karta użycia interfejsu API

Znajdź szczegółowe informacje na temat wykorzystania interfejsu API w czasie rzeczywistym i zobacz, które zdarzenia miały miejsce w danym przedziale czasowym. Wybierz przedział czasowy w menu rozwijanym **Wybierz przedział czasowy**. 

**Użycie interfejsu API** zawiera trzy sekcje: 
- **Wywołania interfejsu API** — wykres, który wizualizuje zagregowaną liczbę wywołań interfejsu API w wybranym przedziale czasu.

- **Transfer danych** — wykres przedstawiający ilość danych przesłanych przez interfejs API w wybranym okresie.

-  **Operacje** — tabelę z wierszami dla każdej dostępnej operacji API i szczegółami użycia tych operacji. Możesz wybrać nazwę operacji, aby przejść do odwołania [do interfejsu API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Operacje korzystające z [pozyskiwania danych w czasie rzeczywistym](real-time-data-ingestion.md) zawierają przycisk z symbolem lornetki do wyświetlania użycia interfejsu API w czasie rzeczywistym. Wybierz przycisk, aby otworzyć panel boczny zawierający szczegóły użycia interfejsu API w czasie rzeczywistym w bieżącym środowisku.   
   Pole **Grupuj według** w okienku **Użycia interfejsu API w czasie rzeczywistym** umożliwia wybranie sposobu najlepszego prezentowania interakcji w czasie rzeczywistym. Dane można pogrupować według metody interfejsu API, kwalifikowanej nazwy encji (pobranej encji), utworzone przez (źródło zdarzenia), wyniku (powodzenie lub niepowodzenie) lub kodów błędów. Dane są dostępne jako wykres chronologiczny i jako tabela.


[!INCLUDE[footer-include](../includes/footer-banner.md)]