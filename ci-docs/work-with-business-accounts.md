---
title: Rozpoczynanie pracy z kontami biznesowymi jako podstawowymi odbiorcami docelowymi
description: Dowiedz się więcej o kontach biznesowych jako podstawowych odbiorcach docelowych w aplikacji Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: f16c8ad50ed290562fa9f223a3e8c86228e5331e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647001"
---
# <a name="work-with-business-accounts"></a>Praca z klientami biznesowymi

Dynamics 365 Customer Insights umożliwia skonfigurowanie środowiska dla różnych podstawowych odbiorców docelowych: indywidualnych konsumentów (B2C) i kont biznesowych (B2B). W scenariuszach B2C dane są skoncentrowane wokół poszczególnych osób. W przypadku B2B głównymi odbiorcami docelowymi są konta — organizacje lub firmy — i kontakty. W tym artykule ułatwiamy rozpoczynanie pracy ze środowiskiem klientów biznesowych. Zawiera on listę różnic między obszarami funkcji w aplikacji Customer Insights w zależności od fokusu środowiska. Aby uzyskać więcej informacji na temat różnic, przejrzyj dokumenty obszarów funkcji. 

## <a name="create-an-environment-for-business-accounts"></a>Tworzenie środowiska dla klientów biznesowych

Administratorzy mogą [utworzyć środowisko w istniejącej organizacji](create-environment.md). Krok procesu tworzenia nowego środowiska pyta administratorów o podstawowych odbiorców docelowych środowiska. Jeśli jest to początkowa konfiguracja po zakupie licencji, nadzorowane środowisko może pomóc w tworzeniu pierwszego środowiska.

Następnie można [pozyskiwać dane](data-sources.md) dla kont biznesowych i kontaktów pokrewnych jako źródeł danych ze wszystkich obsługiwanych źródeł.

Po ujednoliceniu danych [określ hierarchię kont](relationships.md#set-up-account-hierarchies) w ramach konfiguracji relacji. Można także [skonfigurować mapowania semantyczne](semantic-mappings.md) w celu połączenia encji kontaktów i kont. 

## <a name="switch-between-primary-target-audience"></a>Przełączanie się między podstawowymi odbiorcami docelowymi

Jeśli organizacja obsługuje środowiska dla pojedynczych klientów i kont biznesowych, można użyć przełącznika w lewym okienku, aby wybrać podstawowych odbiorców docelowych.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Przełącznik umożliwiający zmianę podstawowych odbiorców docelowych między poszczególnymi klientami i kontami biznesowymi.":::

## <a name="supported-feature-areas"></a>Obsługiwane obszary funkcji

- [Działania](activities.md): obsługa kont i pokrewnych kontaktów w celu tworzenia działań i pokazywania ich na osi czasu.
- [Relacje](relationships.md): kreator działań ułatwia tworzenie relacji encji, aby w widoku klienta można było wyświetlać wszystkie działania związane z kontaktami. Kontakty mogą przejść do szczegółów w celu wyświetlenia widoku kontaktu, a w przypadku agregowania działań klienta można użyć hierarchii.
- [Miary](measures.md): obsługuje miary utworzone w kreatorze miar za pomocą jednego obliczenia. Opcjonalne ustawienie umożliwia zestawienie danych dla kont podrzędnych podczas tworzenia miar.
- [Segmenty](segments.md): obsługuje segmenty, które są tworzone od podstaw przy użyciu kreatora segmentów. Nowe operatory umożliwiają zastosowanie hierarchii klientów podczas tworzenia segmentów.
- [Pozyskiwanie danych](data-sources.md): wszystkie funkcje w tym obszarze są takie same dla klientów biznesowych i indywidualnych klientów.
- [Ujednolicanie danych](data-unification.md): wszystkie funkcje w tym obszarze są takie same dla klientów biznesowych i indywidualnych klientów.
- [Wzbogacanie](enrichment-hub.md): niektóre typy wzbogacania są dostępne tylko dla różnych scenariuszy z klientami, podczas gdy inne są dostępne wyłącznie dla kont biznesowych.
- [Prognozy i gotowe modele](predictions-overview.md): przewidywanie problemów z transakcjami zawiera dodatkowe kroki dla kont biznesowych. Inne przewidywania są dostępne tylko dla pojedynczych klientów.
- [Aktywacja i eksport](export-destinations.md): eksporty są dostępne dla klientów biznesowych i indywidualnych klientów. Niektóre eksporty wymagają dodatkowej konfiguracji i informacji kontaktowych przewidywanych w segmentach bazowych, aby były prawidłowe dla kont biznesowych.
- [Ustawienia systemowe](system.md) i [zarządzanie użytkownikami](permissions.md): wszystkie funkcje w tym obszarze są takie same dla klientów biznesowych i indywidualnych klientów.

