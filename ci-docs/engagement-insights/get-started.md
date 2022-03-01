---
title: Wprowadzenie do funkcji obsługi funkcji analizy interakcji
description: Przegląd zasobów pomocy w celu szybkiego rozpoczęcia pracy.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 12/21/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5ee1567cea834670a16aaa3253912b7957ce26b3
ms.sourcegitcommit: 86739a3f238162fc96837270b5d184e648fab15c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/20/2021
ms.locfileid: "7405371"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Wprowadzenie do funkcji obsługi funkcji analizy interakcji w Dynamics 365 Customer Insights (wersja zapoznawcza)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Obsługa funkcji analizy interakcji umożliwia zbieranie i analizę zachowań klientów w witrynie sieci Web. Integruje się ona z funkcją analizy odbiorców, dzięki czemu oprócz raportów o profilu klienta można zobaczyć bogate analizy behawioralne w czasie rzeczywistym. Łącza określone w tym artykule ułatwiają szybkie skonfigurowanie i wdrożenie środowiska.

## <a name="step-1-review-prerequisites"></a>Krok 1: Przejrzyj wymagania wstępne

Najpierw należy mieć aktywne konto użytkownika Microsoft Azure Active Directory. Następnie przeczytaj poniższe artykuły przed skonfigurowaniem funkcji analizy interakcji w obszarze roboczym.

- Przejrzyj i zaakceptuj [Postanowienia prawne](terms-of-service.md) firmy Microsoft.  
- Przeczytaj artykuł [Zarządzanie plikami cookie i zgoda użytkownika](user-consent-storage.md). Po przejrzeniu tego artykułu należy określić, czy należy zaktualizować powiadomienie o zgodzie użytkownika. Jeśli wcześniej nie ma żadnych niekrytycznych plików cookie, prawdopodobnie trzeba będzie zaktualizować zasady witryny.
- Przejrzyj [słownik](glossary.md), aby szybko zapoznać się z kluczowymi terminami i pojęciami.

## <a name="step-2-explore-engagement-insights"></a>Krok 2: Poznawanie wiedzy dotyczącej zobowiązania

Podczas pierwszego wykorzystania funkcji analizy interakcji użytkownik może skonfigurować ustawienia, przejrzeć zasady i poznać informacje na temat produktu.

1. Zaloguj się do portalu [portal wydajności funkcji analizy interakcji](https://pi.dynamics.com) przy użyciu konta użytkownika Microsoft Azure Active Directory. (Może to być konto szkolne lub konto służbowe).

1. Wybierz region i za pomocą pola wyboru wybierz, czy chcesz otrzymywać aktualizacje i oferty pocztą e-mail.

1. Przejrzyj **warunki użytkowania funkcji analizy interakcji (wersja zapoznawcza)** i **zasady ochrony prywatności** i wybierz **Zapoznaj się z wersją demonstracyjną**, aby je zaakceptować.

1. Poznaj produkt przy użyciu zestawu danych przykładowych.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Krok 3: Konfigurowanie obszaru roboczego i dodawanie kodu do witryny sieci Web

W obszarze roboczym można wyświetlać działania użytkownika w czasie rzeczywistym oraz przechowywać raporty i zarządzać nimi. Dodaj kod do witryny sieci Web, aby rozpocząć zbierania *zdarzeń*, czyli danych dotyczących działań gromadzonych od użytkowników.

1. [Tworzenie obszaru roboczego](create-workspace.md) i dodawanie członków.

1. [Dodaj kod do witryny sieciowej](instrument-website.md) lub [aplikacji mobilnej](developer-resources.md#capture-events-from-mobile-apps), aby zobaczyć działanie użytkownika przechodzące do obszaru roboczego.

1. Wyświetlanie [raportu w czasie rzeczywistym](view-reports.md) wyświetlającego aktywnych użytkowników według przeglądarki, urządzenia, systemu operacyjnego, lokalizacji i języka. Można również tworzyć [raporty niestandardowe](custom-reports.md) w celu tworzenia własnych wizualizacji.
    
## <a name="step-4-export-data-to-other-channels"></a>Krok 4: Eksportowanie danych do innych kanałów

Można tworzyć *zdarzenia opracowane* (widok wirtualny) danych analizy sieci Web. Następnie należy filtrować i eksportować dane do Azure Data Lake Storage. Wyeksportowane dane można pozyskać jako źródło danych. Aby uzyskać informacji, zobacz [Utwórz łącze między wynikami analiz odbiorców i wynikami analiz interakcji](integrate-audience-insights-engagement-insights.md).

1. [Tworzenie zdarzeń opracowanych](refined-events.md) dla eksportu.

1. [Eksportuj dane](export-events.md) do Data Lake Storage.

1. Dowiedz się jak [usuwać i eksportować dane zdarzeń zawierających dane osobowe](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>Krok 5: Pozostań w kontakcie

Doceniamy Wasz aktywny udział i planujemy uwzględnić wszystkie istotne informacje zwrotne przy opracowywaniu przyszłych wersji. Podziel się swoją opinią i zgłoś problem za pomocą jednego z tych kanałów:
- [Społeczność](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Przekazywanie opinii](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Zgłoś prośbę o pomoc techniczną](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
