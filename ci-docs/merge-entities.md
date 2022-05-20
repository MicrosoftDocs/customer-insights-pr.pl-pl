---
title: Ujednolicenie pól klienta lub konta
description: Scalanie encji w celu utworzenia ujednoliconych profili klientów.
recommendations: false
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-merge
- ci-match
- ci-relationships
- customerInsights
ms.openlocfilehash: 78e2528d4a3058f879d83952f72ed88a1da065b6
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740870"
---
# <a name="unify-customer-fields"></a>Ujednolicenie pól klientów

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

W tym kroku procesu ujednolicania wybierz i wyklucz atrybuty, które mają zostać połączone w ramach ujednoliconej jednostki profilu. Na przykład, jeśli trzy encje mają dane mailowe, możesz chcieć zachować wszystkie trzy osobne pola mailowe lub połączyć je w jedno pole mailowe dla ujednoliconego profilu. Niektóre atrybuty są automatycznie łączone przez system. Możesz tworzyć stabilne i unikalne identyfikatory klientów oraz grupować powiązane profile w klastry.

:::image type="content" source="media/m3_unify.png" alt-text="Strona scalania w procesie ujednolicania danych pokazująca tabelę z połączonymi polami definiującymi ujednolicony profil klienta.":::

## <a name="review-and-update-the-customer-fields"></a>Przeglądaj i aktualizuj pola klientów

1. Przejrzyj listę pól, które zostaną zunifikowane w zakładce **Pola klienta** w tabeli. Wprowadź ewentualne zmiany.

   1. Dla dowolnych pól połączonych możesz:
      - [Edytowanie](#edit-a-merged-field)
      - [Zmień nazwę](#rename-fields)
      - [Rozdziel](#separate-merged-fields)
      - [Wyklucz](#exclude-fields)
      - [Przesunąć w górę lub w dół](#change-the-order-of-fields)

   1. Dla każdego pojedynczego pola możesz:
      - [Połącz pola](#combine-fields-manually)
      - [Połącz grupę pól](#combine-a-group-of-fields)
      - [Zmień nazwę](#rename-fields)
      - [Wyklucz](#exclude-fields)
      - [Przesunąć w górę lub w dół](#change-the-order-of-fields)

1. Opcjonalnie, [wygeneruj konfigurację identyfikatora klienta](#configure-customer-id-generation).

1. Opcjonalnie [pogrupuj profile w gospodarstwa domowe lub klastry](#group-profiles-into-households-or-clusters).

> [!div class="nextstepaction"]
> [Następny krok: Przegląd ujednolicenia](review-unification.md)

### <a name="edit-a-merged-field"></a>Edytuj scalone pole

1. Zaznacz pole łączone i wybierz **Edytuj**. Zostanie wyświetlony panel Połącz pola.

1. Określ, jak połączyć lub scalić pola z jednej z trzech opcji:
    - **Ważność**: identyfikuje zwycięską wartość na podstawie klasyfikacji ważności określonej dla uczestniczących pól. Jest to opcja domyślna scalania. Wybierz pozycję **Przenieś w górę/w dół**, aby ustawić ranking ważności.

      :::image type="content" source="media/importance-merge-option.png" alt-text="Opcja Ważność w oknie dialogowym scalania pól.":::

    - **Najnowsze**: identyfikuje zwycięską wartość jako wartość najnowszą. Wymaga pola daty lub pola liczbowego dla każdej encji uczestniczącej w zakresie scalania pól w celu zdefiniowania niedawności.

      :::image type="content" source="media/recency-merge-option.png" alt-text="Opcja Niedawność w oknie dialogowym scalania pól.":::

    - **Najstarsze**: identyfikuje zwycięską wartość jako wartość najstarszą. Wymaga pola daty lub pola liczbowego dla każdej encji uczestniczącej w zakresie scalania pól w celu zdefiniowania niedawności.

1. Aby uczestniczyć w procesie scalania, można dodać więcej pól.

1. Można zmienić nazwę scalonego pola.

1. Wybierz pozycję **Gotowe**, aby zastosować zmiany.

### <a name="rename-fields"></a>Zmień nazwy pól

Zmień nazwę wyświetlania połączonych lub oddzielnych pól. Nie można zmienić nazwy elementu wyjściowego.

1. Zaznacz pole i wybierz **Zmień nazwę**.

1. Wprowadź nową nazwę wyświetlania.

1. Wybierz pozycję **Gotowe**.

### <a name="separate-merged-fields"></a>Oddzielenie połączonych pól

Aby oddzielić połączone pola, znajdź atrybut w tabeli. Oddzielone pola są wyświetlane jako pojedyncze punkty danych na jednolitym profilu klienta.

1. Zaznacz połączone pola i wybierz **Oddziel pola**.

1. Potwierdź rozdział.

### <a name="exclude-fields"></a>Pola wykluczenia

Wykluczenie połączonego lub oddzielnego pola z ujednoliconego profilu klienta. Jeśli pole jest wykorzystywane w innych procesach, np. w segmencie, usuń je z tych procesów, zanim wykluczysz je z profilu klienta.

1. Zaznacz pole łączone i wybierz **Wyklucz**.

1. Potwierdź wykluczenie.

Aby zobaczyć listę wszystkich wykluczonych pól, wybierz **Pola wykluczone**. Jeśli to konieczne, możesz odczytać pole wykluczone.

### <a name="change-the-order-of-fields"></a>Zmiana kolejności pól

Niektóre encje zawierają więcej szczegółów niż inne. Jeśli encja zawiera najnowsze dane o polu, możesz nadać jej priorytet nad innymi encjami podczas łączenia wartości.

1. Zaznacz pole..
  
1. Wybierz **Przesuń w górę/dół**, aby ustawić kolejność, lub przeciągnij i upuść je w wybranym miejscu.

### <a name="combine-fields-manually"></a>Ręcznie połącz grupę pól

Połącz oddzielone pola, by stworzyć połączony atrybut.

1. Wybierz **Połącz** > **Pola**. Zostanie wyświetlony panel Połącz pola.

1. Zwycięskie zasady scalania można określić na liście rozwijanej **Połącz pola wg**.

1. Wybierz **Dodaj pole**, aby połączyć więcej pól.

1. Podaj **nazwę** i **nazwę pola wyjściowego**.

1. Wybierz pozycję **Gotowe**, aby zastosować zmiany.

### <a name="combine-a-group-of-fields"></a>Połącz grupę pól

Traktuj zgrupowane grupy pól jako jedną jednostkę. Na przykład, jeśli nasze rekordy zawierają pola: Adres1, Adres2, Miasto, Stan i Numer pocztowy, nie chcemy łączyć pola Adres2 z innym rekordem, myśląc, że dzięki temu nasze dane będą bardziej kompletne.

1. Wybierz **Połącz** > **Grupa pól**.

1. Zwycięskie zasady scalania można określić na liście rozwijanej **Ustaw kolejność grup według**.

1. Wybierz opcję **Dodaj** i określ, czy do pól chcesz dodać więcej pól, czy grupy.

1. Podaj **Nazwę** i **Nazwę wyjściową** dla każdego połączonego pola.

1. Podaj **Nazwę** grupy pól.

1. Wybierz pozycję **Gotowe**, aby zastosować zmiany.

## <a name="configure-customer-id-generation"></a>Konfigurowanie generowania identyfikatora klienta

Określ, jak generować wartości ID klienta, czyli unikalne identyfikatory profilu klienta. Krok ujednolicenia pól w procesie ujednolicania danych generuje unikalny identyfikator profilu klienta. Identyfikator to *CustomerId* w encji *Klient*, który wynika z procesu ujednolicania danych.

Identyfikator *CustomerId*  jest oparty na haszu pierwszej wartości kluczy podstawowych zwycięzcy, które nie są zerowe. Klucze te pochodzą od encji używanych w ujednolicenia danych i są zależne od kolejności dopasowania. Tak więc wygenerowany identyfikator klienta może się zmienić, gdy zmieni się wartość klucza głównego w encji głównej zamówienia dopasowania. Wartość klucza podstawowego może więc nie zawsze reprezentować tego samego klienta.

Skonfigurowanie stabilnego identyfikatora klienta umożliwia uniknięcie tego zachowania.

1. Wybierz kartę **Klucze**.

1. Najedź kursorem na wiersz **CustomerId** i wybierz **Konfiguruj**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Kontrolka do dostosowywania generowania identyfikatora.":::

1. Wybierz do pięciu pól wchodzących w skład unikatowego identyfikatora klienta i bardziej stabilnych. Rekordy, które nie pasują do konfiguracji, używają identyfikatora skonfigurowanego w systemie.  

1. Wybierz pozycję **Gotowe**.

## <a name="group-profiles-into-households-or-clusters"></a>Grupowanie profilów w gospodarstwa domowe lub klastry

Możesz zdefiniować reguły grupujące powiązane profile w klastry. Obecnie są dostępne dwa typy klastrów — gospodarstwa domowe i klastry niestandardowe. System automatycznie wybiera gospodarstwa domowe ze wstępnie zdefiniowanymi regułami, jeśli encja *Klient* zawiera pola semantyczne *Person.LastName* i *Location.Address*. Można też utworzyć klaster z własnymi regułami i warunkami, podobnie do [reguł dopasowania](match-entities.md#define-rules-for-match-pairs).

1. Wybierz **Zaawansowane** > **Utwórz klaster**.

   :::image type="content" source="media/create-cluster.png" alt-text="Kontrolka do tworzenia nowego klastra.":::

1. Wybierz klaster typu **Gospodarstwo domowe** lub **Niestandardowy**. Jeśli pola semantyczne *Person.LastName* i *Location.Address* znajdują się w encji *Klient*, zostanie automatycznie wybrane gospodarstwo domowe.

1. Podaj nazwę klastra i wybierz opcję **Gotowe**.

1. Wybierz kartę **Klastry**, aby znaleźć utworzony klaster.

1. Określ reguły i warunki definiujące klaster.

1. Wybierz pozycję **Gotowe**. Klaster jest tworzony po zakończeniu procesu ujednolicenia. Identyfikatory klastra są dodawane jako nowe pola do encji *Klient*.

> [!div class="nextstepaction"]
> [Następny krok: Przegląd ujednolicenia](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
