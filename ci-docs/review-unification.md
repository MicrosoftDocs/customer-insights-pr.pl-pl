---
title: Przegląd ujednolicenia danych
description: Przeanalizuj etapy ujednolicania danych, utwórz ujednolicone profile klientów i przejrzyj wyniki
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303980"
---
# <a name="review-data-unification"></a>Przegląd ujednolicenia danych

Przejrzyj podsumowanie zmian, utwórz ujednolicony profil i przejrzyj wyniki.

## <a name="review-and-create-customer-profiles"></a>Przejrzyj i utwórz profile klientów

Ten ostatni krok w procesie ujednolicenia pokazuje podsumowanie kroków w procesie i daje możliwość wprowadzenia zmian przed utworzeniem profilu ujednoliconego.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="Zrzut ekranu funkcji Przeglądanie i tworzenie profili klientów.":::

1. Wybierz **Edytuj** na każdym z etapów ujednolicania danych, aby przejrzeć i wprowadzić ewentualne zmiany.

1. Jeśli jesteś zadowolony z dokonanych wyborów, wybierz **Utwórz profile klientów** (lub **Utwórz profile kont** dla B-to-B). Podczas tworzenia ujednoliconego profilu klienta wyświetlana jest strona **Ujednolicenie**.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Zrzut ekranu przedstawiający stronę ujednolicania z kafelkami z wyświetlaniem kolejki lub odświeżaniem.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Ukończenie algorytmu zajmuje trochę czasu i nie możesz zmienić konfiguracji do czasu jego zakończenia.

## <a name="view-the-results-of-data-unification"></a>Wyświetlanie wyników ujednolicania danych

Po ujednoliceniu na stronie **Dane** > **Ujednolicenie** wyświetlana jest liczba ujednoliconych profili klientów (lub profili kont dla B-do-B). Wyniki każdego kroku w procesie ujednolicenia są wyświetlane na każdym kafelku. Na przykład **Pola źródłowe** pokazują liczbę zmapowanych atrybutów (pól), a **Duplikaty rekordów** pokazują liczbę znalezionych duplikatów rekordów.

:::image type="content" source="media/m3_unified.png" alt-text="Zrzut ekranu strony Ujednolicenia danych po ujednoliceniu danych.":::

> [!TIP]
> Kafelek **Pasujące warunki** jest wyświetlany tylko wtedy, gdy wybrano wiele encji.

Zalecamy, byś przejrzał wyniki, a zwłaszcza jakość swoich [reguł dopasowania](data-unification-update.md#manage-match-rules) i w razie potrzeby je udoskonalił.

W razie potrzeby [wprowadź zmiany w ustawieniach ujednolicenia](data-unification-update.md) i ponownie uruchom profil ujednolicony.

### <a name="verify-output-entities-from-data-unification"></a>Zweryfikuj encje wyjściowe z ujednolicenia danych

Przejdź do **Dane** > **Encje** w celu sprawdzenia encji wyjściowych.

Ujednolicona encja klienta nosi nazwę *Klient* w sekcji **Profile**. Pierwszy udany przebieg ujednolicenia tworzy zunifikowaną encję *Klient*. Wszystkie kolejne etapy rozszerzają tę encję.

Encje deduplikacji i konselacji są tworzone i wyświetlane w sekcji **System**. Zdeduplikowana jednostka dla każdej jednostki źródłowej jest tworzona o nazwie **Deduplication_DataSource_Entity**. Encja **ConflationMatchPairs** zawiera informacje o dopasowaniach między encjami.

Obiekt wyjściowy deduplikacji zawiera następujące informacje:
- Identyfikatory/klucze
  - Pola klucza głównego i alternatywnego identyfikatora. Pole Alternatywny ID zawiera wszystkie identyfikatory alternatywne zidentyfikowane dla danego rekordu.
  - Pole Deduplication_GroupId przedstawia grupę lub klaster zidentyfikowaną w ramach jednostki, która grupuje wszystkie podobne rekordy na podstawie określonych pól deduplikacji. Jest ono używane do przetwarzania w systemie. Jeśli nie określono reguł ręcznej deduplikacji i mają zastosowanie reguły deduplikacji zdefiniowane przez system, to pole może nie być dostępne w jednostce wyjściowej deduplikacji.
  - Deduplication_WinnerId: To pole zawiera identyfikator zwycięzcy ze zidentyfikowanych grup lub klastrów. Jeśli Deduplication_WinnerId jest taki sam jak wartość klucza podstawowego dla rekordu, oznacza to, że rekord jest rekordem zwycięzcy.
- Pola używane do definiowania reguł deduplikacji.
- Pola Reguła i Wynik określające, które z reguł deduplikacji zostały zastosowane, oraz wynik zwracany przez algorytm dopasowujący.

## <a name="next-step"></a>Następny krok

- W przypadku typu B-to-B można opcjonalnie przeprowadzić [ujednolicenie kontaktów](data-unification-contacts.md).

- Dla B-to-C konfiguruj [działania](activities.md), [wzbogacenie](enrichment-hub.md), [powiązania](relationships.md) lub [środki](measures.md), aby uzyskać więcej informacji o swoich klientach.

[!INCLUDE[footer-include](includes/footer-banner.md)]
