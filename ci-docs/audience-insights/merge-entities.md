---
title: Scalanie encji w przypadku zjednoczenia danych
description: Scalanie encji w celu utworzenia ujednoliconych profili klientów.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-merge
ms.openlocfilehash: c218f9c1a1b7711ee48419470bf6c352450ffc0c
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732785"
---
# <a name="merge-entities"></a>Scalanie encji

Faza scalania jest ostatnią fazą procesu unifikacji danych. Jego zastosowanie powoduje uzgadnianie danych powodujących konflikty. Przykłady danych powodujących konflikty mogą zawierać nazwy klientów znalezione w dwóch zestawach danych, które są wyświetlane w różny sposób w każdym miejscu („Grant Marshall” i „Grant Marshal”) lub numery telefoniczne, który różnią się formatem (617-803-091X a 617803091X). Scalanie tych niezgodnych danych jest wykonywane na podstawie poszczególnych atrybutów.

:::image type="content" source="media/merge-fields-page.png" alt-text="Strona scalania w procesie ujednolicania danych pokazująca tabelę z połączonymi polami definiującymi ujednolicony profil klienta.":::

Po zakończeniu [fazy dopasowania](match-entities.md) można rozpocząć fazę scalenia, zaznaczając kafelek **Scalanie** na stronie **Ujednolicanie**.

## <a name="review-system-recommendations"></a>Przejrzyj rekomendacje systemu

W **Dane** > **Ujednolić** > **Scal** wybierasz i wykluczasz atrybuty do połączenia w ramach ujednoliconej jednostki profilu klienta. Ujednolicony profil klienta jest wynikiem procesu unifikacji danych. Niektóre atrybuty są automatycznie scalane przez system.

Aby zobaczyć atrybuty, które są zawarte w jednym z twoich automatycznie połączonych atrybutów, wybierz ten połączony atrybut **Pola klienta** na zakładce tabeli. Dwa nowe wiersze tworzące scalony atrybut będą wyświetlane w dwóch nowych wierszach pod atrybutem scalonym.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Rozdzielanie, zmienianie nazw, wykluczanie i edytowanie pól scalonych

W celu wygenerowania ujednoliconego profilu klienta można zmienić sposób przetwarzania przez system scalonych atrybutów. Wybierz opcję **Pokaż więcej** i wybierz, co chcesz zmienić.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Opcje w menu rozwijanym Pokaż więcej, aby zarządzać połączonymi atrybutami.":::

Aby uzyskać więcej informacji, zobacz następną sekcję.

## <a name="separate-merged-fields"></a>Oddzielenie połączonych pól

Aby oddzielić połączone pola, znajdź atrybut w tabeli. Oddzielone pola są wyświetlane jako pojedyncze punkty danych na jednolitym profilu klienta. 

1. Zaznacz scalone pole.
  
1. Wybierz opcję **Pokaż więcej** i wybierz pozycję **Rozdziel pola**.
 
1. Potwierdź rozdział.

1. Wybierz opcję **Zapisz** i **Uruchom**, aby przetworzyć zmiany.

## <a name="rename-merged-fields"></a>Zmienianie nazw pól scalonych

Zmień wyświetlaną nazwę scalonych atrybutów. Nie można zmienić nazwy elementu wyjściowego.

1. Zaznacz scalone pole.
  
1. Wybierz opcję **Pokaż więcej** i wybierz pozycję **Zmień nazwę**.

1. Potwierdź zmienioną nazwę wyświetlania. 

1. Wybierz opcję **Zapisz** i **Uruchom**, aby przetworzyć zmiany.

## <a name="exclude-merged-fields"></a>Wykluczanie pól połączonych

Wykluczenie atrybutu z ujednoliconego profilu klienta. Jeśli pole jest wykorzystywane w innych procesach, np. w segmencie, usuń je z tych procesów, zanim wykluczysz je z profilu klienta. 

1. Wybierz scalone pole.
  
1. Wybierz opcję **Pokaż więcej** i wybierz pozycję **Wyklucz**.

1. Potwierdź wykluczenie.

1. Wybierz opcję **Zapisz** i **Uruchom**, aby przetworzyć zmiany. 

Na stronie **Scalanie** wybierz pozycję **Wykluczone pola**, aby wyświetlić listę wszystkich pól wykluczonych. To okienko umożliwia dodawanie z powrotem wykluczonych pól.

## <a name="edit-a-merged-field"></a>Edytuj scalone pole

1.  Wybierz scalone pole.

1.  Wybierz opcję **Pokaż więcej** i wybierz pozycję **Edytuj**.

1.  Określ, jak połączyć lub scalić pola z jednej z trzech opcji:
    - **Ważność**: identyfikuje zwycięską wartość na podstawie klasyfikacji ważności określonej dla uczestniczących pól. Jest to opcja domyślna scalania. Wybierz pozycję **Przenieś w górę/w dół**, aby ustawić ranking ważności.
    :::image type="content" source="media/importance-merge-option.png" alt-text="Opcja Ważność w oknie dialogowym scalania pól."::: 
    - **Najnowsze**: identyfikuje zwycięską wartość jako wartość najnowszą. Wymaga pola daty lub pola liczbowego dla każdej encji uczestniczącej w zakresie scalania pól w celu zdefiniowania niedawności.
    :::image type="content" source="media/recency-merge-option.png" alt-text="Opcja Niedawność w oknie dialogowym scalania pól.":::
    - **Najstarsze**: identyfikuje zwycięską wartość jako wartość najstarszą. Wymaga pola daty lub pola liczbowego dla każdej encji uczestniczącej w zakresie scalania pól w celu zdefiniowania niedawności.

1.  Aby uczestniczyć w procesie scalania, można dodać więcej pól.

1.  Można zmienić nazwę scalonego pola.

1. Wybierz pozycję **Gotowe**, aby zastosować zmiany.

1. Wybierz opcję **Zapisz** i **Uruchom**, aby przetworzyć zmiany. 

## <a name="manually-combine-fields"></a>Ręczne łączenie pól

Określ ręcznie łączony atrybut. 

1. Na stronie **Scalanie** wybierz opcję **Połącz pola**.

1. Zwycięskie zasady scalania można określić na liście rozwijanej **Połącz pola wg**.

1. Wybierz pole, które chcesz dodać. Wybierz **Dodaj pola**, aby połączyć więcej pól.

1. Podaj **nazwę** i **nazwę pola wyjściowego**.

1. Wybierz pozycję **Gotowe**, aby zastosować zmiany.

1. Wybierz opcję **Zapisz** i **Uruchom**, aby przetworzyć zmiany. 

## <a name="change-the-order-of-fields"></a>Zmiana kolejności pól

Niektóre encje zawierają więcej szczegółów niż inne. Jeśli encja zawiera najnowsze dane o polu, możesz nadać jej priorytet nad innymi encjami podczas łączenia wartości.

1. Zaznacz scalone pole.
  
1. Wybierz opcję **Pokaż więcej** i wybierz pozycję **Edytuj**.

1. W okienku **Łączenie pól** wybierz opcję **Przenieś w górę/w dół**, aby ustawić kolejność lub przeciągnij je i upuść w żądanym miejscu.

1. Potwierdź zmianę.

1. Wybierz opcję **Zapisz** i **Uruchom**, aby przetworzyć zmiany.

## <a name="configure-customer-id-generation"></a>Konfigurowanie generowania identyfikatora klienta 

Po skonfigurowaniu scalania pól można zdefiniować sposób generowania wartości CustomerId, czyli unikatowych identyfikatorów profilu klienta. Krok scalania w procesie ujednolicania danych generuje unikatowy identyfikator profilu klienta. Identyfikator to CustomerId w encji *Klient*, który wynika z procesu ujednolicania danych. 

Identyfikator CustomerId w encji Klient jest oparty na wartości skrótu pierwszej wartości podstawowych kluczy innych niż null. Klucze pochodzą z encji używanych na etapie dopasowania i scalania i wpływa na nie kolejność dopasowywania. Dlatego wygenerowany identyfikator CustomerID może ulec zmianie w przypadku zmiany wartości klucza podstawowego w encji podstawowej kolejności dopasowania. Wartość klucza podstawowego może więc nie zawsze reprezentować tego samego klienta.

Skonfigurowanie stabilnego identyfikatora klienta umożliwia uniknięcie tego zachowania.

**Konfiguruj unikatowy identyfikator klienta**

1. Przejdź do opcji **Ujednolicanie** > **Scal**.

1. Wybierz kartę **Klucze**. 

1. Zatrzymaj kursor w wierszu **CustomerId** i wybierz opcję **Skonfiguruj**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Kontrolka do dostosowywania generowania identyfikatora.":::

1. Wybierz do pięciu pól wchodzących w skład unikatowego identyfikatora klienta i bardziej stabilnych. Rekordy, które nie pasują do konfiguracji, używają identyfikatora skonfigurowanego w systemie.  

1. Wybierz opcję **Gotowe** i uruchom proces scalania w celu zastosowania zmian.

## <a name="group-profiles-into-households-or-clusters"></a>Grupowanie profilów w gospodarstwa domowe lub klastry

W procesie konfigurowania generowania profilu klienta można zdefiniować reguły grupowania profilów pokrewnych w klaster. Obecnie są dostępne dwa typy klastrów — gospodarstwa domowe i klastry niestandardowe. System automatycznie wybiera gospodarstwa domowe ze wstępnie zdefiniowanymi regułami, jeśli encja *Klient* zawiera pola semantyczne *Person.LastName* i *Location.Address*. Można też utworzyć klaster z własnymi regułami i warunkami, podobnie do [reguł dopasowania](match-entities.md#define-rules-for-match-pairs).

**Definiowanie gospodarstwa domowego lub klastra**

1. Przejdź do opcji **Ujednolicanie** > **Scal**.

1. Na karcie **Scalanie** wybierz pozycję **Zaawansowane** > **Utwórz klaster**.

   :::image type="content" source="media/create-cluster.png" alt-text="Kontrolka do tworzenia nowego klastra.":::

1. Wybierz klaster typu **Gospodarstwo domowe** lub **Niestandardowy**. Jeśli pola semantyczne *Person.LastName* i *Location.Address* znajdują się w encji *Klient*, zostanie automatycznie wybrane gospodarstwo domowe.

1. Podaj nazwę klastra i wybierz opcję **Gotowe**.

1. Wybierz kartę **Klastry**, aby znaleźć utworzony klaster.

1. Określ reguły i warunki definiujące klaster.

1. Wybierz opcję **Uruchom**, aby uruchomić proces scalania i utworzyć klaster.

Po uruchomieniu procesu scalania identyfikatory klastra są dodawane jako nowe pola do encji *Klient*.

## <a name="run-your-merge"></a>Uruchamianie scalania

Niezależnie od tego, czy ręcznie scalono atrybuty, czy pozwolono, aby system je scalił, zawsze można uruchomić scalanie. Wybierz **Uruchom** na stronie **Scalanie**, aby zacząć proces.

> [!div class="mx-imgBorder"]
> ![Zapis i uruchomienie scalania danych.](media/configure-data-merge-save-run.png "Zapis i uruchomienie scalania danych")

Wybierz opcję **Uruchom tylko scalanie**, jeśli chcesz, aby wyniki pracy zostały odzwierciedlone w ujednoliconej encji klienta. Procesy niższego szczebla zostaną odświeżone zgodnie [z definicją w harmonogramie odświeżania](system.md#schedule-tab).

Wybierz **Uruchom procesy scalania i procesy niższego rzędu**, aby odświeżyć system przy użyciu zmian. Wszystkie procesy, w tym wzbogacenie, segmenty i miary, zostaną automatycznie ponownie uruchomione. Po zakończeniu wszystkich dalszych procesów, profile klientów odzwierciedlają wszystkie wprowadzone zmiany.

Aby wprowadzić więcej zmian i ponownie uruchomić krok, można anulować trwające scalanie. Wybierz **Odświeżanie...** i wybierz **Anuluj zadanie**  w pojawiającym się okienku bocznym.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

:::image type="content" source="media/process-detail-path.png" alt-text="Ścieżka przechodzenia do szczegółów, aby uzyskać szczegółowe informacje z łącza stanu zadania.":::

## <a name="next-step"></a>Następny krok

Skonfiguruj [działania](activities.md), [wzbogacenie](enrichment-hub.md) lub [relacje](relationships.md), aby uzyskać dokładniejsze informacje o klientach.

Jeśli już skonfigurowałeś działania, wzbogacenia lub segmenty, zostaną one przetworzone automatycznie, aby wykorzystać najnowsze dane o klientach.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
