---
title: Zaktualizuj ustawienia ujednolicania
description: Uaktualnij zduplikowane reguły, reguły dopasowania lub zunifikowane pola w ustawieniach ujednolicenia.
ms.date: 06/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 590a2996cf8b2b1c6def59b78583169ec1910b59
ms.sourcegitcommit: 760fbac397c738407c7dea59297d54cae19b6f57
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844053"
---
# <a name="update-the-unification-settings"></a>Zaktualizuj ustawienia ujednolicania

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Aby przejrzeć lub zmienić ustawienia ujednolicenia po utworzeniu profilu ujednoliconego, wykonaj następujące czynności.

1. Przejdź do sekcji **Dane** > **Ujednolicanie**.

   :::image type="content" source="media/m3_unified.png" alt-text="Zrzut ekranu strony Ujednolicenia danych po ujednoliceniu danych.":::

   > [!TIP]
   > Kafelek **Pasujące warunki** jest wyświetlany tylko wtedy, gdy wybrano wiele encji.

1. Wybierz, co chcesz zaktualizować:
   - [Pola źródłowe](#edit-source-fields), aby dodać encje lub atrybuty albo zmienić typy atrybutów.
   - [Duplikaty rekordów](#manage-deduplication-rules), aby zarządzać regułami deduplikacji lub preferencjami scalania.
   - [Warunki dopasowania](#manage-match-rules), aby zaktualizować reguły dopasowania dla dwóch lub więcej encji.
   - [Zunifikowane pola klienta](#manage-unified-fields), aby połączyć lub wykluczyć pola. Możesz także grupować powiązane profile w klastry.

1. Po wprowadzeniu zmian wybierz następną opcję:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Zrzut ekranu strony Ujednolicenie danych z zaznaczonymi opcjami Ujednolicenie.":::

   - Aby ocenić jakość swoich warunków dopasowania (ponowną duplikację i reguły dopasowania) bez aktualizowania profilu zunifikowanego, zobacz [Uruchom warunki dopasowania](#run-matching-conditions). Opcja **Uruchom tylko pasujące warunki** nie jest wyświetlana dla pojedynczej encji.
   - [Ujednolicenie profili klientów](#run-updates-to-the-unified-customer-profile) do uruchomienia dopasowanych warunków u aktualizacji encji unified customer profile bez wpływu na zależności (takie jak wzbogacenia, segmenty czy miary). Zależne procesy nie są uruchamiane, ale będą odświeżane zgodnie z [definicją w harmonogramie odświeżania](system.md#schedule-tab).
   - [Ujednolicenie profili klientów i zależności](#run-updates-to-the-unified-customer-profile) do uruchomienia dopasowanych warunków u aktualizacji encji unified customer profile i wszystkich zależności (takie jak wzbogacenia, segmenty czy miary). Wszystkie procesy są wznawiane automatycznie.

## <a name="edit-source-fields"></a>Edytuj pola źródłowe

Nie możesz usunąć atrybutu lub encji, jeśli zostały one już zunifikowane.

1. Wybierz **Edytuj** na kafelku **Pola źródłowe**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Zrzut ekranu strony Pola źródłowe pokazujący liczbę kluczy głównych, zmapowanych i niezmapowanych pól":::

   Wyświetlana jest liczba zmapowanych i niezmapowanych pól.

1. Wybierz **Wybierz encje i pola**, aby dodać inne atrybuty lub encje. Aby znaleźć i wybrać swoje atrybuty i encje, należy użyć narzędzia Wyszukaj lub przewinąć. Wybierz **Zastosuj**.

1. Opcjonalnie możesz zmienić klucz główny dla encji, typy atrybutów oraz włączyć lub wyłączyć **inteligentne mapowanie**. Aby uzyskać więcej informacji, zobacz [Wybierz klucz podstawowy i typ semantyczny dla atrybutów](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Wybierz **Następny**, aby wprowadzić zmiany w regułach deduplikacji, lub wybierz **Zapisz i zamknij** i wróć do [Aktualizuj ustawienia ujednolicenia](#update-the-unification-settings)

## <a name="manage-deduplication-rules"></a>Zarządzaj regułami deduplikacji

1. Wybierz **Edytuj** na kafelku **Duplikaty rekordów**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Zrzut ekranu strony z duplikatami rekordów pokazujący liczbę zduplikowanych rekordów" lightbox="media/m3_duplicates_edit.png":::

   Liczba znalezionych zduplikowanych rekordów jest wyświetlana pod **Duplikaty**. Kolumna **Rekordy zduplikowane** pokazuje, które jednostki miały zduplikowane rekordy i jaki był procent zduplikowanych rekordów.

1. Jeśli dodałeś encję wzbogaconą, wybierz **Użyj encji wzbogaconych**. Aby uzyskać więcej informacji, zobacz [Wzbogacanie dla źródeł danych](data-sources-enrichment.md).

1. Aby zarządzać regułami deduplikacji, wybierz jedną z poniższych opcji:
   - **Utwórz nową regułę**: Wybierz **Dodaj regułę** pod odpowiednią jednostką. Aby uzyskać więcej informacji, zobacz [Definiowanie reguł deduplikacji](remove-duplicates.md#define-deduplication-rules).
   - **Zmień warunki reguły**: Wybierz regułę, a następnie **Edytuj**. Zmieniaj pola, dodawaj i usuwaj warunki oraz dodawaj i usuwaj wyjątki.
   - **Podgląd**: Wybierz regułę, a następnie **Przegląd**, aby zobaczyć wyniki ostatniego uruchomienia tej reguły.
   - **Dezaktywuj regułę**: Wybierz regułę, a następnie **Dezaktywuj**, aby zachować regułę deduplikacji, wyłączając ją z procesu dopasowywania.
   - **Powielanie reguły**: Wybierz regułę, a następnie **Duplikuj**, aby utworzyć podobną regułę z modyfikacjami.
   - **Usuń regułę**: Wybierz regułę, a następnie **Usuń**.

1. Aby zmienić preferencje scalania, wybierz jednostkę. Możesz zmienić preferencje tylko wtedy, gdy reguła jest utworzona.
   1. Wybierz **Edytuj preferencje scalania** i zmień opcję **Zapisywanie do zachowania**.
   1. Aby zmienić preferencje dotyczące scalania poszczególnych atrybutów encji, wybierz **Zaawansowane** i wprowadź niezbędne zmiany.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Zrzut ekranu preferencji zaawansowanego scalania pokazujący najnowszy e-mail i najbardziej kompletny adres":::

   1. Wybierz pozycję **Gotowe**.

1. Wybierz **Następny**, aby wprowadzić zmiany w warunkach dopasowania, lub wybierz **Zapisz i zamknij** i wróć do [Aktualizuj ustawienia ujednolicenia](#update-the-unification-settings)

## <a name="manage-match-rules"></a>Zarządzanie regułami dopasowania

Większość parametrów dopasowania można ponownie skonfigurować i odpowiednio dostosować. Nie możesz dodawać ani usuwać encji. Reguły dopasowania nie odnoszą się do pojedynczej jednostki.

1. Wybierz **Edytuj** na kafelku **Warunki dopasowania**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Zrzut ekranu strony z zasadami i warunkami meczu oraz statystykami." lightbox="media/m3_match_edit.png":::

   Na stronie wyświetlana jest kolejność dopasowania i zdefiniowane reguły oraz następujące statystyki:
   - **Unikatowe rekordy źródłowe** — liczba poszczególnych rekordów źródłowych przetworzonych w ostatnim uruchomieniu dopasowania.
   - **Rekordy dopasowane i niedopasowane** — liczba wskazująca, ile unikatowych rekordów pozostaje po przetworzeniu reguł dopasowania.
   - **Tylko rekordy dopasowane** — liczba dopasowań we wszystkich parach dopasowania.

1. Aby wyświetlić wyniki wszystkich reguł i ich punktację, wybierz **Zobacz ostatnie uruchomienie**. Zostaną wyświetlone wyniki, w tym identyfikatory zastępczych kontaktów. Możesz pobrać wyniki.

1. Aby zobaczyć wyniki i punktację danej reguły, wybierz regułę, a następnie **Przegląd**. Zostaną wyświetlone wyniki. Możesz pobrać wyniki.

1. Aby zobaczyć wyniki określonego warunku w regule, wybierz regułę, a następnie **Edytuj**. W panelu Edycja wybierz **Podgląd** pod warunkiem. Możesz pobrać wyniki.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Graficzne przedstawienie niedopasowanych i dopasowanych rekordów wraz z listą danych.":::

1. Jeśli dodałeś encję wzbogaconą, wybierz **Użyj encji wzbogaconych**. Aby uzyskać więcej informacji, zobacz [Wzbogacanie dla źródeł danych](data-sources-enrichment.md).

1. Aby zarządzać regułami, wybierz jedną z poniższych opcji:
   - **Utwórz nową regułę**: Wybierz **Dodaj regułę** pod odpowiednią jednostką. Aby uzyskać więcej informacji, zobacz [Definiowanie reguł dla par dopasowań](match-entities.md#define-rules-for-match-pairs).
   - **Zmień kolejność swoich reguł**, jeśli zdefiniowałeś wiele reguł: Przeciągnij i upuść reguły w wybranej przez siebie kolejności. Aby uzyskać więcej informacji dotyczących CORS, zobacz [Określ kolejność dopasowania](match-entities.md#specify-the-match-order).
   - **Zmień warunki reguły**: Wybierz regułę, a następnie **Edytuj**. Zmieniaj pola, dodawaj i usuwaj warunki oraz dodawaj i usuwaj wyjątki.
   - **Dezaktywuj regułę**: Wybierz regułę, a następnie **Dezaktywuj**, aby zachować regułę dopasowania, wyłączając ją z procesu dopasowywania.
   - **Powielanie reguły**: Wybierz regułę, a następnie **Duplikuj**, aby utworzyć podobną regułę z modyfikacjami.
   - **Usuń regułę**: Wybierz regułę, a następnie **Usuń**.

1. Wybierz **Następny**, aby wprowadzić zmiany w ujednoliconych polach, lub wybierz **Zapisz i zamknij** i wróć do [Aktualizuj ustawienia ujednolicenia](#update-the-unification-settings)

## <a name="manage-unified-fields"></a>Zarządzaj polami ujednoliconymi

1. Wybierz **Edytuj** na kafelku **Ujednolicone pola klientów**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Zrzut ekranu ujednoliconych pól klienta":::

1. Przejrzyj pola połączone i wykluczone i wprowadź ewentualne zmiany. Dodaj lub edytuj klucz CustomerID lub pogrupuj profile w klastry. Aby uzyskać więcej informacji, zobacz temat [Ujednolicenie pól klientów](merge-entities.md).

1. Wybierz **Dalej**, aby przejrzeć ustawienia ujednolicenia i [zaktualizować profil ujednolicony i zależności](#run-updates-to-the-unified-customer-profile), lub wybierz **Zapisz i zamknij** i wróć do [Aktualizuj ustawienia ujednolicenia](#update-the-unification-settings), aby wprowadzić więcej zmian.

## <a name="run-matching-conditions"></a>Uruchom warunki dopasowania

Uruchamianie dopasowanych warunków tylko uruchamia ponowną duplikację i reguły dopasowania oraz aktualizuje encje *Ponowną duplikacją* i *ConflationMatchPair*.

1. Na stronie **Dane** > **Ujednolicenie** wybierz **Uruchamiaj tylko pasujące warunki**.

   Na kafelkach **Duplikaty rekordów** i **Pasujące warunki** znajdują się **Kolejka** lub stan **Odświeżanie**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Kiedy proces dopasowania zostanie zakończony, wybierz **Edytuj** na kafelku **Warunki dopasowania**.

   :::image type="content" source="media/match-KPIs.png" alt-text="Przycięty zrzut ekranu przedstawiający kluczowe metryki na stronie dopasowania z liczbami i szczegółami.":::

1. Aby wprowadzić zmiany, zobacz [Zarządzaj regułami deduplikacji](#manage-deduplication-rules) lub [Zarządzaj regułami dopasowania](#manage-match-rules).

1. Uruchom ponownie proces dopasowania lub [przeprowadź aktualizację profilu klienta](#run-updates-to-the-unified-customer-profile).

## <a name="run-updates-to-the-unified-customer-profile"></a>Uaktualnia ujednolicony profil klienta

1. Na stronie **Dane** > **Ujednolicenie** wybierz:

   - **Ujednolicenie profili klientów**: uruchamia dopasowane warunki i aktualizacje encji unified customer profile bez wpływu na zależności (takie jak wzbogacenia, segmenty czy miary). Zależne procesy nie są uruchamiane, ale będą odświeżane zgodnie z [definicją w harmonogramie odświeżania](system.md#schedule-tab).

   - **Ujednolicenie profili klientów i zależności**: uruchamia dopasowane warunki i aktualizacje encji ujednoliconego profilu klienta i wszystkich zależności. Wszystkie procesy są wznawiane automatycznie. Po zakończeniu wszystkich dalszych procesów profil klienta odzwierciedla zaktualizowane dane.

   Na kafelkach **Duplikaty rekordów**, **Pasujące warunki** i **Ujednolicone pola klientów** widnieje **Odrobienie** lub stan **Odświeżenie**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Wyniki udanego uruchomienia są wyświetlane na stronie **Ujednolicanie**, pokazując liczbę ujednoliconych profili klientów.
