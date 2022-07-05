---
title: Łączenie ze źródłem danych Power Query (zawiera wideo)
description: Pozyskiwanie danych przez łącznik Power Query (zawiera wideo).
ms.date: 06/13/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: matgos
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 6736b253e3a7e652f92f61bc44bfb31ca69be31a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081270"
---
# <a name="connect-to-a-power-query-data-source"></a>Łączenie ze źródłem danych Power Query

Edytor Power Query oferuje szeroki zestaw łączników służących do pozyskiwania danych. Większość z tych łączników jest obsługiwana przez Dynamics 365 Customer Insights.

Dodawanie źródeł danych opartych na łącznikach Power Query zasadniczo przebiega zgodnie z krokami opisanymi w tym obszarze. W zależności od używanego łącznika wymagane są jednak różne informacje. Aby dowiedzieć się więcej, zobacz dokumentację poszczególnych łączników w temacie [Dokumentacja łączników Power Query](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Utwórz nowe źródło danych

1. Przejdź do **Dane** > **Źródła danych**.

1. Wybierz **Dodaj źródła danych**.

1. Wybierz opcję **Microsoft Power Query**.

1. Podaj **nazwę** i opcjonalny **opis** źródło danych i wybierz opcję **Dalej**.

1. Wybierz jeden z [dostępnych łączników](#available-power-query-data-sources). W tym przykładzie wybieramy łącznik **Text/CSV**.

1. Wprowadź wymagane informacje szczegółowe w **Ustawienia połączenia** dla wybranego łącznika i wybierz **Dalej**, aby wyświetlić podgląd danych.

1. Wybierz **Przekształć dane**. W tym kroku encje zostaną dodane do źródła danych. Encje są zestawami danych. Jeśli istnieje baza danych zawierająca wiele zestawów danych, każdy zestaw danych jest swoją własną encją.

1. Okno dialogowe **Power Query — edytowanie zapytań** umożliwia przeglądanie i precyzowanie danych. Encje, które zostały określone przez systemy w wybranych źródłach danych, są wyświetlane w lewym okienku.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Okno dialogowe Edytuj zapytania":::

1. Dane można również przekształcać. Wybierz encję do edycji lub przekształcenia. Użyj opcji dostępnych w oknie edytora Power Query, aby zastosować przekształcenia. Każde przekształcenie jest wymienione w obszarze **Zastosowane kroki**. Edytor Power Query zawiera wiele wstępnie zbudowanych opcji przekształceń. Aby uzyskać więcej informacji, zobacz [Przekształcenia w edytorze Power Query](/power-query/power-query-what-is-power-query#transformations).

   Zalecamy używanie następujących transformacji:

   - Jeśli pozyskujesz dane z pliku CSV, pierwszy wiersz często zawiera nagłówki. Przejdź do pozycji **Przekształć** i wybierz pozycję **Użyj pierwszego wiersza jako nagłówków**.
   - Upewnij się, że typ danych jest odpowiednio ustawiony. Na przykład w przypadku pól daty wybierz typ daty.

1. Aby dodać więcej encji do źródła danych w oknie dialogowym **Edytowanie zapytań** przejdź do obszaru **Strona główna** i wybierz opcję **Pobierz dane**. Powtarzaj kroki 6–10 do momentu dodania wszystkich encji do źródła danych.

1. Wybierz pozycję **Zapisz**. Zostanie otwarta strona **Źródła danych** z nowymi źródło danych **Odświeżania**.

### <a name="available-power-query-data-sources"></a>Dostępne źródła danych edytora Power Query

Zobacz [dokumentację dotyczącą łączników w edytorze Power Query](/power-query/connectors/), aby poznać listę łączników, których możesz użyć do importowania danych do aplikacji Customer Insights.

Łączniki ze znacznikiem wyboru w kolumnie **Customer Insights (przepływy danych)** są dostępne do tworzenia nowych źródeł danych na podstawie edytora Power Query. Zapoznaj się z dokumentacją określonego łącznika, aby dowiedzieć się więcej o jego wymaganiach wstępnych, [ograniczeniach zapytań](/power-query/power-query-online-limits) i innych szczegółach.

## <a name="add-data-from-on-premises-data-sources"></a>Dodawanie danych z lokalnych źródeł danych

Przetwarzanie danych z lokalnych źródeł danych jest obsługiwane na podstawie przepływu danych Microsoft Power Platform (PPDF). Możesz włączyć przepływy danych w Customer Insights poprzez [podanie adresu URL środowiska Microsoft Dataverse](create-environment.md) podczas konfigurowania środowiska.

Źródła danych, które są tworzone po powiązaniu środowiska Dataverse z Customer Insights domyślnie używają [przepływów danych Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Przepływy danych obsługują lokalną łączność przy użyciu bramy danych. Możesz usunąć i odtworzyć źródła danych, które istniały przed powiązaniem środowiska Dataverse [używając lokalnych bram danych](/data-integration/gateway/service-gateway-app).

Brama danych z istniejącego lub środowiska Power BI lub Power Apps będzie widoczna i można jej użyć ponownie w usłudze Customer Insights. Na stronie źródeł danych znajdują się łącza umożliwiające przejście do środowiska Microsoft Power Platform, w którym można wyświetlić i skonfigurować lokalne bramy danych.

> [!IMPORTANT]
> Upewnij się, że portale zostały zaktualizowane do najnowszej wersji. Możesz zainstalować aktualizację i ponownie skonfigurować bramę z monitu wyświetlanego bezpośrednio na ekranie bramy lub [pobierz najnowszą wersję](https://powerapps.microsoft.com/downloads/). Jeśli nie używasz najnowszej wersji bramy, odświeżanie przepływu danych kończy się niepowodzeniem z komunikatami o błędach, takimi jak **Słowo kluczowe nie jest obsługiwane: właściwości konfiguracyjne. Nazwa parametru: słowo kluczowe**.

## <a name="edit-power-query-data-sources"></a>Edytowanie źródeł danych edytora Power Query

> [!NOTE]
> Wprowadzenie zmian w źródłach danych, które są obecnie używane w jednym z procesów aplikacji (na przykład *segmentacja*, *dopasowywanie* lub *scalanie*) może być niemożliwe.
>
> Przy użyciu strony **Ustawienia** można śledzić postępy wszystkich aktywnych procesów. Po zakończeniu procesu można powrócić do strony **Źródła danych** i wprowadzić zmiany.

1. Przejdź do **Dane** > **Źródła danych**.

1. Obok źródła danych, które chcesz zaktualizować, wybierz **Edytuj**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

1. Zastosuj zmiany i przekształcenia w oknie dialogowym **Power Query — edytowanie zapytań** zgodnie z opisem w obszarze [Tworzenie nowego źródła danych](#create-a-new-data-source).

1. Wybierz przycisk **Zapisz** w edytorze Power Query po zakończeniu edycji, aby zapisać zmiany.
