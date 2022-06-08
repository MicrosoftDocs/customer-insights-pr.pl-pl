---
title: Pozyskiwanie danych przez łącznik Power Query (zawiera wideo)
description: Łączniki dla źródeł danych na podstawie edytora Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 4db97ec02eb96662d30a8536ea42372f81f318d2
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800188"
---
# <a name="connect-to-a-power-query-data-source"></a>Łączenie ze źródłem danych Power Query

Edytor Power Query oferuje szeroki zestaw łączników służących do pozyskiwania danych. Większość z tych łączników jest obsługiwana przez Dynamics 365 Customer Insights. 

Dodawanie źródeł danych opartych na łącznikach Power Query zasadniczo przebiega zgodnie z krokami opisanymi w tym obszarze. W zależności od używanego łącznika wymagane są jednak różne informacje. Aby dowiedzieć się więcej, zobacz dokumentację poszczególnych łączników w temacie [Dokumentacja łączników Power Query](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Utwórz nowe źródło danych

1. Przejdź do **Dane** > **Źródła danych**.

1. Wybierz **Dodaj źródła danych**.

1. Wybierz opcję **Microsoft Power Query**.

1. Wprowadź **Nazwę** źródła danych i wybierz **Dalej**, aby utworzyć źródło danych.

1. Wybierz jeden z [dostępnych łączników](#available-power-query-data-sources). W tym przykładzie wybieramy łącznik **Text/CSV**.

1. Wprowadź wymagane informacje szczegółowe w **Ustawienia połączenia** dla wybranego łącznika i wybierz **Dalej**, aby wyświetlić podgląd danych.

1. Wybierz **Przekształć dane**. W tym kroku encje zostaną dodane do źródła danych. Encje są zestawami danych. Jeśli istnieje baza danych zawierająca wiele zestawów danych, każdy zestaw danych jest swoją własną encją.

1. Okno dialogowe **Power Query — edytowanie zapytań** umożliwia przeglądanie i precyzowanie danych. Encje, które zostały określone przez systemy w wybranych źródłach danych, są wyświetlane w lewym okienku.

   > [!div class="mx-imgBorder"]
   > ![Okno dialogowe Edytuj zapytania.](media/data-manager-configure-edit-queries.png "Okno dialogowe Edytuj zapytania")

1. Dane można również przekształcać. Wybierz encję do edycji lub przekształcenia. Użyj opcji dostępnych w oknie edytora Power Query, aby zastosować przekształcenia. Każde przekształcenie jest wyświetlane w obszarze **Zastosowane kroki**. Edytor Power Query zawiera wiele wstępnie zbudowanych opcji przekształceń. Aby uzyskać więcej informacji, zobacz [Przekształcenia w edytorze Power Query](/power-query/power-query-what-is-power-query#transformations).

   Zalecamy używanie następujących transformacji:

   - Jeśli pozyskujesz dane z pliku CSV, pierwszy wiersz często zawiera nagłówki. Przejdź do pozycji **Przekształć** i wybierz pozycję **Użyj pierwszego wiersza jako nagłówków**.
   - Upewnij się, że typ danych jest odpowiednio ustawiony. Na przykład w przypadku pól daty wybierz typ daty.

1. Aby dodać więcej encji do źródła danych w oknie dialogowym **Edytowanie zapytań** przejdź do obszaru **Strona główna** i wybierz opcję **Pobierz dane**.

1. Wybierz przycisk **Zapisz** na dole okna edytora Power Query, aby zapisać przekształcenia. Po zapisaniu źródło danych będzie znajdować się w **Dane** > **Źródła danych**.

1. Na stronie **Źródła danych** zobaczysz, że nowe źródło danych jest w stanie **Odświeżanie**.

## <a name="available-power-query-data-sources"></a>Dostępne źródła danych edytora Power Query

Zobacz [dokumentację dotyczącą łączników w edytorze Power Query](/power-query/connectors/), aby poznać listę łączników, których możesz użyć do importowania danych do aplikacji Customer Insights. 

Łączniki ze znacznikiem wyboru w kolumnie **Customer Insights (przepływy danych)** są dostępne do tworzenia nowych źródeł danych na podstawie edytora Power Query. Przejrzyj dokumentację określonego łącznika, aby dowiedzieć się więcej o jego wymaganiach wstępnych, ograniczeniach i innych szczegółach.

## <a name="edit-power-query-data-sources"></a>Edytowanie źródeł danych edytora Power Query

> [!NOTE]
> Wprowadzenie zmian w źródłach danych, które są obecnie używane w jednym z procesów aplikacji (na przykład *segmentacja*, *dopasowywanie* lub *scalanie*) może być niemożliwe. 
>
> Przy użyciu strony **Ustawienia** można śledzić postępy wszystkich aktywnych procesów. Po zakończeniu procesu można powrócić do strony **Źródła danych** i wprowadzić zmiany.

1. Przejdź do **Dane** > **Źródła danych**.

2. Wybierz wielokropek (&vellip;) pionowy obok źródła danych, które chcesz zmienić, i z menu rozwijanego wybierz pozycję **Edytuj**.

   > [!div class="mx-imgBorder"]
   > ![Opcja Edytuj.](media/edit-option-data-sources.png "Opcja Edytuj")

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]
   
3. Zastosuj zmiany i przekształcenia w oknie dialogowym **Power Query — edytowanie zapytań** zgodnie z opisem w obszarze [Tworzenie nowego źródła danych](#create-a-new-data-source).

4. Wybierz przycisk **Zapisz** w edytorze Power Query po zakończeniu edycji, aby zapisać zmiany.


[!INCLUDE [footer-include](includes/footer-banner.md)]
