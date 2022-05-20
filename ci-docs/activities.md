---
title: Działania klienta
description: Definiowanie działań klientów i wyświetlanie ich na osi czasu w profilach klientów.
ms.date: 11/01/2021
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
ms.openlocfilehash: 6c0a1bc5d9a42806b458142804199c733ff530ec
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755511"
---
# <a name="customer-activities"></a>Działania klienta

Łączenie działań klientów z [różnych źródeł danych](data-sources.md) w Dynamics 365 Customer Insights. Stwórz oś czasu, na której umieścisz chronologicznie wszystkie działania. Uwzględnij oś czasu w aplikacjach Dynamics 365 za pomocą rozwiązania [Dodatek kart klientów](customer-card-add-in.md).

## <a name="define-an-activity"></a>Definiuj działanie

Źródła danych mogą zawierać encje z danymi transakcyjnymi i danymi działań z wielu źródeł danych. Zidentyfikuj te encje i wybierz działania, które mają być wyświetlane na osi czasu klienta. Wybierz encję zawierającą docelowe działanie lub działania.

Encja musi zawierać co najmniej jeden atrybut typu **Data**, który ma zostać uwzględniony na osi czasu klienta, i nie można dodawać encji bez pól **Data**. Formant **Dodaj działanie** jest wyłączany jeśli nie zostanie znaleziona taka encja.

1. Wybierz pozycję **Dane** > **Działania**.

1. Wybierz opcję **Dodaj działanie**, aby rozpocząć proces konfigurowania działania z przewodnikiem.

1. W kroku **Dane działania** ustaw wartości następujących pól:

   - **Nazwa działania**: wybierz nazwę działania.
   - **Encja**: Wybierz encję zawierającą dane transakcyjne lub działania.
   - **Klucz podstawowy**: Wybierz pole, które jednoznacznie identyfikuje rekord. Nie może ono zawierać żadnych powielonych wartości, pustych wartości ani brakujących wartości.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Skonfiguruj dane działań za pomocą nazwy, encji i klucza podstawowego.":::

1. Wybierz pozycję **Dalej**, aby przejść do następnego kroku.

1. W kroku **Relacja** skonfiguruj szczegóły, aby łączyć dane działania z odpowiadającym im rekordem klienta. Ten krok obrazuje połączenie między encjami.  

   - **Pierwszy**: pole obce w encji działania, które będzie używane do ustanowienia relacji z inną encją.
   - **Drugi**: odpowiadająca jej encja klienta źródłowego, z którą encja działania będzie w relacji. Można utworzyć relację tylko z encjami klienta źródłowego, które są używane w procesie ujednolicania danych.
   - **Trzeci**: jeśli relacja między tą encją działania a wybraną encją klienta źródłowego już istnieje, nazwa relacji będzie w trybie tylko do odczytu. Jeśli taka relacja nie istnieje, zostanie utworzona nowa relacja z nazwą podaną w tym polu.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definiowanie relacji encji.":::

   > [!TIP]
   > W środowiskach B2B można wybrać między encją kont a innymi encjami. Po wybraniu encji konta ścieżka relacji jest ustawiana automatycznie. W przypadku innych encji należy zdefiniować ścieżkę relacji dla jednej lub większej liczby encji pośrednich do momentu osiągnięcia encji klienta.

1. Wybierz pozycję **Dalej**, aby przejść do następnego kroku. 

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

1. Wybierz pozycję **Dalej**, aby przejść do następnego kroku. Aby zapisać teraz działanie z typem działania ustawionym jako **Inne**, można wybrać opcję **Zakończ i przejrzyj**. 

1. W kroku **Typ działania** wybierz typ działania i, opcjonalnie, wybierz, czy chcesz etapami mapować niektóre typy działań do użycia w innych obszarach programu Customer Insights. Typy działań typu *Opinie*, *Lojalność*, *ZamówienieSprzedaży*, *WierszZamówieniaSprzedaży* i *Subskrypcja* obsługują obecnie obszary po uzgodnieniu mapowania pól. Jeśli typ działania nie jest odpowiedni dla nowego działania, można wybrać opcję *Inne* lub *Utwórz nowe* dla niestandardowego typu działania.

1. Wybierz pozycję **Dalej**, aby przejść do następnego kroku. 

1. W kroku **Przegląd** sprawdź wybór. Wróć do każdego z poprzednich kroków i w razie potrzeby zaktualizuj informacje.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Przeglądanie określonych pól dla działania.":::
   
1. Wybierz opcję **Zapisz działanie**, aby zastosować zmiany i wybierz opcję **Wykonane**, aby wrócić do **Dane** > **Działania**. Tutaj możesz zobaczyć, które działania mają być wyświetlane na osi czasu. 

1. Na stronie **Działania** wybierz opcję **Uruchom**, aby przetworzyć działanie. 

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Zarządzanie istniejącymi działaniami

W **Dane** > **Działania** można wyświetlić wszystkie zapisane działania i nimi zarządzać. Każde działanie jest reprezentowane przez wiersz, który zawiera także szczegółowe informacje o źródle, encji i typie działania.

Po wybraniu działania są dostępne następujące akcje. 

- **Edycja**: powoduje otwarcie konfiguratowa działania w kroku przeglądu. W tym kroku można zmienić dowolną lub całą bieżącą konfigurację. Po zmianie konfiguracji wybierz opcję **Zapisz działanie**, a następnie wybierz opcję **Uruchom**, aby przetworzyć zmiany.

- **Zmień nazwę**: Otwiera okno dialogowe, w którym można wprowadzić inną nazwę wybranego działania. Wybierz pozycję **Zapisz**, aby zastosować zmiany.

- **Usuń**: otwiera okno dialogowe w celu potwierdzenia usunięcia wybranego działania. Możesz także usunąć wiele działań jednocześnie, zaznaczając działania i wybierając ikonę usuwania. Aby potwierdzić usunięcie, wybierz opcję **Usuń**.

## <a name="view-activity-timelines-on-customer-profiles"></a>Wyświetlanie osi czasu działań w profilach klientów

Po skonfigurowaniu działań klienta wybierz opcję **Pokaż na osi czasu działań** w konfiguracji działania, aby znaleźć wszystkie działania klienta w jego profilu klienta.

Aby otworzyć oś czasu dla klienta, wybierz pozycję **Klienci** i wybierz profil klienta, który chcesz wyświetlić.

Jeśli klient uczestniczył w skonfigurowanej aktywności, znajdziesz to w sekcji **Oś czasu działania**.

:::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Wyświetlanie skonfigurowanych działań w profilach klientów.":::

Istnieje kilka sposobów filtrowania działań na osi czasu działań:

- Aby uściślić wyniki i uwzględnić tylko wybrane typy, można wybrać jedną lub wiele ikon działań.

  :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtrowanie działań według typów przy użyciu ikon.":::

- Możesz wybrać opcję **Filtruj**, aby otworzyć panel filtrów w celu skonfigurowania filtrów osi czasu.

   1. Można filtrować według *typu działania* i *daty*
   1. Wybierz opcję **Zastosuj**, aby używać filtrów na osi czasu działania.

   :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Używanie panelu filtrów do konfigurowania warunków filtrowania.":::

Aby usunąć filtry, wybierz **x** obok każdego filtru zastosowanego do osi czasu lub wybierz opcję **Wyczyść filtry**.


> [!NOTE]
> Filtry działań są usuwane po opuszczeniu profilu klienta. Należy je stosować po każdym otwarciu ich w profilu klienta.

[!INCLUDE [footer-include](includes/footer-banner.md)]
