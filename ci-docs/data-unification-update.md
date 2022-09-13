---
title: Aktualizowanie ustawieńification klienta, konta lub kontaktu
description: Zaktualizuj zduplikowane reguły, reguły dopasowania lub ujednolicone pola w ustawieniach ujednolicenia klienta lub konta.
ms.date: 08/26/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: Scott-Stabbert
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: e893e66fd7691b9703d51ed8f87cfad63880cc3b
ms.sourcegitcommit: 560c4ee16376a9c6fdd7860988ce2d2440194fa5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2022
ms.locfileid: "9392484"
---
# <a name="update-unification-settings"></a>Zaktualizuj ustawienia ujednolicania

Aby przejrzeć lub zmienić ustawienia ujednolicenia po utworzeniu profilu ujednoliconego, wykonaj następujące czynności.

1. Przejdź do sekcji **Dane** > **Ujednolicanie**.

   W przypadku poszczególnych klientów (B-to-C) na stronie **Ujednolicanie** jest wyświetlana liczba ujednoliconych profilów klientów i kafelków dla każdego z kroków unifikowania.

   :::image type="content" source="media/m3_unified.png" alt-text="Zrzut ekranu strony Ujednolicenia danych po ujednoliceniu danych." lightbox="media/m3_unified.png":::

   W przypadku kont firmowych (B-do-B) strona **Ujednolicanie** wyświetla liczbę ujednoliconych profili kont i kafelków dla każdego etapu ujednolicenia konta. Jeśli kontakty były ujednolicone, wyświetlana jest liczba ujednoliconych profili kontaktów i kafelków dla każdego z etapów ujednolicenia kontaktu. Wybierz odpowiedni kafelek w sekcji **Ujednolicanie kont** lub **Ujednolicanie kontaktów (wersja zapoznawcza)** w zależności od tego, co chcesz zaktualizować.

   :::image type="content" source="media/b2b_unified.png" alt-text="Zrzut ekranu strony Ujednolicenie danych po ujednoliceniu konta i danych kontaktowych." lightbox="media/b2b_unified.png":::

   > [!TIP]
   > Kafelek **Pasujące warunki** jest wyświetlany tylko wtedy, gdy wybrano wiele encji.

1. Wybierz, co chcesz zaktualizować:
   - [Pola źródłowe](#edit-source-fields), aby dodać atrybuty lub encje albo zmienić typy atrybutów. Aby usunąć atrybut, zobacz [Usuwanie ujednoliconego pola](#remove-a-unified-field). Aby usunąć encję, zobacz [Usuwanie ujednoliconej encji](#remove-a-unified-entity).
   - [Duplikaty rekordów](#manage-deduplication-rules), aby zarządzać regułami deduplikacji lub preferencjami scalania.
   - [Warunki dopasowania](#manage-match-rules), aby zaktualizować reguły dopasowania dla dwóch lub więcej encji.
   - [Zunifikowane pola klienta](#manage-unified-fields), aby połączyć lub wykluczyć pola. Możesz także grupować powiązane profile w klastry.
   - [Pola formularzy do](#manage-semantic-fields-for-unified-contacts) zarządzania typami obiektów, które są ujednolicone.
   - [Relacje](#manage-contact-and-account-relationships) do zarządzania relacją kontakt-konto.

1. Po wprowadzeniu zmian wybierz następną opcję:

   - Aby ocenić jakość swoich warunków dopasowania (ponowną duplikację i reguły dopasowania) bez aktualizowania profilu zunifikowanego, zobacz [Uruchom warunki dopasowania](#run-matching-conditions). Opcja **Uruchom tylko pasujące warunki** nie jest wyświetlana dla pojedynczej encji.
   - [Ujednolicenie profili](#run-updates-to-the-unified-profile) do uruchomienia dopasowanych warunków u aktualizacji encji unified profile bez wpływu na zależności (takie jak wzbogacenia, segmenty czy miary). Zależne procesy nie są uruchamiane, ale będą odświeżane zgodnie z [definicją w harmonogramie odświeżania](schedule-refresh.md).
   - [Ujednolicenie profili i zależności](#run-updates-to-the-unified-profile), aby uruchomić pasujące warunki, zaktualizować encję ujednoliconego profilu i zaktualizować wszystkie zależności (takie jak wzbogacenia, segmenty lub miary). Wszystkie procesy są wznawiane automatycznie. W B-to-B ujednolicenie odbywa się zarówno na koncie, jak i na podmiotach kontaktowych aktualizujących ujednolicone profile.

## <a name="edit-source-fields"></a>Edytuj pola źródłowe

1. Wybierz **Edytuj** na kafelku **Pola źródłowe**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Zrzut ekranu strony Pola źródłowe pokazujący liczbę kluczy głównych, zmapowanych i niezmapowanych pól":::

   Wyświetlana jest liczba zmapowanych i niezmapowanych pól.

1. Aby dodać inne atrybuty lub podmioty, wybierz **Wybierz encje i pola**.

1. Opcjonalnie możesz zmienić klucz główny dla encji, typy atrybutów oraz włączyć lub wyłączyć **inteligentne mapowanie**. Aby uzyskać więcej informacji, zobacz temat [Wybierz pola źródłowe](map-entities.md).

1. Wybierz **Następny**, aby wprowadzić zmiany w regułach deduplikacji, lub wybierz **Zapisz i zamknij** i wróć do [Aktualizuj ustawienia ujednolicenia](#update-unification-settings)

### <a name="remove-a-unified-field"></a>Usuwanie ujednoliconego pola

Aby usunąć pole, które zostało ujednolicone, należy je usunąć z zależności, takich jak segmenty, miary, wzbogacenia lub relacje.

1. Po usunięciu wszystkich zależności pola przejdź do pozycji **Dane** > **Ujednolicanie**.

1. Wybierz **Edytuj** na kafelku **Ujednolicone pola klientów**.

1. Wybierz wszystkie wystąpienia pola, a następnie wybierz opcję **Wyklucz**.

   :::image type="content" source="media/m3_remove_attribute1.png" alt-text="Zrzut ekranu strony ujednoliconych pól przedstawiający wybrane pola i przycisk Wyklucz":::

1. Wybierz pozycję **Gotowe**, aby potwierdzić, a następnie wybierz **Zapisz i zamknij**.

   > [!TIP]
   > Jeśli zostanie wyświetlony komunikat „Nie można zapisać ujednolicenia. Nie można zmodyfikować ani usunąć określonego zasobu z powodu wcześniejszych zależności”, pole jest nadal używane we wcześniejszej zależności.

1. Jeśli pole jest używane w regule dla zduplikowanych rekordów lub pasujących warunków, należy wykonać następujące kroki. W przeciwnym razie przejdź do następnego kroku.
   1. Wybierz **Edytuj** na kafelku **Duplikaty rekordów**.
   1. Usuń pole ze wszystkich reguł, w których jest używane, a następnie wybierz opcję **Dalej**.
   1. Na stronie **Pasujące warunki** usuń pole ze wszystkich reguł, w których jest używane (jeśli tak jest), a następnie wybierz opcję **Zapisz i zamknij**.
   1. Wybierz pozycję **Ujednolicanie** > **Ujednolić profile i zależności klientów**. Przed podjęciem następnego kroku poczekaj na zakończenie procesu ujednolicania.

1. Wybierz **Edytuj** na kafelku **Pola źródłowe**.

1. Wybierz pozycję **Wybierz encje i pola** i wyczyść pole wyboru obok każdego wystąpienia pola.

   :::image type="content" source="media/m3_remove_attribute2.png" alt-text="Zrzut ekranu przedstawiający okno dialogowe Wybieranie encji i pól z wyczyszczonymi polami wyboru":::

1. Wybierz **Zastosuj**.

1. Wybierz **Zapisz i zamknij**.

1. Wybierz pozycję **Ujednolicanie** > **Ujednolić profile i zależności klientów**, aby zaktualizować ujednolicony profil.

### <a name="remove-a-unified-entity"></a>Usuwanie ujednoliconej encji

Aby usunąć encję, która zostało ujednolicona, należy ją usunąć z zależności, takich jak segmenty, miary, wzbogacenia lub relacje.

1. Po usunięciu wszystkich zależności encji przejdź do pozycji **Dane** > **Ujednolicanie**.

1. Wybierz **Edytuj** na kafelku **Ujednolicone pola klientów**.

1. Wybierz wszystkie pola dla encji, a następnie wybierz pozycję **Wyklucz**.

   :::image type="content" source="media/m3_remove_entity1.png" alt-text="Zrzut ekranu ujednoliconych pól z zaznaczonymi wszystkimi polami dla encji i przyciskiem Wyklucz":::

1. Wybierz pozycję **Gotowe**, aby potwierdzić, a następnie wybierz **Zapisz i zamknij**.

   > [!TIP]
   > Jeśli zostanie wyświetlony komunikat „Nie można zapisać ujednolicenia. Nie można zmodyfikować ani usunąć określonego zasobu z powodu wcześniejszych zależności”, encja jest nadal używana we wcześniejszej zależności.

1. Wybierz **Edytuj** na kafelku **Duplikaty rekordów**.

1. Usuń wszystkie reguły z encji, jeśli istnieją, a następnie wybierz opcję **Dalej**.

1. Na stronie **Pasujące warunki** wybierz encję, a następnie wybierz opcję **Usuń**.

   :::image type="content" source="media/m3_remove_entity2.png" alt-text="Zrzut ekranu pasujących warunków z zaznaczoną encją i przyciskiem Usuń":::

1. Wybierz **Zapisz i zamknij**.

1. Wybierz **Edytuj** na kafelku **Pola źródłowe**.

1. Wybierz pozycję **Wybierz encje i pola** i wyczyść pole wyboru obok każdej encji.

   :::image type="content" source="media/m3_remove_entity3.png" alt-text="Zrzut ekranu przedstawiający okno dialogowe Wybieranie encji i pól z wyczyszczonym polem wyboru encji":::

1. Wybierz **Zastosuj**.

1. Wybierz **Zapisz i zamknij**.

1. Wybierz pozycję **Ujednolicanie** > **Ujednolić profile i zależności klientów**, aby zaktualizować ujednolicony profil.

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

   1. Wybierz pozycję **Gotowe**.

1. Wybierz **Następny**, aby wprowadzić zmiany w warunkach dopasowania, lub wybierz **Zapisz i zamknij** i wróć do [Aktualizuj ustawienia ujednolicenia](#update-unification-settings)

## <a name="manage-match-rules"></a>Zarządzanie regułami dopasowania

Większość parametrów dopasowania można ponownie skonfigurować i odpowiednio dostosować. Nie możesz dodawać ani usuwać encji. Reguły dopasowania nie odnoszą się do pojedynczej jednostki.

1. Wybierz **Edytuj** na kafelku **Warunki dopasowania**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Zrzut ekranu strony z zasadami i warunkami meczu oraz statystykami." lightbox="media/m3_match_edit.png":::

   Na stronie wyświetlana jest kolejność dopasowania i zdefiniowane reguły oraz następujące statystyki:
   - **Unikatowe rekordy źródłowe** — liczba poszczególnych rekordów źródłowych przetworzonych w ostatnim uruchomieniu dopasowania.
   - **Rekordy dopasowane i niedopasowane** — liczba wskazująca, ile unikatowych rekordów pozostaje po przetworzeniu reguł dopasowania.
   - **Tylko rekordy dopasowane** — liczba dopasowań we wszystkich parach dopasowania.

1. Aby wyświetlić wyniki wszystkich reguł i ich punktację, wybierz **Zobacz ostatnie uruchomienie**. Zostaną wyświetlone wyniki, w tym identyfikatory zastępczych kontaktów. Możesz pobrać wyniki.

1. Aby zobaczyć wyniki i punktację danej reguły, wybierz regułę, a następnie **Przegląd**. Wyświetlone zostaną wyniki. Możesz pobrać wyniki.

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

1. Wybierz **Następny**, aby wprowadzić zmiany w ujednoliconych polach, lub wybierz **Zapisz i zamknij** i wróć do [Aktualizuj ustawienia ujednolicenia](#update-unification-settings)

## <a name="manage-unified-fields"></a>Zarządzaj polami ujednoliconymi

1. Wybierz **Edytuj** na kafelku **Ujednolicone pola klientów**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Zrzut ekranu ujednoliconych pól klienta":::

1. Przejrzyj pola połączone i wykluczone i wprowadź ewentualne zmiany. Dodaj lub edytuj klucz CustomerID lub pogrupuj profile w klastry. Aby uzyskać więcej informacji, zobacz temat [Ujednolicenie pól klientów](merge-entities.md).

1. W przypadku klientów lub kont wybierz opcję **Dalej**, aby przejrzeć i [zaktualizować ujednolicony profil i zależności](#run-updates-to-the-unified-profile). Możesz też wybrać **Zapisz i zamknij** i wróć do [Zaktualizuj ustawienia ujednolicenia](#update-unification-settings), by wprowadzić więcej zmian.

   W przypadku kontaktów wybierz opcję **Dalej**, aby zarządzać polami pochyłymi. Możesz też wybrać **Zapisz i zamknij** i wróć do [Zaktualizuj ustawienia ujednolicenia](#update-unification-settings), by wprowadzić więcej zmian.

## <a name="manage-semantic-fields-for-unified-contacts"></a>Zarządzaj polami semantycznymi dla ujednoliconych kontaktów

1. Wybierz **Edytuj** na kafelku **Pola semantyczne**.

1. Aby zmienić typ analizy dla ujednoliconego pola, wybierz nowy typ. Aby uzyskać więcej informacji, zobacz [Zdefiniuj pola semantyczne dla ujednoliconych kontaktów](data-unification-contacts.md#define-the-semantic-fields-for-unified-contacts).

1. Wybierz **Następny**, aby zarządzać kontem i relacją z kontaktem, lub wybierz **Zapisz i zamknij** i wróć do [Aktualizuj ustawienia ujednolicenia](#update-unification-settings), aby wprowadzić więcej zmian.

## <a name="manage-contact-and-account-relationships"></a>Zarządzaj kontaktami i relacjami z kontem

1. Wybierz **Edytuj** na kafelku **Relacje**.

1. Aby zmienić kontakt i relację z kontem, zmień dowolne z następujących informacji:

   - **Klucz obcy od podmiotu kontaktowego**: Wybierz atrybut, który łączy Twój podmiot kontaktowy z kontem.
   - **Do encji konta**: wybierz encję klienta skojarzoną z kontaktem.

1. Wybierz **Dalej**, aby przejrzeć ustawienia ujednolicenia i [zaktualizować profil ujednolicony i zależności](#run-updates-to-the-unified-profile), lub wybierz **Zapisz i zamknij** i wróć do [Aktualizuj ustawienia ujednolicenia](#update-unification-settings), aby wprowadzić więcej zmian.

## <a name="run-matching-conditions"></a>Uruchom warunki dopasowania

Uruchamianie dopasowanych warunków tylko uruchamia ponowną duplikację i reguły dopasowania oraz aktualizuje encje *Ponowną duplikacją* i *ConflationMatchPair*.

1. Na stronie **Dane** > **Ujednolicenie** wybierz **Uruchamiaj tylko pasujące warunki**.

   Na kafelkach **Duplikaty rekordów** i **Pasujące warunki** znajdują się **Kolejka** lub stan **Odświeżanie**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Kiedy proces dopasowania zostanie zakończony, wybierz **Edytuj** na kafelku **Warunki dopasowania**.

   :::image type="content" source="media/match-KPIs.png" alt-text="Przycięty zrzut ekranu przedstawiający kluczowe metryki na stronie dopasowania z liczbami i szczegółami.":::

1. Aby wprowadzić zmiany, zobacz [Zarządzaj regułami deduplikacji](#manage-deduplication-rules) lub [Zarządzaj regułami dopasowania](#manage-match-rules).

1. Uruchom ponownie proces dopasowania lub [przeprowadź aktualizację profilu](#run-updates-to-the-unified-profile).

## <a name="run-updates-to-the-unified-profile"></a>Uaktualnia ujednolicony profil

- Aby uruchomić pasujące warunki i zaktualizować ujednoliconą encję profilu *bez* wpływających na zależności (takie jak karty klientów, wzbogacenia, segmenty lub miary), wybierz **Ujednolicenie profili klientów**. W przypadku kont wybierz opcję **Ujednolicenie kont** > **Ujednolicenie profili**. W przypadku kontaktów wybierz **Ujednolicenie kontaktów (podgląd)** > **Ujednolicenie profili**. Zależne procesy nie są uruchamiane, ale będą odświeżane zgodnie z [definicją w harmonogramie odświeżania](schedule-refresh.md).
- Aby uruchomić pasujące warunki, zaktualizuj ujednolicony profil i uruchom wszystkie zależności, wybierz **Ujednolicenie profili i zależności klientów**. Wszystkie procesy są wznawiane automatycznie. W przypadku kont i kontaktów wybierz **Ujednolicenie kont** > **Ujednolicenie profili i zależności**. Warunki dopasowania są uruchamiane zarówno dla kont, jak i kontaktów aktualizujących oba ujednolicone profile i uruchamiane są wszystkie inne zależności.

Wszystkie kafelki poza **Pola źródła** pokazują **W kolejce** lub **Odświeżanie**.

[!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Wyniki udanego uruchomienia są wyświetlane na stronie **Ujednolicanie**, pokazując liczbę ujednoliconych profili.
