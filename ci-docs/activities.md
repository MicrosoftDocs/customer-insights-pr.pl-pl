---
title: Działania związane z klientami lub kontaktami biznesowymi
description: Definiowanie działań klientów i wyświetlanie ich na osi czasu w profilach klientów.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: bbb8bc30d079273bc935181c628915bb3c02d982
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304118"
---
# <a name="customer-or-business-contact-activities"></a>Działania związane z klientami lub kontaktami biznesowymi

Działania klienta to akcje lub zdarzenia wykonywane przez klientów lub kontakty biznesowe. Na przykład transakcje, czas trwania połączenia pomocy technicznej, recenzje witryn, zakupy lub zwroty. Te działania są zawarte w co najmniej jednym źródle danych. Dzięki Customer Insights skonsoliduj działania klientów na podstawie tych [źródeł danych](data-sources.md) i powiąż je z profilami klientów. Działania te pojawiają się chronologicznie na osi czasu na profilu klienta. Uwzględnij oś czasu w aplikacjach Dynamics 365 za pomocą rozwiązania [Dodatek kart klientów](customer-card-add-in.md).

## <a name="define-a-customer-activity"></a>Zdefiniuj działania klientów

Encja musi zawierać co najmniej jeden atrybut typu **Data**, który ma zostać uwzględniony na osi czasu klienta. Formant **Dodaj działanie** jest wyłączany jeśli nie zostanie znaleziona taka encja.

1. Wybierz pozycję **Dane** > **Działania**.

1. Wybierz opcję **Dodaj działanie**, aby uruchomić środowisko nadzorowane.

1. W kroku **Dane dotyczące działania** wpisz następujące informacje:

   - **Nazwa działania**: wybierz nazwę działania.
   - **Encja działań**: Wybierz encję zawierającą dane transakcyjne lub działania.
   - **Klucz podstawowy**: Wybierz pole, które jednoznacznie identyfikuje rekord. Nie może ono zawierać żadnych powielonych wartości, pustych wartości ani brakujących wartości.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Skonfiguruj dane działań za pomocą nazwy, encji i klucza podstawowego.":::

1. Wybierz **Dalej**.

1. W kroku **Relacja** wybierz **Dodaj relację**, aby połączyć dane dotyczące aktywności z odpowiednim rekordem klienta. Ten krok obrazuje połączenie między encjami.  

   - **Obcy klucz**: pole obce w encji działania, które będzie używane do ustanowienia relacji z inną encją.
   - **Do nazwy encji**: odpowiadająca jej encja klienta źródłowego, z którą encja działania będzie w relacji. Można utworzyć relację tylko z encjami klienta źródłowego, które są używane w procesie ujednolicania danych.
   - **Nazwa relacji**: Jeśli relacja między tą encją działania a wybraną encją źródłową klienta już istnieje, nazwa relacji zostanie wyświetlona w trybie tylko do odczytu. Jeśli taka relacja nie istnieje, zostanie utworzona nowa relacja z nazwą podaną w tym polu.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definiowanie relacji encji.":::

   > [!TIP]
   > W środowiskach B2B można wybrać między encją kont a innymi encjami. Po wybraniu encji konta ścieżka relacji jest ustawiana automatycznie. W przypadku innych encji należy zdefiniować ścieżkę relacji dla jednej lub większej liczby encji pośrednich do momentu osiągnięcia encji klienta.

1. Wybierz pozycję **Zastosuj**, aby utworzyć relację.

1. Wybierz **Dalej**.

1. W kroku **Ujednolicanie działania** wybierz zdarzenie działania i czas rozpoczęcia działania.
   - **Pola wymagane**
      - **Działanie zdarzenia**: pole, które jest zdarzeniem tego działania.
      - **Sygnatura czasowa**: pole reprezentujące czas rozpoczęcia działania.

   - **Pola opcjonalne**
      - **Dodatkowe szczegóły**: pole z odpowiednimi informacjami dla tego działania.
      - **Ikona**: ikona najlepiej reprezentująca ten typ działania.
      - **Adres internetowy**: pole zawierające adres URL z informacjami o tym działaniu. Na przykład system transakcyjny, który zawiera źródło tego działania. Ten adres URL może być dowolnym polem ze źródła danych lub może być skonstruowany jako nowe pole za pomocą transformacji usługi Power Query. Dane adresu URL będą przechowywane w encji *Ujednolicone działanie*, która może być konsumowana w dół przy użyciu [interfejsów API](apis.md).

   - **Pokaż na osi czasu**
      - Wybierz, czy chcesz pokazywać to działanie w widoku osi czasu profilów Twoich klientów. Wybierz opcję **Tak**, aby pokazać działanie na osi czasu, lub opcję **Nie**, aby je ukryć.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Określ dane działań klienta w encji Ujednolicone działanie.":::

1. Wybierz **Dalej**, aby wybrać typ aktywności, lub **Zakończ i sprawdź**, aby zapisać aktywność z typem aktywności ustawionym na **Inna**.

1. W kroku **Typ działania** wybierz typ działania i, opcjonalnie, wybierz, czy chcesz etapami mapować niektóre typy działań do użycia w innych obszarach programu Customer Insights. Typy działań typu *Opinie*, *Lojalność*, *ZamówienieSprzedaży*, *WierszZamówieniaSprzedaży* i *Subskrypcja* obsługują obecnie obszary po uzgodnieniu mapowania pól. Jeśli typ działania nie jest odpowiedni dla nowego działania, można wybrać opcję *Inne* lub *Utwórz nowe* dla niestandardowego typu działania.

1. Wybierz **Dalej**.

1. W kroku **Przegląd** sprawdź wybór. Wróć do każdego z poprzednich kroków i w razie potrzeby zaktualizuj informacje.

1. Wybierz opcję **Zapisz działanie**, aby zastosować zmiany i wybierz opcję **Wykonane**, aby wrócić do **Dane** > **Działania**. Zostanie wyświetlone utworzone działanie.

1. Po utworzeniu wszystkich działań wybierz opcję **Uruchom**, aby je przetworzyć.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-customer-activities"></a>Zarządzanie istniejącymi działaniami

Przejdź do **Dane** > **Działania**, aby wyświetlić zapisane działania, ich źródłową encję, typ działania i czy są uwzględnione na osi czasu klienta. Możesz posortować listę działań według dowolnej kolumny lub skorzystać z pola wyszukiwania, aby znaleźć działanie, którym chcesz zarządzać.

Wybierz aktywność, aby wyświetlić dostępne działania.

- **Edytować** działanie, aby zmienić jego konfigurację. Konfiguracja otwiera się na etapie przeglądu. Po zmianie konfiguracji wybierz opcję **Zapisz działanie**, a następnie wybierz opcję **Uruchom**, aby przetworzyć zmiany.
- **Zmień nazwę** działania. Wybierz pozycję **Zapisz**, aby zastosować zmiany.
- **Usuń** działanie. Aby usunąć więcej niż jedną aktywność naraz, wybierz aktywności, a następnie **Usuń**. Potwierdź usunięcie.

## <a name="view-activity-timelines-on-customer-profiles"></a>Wyświetlanie osi czasu działań w profilach klientów

1. Jeśli wybrałeś **Pokaż na osi czasu działania** w konfiguracji działania, przejdź do **Klienci** i wybierz profil klienta, aby wyświetlić działania klienta w sekcji **Oś czasu działania**.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Wyświetlanie skonfigurowanych działań w profilach klientów.":::

1. Aby filtrować aktywności na osi czasu aktywności:

   - Wybierz jedną lub więcej ikon aktywności, aby zawęzić wyniki i uwzględnić tylko wybrane typy.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtrowanie działań według typów przy użyciu ikon.":::

   - Wybierz opcję **Filtruj**, aby otworzyć panel filtrów w celu skonfigurowania filtrów osi czasu. Można filtrować według *ActivityType* i *Daty*. Wybierz **Zastosuj**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Używanie panelu filtrów do konfigurowania warunków filtrowania.":::

> [!NOTE]
> Filtry działań są usuwane po opuszczeniu profilu klienta. Należy je stosować po każdym otwarciu ich w profilu klienta.

## <a name="define-a-contact-activity"></a>Zdefiniuj działania klientów

W przypadku kont firmowych (od B do B) użyj encji *ContactProfile*, aby rejestrować działania kontaktów. Dzięki temu możesz zobaczyć na osi czasu aktywności na koncie, który kontakt był odpowiedzialny za poszczególne aktywności. Większość kroków jest zgodna z typową konfiguracją mapowania aktywności.

   > [!NOTE]
   > Aby zdefiniować działanie na poziomie kontaktu, *musi zostać utworzona encja ContactProfile*, zarówno jako [ujednolicony profil kontaktu](data-unification-contacts.md), [jak i mapowanie mapowań mapowań](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).
   >
   > Musisz posiadać oba atrybuty **AccountID** i **ContactID** dla każdego rekordu w danych aktywności.
  
1. Wybierz pozycję **Dane** > **Działania**.

1. Wybierz **Dodaj działanie**.

1. Nazwij aktywność, wybierz źródłową encję aktywności i wybierz klucz główny encji aktywności.

1. W kroku **Relacje** utwórz pośrednią relację między danymi źródłowymi aktywności a kontami, używając danych kontaktowych jako jednostki pośredniczącej. Aby uzyskać więcej informacji, przejdź do [ścieżek relacji bezpośredniej i pośredni](relationships.md#relationship-paths).
   - Przykładowa relacja dla działania o nazwie *Zakupy*:
      - **Dane aktywności Źródła Zakupów** > **Dane kontaktowe** na atrybucie **ContactID**
      - **Dane kontaktu** > **Dane konta** na atrybucie **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Przykładowa konfiguracja relacji.":::

1. Po ustawieniu relacji wybierz **Dalej** i zakończ konfigurację mapowania aktywności. Szczegółowe kroki dotyczące tworzenia aktywności znajdziesz w dziale [definiowanie aktywności klienta](#define-a-customer-activity).

1. Uruchom swoje mapowania aktywności.

1. Twoje działania na poziomie kontaktu będą teraz widoczne na Twojej osi czasu klienta.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Wynik końcowy po skonfigurowaniu działań kontaktowych":::

## <a name="contact-level-activity-timeline-filtering"></a>Filtrowanie osi czasu aktywności na poziomie kontaktu

Po skonfigurowaniu mapowania aktywności na poziomie kontaktu i uruchomieniu go, oś czasu aktywności dla twoich klientów zostanie zaktualizowana. Zawiera ich identyfikatory lub imiona, w zależności od konfiguracji twojego *ContactProfile*, dla działań, które podjęli. Możesz filtrować aktywności według kontaktów na osi czasu, aby zobaczyć konkretne kontakty, które Cię interesują. Dodatkowo możesz zobaczyć wszystkie aktywności, które nie są przypisane do konkretnego kontaktu, wybierając **Aktywności nieprzypisane do kontaktu**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Opcje filtrowania dostępne dla aktywności na poziomie kontaktu.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
