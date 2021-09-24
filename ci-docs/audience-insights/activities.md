---
title: Działania klienta
description: Definiowanie działań klientów i wyświetlanie ich na osi czasu w profilach klientów.
ms.date: 09/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: c5697df8a7d011c70384c8bc5e4773d7fcc25a62
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494424"
---
# <a name="customer-activities"></a>Działania klienta

Łącząc działania klientów z [różnych źródeł danych](data-sources.md) w Dynamics 365 Customer Insights do tworzenia osi czasu, będącej listą działań Dodawaj oś czasu w aplikacjach usługi Dynamics 365 za pomocą rozwiązania [dodatku Customer Card](customer-card-add-in.md) lub pulpitu nawigacyjnego Power BI.

## <a name="define-an-activity"></a>Definiuj działanie

Źródła danych mogą zawierać encje z danymi transakcyjnymi i danymi działań z wielu źródeł danych. Zidentyfikuj te encje i wybierz działania, które mają być wyświetlane na osi czasu klienta. Wybierz encję zawierającą docelowe działanie lub działania.

> [!NOTE]
> Encja musi zawierać co najmniej jeden atrybut typu **Data**, który ma zostać uwzględniony na osi czasu klienta, i nie można dodawać encji bez pól **Data**. Formant **Dodaj działanie** jest wyłączany jeśli nie zostanie znaleziona taka encja.

1. W analizach odbiorców przejdź do **Dane** > **Działania**.

1. Wybierz opcję **Dodaj działanie**, aby rozpocząć proces konfigurowania działania z przewodnikiem.

1. W kroku **Dane działania** ustaw wartości następujących pól:

   - **Nazwa działania**: wybierz nazwę działania.
   - **Encja**: Wybierz encję zawierającą dane transakcyjne lub działania.
   - **Klucz podstawowy**: Wybierz pole, które jednoznacznie identyfikuje rekord. Nie może ono zawierać żadnych powielonych wartości, pustych wartości ani brakujących wartości.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Skonfiguruj dane działań za pomocą nazwy, encji i klucza podstawowego.":::

1. Wybierz pozycję **Dalej**, aby przejść do następnego kroku.

1. W kroku **Relacja** skonfiguruj szczegóły, aby połączyć dane działań z odpowiednim klientem. Ten krok obrazuje połączenie między encjami.  

   - **Pierwszy**: pole obce w encji działania, które będzie używane do ustanowienia relacji z inną encją.
   - **Drugi**: odpowiadająca jej encja klienta źródłowego, z którą encja działania będzie w relacji. Można utworzyć relację tylko z encjami klienta źródłowego, które są używane w procesie ujednolicania danych.
   - **Trzeci**: jeśli relacja między tą encją działania a wybraną encją klienta źródłowego już istnieje, nazwa relacji będzie w trybie tylko do odczytu. Jeśli taka relacja nie istnieje, zostanie utworzona nowa relacja z nazwą podaną w tym polu.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definiowanie relacji encji.":::

1. Wybierz pozycję **Dalej**, aby przejść do następnego kroku. 

1. W kroku **Ujednolicanie działania** wybierz zdarzenie działania i czas rozpoczęcia działania. 
   - **Pola wymagane**
      - **Działanie zdarzenia**: pole, które jest zdarzeniem tego działania.
      - **Sygnatura czasowa**: pole reprezentujące czas rozpoczęcia działania.

   - **Pola opcjonalne**
      - **Dodatkowe szczegóły**: pole z odpowiednimi informacjami dla tego działania.
      - **Ikona**: ikona najlepiej reprezentująca ten typ działania.
      - **Adres internetowy**: pole zawierające adres URL z informacjami o tym działaniu. Na przykład system transakcyjny, który zawiera źródło tego działania. Ten adres URL może być dowolnym polem ze źródła danych lub może być skonstruowany jako nowe pole przy użyciu przekształcenia Power Query. Dane adresu URL będą przechowywane w encji *Ujednolicone działanie*, która może być konsumowana w dół przy użyciu [interfejsów API](apis.md).

   - **Pokaż na osi czasu**
      - Wybierz, czy chcesz pokazywać to działanie w widoku osi czasu profilów Twoich klientów. Wybierz opcję **Tak**, aby pokazać działanie na osi czasu, lub opcję **Nie**, aby je ukryć.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Określ dane działań klienta w encji Ujednolicone działanie.":::

1. Wybierz pozycję **Dalej**, aby przejść do następnego kroku. Aby zapisać teraz działanie z typem działania ustawionym jako **Inne**, można wybrać opcję **Zakończ i przejrzyj**. 

1. W kroku **Typ działania** wybierz typ działania i, opcjonalnie, wybierz, czy chcesz etapami mapować niektóre typy działań do użycia w innych obszarach programu Customer Insights. Obecnie typy działań *Opinia*, *Lojalność*, *SalesOrder*, *SalesOrderLine* i *Subskrypcja* mogą być mapowane semantycznie po uzgodnieniu mapowania pól. Jeśli typ działania nie jest odpowiedni dla nowego działania, można wybrać opcję *Inne* lub *Utwórz nowe* dla niestandardowego typu działania.

1. Wybierz pozycję **Dalej**, aby przejść do następnego kroku. 

1. W kroku **Przegląd** sprawdź wybór. Wróć do każdego z poprzednich kroków i w razie potrzeby zaktualizuj informacje.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Przeglądanie określonych pól dla działania.":::
   
1. Wybierz opcję **Zapisz działanie**, aby zastosować zmiany i wybierz opcję **Wykonane**, aby wrócić do **Dane** > **Działania**. Tutaj możesz zobaczyć, które działania mają być wyświetlane na osi czasu. 

1. Na stronie **Działania** wybierz opcję **Uruchom**, aby przetworzyć działanie. 

> [!TIP]
> Istnieje [sześć typów stanu](system.md#status-types) zadań/procesów. Ponadto większość procesów [zależy od innych procesów podrzędnych](system.md#refresh-policies). Istnieje możliwość wybrania stanu procesu w celu wyświetlenia szczegółowych informacji o postępie w całym zadaniu. Po wybraniu opcji **Zobacz szczegółowe informacje** dla jednego z zadań zadania, można znaleźć więcej informacji: czas przetwarzania, Data ostatniego przetwarzania oraz wszystkie błędy i ostrzeżenia skojarzone z zadaniem.


## <a name="manage-existing-activities"></a>Zarządzanie istniejącymi działaniami

W **Dane** > **Działania** można wyświetlić wszystkie zapisane działania i nimi zarządzać. Każde działanie jest reprezentowane przez wiersz, który zawiera także szczegółowe informacje o źródle, encji i typie działania.

Po wybraniu działania są dostępne następujące akcje. 

- **Edycja**: powoduje otwarcie konfiguratowa działania w kroku przeglądu. W tym kroku można zmienić dowolną lub całą bieżącą konfigurację. Po zmianie konfiguracji wybierz opcję **Zapisz działanie**, a następnie wybierz opcję **Uruchom**, aby przetworzyć zmiany.

- **Zmień nazwę**: Otwiera okno dialogowe, w którym można wprowadzić inną nazwę wybranego działania. Wybierz pozycję **Zapisz**, aby zastosować zmiany.

- **Usuń**: otwiera okno dialogowe w celu potwierdzenia usunięcia wybranego działania. Możesz także usunąć wiele działań jednocześnie, zaznaczając działania i wybierając ikonę usuwania. Aby potwierdzić usunięcie, wybierz opcję **Usuń**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
