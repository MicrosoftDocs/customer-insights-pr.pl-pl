---
title: Utwórz ujednolicony profil kontaktu (podgląd)
description: Przejdź przez proces ujednolicenia danych, aby utworzyć jeden główny zbiór danych kontaktowych.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305049"
---
# <a name="create-a-unified-contact-profile-preview"></a>Utwórz ujednolicony profil kontaktu (podgląd)

Po [unifikacji kont biznesowych](map-entities.md) można opcjonalnie ujednoliceć kontakty dotyczące tych klientów i połączyć ujednolicone kontakty z ujednoliconymi kontami. Proces ujednolicania kontaktów mapuje dane kontaktowe z wielu źródeł danych, usuwa duplikaty, dopasowuje dane między podmiotami, konfiguruje mapowanie semantyczne, tworzy relacje między kontaktami i kontami, a następnie tworzy ujednolicony profil kontaktu.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

Kilka pierwszych kroków jest identycznych z krokami rozsyłania kont.

## <a name="prerequisites"></a>Wymagania wstępne

Rekordy klientów i kontaktów muszą mieć unikatowy klucz (nazywany kluczem obcym), który łączy się z nimi. Na przykład identyfikator konta, który istnieje w rekordzie konta i rekordzie kontaktu, który wiąże ze sobą konto i kontakt.

## <a name="preview-limitations"></a>Ograniczenia wersji zapoznawczej

- Kontakty bez łącza do klienta są upuszczane.
- Jeśli konto jest deduplikowane, rekord zwycięzcy jest identyfikowany na podstawie preferencji scalania. Rekordy przegranych nie są wybierane i dlatego są usuwane. Kontakty powiązane z utraconymi rekordami są usuwane.
- Konto może mieć wiele kontaktów, ale kontakt jest połączony z jednym kontem.
- Atrybuty kontaktu mapowane w kroku mapowania semantycznego są jedynymi atrybutami, które mogą być wyświetlane na karcie klienta. Jednak dostępnych jest 17 atrybutów.

## <a name="select-source-fields"></a>Wybierz pola źródłowe

1. W obszarze **Ujednolicenie kontaktów (podgląd)** wybierz opcję **Wprowadzenie**.

1. [Wybierz encje i pola dla](map-entities.md) źródeł danych kontaktów, w tym klucze podstawowe i typy atrybutów.

1. Wybierz **Dalej**.

## <a name="remove-duplicate-records"></a>Usuń zduplikowane rekordy

1. Opcjonalnie [można zdefiniować reguły deduplikacji](remove-duplicates.md) dla wybranych encji.

1. Wybierz **Dalej**.

## <a name="match-conditions"></a>Warunki dopasowywania

1. [Definiowanie kolejności i reguł](match-entities.md) w celu dopasowania między encjami.

1. Wybierz **Dalej**.

## <a name="unify-contact-fields"></a>Ujednolicenie pól kontaktowych

1. [Łączenie i wykluczanie pól kontaktu](merge-entities.md).

1. Wybierz **Dalej**.

## <a name="define-the-semantic-fields-for-unified-contacts"></a>Zdefiniuj pola semantyczne dla ujednoliconych kontaktów

Ten krok w procesie unifikacji mapuje ujednolicone pola kontaktów na typy danych. W programie B-to-B w kartach klientów są wyświetlane konta. Po wybraniu karty zostaną wybrane wszystkie kontakty skojarzone z kontem. Pola mapować w tym kroku to pola, które będą wyświetlane na kartach.

1. Wybierz typ semantyczny, który mapuje do każdego pola ujednoliconego. Wybierz opcję **Brak**, jeśli typ forum nie jest dostępny.

   :::image type="content" source="media/semantic_mapping.png" alt-text="Zrzut ekranu strony Pola semantyczne w celu zdefiniowania typów semantycznych." lightbox="media/semantic_mapping.png":::

1. Po zamapowaniu wszystkich ujednoliconych pól wybierz opcję **Dalej**.

## <a name="set-the-relationship-between-contacts-and-accounts"></a>Ustaw relację między kontaktami a kontami

Ten krok w procesie ujednolicenia łączy Twoje dane kontaktowe z odpowiednimi danymi konta.

1. Dla każdego podmiotu wprowadź następujące informacje:

   - **Klucz obcy od podmiotu kontaktowego**: Wybierz atrybut, który łączy Twój podmiot kontaktowy z kontem.
   - **Do encji konta**: wybierz encję klienta skojarzoną z kontaktem.

   :::image type="content" source="media/contact_relationship.png" alt-text="Zrzut ekranu strony Relacja w celu połączenia encji kontaktów i kont.":::

1. Wybierz **Dalej**.

## <a name="review-contact-unification"></a>Sprawdź ujednolicenie kontaktów

Przejrzyj podsumowanie zmian, utwórz ujednolicony profil i przejrzyj wyniki.

### <a name="review-and-create-contact-profiles"></a>Przejrzyj i utwórz profile kontaktów

Ten ostatni krok w procesie ujednolicenia pokazuje podsumowanie kroków w procesie i daje możliwość wprowadzenia zmian przed utworzeniem profilu ujednoliconego kontaktu.

:::image type="content" source="media/b2b_review_contacts.png" alt-text="Zrzut ekranu funkcji Przeglądanie i tworzenie profili kontaktów.":::

1. Wybierz **Edytuj** na każdym z etapów ujednolicania kontaktów, aby przejrzeć i wprowadzić ewentualne zmiany.

1. Jeśli jesteś zadowolony z dokonanych wyborów, wybierz **Utwórz profile kontaktów**. Podczas tworzenia ujednoliconego profilu kontaktu wyświetlana jest strona **Ujednolicenie**.
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="Zrzut ekranu przedstawiający stronę ujednolicania kontaktów z kafelkami z wyświetlaniem kolejki lub odświeżaniem.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Ukończenie algorytmu zajmuje trochę czasu i nie możesz zmienić konfiguracji do czasu jego zakończenia.

### <a name="view-the-results-of-contact-unification"></a>Zobacz wyniki ujednolicenia kontaktów

Po ujednoliceniu na stronie **Dane** > **Ujednolicenie** wyświetlana jest liczba ujednoliconych profili kontaktów. Wyniki każdego kroku w procesie ujednolicenia są wyświetlane na każdym kafelku. Na przykład **Pola źródłowe** pokazują liczbę zmapowanych atrybutów (pól), a **Duplikaty rekordów** pokazują liczbę znalezionych duplikatów rekordów.

:::image type="content" source="media/unified_contacts.png" alt-text="Zrzut ekranu strony Ujednolicenia danych po ujednoliceniu kontaktów.":::

> [!TIP]
> Kafelek **Pasujące warunki** jest wyświetlany tylko wtedy, gdy wybrano wiele encji.

Zalecamy, byś przejrzał wyniki, a zwłaszcza jakość swoich [reguł dopasowania](data-unification-update.md#manage-match-rules) i w razie potrzeby je udoskonalił.

W razie potrzeby [wprowadź zmiany w ustawieniach ujednolicenia kontaktów](data-unification-update.md) i ponownie uruchom profil ujednolicony.

### <a name="verify-output-entities-from-data-unification"></a>Zweryfikuj encje wyjściowe z ujednolicenia danych

Przejdź do **Dane** > **Encje** w celu sprawdzenia encji wyjściowych.

Ujednolicona encja profilu kontaktu o nazwie *ContactProfile* jest wyświetlana w sekcji **Encje jednostki**. Pierwszy udany przebieg ujednolicenia tworzy zunifikowaną encję *ContactProfile*. Wszystkie kolejne etapy rozszerzają tę encję.

Obiekt *ContactsCustomer* (podgląd) zostanie utworzony i wyświetlony w sekcji **Profile**. Ta encja zawiera dane kontaktów bez łączy do klientów. Ta encja jest używana jako dane wejściowe do mapowania semantycznego i etapów relacji ujednolicenia kontaktu.

Encje deduplikacji i konselacji są tworzone i wyświetlane w sekcji **System**. Zdeduplikowana jednostka dla każdej jednostki źródłowej jest tworzona o nazwie **Deduplication_DataSource_Entity**. Encja **ContactsConflationMatchPairs** zawiera informacje o dopasowaniach między encjami.

Obiekt wyjściowy deduplikacji zawiera następujące informacje:
- Identyfikatory/klucze
  - Pola klucza głównego i alternatywnego identyfikatora. Pole Alternatywny ID zawiera wszystkie identyfikatory alternatywne zidentyfikowane dla danego rekordu.
  - Pole Deduplication_GroupId przedstawia grupę lub klaster zidentyfikowaną w ramach jednostki, która grupuje wszystkie podobne rekordy na podstawie określonych pól deduplikacji. Jest ono używane do przetwarzania w systemie. Jeśli nie określono reguł ręcznej deduplikacji i mają zastosowanie reguły deduplikacji zdefiniowane przez system, to pole może nie być dostępne w jednostce wyjściowej deduplikacji.
  - Deduplication_WinnerId: To pole zawiera identyfikator zwycięzcy ze zidentyfikowanych grup lub klastrów. Jeśli Deduplication_WinnerId jest taki sam jak wartość klucza podstawowego dla rekordu, oznacza to, że rekord jest rekordem zwycięzcy.
- Pola używane do definiowania reguł deduplikacji.
- Pola Reguła i Wynik określające, które z reguł deduplikacji zostały zastosowane, oraz wynik zwracany przez algorytm dopasowujący.

## <a name="next-step"></a>Następny krok

Skonfiguruj [działania](activities.md), [wzbogacenie](enrichment-hub.md) lub [relacje](relationships.md), aby uzyskać dokładniejsze informacje o kontaktach.
