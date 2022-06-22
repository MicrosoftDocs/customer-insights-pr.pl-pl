---
title: Przegląd ujednolicenia danych
description: Przeanalizuj etapy ujednolicania danych, utwórz ujednolicone profile klientów i przejrzyj wyniki
ms.date: 06/02/2022
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
ms.openlocfilehash: 0f7b2e9af65796c4d304dbd9893a21617e847620
ms.sourcegitcommit: 760fbac397c738407c7dea59297d54cae19b6f57
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844099"
---
# <a name="review-data-unification"></a>Przegląd ujednolicenia danych

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Ten ostatni krok w procesie ujednolicenia pokazuje podsumowanie kroków w procesie i daje możliwość wprowadzenia zmian przed utworzeniem profilu ujednoliconego.

:::image type="content" source="media/m3_review.png" alt-text="Zrzut ekranu funkcji Przeglądanie i tworzenie profili klientów.":::

## <a name="review-the-data-unification-steps"></a>Zapoznaj się z krokami ujednolicenia danych

1. Wybierz **Edytuj** na każdym z etapów ujednolicania danych, aby przejrzeć i wprowadzić ewentualne zmiany.

1. Jeśli jesteś zadowolony z dokonanych wyborów, wybierz **Utwórz profile klientów**. Podczas tworzenia ujednoliconego profilu klienta wyświetlana jest strona **Ujednolicenie**. Wszystkie kafelki poza **Pola źródła** pokazują stan **W kolejce** lub **Odświeżanie**.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Zrzut ekranu przedstawiający stronę ujednolicania z kafelkami z wyświetlaniem kolejki lub odświeżaniem.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Ukończenie algorytmu zajmuje trochę czasu i nie możesz zmienić konfiguracji do czasu jego zakończenia. Po zakończeniu procesu ujednolicona encja profilu klienta o nazwie *Klient* zostaje umieszczona na stronie **Encje** w sekcji **Profile**. Pierwszy udany przebieg ujednolicenia tworzy zunifikowaną encję *Klient*. Wszystkie kolejne etapy rozszerzają tę encję.

## <a name="review-the-results-of-data-unification"></a>Przegląd wyników ujednolicania danych

Po ujednoliceniu na stronie **Dane** > **Ujednolicenie** wyświetlana jest liczba ujednoliconych profili klientów. Wyniki każdego kroku w procesie ujednolicenia są wyświetlane na każdym kafelku. Na przykład **Pola źródłowe** pokazują liczbę zmapowanych atrybutów (pól), a **Duplikaty rekordów** pokazują liczbę znalezionych duplikatów rekordów.

:::image type="content" source="media/m3_unified.png" alt-text="Zrzut ekranu strony Ujednolicenia danych po ujednoliceniu danych.":::

> [!TIP]
> Kafelek **Pasujące warunki** jest wyświetlany tylko wtedy, gdy wybrano wiele encji.

Zalecamy, byś przejrzał wyniki, a zwłaszcza jakość swoich [reguł dopasowania](data-unification-update.md#manage-match-rules) i w razie potrzeby je udoskonalił.

W razie potrzeby [wprowadź zmiany w ustawieniach ujednolicenia](data-unification-update.md) i ponownie uruchom profil ujednolicony.

## <a name="next-step"></a>Następny krok

Skonfiguruj [działania](activities.md), [wzbogacenie](enrichment-hub.md), [powiązania](relationships.md) lub [środki](measures.md), aby uzyskać więcej informacji o swoich klientach.

[!INCLUDE[footer-include](includes/footer-banner.md)]
