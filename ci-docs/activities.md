---
title: Działania klienta
description: Definiowanie działań klientów i wyświetlanie ich na osi czasu w profilach klientów.
ms.date: 07/22/2022
ms.subservice: audience-insights
ms.reviewer: mhart
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
- customerInsight
ms.openlocfilehash: cc21b0eeb368156437e60d851c2d144f3974c066
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188152"
---
# <a name="customer-activities"></a>Działania klienta

Działania klienta to akcje lub zdarzenia wykonywane przez klientów. Na przykład transakcje, czas trwania połączenia pomocy technicznej, recenzje witryn, zakupy lub zwroty. Te działania są zawarte w co najmniej jednym źródle danych. Dzięki Customer Insights skonsoliduj działania klientów na podstawie tych [źródeł danych](data-sources.md) i powiąż je z profilami klientów. Działania te pojawiają się chronologicznie na osi czasu na profilu klienta. Uwzględnij oś czasu w aplikacjach Dynamics 365 za pomocą rozwiązania [Dodatek kart klientów](customer-card-add-in.md).

## <a name="define-an-activity"></a>Definiuj działanie

Encja musi zawierać co najmniej jeden atrybut typu **Data**, który ma zostać uwzględniony na osi czasu klienta. Formant **Dodaj działanie** jest wyłączany jeśli nie zostanie znaleziona taka encja.

1. Wybierz pozycję **Dane** > **Działania**.

1. Wybierz opcję **Dodaj działanie**, aby uruchomić środowisko nadzorowane.

1. W kroku **Dane dotyczące działania** wpisz następujące informacje:

   - **Nazwa działania**: nazwa działania.
   - **Encja działania**: encja zawierającą dane transakcyjne lub działania.
   - **Klucz podstawowy**: pole, które jednoznacznie identyfikuje rekord. Nie może ono zawierać żadnych powielonych wartości, pustych wartości ani brakujących wartości.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Skonfiguruj dane działań za pomocą nazwy, encji i klucza podstawowego.":::

1. Wybierz **Dalej**.

1. W kroku **Relacja** wybierz **Dodaj relację**, aby połączyć dane dotyczące aktywności z odpowiednim rekordem klienta. Ten krok obrazuje połączenie między encjami.  

   - **Klucz obcy z encji**: pole w encji aktywności, które będzie używane do nawiązania relacji z inną encją.
   - **Do nazwy encji**: odpowiadająca jej encja klienta źródłowego, z którą encja działania będzie w relacji. Można utworzyć relację tylko z encjami klienta źródłowego, które są używane w procesie ujednolicania danych.
   - **Nazwa relacji**: nazwa identyfikująca relację między encjiami. Jeśli relacja między tą encją działania a wybraną encją klienta źródłowego już istnieje, nazwa relacji będzie w trybie tylko do odczytu.

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

## <a name="manage-existing-activities"></a>Zarządzanie istniejącymi działaniami

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

1. Aby usunąć filtry, wybierz opcję **Wyczyść filtry** lub wybierz opcję **Filtruj** i wyczyść pole wyboru filtru.

> [!NOTE]
> Filtry działań są usuwane po opuszczeniu profilu klienta. Należy je stosować po każdym otwarciu ich w profilu klienta.

[!INCLUDE [footer-include](includes/footer-banner.md)]
