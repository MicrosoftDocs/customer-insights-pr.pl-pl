---
title: Tworzenie ujednoliconego widoku klientów
description: Przejdź przez proces ujednolicenia danych ze swoimi danymi, aby utworzyć jeden podstawowy zestaw danych kont lub profili klientów.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: c2a81776eab147c4b5209a6fbf89c0f4c9853d1d
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304440"
---
# <a name="data-unification-overview"></a>Omówienie ujednolicenia danych

Po [skonfigurowaniu źródeł danych](data-sources.md) można ujednolicić dane. Ujednolicenie danych pozwala na połączenie niegdyś odrębnych źródeł danych w jeden główny zbiór danych, który zapewnia ujednolicony widok tych danych.

W przypadku konsumentów indywidualnych (B-do-C), gdzie dane skupiają się wokół pojedynczych osób, ujednolicenie zapewnia ujednolicony obraz klientów. W przypadku kont biznesowych (B-to-B), gdzie dane są skoncentrowane wokół kont, ujednolicenie zapewnia ujednolicony widok kont. [Unifiacja kontaktów (podgląd)](data-unification-contacts.md) umożliwia oddzielne unifikowanie i kojaowanie kontaktów z kontami.

Dane mogą być ujednolicone dla pojedynczej lub wielu encji.

# <a name="individual-consumers-b-to-c"></a>[Klienci indywidualni (B2C)](#tab/b2c)

Proces unifikowania mapuje dane klienta ze źródeł danych, usuwa duplikaty, dopasowuje dane do danych między encji i tworzy ujednolicony profil. Ujednolicenie jest wykonywane w następującej kolejności:

1. [Pola źródłowe](map-entities.md) (nazywane wcześniej mapą): W kroku Pola źródłowe wybierz encje i pola, które mają być uwzględnione w procesie ujednolicenia. Zmapuj pola do wspólnego typu semantycznego, który opisuje przeznaczenie pola.

1. [Duplikaty rekordów](remove-duplicates.md) (poprzednio część Dopasowania): W kroku duplikaty rekordów opcjonalnie zdefiniuj reguły usuwania duplikatów rekordów klientów z każdej encji.

1. [Warunki dopasowania](match-entities.md) (poprzednio nazywane Dopasowaniem): W kroku Warunki dopasowania zdefiniuj reguły, które dopasowują rekordy klientów pomiędzy encjami. Kiedy klient znajduje się w dwóch lub więcej jednostkach, tworzony jest jeden skonsolidowany rekord zawierający wszystkie kolumny i dane z każdej encji.

1. [Ujednolicone pola klienta](merge-entities.md) (wcześniej nazywane Merge): W kroku Ujednolicone pola klienta określ, które pola źródłowe powinny być włączone, wykluczone lub połączone w ujednolicony profil klienta.  

1. [Sprawdź](review-unification.md) i utwórz profil ujednolicony.

# <a name="business-accounts-b-to-b"></a>[Klienci biznesowi (B2B)](#tab/b2b)

Proces unifikowania mapuje dane konta ze źródeł danych, usuwa duplikaty, dopasowuje dane do danych między encji i tworzy ujednolicony profil. Ujednolicenie jest wykonywane w następującej kolejności:

1. [Pola źródłowe](map-entities.md) (nazywane wcześniej mapą): W kroku Pola źródłowe wybierz encje i pola, które mają być uwzględnione w procesie ujednolicenia kont. Zmapuj pola do wspólnego typu semantycznego, który opisuje przeznaczenie pola.

1. [Duplikaty rekordów](remove-duplicates.md) (poprzednio część Dopasowania): W kroku duplikaty rekordów opcjonalnie zdefiniuj reguły usuwania duplikatów rekordów kont z każdej encji.

1. [Warunki dopasowania](match-entities.md) (poprzednio nazywane Dopasowaniem): W kroku Warunki dopasowania zdefiniuj reguły, które dopasowują rekordy kont pomiędzy encjami. Kiedy klient znajduje się w dwóch lub więcej jednostkach, tworzony jest jeden skonsolidowany rekord zawierający wszystkie kolumny i dane z każdej encji.

1. [Ujednolicone pola klienta](merge-entities.md) (wcześniej nazywane Merge): W kroku Ujednolicone pola klienta określ, które pola źródłowe powinny być włączone, wykluczone lub połączone w ujednolicony profil klienta.  

1. [Sprawdź](review-unification.md) i utwórz profil ujednolicony.

Po [unifikacji kont biznesowych](data-unification-contacts.md) można opcjonalnie ujednoliceć kontakty dotyczące tych klientów i połączyć ujednolicone kontakty z ujednoliconymi kontami.

---

Po zakończeniu ujednolicenia danych można opcjonalnie:

- [Konfigurować relacje między encjami](relationships.md) w celu utworzenia rozbudowanych segmentów.
- [Wzbogacić dane](enrichment-hub.md) w celu zdobycia szerszego zakresu informacji o klientach.
- [Zdefiniować działania](activities.md) na podstawie niektórych pozyskanych atrybutów.
- [Tworzyć miaru](measures.md), aby lepiej zrozumieć zachowania klientów i wyniki biznesowe.

[!INCLUDE [footer-include](includes/footer-banner.md)]