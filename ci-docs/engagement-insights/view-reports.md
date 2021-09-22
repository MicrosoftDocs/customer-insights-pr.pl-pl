---
title: Wyświetl tabelę danych
description: Użyj dostępnych raportów, aby zobaczyć aktywność w czasie rzeczywistym na swojej stronie.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 06/18/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: cb6d9ab75b95a5f677d2267f5412a55327930987b2fc3a1a21958633a8116bd2
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036661"
---
# <a name="view-reports"></a>Wyświetl raporty

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Raport jest zbiorem wizualizacji danych, wykorzystujących dane zebrane za pomocą SDK, które pomagają zmierzyć i zrozumieć zachowanie użytkowników. Szczegółowe informacje na temat interakcji w Dynamics 365 Customer Insights obejmują obecnie raporty typu raporty out-of-the-box (OOB) dla projektów internetowych i mobilnych.  

## <a name="web-reports"></a>Raporty sieciowe

Dostęp do raportów sieci Web można uzyskać w obszarze **Poznaj** w lewym okienku nawigacji.

:::image type="content" source="media/report-menu.png" alt-text="Nawigacja po wyświetlaniu listy dostępnych raportów.":::

### <a name="real-time-usage-report"></a>Raport użycia w czasie rzeczywistym

**Raport użycia w czasie rzeczywistym** udostępnia omówienie bieżącego działania w witrynie, które automatycznie odświeża się co minutę. Używaj funkcji w czasie rzeczywistym do monitorowania wpływu kampanii marketingowych, wydarzeń i innych scenariuszy na ruch witryny.

### <a name="key-metrics-reports"></a>Raporty dot. kluczowych metryk

- **Wyświetlenia strony** zestawienie odsłon dla poszczególnych stron wraz z liczbą całkowitych odsłon w wybranym przedziale czasowym.

- **Wizyty** pokazują informacje o liczbie wizyt i czasie trwania wizyty.

- **Goście** informuje o nowych i powracających unikalnych odwiedzających Twoją stronę.

### <a name="content-reports"></a>Raporty dot. treści

- **W łączach** są wyświetlane informacje o liczbie i typie kliknięć.

- Na **stronach wyjściowych** są listy łączy, które goście kliknęli, aby zakończyć pracę z witryną.

### <a name="traffic-sources-reports"></a>Raporty — źródła ruchu

- **Odnośniki** to lista domen i adresów URL, które skierowały odwiedzających do Twojej witryny.

- **Kody śledzenia** zawierają szczegółowe informacje o kodach śledzenia w łączach, które wprowadziły gości do witryny.

### <a name="visitor-profiles-reports"></a>Raporty o profilach użytkowników

- **Urządzenia** to lista urządzeń fizycznych, które zostały użyte do uzyskiwania dostępu do Twojej witryny.

- **Systemy operacyjne i przeglądarki** zapewniają wgląd w systemy operacyjne i przeglądarki uruchomione w czasie uzyskiwania dostępu do witryny.

- **Lokalizacje** pokazują informacje o gościach według kraju, regionu i miasta.

- **Języki** są widokami strony listy według preferowanych języków użytkownika.

## <a name="mobile-reports"></a>Raporty dla urządzeń przenośnych

Raporty mobilne są pogrupowane w kategoriach użytkowania w czasie rzeczywistym, aplikacji i użytkowników. Dostęp do raportów dot. urządzeń przenośnych można uzyskać w obszarze **Poznaj** w lewym okienku nawigacji.   

:::image type="content" source="media/mobile-reports.png" alt-text="Interfejs użytkownika analizy interakcji prezentujący raport użycia w czasie rzeczywistym, który wyświetla dane w postaci wykresów i zestawień.":::   

### <a name="real-time-usage"></a>Użycie w czasie rzeczywistym

**Użycie w czasie rzeczywistym** umożliwia sprawdzenie bieżącego działania w aplikacji mobilnej, które automatycznie odświeża się co minutę. Wykorzystaj wykorzystanie w czasie rzeczywistym do monitorowania liczby użytkowników i sesji aktualnie aktywnych w Twojej aplikacji oraz widoków najpopularniejszych ekranów.

### <a name="app-reports"></a>Raporty aplikacji

- **Wyświetlenia ekranu** to lista wyświetleń ekranu dla poszczególnych ekranów w aplikacji oraz całkowita liczba wyświetleń ekranu w wybranym przedziale czasowym. Wyświetlenia ekranu może analizować według nazwy ekranu lub tytułu ekranu.

- **Sesje** pokazują informacje o liczbie sesji i ich czasie trwania.

- **Częstotliwość powrotów** grupuje zliczenia sesji według liczby dni, które upłynęły od ostatniej sesji.

- **Użytkownicy** pokazuje nowych i powracających użytkowników w aplikacji mobilnej.

- **Wydarzenia** pokazuje sumowane wszystkie zdarzenia zebrane w aplikacji oraz łączną liczbę wszystkich zdarzeń.

### <a name="user-reports"></a>Raporty użytkowników

- **Wersje aplikacji** to lista wersji aplikacji mobilnej, która jest używana przez użytkowników.

- **Wersje urządzeń i systemu operacyjnego** zapewniają wgląd w to, które urządzenia i systemy operacyjne działają na aplikacji mobilnej.

- **Lokalizacje** pokazują informacje o użytkownikach aplikacji według kraju, regionu i miasta.

## <a name="filter-by-time-or-value"></a>Filtrowanie według czasu lub wartości

Można wybrać przedział czasowy lub wartość w raporcie internetowym lub mobilnym, aby skupić się na wartości lub przedziale czasowym. 

- Aby wybrać horyzont czasowy w celu wybrania opcji **Więcej [...]** z listy rozwijanej raportu. Wybór zakresu czasu jest wyłączony w raporcie użycia w czasie rzeczywistym. Zakres czasu dla raportu użycia w czasie rzeczywistym to „tu i teraz”.

- W większości raportów wybierz wartość na wykresie lub liście w celu odfiltrowania raportu dla wybranej wartości.

[!INCLUDE[footer-include](../includes/footer-banner.md)]