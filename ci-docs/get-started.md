---
title: Wprowadzenie do Dynamics 365 Customer Insights
description: Przegląd funkcji Customer Insights pomaga zasobom w umożliwianiu szybkiego rozpoczęcia pracy.
ms.reviewer: v-wendysmith
ms.author: mhart
author: m-hartmann
ms.date: 04/12/2022
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 68c26eb0ad0da787a9f594b4aebe679588b0d6bf
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833588"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Wprowadzenie do Dynamics 365 Customer Insights

Dzięki Customer Insights można lepiej zrozumieć klientów. Dane z różnych źródeł transakcyjnych, behawioralnych i obserwacji można połączyć w celu utworzenia pełnego widoku klienta. Użyj tych wyników analiz, aby utworzyć skoncentrowane na kliencie rozwiązania i procesy. Ujednolicaj i zrozum dane klientów oraz wykorzystaj je do inteligentnych spostrzeżeń i działań.

## <a name="step-1-create-an-environment"></a>Krok 1. Tworzenie środowiska

Najpierw stwórz środowisko do pracy. Jeśli organizacja już zakupiła licencję, zobacz temat [Tworzenie środowiska](create-environment.md). Aby rozpocząć próbną wersję usługi Customer Insights, zobacz [Konfigurowanie środowiska próbnego](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>Krok 2: poznanie aplikacji Customer Insights

Przy pierwszym logowaniu do Customer Insights skonfiguruj ustawienia i poznaj produkt.

1. [Zaloguj się do rozwiązania Customer Insights](https://home.ci.ai.dynamics.com), korzystając z konta użytkownika Microsoft Azure Active Directory (AAD).

1. Zmień środowisko, aby wyświetlić dane demonstracyjne i [poznać środowisko Customer Insights](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Krok 3. Pozyskiwanie, ujednolicanie i konfigurowanie relacji dla danych

Ujednolicone profile to podstawy do uzyskania wglądu w dane i podjęcia działań dotyczących danych. Pobierz dane z różnych źródeł i uruchom proces ujednolicania danych w celu połączenia ujednoliconych profilów. Określ relacje między pozyskiwanymi encjami i użyj funkcji wzbogacania, aby dodać informacje do profili.

1. Pozyskuj dane, tworząc źródła danych z wielu opcji. Wybierz między [łącznikami usługi Power Query](connect-power-query.md) a [folderem Common Data Model](connect-common-data-model.md) lub [Microsoft Dataverse](connect-dataverse-managed-lake.md).

1. Uruchom [proces ujednolicania danych](data-unification.md), identyfikując [pola źródłowe](map-entities.md), usuwając [duplikaty](remove-duplicates.md), [warunki dopasowania](match-entities.md) i [pola ujednolicające](merge-entities.md).

1. Zapoznaj się z [encjami, które tworzy system](entities.md) i utwórz [relacje między pozyskanymi encjami](relationships.md).

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Krok 4. Rozszerzanie ujednoliconych profilów przy użyciu przewidywać, działań i miar

Dzięki skonfigurowanym zunifikowanym profilom możesz ulepszać swoje dane i jeszcze bardziej zwiększać ilość dostarczanych przez nie informacji.

1. Wybierz opcje z rozszerzonej biblioteki dostaw wzbogaceń, aby [wzbogacić dane klientów](enrichment-hub.md).

1. Użyj [gotowych modeli](predictions-overview.md), aby przewidzieć prawdopodobieństwo problemów lub oczekiwane przychody.

1. [Skonfiguruj działania](activities.md) na podstawie pozyskanych danych i wizualizuj interakcje z klientami przy użyciu chronologicznej osi czasu.

1. [Skompiluj miary](measures.md) w celu oceny celów biznesowych i wskaźników KPI.

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Krok 5. Tworzenie segmentów i aktywowanie danych za pomocą różnych opcji eksportowania

Teraz, gdy Twoje dane są kompletne i zawierają szeroki zakres informacji o Twoich klientach, poszukaj sposobów na podjęcie działań na tych danych.

1. [Utwórz segmenty](segments.md), czyli podzestawy bazy klientów, aby upewnić się, że działania są odpowiednie dla klientów docelowych.

1. Przeglądaj rosnący wykaz [opcji eksportowania](export-destinations.md), w których można użyć danych klientów. Można na przykład zarządzać promocjami i kontaktować się z klientami za pomocą marketingu cyfrowego.

1. Przejrzyj opcje integracji, na przykład w innych aplikacjach usługi Dynamics 365 za pomocą [dodatku Karta klienta](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]
