---
title: Wyświetl konfigurację systemu
description: Informacje o ustawieniach systemu w Dynamics 365 Customer Insights.
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 6e60bf7c18939a29f660e06989e262deeb59a39b
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2022
ms.locfileid: "9396014"
---
# <a name="view-system-configuration"></a>Wyświetl konfigurację systemu

Wyświetlanie informacji systemowych, stanu systemu i użycia interfejsów API.

## <a name="view-api-usage"></a>Wyświetl użycie interfejsu API

Wyświetl szczegółowe informacje na temat wykorzystania interfejsu API w czasie rzeczywistym i zobacz, które zdarzenia miały miejsce w danym przedziale czasowym.

1. Przejdź do pozycji **Administracja** > **System** i wybierz kartę **Użycie interfejsu API**.

1. **Wybierz horyzont czasowy** do wyświetlenia.

   Strona **Użycie interfejsu API** zawiera trzy sekcje:

   - **Wywołania interfejsu API** — wykres, który wizualizuje zagregowaną liczbę wywołań interfejsu API w wybranym przedziale czasu.
   - **Transfer danych** — wykres przedstawiający ilość danych przesłanych przez interfejs API w wybranym okresie.
   - **Operacje** — tabelę z wierszami dla każdej dostępnej operacji API i szczegółami użycia tych operacji. Wybierz nazwę operacji, aby przejść do odwołania [do interfejsu API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

## <a name="view-system-information"></a>Wyświetl informacje o systemie

Wyświetl nazwę wyświetlaną środowiska, identyfikator, region i identyfikator sesji.

1. Przejdź do pozycji **Administracja** > **System** i wybierz kartę **O programie**.

1. Aby wyświetlić język i kraj/region, wybierz kartę **Ogólne**.

### <a name="update-preferred-language-or-countryregion"></a>Zaktualizuj preferowany język lub kraj/region

Aplikacja Customer Insights [obsługuje wiele języków](/dynamics365/get-started/availability). Aplikacja wykorzystuje preferencje językowe do wyświetlania elementów, takich jak menu, tekst etykiety i komunikaty systemowe w preferowanym języku.

Zaimportowane dane i informacje wprowadzone ręcznie nie są przetłumaczone.

1. Przejdź do pozycji **Administracja** > **System** i wybierz kartę **Ogólne**.

1. Aby zmienić preferowany język, wybierz **Język** z listy rozwijanej.

1. Aby zmienić preferowany format dat, godzin i liczb, użyj listy rozwijanej **Format kraju/regionu**. Zostanie wyświetlony podgląd formatowania. System automatycznie sugeruje wybór, gdy wybierzesz nowy język.

1. Wybierz pozycję **Zapisz**.

## <a name="view-system-status"></a>Wyświetl stan systemowy

Śledź postęp zadań, pozyskiwanie danych, eksportowanie danych i kilka innych ważnych procesów produktu. Przejrzyj informacje, aby zapewnić pełne wykonywanie aktywnych zadań i procesów.

1. Przejdź do pozycji **Administracja** > **System** i wybierz kartę **Stan**.

   Wyświetlanie stanu i informacji o przetwarzaniu dla różnych procesów. Wyświetl **Nazwę** zadania, **Stan** ostatniego uruchomienia oraz datę **Ostatniej aktualizacji**.

1. Aby wyświetlić szczegółowe informacje dotyczące ostatnich uruchomionych zadań, wybierz nazwę zadania lub procesu.

1. Aby wyświetlić postęp szczegółów dla zadania, wybierz stan. Zostanie wyświetlony panel **Szczegóły postępu**.

   :::image type="content" source="media/system-progress-details.png" alt-text="Okienko szczegółów postępu systemu":::

1. Aby wyświetlić szczegóły postępu dla wszystkich zadań, zaznacz opcję **Cały przepływ pracy**.

### <a name="status-definitions"></a>Definicje stanów

W przypadku zadań i procesów system używa następujących stanów:

|Status  |Definicja  |
|---------|---------|
|Anulowane |Zadanie lub proces zostały anulowane przez użytkownika przed ich zakończeniem.   |
|Zakończone niepowodzeniem   |Zadanie lub proces natrafiły na błędy.         |
|Błąd  |Zadanie lub proces zakończył się niepowodzeniem.  |
|Nie rozpoczęto   |Źródło danych nie ma jeszcze pozyskanych danych lub zadanie nadal jest w trybie roboczym.         |
|Trwa przetwarzanie  |Zadanie lub proces jest w toku.  |
|Odświeżanie    |Zadanie lub proces jest w toku. Aby anulować tę operację, wybierz opcję **Odświeżanie** i **Anulowanie zadania**. Zatrzymanie odświeżania zadania lub procesu spowoduje przywrócenie jego ostatniego stanu odświeżania.       |
|Pominięty  |Zadanie lub proces został pominięty. Co najmniej jeden z procesów podrzędnych, od którego zależy to zadanie, zakończył się niepowodzeniem lub został pominięty.|
|Zakończone powodzeniem  |Zadanie lub proces zostało zakończony pomyślnie. W przypadku źródeł danych oznacza, że dane zostały pomyślnie pozyskane, jeśli w kolumnie **Odświeżono** zostanie podana godzina.|
|W kolejce | Przetwarzanie znajduje się w kolejce i rozpocznie się po zakończeniu wszystkich zadań i procesów. Aby uzyskać więcej informacji zobacz temat [Odświeżanie procesów](#refresh-processes).|

### <a name="refresh-processes"></a>Odświeżanie procesów

Odświeżanie zadań i procesów jest wykonywane zgodnie ze [skonfigurowanym harmonogramem](schedule-refresh.md).

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


[!INCLUDE [footer-include](includes/footer-banner.md)]
