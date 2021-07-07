---
title: Spożycie danych za pośrednictwem łącznika Power Query
description: Łączniki źródeł danych oparte na Power Query.
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 50c231070ff9930c1ea82971bf4f8541a89d5027
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305904"
---
# <a name="connect-to-a-power-query-data-source"></a>Nawiązywanie połączenia ze źródłem danych Power Query

Power Query oferuje szeroki zestaw łączników do pozyskiwania danych. Większość z tych łączników jest obsługiwana przez Dynamics 365 Customer Insights. Dodawanie źródeł danych na podstawie łączników Power Query zazwyczaj przebiega zgodnie z krokami opisanymi w następnej sekcji. W zależności od używanego łącznika wymagane są jednak różne informacje. Aby uzyskać więcej informacji, zobacz dokumentację dla poszczególnych łączników w [Informacje na temat łączników Power Query](/power-query/connectors/).

## <a name="create-a-new-data-source"></a>Utwórz nowe źródło danych

1. W analizach odbiorców przejdź do **Dane** > **Źródła danych**.

1. Wybierz **Dodaj źródła danych**.

1. Wybierz metodę **importu danych** i wybierz **Dalej**.

1. Wprowadź **Nazwę** źródła danych i wybierz **Dalej**, aby utworzyć źródło danych. Wytyczne dotyczące nazw: 
   - Rozpocznij od litery.
   - Używaj tylko liter i liczb. Spacje i znaki specjalne są niedozwolone.
   - Użyj między 3 do 64 znaków.

1. Wybierz jeden z [dostępnych łączników](#available-power-query-data-sources). W tym przykładzie wybraliśmy łącznik **Tekst/CSV**.

1. Wprowadź wymagane informacje szczegółowe w **Ustawienia połączenia** dla wybranego łącznika i wybierz **Dalej**, aby wyświetlić podgląd danych.

1. Wybierz **Przekształć dane**. W tym kroku encje zostaną dodane do źródła danych. Encje są zestawami danych. Jeśli istnieje baza danych zawierająca wiele zestawów danych, każdy zestaw danych jest swoją własną encją.

1. Dialog **Power Query — edytuj zapytania** pozwala na przejrzenie i uściślenie danych. Encje, które zostały określone przez systemy w wybranych źródłach danych, są wyświetlane w lewym okienku.

   > [!div class="mx-imgBorder"]
   > ![Okno dialogowe Edytuj zapytania](media/data-manager-configure-edit-queries.png "Okno dialogowe Edytuj zapytania")

1. Dane można również przekształcać. Wybierz encję do edycji lub przekształcenia. Korzystając z opcji dostępnych w oknie Power Query, można stosować przekształcenia. Każde przekształcenie jest wyświetlane w obszarze **Zastosowane kroki**. Power Query oferuje wiele wstępnie wbudowanych opcji transformacji. Aby uzyskać więcej informacji, zobacz [Transformacje Power Query](/power-query/power-query-what-is-power-query#transformations).

1. Kolejne encje można dodać do źródła danych, wybierając polecenie **Pobierz dane** w oknie dialogowym **Edytuj zapytania**.

   Te przekształcenia są zdecydowanie zalecane:

   - Jeśli pozyskujesz dane z pliku CSV, pierwszy wiersz często zawiera nagłówki. Przejdź do **Przekształć tabelę** i wybierz **Użyj nagłówków jako pierwszego wiersza**.
   - Upewnij się, że typ danych jest odpowiednio ustawiony.

1. Wybierz **Zapisz** u dołu okna Power Query, aby zapisać przekształcenia. Po zapisaniu źródło danych będzie znajdować się w **Dane** > **Źródła danych**.

1. Na stronie **Źródła danych** zobaczysz, że nowe źródło danych jest w stanie **Odświeżanie**.

## <a name="available-power-query-data-sources"></a>Dostępne źródła danych Power Query

Sprawdź [Informacje na temat łączników Power Query](/power-query/connectors/), aby otrzymać aktualną listę łączników, które można wybrać w celu zaimportowania danych do usługi Customer Insights. 

Łączniki ze znacznikiem wyboru w kolumnie **Customer Insights (Przepływy danych)** są dostępne w celu utworzenia nowych źródeł danych na podstawie Power Query. Przejrzyj dokumentację określonego łącznika, aby dowiedzieć się więcej o jego wymaganiach wstępnych, ograniczeniach i innych szczegółach.

## <a name="edit-power-query-data-sources"></a>Edytuj źródła danych Power Query

> [!NOTE]
> Wprowadzenie zmian w źródłach danych, które są obecnie używane w jednym z procesów aplikacji (na przykład *segmentacja*, *dopasowywanie* lub *scalanie*) może być niemożliwe. 
>
> Przy użyciu strony **Ustawienia** można śledzić postępy wszystkich aktywnych procesów. Po zakończeniu procesu można powrócić do strony **Źródła danych** i wprowadzić zmiany.

1. W analizach odbiorców przejdź do **Dane** > **Źródła danych**.

2. Wybierz wielokropek pionowy obok źródła danych, które chcesz zmienić, i z menu rozwijanego wybierz pozycję **Edytuj**.

   > [!div class="mx-imgBorder"]
   > ![Opcja Edytuj](media/edit-option-data-sources.png "Opcja Edytuj")

3. Zastosuj zmiany i przekształcenia w oknie dialogowym **Power Query - edytuj zapytania**, jak to opisano w sekcji [Tworzenie nowego źródła danych](#create-a-new-data-source).

4. Wybierz **Zapisz** w Power Query po zakończeniu edycji, aby zapisać zmiany.


[!INCLUDE[footer-include](../includes/footer-banner.md)]