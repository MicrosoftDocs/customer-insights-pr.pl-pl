---
title: Integruj dane sieci Web dzięki wglądowi w dane dotyczące odbiorcy klientów
description: Przenieś informacje internetowe o klientach, od statystyk zaangażowania do statystyk odbiorców.
ms.date: 06/24/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 76a53a897e90152707a7c1255ed5ed93a5f3b5a0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305031"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Integruj dane sieci Web dzięki wglądowi w dane dotyczące odbiorcy klientów

Klienci często dokonują codziennych transakcji online za pośrednictwem witryn internetowych. Funkcja analizy zaangażowania (wersja zapoznawcza) w Dynamics 365 Customer Insights jest poręcznym rozwiązaniem umożliwiającym integrację danych internetowych jako źródła. Oprócz danych transakcyjnych, demograficznych lub behawioralnych możemy zobaczyć działania w Internecie w ujednoliconych profilach klientów. Możemy wykorzystać te profile do uzyskania dodatkowych analiz, takich jak segmenty, miary czy przewidywania dotyczące aktywacji odbiorców.

W tym artykule opisano, jak przenieść dane o aktywności internetowej klientów ze statystyk zaangażowania do istniejącego środowiska statystyk odbiorców.

W tym przykładzie zakładamy, że środowisko zawiera ujednolicone profile klientów. Profile zostały ujednolicone ze źródłami z ankiet, sprzedaży detalicznej i systemu biletowego. Prezentujemy w nim również działania pokrewne klientów. 

Chcemy teraz wiedzieć, czy klient odwiedza nasze usługi internetowe i rozumie ich działania. Działania obejmują na przykład odwiedzane witryny internetowe lub przeglądane strony produktów za pośrednictwem łącza otrzymanego w wiadomości e-mail.

## <a name="prerequisites"></a>Wymagania wstępne

Aby zintegrować dane ze wglądu w dane dotyczące zobowiązania, należy spełnić kilka wymagań wstępnych: 

- Zintegruj zestaw SDK rozwiązania informacji o zaangazowaniu z witryną sieci Web. Aby uzyskać więcej informacji, zobacz [Podstawowe informacje o zasobach dla deweloperów](../engagement-insights/developer-resources.md).
- Eksportowanie zdarzeń sieci Web z danych analizy zaangażowania wymaga dostępu do konta Azure Data Lake Storage, które będzie wykorzystywane do pozyskiwania danych o zdarzeniach internetowych do analizy. Aby uzyskać więcej informacji, zobacz [Eksportowanie zdarzeń](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Konfigurowanie zdarzeń niepożądanych w wglądu w dane dotyczące zobowiązania

Po wprowadzeniu przez administratora instrumentów na stronie internetowej za pomocą SDK analizy zaangażowania, *zdarzenia bazowe* są zbierane, gdy użytkownik ogląda stronę lub klika w jakieś miejsce. Zdarzenia podstawowe, które mają zawierać wiele szczegółów. W zależności od przypadku użycia potrzebujesz tylko podzbioru danych w zdarzeniu podstawowym. Wgląd w zaangażowanie umożliwia tworzenie *dopracowanych zdarzeń*, które zawierają tylko właściwości wybranego zdarzenia podstawowego.     

Aby uzyskać więcej informacji, zobacz temat [Tworzenie i modyfikowanie zdarzeń modyfikujących](../engagement-insights/refined-events.md).

Rozważania podczas tworzenia zdarzeń dopracowanych: 

- Należy podać znaczącą nazwę zdarzenia dopracowanego. Będzie to używane jako nazwa działania dla analizy odbiorców.
- Wybierz co najmniej następujące właściwości, aby utworzyć działanie w statystykach odbiorców: 
    - Signal.Action.Name — wskazuje szczegóły działania.
    - Signal.User.Id — służy do mapowania z identyfikatorem klienta.
    - Strona.Widok.Uri — używany jako adres sieci Web jako podstawa dla segmentów lub działań.
    - Signal.Export.Id — używany jako klucz podstawowy zdarzeń.
    - Signal.Timestamp — pokazuje daty i godziny działania.

Wybierz filtry, aby skupić się na zdarzeniach i stronach, które mają znaczenie dla Twojego przypadku użycia. W tym przykładzie użyjemy nazwy akcji „Promocja e-mailowa”.

## <a name="export-the-refined-web-events"></a>Eksportuj dopracowane zdarzenia sieciowe 

Po zdefiniowaniu doprecyzowanego zdarzenia należy skonfigurować eksport danych zdarzenia do Azure Data Lake Storage, który może być ustawiony jako źródło danych dla pozyskiwania danych w ramach analizy odbiorców. Eksport odbywa się stale w miarę przepływu zdarzeń z usługi internetowej.

Aby uzyskać więcej informacji, zobacz [Eksportowanie zdarzeń](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Przetwarzaj dane o wydarzeniach do statystyk odbiorców

Po zdefiniowaniu dopracowanego zdarzenia i skonfigurowaniu jego eksportu przechodzimy do pozyskiwania danych do statystyk odbiorców. Musisz utworzyć nowe źródło danych w oparciu o folder Common Data Model. Wprowadź szczegóły konta magazynu, do którego eksportujesz zdarzenia. W pliku *default.cdm.json* wybierz doprecyzowane zdarzenie do przetworzenia i utwórz jednostkę w statystykach odbiorców.

Aby uzyskać więcej informacji, zobacz temat [Łączenie się z folderem Common Data Model przy użyciu konta Azure Data Lake](connect-common-data-model.md).


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Powiąż dopracowane dane zdarzeń jako aktywność profilu klienta

Po zakończeniu pozyskiwania encji można skonfigurować działanie dla profilu klienta.

Aby uzyskać więcej informacji, zobacz [Działania klientów](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Strona działań z rozszerzonym panelem edycji czynności i wypełnionymi polami.":::

Skonfiguruj nowe działanie z następującym mapowaniem: 

- **Klucz podstawowy**: Signal.Export.Id, unikalny identyfikator, który jest dostępny dla każdego rekordu zdarzenia w analizie zaangażowania. Ta właściwość jest generowana automatycznie.

- **Sygnatura czasowa**: Signal.Timestamp we właściwości wydarzenia.

- **Zdarzenie**: Signal.Name, nazwa zdarzenia, które chcesz śledzić.

- **Adres sieciowy**: Signal.View.Uri odwołujące się do adresu URI strony, która utworzyła zdarzenie.

- **Szczegóły**: Signal.Action.Name do reprezentowania informacji do skojarzenia ze zdarzeniem. Wybrana właściwość w tym przypadku wskazuje, że wydarzenie jest przeznaczone do promocji e-mailowej.

- **Typ działania**: w tym przykładzie wybieramy istniejący typ działania WebLog. Ten wybór jest przydatną opcją filtru do uruchamiania modeli prognozowania lub tworzenia segmentów w oparciu o ten typ aktywności.

- **Konfigurowanie relacji**: To ważne ustawienie wiąże aktywność z istniejącymi profilami klientów. **Signal.User.Id** to identyfikator skonfigurowany w pakiecie SDK do zbierania, który odnosi się do identyfikatora użytkownika w innych źródłach danych, które są skonfigurowane w statystykach odbiorców. W tym przykładzie konfigurujemy relację pomiędzy Signal.User.Id a RetailCustomers:CustomerRetailId, która jest kluczem głównym, który został zidentyfikowany w kroku mapowania procesu unifikacji danych.

Po przetworzeniu działań można przejrzeć rekordy klientów i otworzyć kartę klienta, aby zobaczyć działania z informacji o zaangażowaniu na osi czasu. 

> [!TIP]
> Aby znaleźć identyfikator klienta, który ma aktywność wglądu w zaangażowanie, przejdź do **Encje** i wyświetl podgląd danych dla jednostki UnifiedActivity. ActivityTypeDisplay = Plik WebLog zawiera działanie funkcji analiza zaangażowania skonfigurowanej w powyższej przykładzie. Skopiuj identyfikator klienta dla jednego z tych rekordów i dla tego identyfikatora na stronie **Klienci**.

## <a name="next-steps"></a>Następne kroki

Teraz można tworzyć [segmenty](segments.md), [miary](measures.md) i [przewidywania](predictions.md), aby utworzyć istotne połączenie z klientami.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
