---
title: Tworzenie ujednoliconego widoku klientów
description: Przejdź przez proces ujednolicania swoich danych, aby utworzyć jeden ujednolicony zestaw danych profilów klientów.
ms.date: 05/10/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: v-wendysmith
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: bb8da6f4b9f92f2b265ff9807e04638edae4f814
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755747"
---
# <a name="data-unification-overview"></a>Omówienie ujednolicenia danych

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Po [skonfigurowaniu źródeł danych](data-sources.md) można ujednolicić dane. Ujednolicenie danych pozwala na połączenie niegdyś odrębnych źródeł danych w jeden główny zbiór danych, który zapewnia ujednolicony widok tych danych. W przypadku konsumentów indywidualnych (B-do-C), gdzie dane skupiają się wokół pojedynczych osób, ujednolicenie zapewnia ujednolicony obraz klientów. W przypadku kont biznesowych (B-to-B), gdzie dane są skoncentrowane wokół kont, ujednolicenie zapewnia ujednolicony widok kont.

Dane mogą być ujednolicone dla pojedynczej lub wielu encji. Ujednolicenie jest wykonywane w następującej kolejności:

1. [Pola źródłowe](map-entities.md) (nazywane wcześniej mapą): W kroku Pola źródłowe wybierz encje i pola, które mają być uwzględnione w procesie ujednolicenia. Zmapuj pola do wspólnego typu semantycznego, który opisuje przeznaczenie pola.

1. [Duplikaty rekordów](remove-duplicates.md) (poprzednio część Dopasowania): W kroku duplikaty rekordów opcjonalnie zdefiniuj reguły usuwania duplikatów rekordów klientów z każdej encji.

1. [Warunki dopasowania](match-entities.md) (poprzednio nazywane Dopasowaniem): W kroku Warunki dopasowania zdefiniuj reguły, które dopasowują rekordy klientów pomiędzy encjami. Kiedy klient znajduje się w dwóch lub więcej jednostkach, tworzony jest jeden skonsolidowany rekord zawierający wszystkie kolumny i dane z każdej encji.

1. [Ujednolicone pola klienta](merge-entities.md) (wcześniej nazywane Merge): W kroku Ujednolicone pola klienta określ, które pola źródłowe powinny być włączone, wykluczone lub połączone w ujednolicony profil klienta.  

1. [Sprawdź](review-unification.md) i utwórz profil ujednolicony.

Po zakończeniu ujednolicenia danych można opcjonalnie:

- [Konfigurować relacje między encjami](relationships.md) w celu utworzenia rozbudowanych segmentów.
- [Wzbogacić dane](enrichment-hub.md) w celu zdobycia szerszego zakresu informacji o klientach.
- [Zdefiniować działania](activities.md) na podstawie niektórych pozyskanych atrybutów.
- [Tworzyć miaru](measures.md), aby lepiej zrozumieć zachowania klientów i wyniki biznesowe.

[!INCLUDE [footer-include](includes/footer-banner.md)]
