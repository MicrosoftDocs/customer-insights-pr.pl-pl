---
title: Integruj dane sieci Web dzięki wglądowi w dane dotyczące odbiorcy klientów
description: Przenieś informacje internetowe o klientach, od statystyk zaangażowania do statystyk odbiorców.
ms.date: 12/17/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 14ebff30d3ec7fc52dca6f86136309a3f454fa27
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597478"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Integruj dane sieci Web dzięki wglądowi w dane dotyczące odbiorcy klientów

Klienci często dokonują codziennych transakcji online za pośrednictwem witryn internetowych. Funkcja analizy zaangażowania w Dynamics 365 Customer Insights to poręczne rozwiązanie do integracji danych internetowych jako źródła. Oprócz danych transakcyjnych, demograficznych lub behawioralnych możemy zobaczyć działania w Internecie w ujednoliconych profilach klientów. Możemy użyć tego profilu, aby uzyskać dodatkowe informacje, takie jak segmenty, miary lub prognozy dotyczące aktywacji odbiorców.

W tym artykule opisano, jak przenieść dane o aktywności internetowej klientów ze statystyk zaangażowania do istniejącego środowiska statystyk odbiorców.

W tym przykładzie zakładamy, że środowisko zawiera ujednolicone profile klientów. Profile zostały ujednolicone ze źródłami z ankiet, sprzedaży detalicznej i systemu biletowego. Prezentujemy w nim również działania pokrewne klientów. 

Chcemy teraz wiedzieć, czy klient odwiedza nasze usługi internetowe i rozumie ich działania. Działania obejmują na przykład odwiedzane witryny internetowe lub przeglądane strony produktów za pośrednictwem łącza otrzymanego w wiadomości e-mail.

## <a name="prerequisites"></a>Wymagania wstępne

Aby zintegrować dane ze wglądu w dane dotyczące zobowiązania, należy spełnić kilka wymagań wstępnych: 

- Zintegruj zestaw SDK rozwiązania informacji o zaangazowaniu z witryną sieci Web. Więcej informacji znajduje się w temacie [Rozpoczęcie pracy z SDK](../engagement-insights/instrument-website.md).
- Eksportowanie zdarzeń sieci Web z informacji o zaangażowaniu wymaga dostępu do konta magazynu ADLS Gen 2, które będzie używane do pozyskiwania danych zdarzeń sieci Web do wglądu w odbiorców. Aby uzyskać więcej informacji, zobacz [Eksportowanie zdarzeń](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Konfigurowanie zdarzeń niepożądanych w wglądu w dane dotyczące zobowiązania

Po tym, jak administrator oprzyrządował witrynę internetową za pomocą pakietu informacji o zaangażowaniu SDK, *podstawowe zdarzenia* są gromadzone, gdy użytkownik wyświetli stronę internetową lub gdzieś kliknie. Zdarzenia podstawowe, które mają zawierać wiele szczegółów. W zależności od przypadku użycia potrzebujesz tylko podzbioru danych w zdarzeniu podstawowym. Wgląd w zaangażowanie umożliwia tworzenie *dopracowanych zdarzeń*, które zawierają tylko właściwości wybranego zdarzenia podstawowego.     

Aby uzyskać więcej informacji, zobacz temat [Tworzenie i modyfikowanie zdarzeń modyfikujących](../engagement-insights/refined-events.md).

Rozważania podczas tworzenia zdarzeń dopracowanych: 

- Należy podać znaczącą nazwę zdarzenia dopracowanego. Jest używane jako nazwa aktywności w statystykach odbiorców.
- Wybierz co najmniej następujące właściwości, aby utworzyć działanie w statystykach odbiorców: 
    - Signal.Action.Name — wskazując szczegóły działania
    - Signal.User.Id — służy do mapowania z identyfikatorem klienta
    - Strona.Widok.Uri — używany jako adres sieci Web jako podstawa dla segmentów lub działań
    - Signal.Export.Id — do użycia jako klucz podstawowy dla zdarzeń <!-- system generated, do we need to list?-->
    - Zdjęcia.Timestamp — do ustalenia daty i godzin działania

Wybierz filtry, aby skupić się na zdarzeniach i stronach, które mają znaczenie dla Twojego przypadku użycia. W tym przykładzie użyjemy nazwy akcji „Promocja e-mailowa”.

## <a name="export-the-refined-web-events"></a>Eksportowanie dopracowanych zdarzeń sieci Web 

Po zdefiniowaniu doprecyzowanego zdarzenia należy skonfigurować eksport danych zdarzenia do Azure Data Lake Storage, które można ustawić jako źródło danych do pozyskiwania w szczegółowych informacjach o odbiorcach. Eksport odbywa się stale w miarę przepływu zdarzeń z usługi internetowej.

Aby uzyskać więcej informacji, zobacz [Eksportowanie zdarzeń](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Przetwarzaj dane o wydarzeniach do statystyk odbiorców

Po zdefiniowaniu dopracowanego zdarzenia i skonfigurowaniu jego eksportu przechodzimy do pozyskiwania danych do statystyk odbiorców. Musisz utworzyć nowe źródło danych w oparciu o folder Common Data Model. Wprowadź szczegóły konta magazynu, do którego eksportujesz zdarzenia. W pliku *default.cdm.json* wybierz doprecyzowane zdarzenie do przetworzenia i utwórz jednostkę w statystykach odbiorców.

Aby uzyskać więcej informacji, zobacz temat [Łączenie się z folderem Common Data Model przy użyciu konta Azure Data Lake](connect-common-data-model.md)


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Powiąż dopracowane dane zdarzeń jako aktywność profilu klienta

Po zakończeniu pozyskiwania encji można skonfigurować działanie dla profilu klienta.

Aby uzyskać więcej informacji, zobacz [Działania klientów](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Strona działań z rozszerzonym panelem edycji czynności i wypełnionymi polami.":::

Skonfiguruj nowe działanie z następującym mapowaniem: 

- **Klucz podstawowy:** Signal.Export.Id, unikalny identyfikator, który jest dostępny dla każdego rekordu zdarzenia w analizie zaangażowania. Ta właściwość jest generowana automatycznie.

- **Sygnatura czasowa:** Signal.Timestamp we właściwości wydarzenia.

- **Zdarzenie:** Signal.Name, nazwa zdarzenia, które chcesz śledzić.

- **Adres sieci Web:** Signal.View.Uri odwołujący się do adresu URL strony, która utworzyła zdarzenie.

- **Szczegóły:** Signal.Action.Name do reprezentowania informacji do skojarzenia ze zdarzeniem. Wybrana właściwość w tym przypadku wskazuje, że wydarzenie jest przeznaczone do promocji e-mailowej.

- **Typ działania:** W tym przykładzie wybieramy istniejący typ aktywności WebLog. Ten wybór jest przydatną opcją filtru do uruchamiania modeli prognozowania lub tworzenia segmentów w oparciu o ten typ aktywności.

- **Konfigurowanie relacji:** To ważne ustawienie wiąże aktywność z istniejącymi profilami klientów. **Signal.User.Id** to identyfikator skonfigurowany w pakiecie SDK do zbierania, który odnosi się do identyfikatora użytkownika w innych źródłach danych, które są skonfigurowane w statystykach odbiorców. W tym przykładzie konfigurujemy relację między Signal.User.Id i RetailCustomers: CustomerRetailId, który jest kluczem podstawowym zdezynfekowanym na etapie mapowania w procesie ujednolicania danych.


Po przetworzeniu działań można przejrzeć rekordy klientów i otworzyć kartę klienta, aby zobaczyć działania z informacji o zaangażowaniu na osi czasu. 

> [!TIP]
> Aby znaleźć identyfikator klienta, który ma aktywność wglądu w zaangażowanie, przejdź do **Encje** i wyświetl podgląd danych dla jednostki UnifiedActivity. ActivityTypeDisplay = WebLog zawiera informacje o zaangażowaniu skonfigurowane w powyższym przykładzie. Skopiuj identyfikator klienta dla jednego z tych rekordów i dla tego identyfikatora na stronie **Klienci**.

## <a name="next-steps"></a>Następne kroki

Teraz można tworzyć [segmenty](segments.md), [miary](measures.md) i [przewidywania](predictions.md), aby utworzyć istotne połączenie z klientami.


[!INCLUDE[footer-include](../includes/footer-banner.md)]