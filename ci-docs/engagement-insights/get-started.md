---
title: Wprowadzenie do funkcji obsługi funkcji analizy interakcji
description: Przegląd zasobów pomocy w celu szybkiego rozpoczęcia pracy.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: c435810e712bbbf69f8f1cfb582fc0a971566de6
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225611"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Wprowadzenie do funkcji obsługi funkcji analizy interakcji w Dynamics 365 Customer Insights (wersja zapoznawcza)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Obsługa funkcji analizy interakcji umożliwia zbieranie i analizę zachowań klientów w witrynie sieci Web. Integruje się ona z funkcją analizy odbiorców, dzięki czemu oprócz raportów o profilu klienta można zobaczyć bogate analizy behawioralne w czasie rzeczywistym. Łącza określone w tym artykule ułatwiają szybkie skonfigurowanie i wdrożenie środowiska.

## <a name="step-1-review-prerequisites"></a>Krok 1: Przejrzyj wymagania wstępne

Najpierw należy mieć aktywne konto użytkownika Microsoft Azure Active Directory (AAD). Następnie przeczytaj poniższe artykuły przed skonfigurowaniem funkcji analizy interakcji w obszarze roboczym.

- Przejrzyj i zaakceptuj [Warunki użytkowania usługi](terms-of-service.md) firmy Microsoft.  
- Przeczytaj artykuł [Zarządzanie plikami cookie i zgoda użytkownika](user-consent-storage.md). Później należy ocenić, czy trzeba zaktualizować powiadomienie dotyczące zgody użytkownika. Jeśli wcześniej nie ma żadnych niekrytycznych plików cookie, prawdopodobnie trzeba będzie zaktualizować zasady witryny.
- Przejrzyj [słownik](glossary.md), aby szybko zapoznać się z kluczowymi terminami i pojęciami.

## <a name="step-2-explore-engagement-insights"></a>Krok 2: Poznawanie wiedzy dotyczącej zobowiązania

Przy pierwszym odwiedzeniu obszaru szczegółowych informacji o zaangażowaniu można skonfigurować ustawienia, przejrzeć zasady i poznać możliwości.

1. Zaloguj się w [portalu funkcji szczegółowych informacji o zaangażowaniu](https://home.ci.ai.dynamics.com/app/engagement-insights) przy użyciu konta (służbowego) użytkownika usługi Microsoft AAD.

1. Wybierz region i zaznacz pole wyboru, jeśli chcesz otrzymywać aktualizacje i oferty pocztą e-mail.

1. Przejrzyj **Warunki użytkowania funkcji szczegółowych informacji o zaangażowaniu** oraz **Oświadczenie o ochronie prywatności** dla szczegółowych informacji o zaangażowaniu (wersja zapoznawcza) i wybierz pozycję **Poznaj demonstrację**, aby zaakceptować te ustawienia.

1. Poznaj produkt przy użyciu zestawu danych przykładowych.

##  <a name="step-3-set-up-a-workspace-and-create-reports"></a>Krok 3: Konfigurowanie obszaru roboczego i tworzenie raportów

Obszar roboczy to obszar, w którym można wyświetlać działania użytkownika w czasie rzeczywistym oraz przechowywać raporty i zarządzać nimi. Dodaj kod do witryny sieci Web, aby rozpocząć zbierania *zdarzeń*, czyli danych dotyczących działań gromadzonych od użytkowników.

1. [Tworzenie obszaru roboczego](create-workspace.md) i dodawanie członków.

1. Dodaj kod do [witryny internetowej](instrument-website.md) lub [aplikacji mobilnej](developer-resources.md#capture-events-from-mobile-apps), aby zobaczyć działanie użytkownika przechodzące do obszaru roboczego.

1. Wyświetl [raport w czasie rzeczywistym](view-reports.md), w którym są wyświetlani aktywni użytkownicy według przeglądarki, urządzenia, systemu operacyjnego, lokalizacji i języka. Można również tworzyć [raporty niestandardowe](custom-reports.md) w celu tworzenia własnych wizualizacji.

1. Utwórz [wymiary](dimensions.md), aby sortować gości według nowych i powracających użytkowników, [metryki](metrics.md) pomocne w lepszym zrozumieniu zachowań użytkowników oraz [segmenty](segments.md) w celu zidentyfikowania podzestawów osób odwiedzających tę stronę w oparciu o charakterystyki lub interakcje w witrynie internetowej.
    
## <a name="step-4-export-data-to-other-channels"></a>Krok 4: Eksportowanie danych do innych kanałów

Można tworzyć *zdarzenia opracowane* (widok wirtualny) danych analizy sieci Web. Następnie należy filtrować i eksportować dane do Azure Data Lake Storage. Wyeksportowane dane można pozyskać jako źródło danych.

1. [Tworzenie zdarzeń opracowanych](refined-events.md) dla eksportu.

1. [Eksportowanie danych](export-events.md) do usługi Azure Data Lake Storage.

1. [Utwórz połączenie między szczegółowymi informacjami o odbiorcach i szczegółowymi informacjami o zaangażowaniu](integrate-audience-insights-engagement-insights.md) w celu udostępniania danych między tymi dwoma funkcjami.

1. [Rozpoznawaj zdarzenia internetowe od wcześniej uwierzytelnionych użytkowników](unknown-to-known.md) przy użyciu funkcji **od nieznanego do znanego**.

1. Dowiedz się jak [usuwać i eksportować dane zdarzeń zawierających dane osobowe](delete-export-personal-data.md).

## <a name="step-5-create-and-manage-funnel-reports"></a>Krok 5: Tworzenie raportów lejka i zarządzanie nimi

Raport lejka zbiera informacje o krokach, które występują podczas podróży klienta przez Twoją stronę internetową lub aplikację mobilną. Oprócz tworzenia dostosowanych do wyboru raportów profilowych i raportów niestandardowych można utworzyć raport lejka identyfikujący ścieżki klientów używane przed zakupem. 

1. [Utwórz raport lejka](funnel-reports.md) w celu podejmowania uzasadnionych decyzji oraz określenia obszarów optymalizacji i udoskonaleń procesów.

1. Utwórz raporty lejka w różnych kanałach, po instrumentacji dla aplikacji mobilnej za pomocą [zestawu SDK dla systemu Android](get-started-android.md) lub [zestawu SDK dla systemu iOS](get-started-ios.md) usługi wyników analiz interakcji.

1. Dzięki [funkcji szczegółowych informacji dotyczących lejka](funnel-reports.md#funnel-insights) można uzyskać głębsze dane na temat zachowań klientów w ramach kroków raportu lejka.
 
## <a name="step-6-stay-connected"></a>Krok 6: Pozostań w kontakcie

Jesteśmy wdzięczni za aktywne zaangażowanie i uwzględniamy wszystkie odpowiednie opinie podczas opracowywania przyszłych wersji. Podziel się swoją opinią i zgłoś problem za pomocą jednego z tych kanałów:
- [Społeczność](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Przekazywanie opinii](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Zgłoś prośbę o pomoc techniczną](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
