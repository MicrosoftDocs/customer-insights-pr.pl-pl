---
title: Konfiguracja systemu w statystykach odbiorców
description: Dowiedz się o ustawieniach systemu w możliwości analiz odbiorców w Dynamics 365 Customer Insights.
ms.date: 06/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: 7dd72e6512cd87ac70235d21667399298408db21
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406592"
---
# <a name="system-configuration"></a>Konfiguracja systemu

Strona **System** zawiera cztery karty: **Stan**, **Harmonogram**, **Informacje** i **Ogólne**.

> [!div class="mx-imgBorder"]
> ![Strona systemowa](media/system-tabs.png "Strona systemowa")

## <a name="status-tab"></a>Karta Stan

**Karta Stan** umożliwia śledzenie postępu przyjmowania danych, eksportu danych, i kilka ważnych procesów produktu. Przejrzyj informacje na tej karcie, aby zapewnić kompletność aktywnych procesów.

Na tej karcie są zawarte tabele stanu dla **Źródeł danych**, **Procesów systemowych** i **Przygotowywania danych**. Każda tabela śledzi **Nazwę** zadania, odpowiadającą mu encję, **Stan** ostatniego uruchomienia oraz datę **Ostatniej aktualizacji**.

Wyświetl szczegółowe informacje na temat kilku ostatnich uruchomień zadania wybierajac jego nazwę.

### <a name="status-types"></a>Typy stanu

Istnieje sześć typów stanu zadań. Poniższe typy stanów są również widoczne na stronach *Dopasuj*, *Scal*, *Źródła danych*, *Segmenty*, *Miary*, *Wzbogacenie*, *Działania* i *Przewidywania*:

- **Przetwarzanie:** Zadanie jest w toku. Stan może zmienić się na Powodzenie lub Niepowodzenie.
- **Powodzenie:** Zadanie zostało ukończone pomyślnie.
- **Pominięto:** Zadanie zostało pominięte. Co najmniej jeden z procesów podrzędnych, od którego zależy to zadanie, zakończył się niepowodzeniem lub został pominięty.
- **Niepowodzenie:** Przetwarzanie zadania nie powiodło się.
- **Anulowano:** Przetwarzanie zostało anulowane przez użytkownika przed jego zakończeniem.
- **W kolejce:** Przetwarzanie jest kolejkowane i uruchomi się po zakończeniu wszystkich zadań podrzędnych. Aby uzyskać więcej informacji, zobacz [Zasady odświeżania](#refresh-policies).

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

Zapoznaj się ze szczegółowymi informacjami o wykorzystaniu interfejsów API w czasie rzeczywistym i zobacz, jakie zdarzenia wystąpiły w danym zakresie czasu. Aby uzyskać więcej informacji, zobacz [Pozyskiwanie danych w czasie rzeczywistym](real-time-data-ingestion.md).
