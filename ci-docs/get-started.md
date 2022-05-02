---
title: Wprowadzenie do Dynamics 365 Customer Insights
description: Przegląd funkcji Customer Insights pomaga zasobom w umożliwianiu szybkiego rozpoczęcia pracy.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.subservice: audience-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 6d23552687530fddf42418b924571dddc0209e69
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646749"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Wprowadzenie do Dynamics 365 Customer Insights

Dzięki Customer Insights można lepiej zrozumieć klientów. Dane z różnych źródeł transakcyjnych, behawioralnych i obserwacji można połączyć w celu utworzenia pełnego widoku klienta. Użyj tych wyników analiz, aby utworzyć skoncentrowane na kliencie rozwiązania i procesy. Ujednolicaj i zrozum dane klientów oraz wykorzystaj je do inteligentnych spostrzeżeń i działań.

## <a name="step-1-create-an-environment"></a>Krok 1. Tworzenie środowiska

Zacznij od utworzenia środowiska, w którym będzie można pracować. Jeśli organizacja już zakupiła licencję, zobacz temat [Tworzenie środowiska](create-environment.md). Aby rozpocząć próbną wersję usługi Customer Insights, zobacz [Konfigurowanie środowiska próbnego](trial-signup.md). 

## <a name="step-2-explore-customer-insights"></a>Krok 2: poznanie aplikacji Customer Insights

Po pierwszym logowanie się do programu Customer Insights można skonfigurować ustawienia i poznać jego możliwości.

1. [Zaloguj się do rozwiązania Customer Insights](https://home.ci.ai.dynamics.com), korzystając z konta użytkownika Microsoft Azure Active Directory (AAD).

1. [Zmień środowisko](manage-environments.md#switch-environments), aby wyświetlić dane demonstracyjne i poznać [środowisko Customer Insights](home.md).

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Krok 3. Pozyskiwanie, ujednolicanie i konfigurowanie relacji dla danych

Ujednolicone profile to podstawy do uzyskania wglądu w dane i podjęcia działań dotyczących danych. Pobierz dane z różnych źródeł i uruchom proces ujednolicania danych w celu połączenia ujednoliconych profilów. Określ relacje między pozyskanymi encjami przy użyciu funkcji wzbogacenia, aby dodawać informacje do profilów. 

1. Pozyskuj dane, tworząc źródła danych z wielu opcji. Wybierz między [łącznikami usługi Power Query](connect-power-query.md) a [folderem Common Data Model](connect-common-data-model.md) lub [Microsoft Dataverse](connect-dataverse-managed-lake.md). 

1. Uruchom [proces ujednolicania danych](data-unification.md), przechodząc przez etapy [mapowania](map-entities.md), [dopasowywania](match-entities.md) i [scalania](merge-entities.md).

1. Zapoznaj się z [encjami, które tworzy system](entities.md) i utwórz [relacje między pozyskanymi encjami](relationships.md).
    
## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Krok 4. Rozszerzanie ujednoliconych profilów przy użyciu przewidywać, działań i miar

Skonfigurowanie profilów ujednoliconych umożliwia zwiększenie wydajności danych i dalsze zwiększenie liczby zapewnianych przez nie informacji.

1. Wybierz opcje z rozszerzonej biblioteki dostaw wzbogaceń, aby [wzbogacić dane klientów](enrichment-hub.md).

1. Użyj [gotowych modeli](predictions-overview.md), aby przewidzieć prawdopodobieństwo problemów lub oczekiwane przychody.

1. [Skonfiguruj działania](activities.md) na podstawie pozyskanych danych i wizualizuj interakcje z klientami przy użyciu chronologicznej osi czasu. 

1. [Skompiluj miary](measures.md) w celu oceny celów biznesowych i wskaźników KPI.
 
## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Krok 5. Tworzenie segmentów i aktywowanie danych za pomocą różnych opcji eksportowania

Gdy dane są już gotowe i zawierają szeroki zakres informacji o klientach, czas zwrócić uwagę na sposoby podjęcia działań w związku z tym danymi. 

1. [Utwórz segmenty](segments.md), czyli podzestawy bazy klientów, aby upewnić się, że działania są odpowiednie dla klientów docelowych.

1. Przeglądaj rosnący wykaz [opcji eksportowania](export-destinations.md), w których można użyć danych klientów. Można na przykład zarządzać promocjami i kontaktować się z klientami za pomocą marketingu cyfrowego.

1. Przejrzyj opcje integracji, na przykład w innych aplikacjach usługi Dynamics 365 za pomocą [dodatku Karta klienta](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]