---
title: Łączenie ze źródłem danych Power Query (zawiera wideo)
description: Pozyskiwanie danych przez łącznik Power Query (zawiera wideo).
ms.date: 09/29/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 4cc7e57dfb0f8d050e91adc441c24e849882f5d8
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609909"
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

1. Wybierz **Przekształć dane**.

1. Przeglądanie i precyzowanie danych na stronie **Power Query — edytuj zapytania**. Encje, które zostały określone przez systemy w wybranych źródłach danych, są wyświetlane w lewym okienku.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Okno dialogowe Edytuj zapytania":::

1. Przekształć swoje dane. Wybierz encję do edycji lub przekształcenia. Użyj opcji dostępnych w oknie edytora Power Query, aby zastosować przekształcenia. Każde przekształcenie jest wymienione w obszarze **Zastosowane kroki**. Edytor Power Query zawiera wiele [wstępnie zbudowanych opcji przekształceń](/power-query/power-query-what-is-power-query#transformations).

   > [!IMPORTANT]
   > Zalecamy używanie następujących transformacji:
   >
   > - Jeśli pozyskujesz dane z pliku CSV, pierwszy wiersz często zawiera nagłówki. Przejdź do pozycji **Przekształć** i wybierz pozycję **Użyj pierwszego wiersza jako nagłówków**.
   > - Upewnij się, że typ danych jest odpowiednio ustawiony i pasuje do danych. Na przykład w przypadku pól daty wybierz typ daty.

1. Aby dodać więcej encji do źródła danych w oknie dialogowym **Edytowanie zapytań** przejdź do obszaru **Strona główna** i wybierz opcję **Pobierz dane**. Powtarzaj kroki 5–10 do momentu dodania wszystkich encji do źródła danych. Jeśli istnieje baza danych zawierająca wiele zestawów danych, każdy zestaw danych jest swoją własną encją.

1. Wybierz pozycję **Zapisz**. Zostanie otwarta strona **Źródła danych** z nowymi źródło danych **Odświeżania**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Ładowanie danych może zająć czas. Po pomyślnym odświeżeniu dane z pobierania można przejrzeć na stronie [**Encji**](entities.md).

> [!CAUTION]
>
> - Źródło danych oparte na Power Query tworzy [przepływ danych w Dataverse](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Nie należy zmieniać nazwy przepływu danych w centrum administracyjnym Power Platform używanego w aplikacji Customer Insights. Zmiana nazwy przepływu danych powoduje problemy z odwołaniami między danymi w aplikacji Customer Insights źródło danych przepływem danych Dataverse.
> - Jednoczesne oceny źródeł danych Power Query w Customer Insights mają takie same [ograniczenia odświeżania, jak przepływy danych w PowerBI.com](/power-query/power-query-online-limits#refresh-limits). Jeśli odświeżenie danych zakończy się niepowodzeniem, ponieważ osiągnięto limit oceny, zaleca się dostosowanie harmonogramu odświeżania dla każdego przepływu danych, aby zapewnić, że źródła danych nie będą przetwarzane jednocześnie.

### <a name="available-power-query-data-sources"></a>Dostępne źródła danych edytora Power Query

Zobacz [dokumentację dotyczącą łączników w edytorze Power Query](/power-query/connectors/), aby poznać listę łączników, których możesz użyć do importowania danych do aplikacji Customer Insights.

Łączniki ze znacznikiem wyboru w kolumnie **Customer Insights (przepływy danych)** są dostępne do tworzenia nowych źródeł danych na podstawie edytora Power Query. Zapoznaj się z dokumentacją określonego łącznika, aby dowiedzieć się więcej o jego wymaganiach wstępnych, [ograniczeniach zapytań](/power-query/power-query-online-limits) i innych szczegółach.

## <a name="add-data-from-on-premises-data-sources"></a>Dodawanie danych z lokalnych źródeł danych

Przetwarzanie danych z lokalnych źródeł danych jest obsługiwane na podstawie przepływu danych Microsoft Power Platform (PPDF). Możesz włączyć przepływy danych w Customer Insights poprzez [podanie adresu URL środowiska Microsoft Dataverse](create-environment.md) podczas konfigurowania środowiska.

Źródła danych, które są tworzone po powiązaniu środowiska Dataverse z Customer Insights domyślnie używają [przepływów danych Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Przepływy danych obsługują lokalną łączność przy użyciu bramy danych. Możesz usunąć i odtworzyć źródła danych, które istniały przed powiązaniem środowiska Dataverse [używając lokalnych bram danych](/data-integration/gateway/service-gateway-app).

Bramy danych z istniejących środowisk Power BI lub Power Apps będą widoczne i można ich użyć ponownie w usłudze Customer Insights, jeśli brama danych i środowisko Customer Insights znajdują się w tym samym regionie świadczenia platformy Azure. Na stronie źródeł danych znajdują się łącza umożliwiające przejście do środowiska Microsoft Power Platform, w którym można wyświetlić i skonfigurować lokalne bramy danych.

> [!IMPORTANT]
> Upewnij się, że portale zostały zaktualizowane do najnowszej wersji. Możesz zainstalować aktualizację i ponownie skonfigurować bramę z monitu wyświetlanego bezpośrednio na ekranie bramy lub [pobierz najnowszą wersję](https://powerapps.microsoft.com/downloads/). Jeśli nie używasz najnowszej wersji bramy, odświeżanie przepływu danych kończy się niepowodzeniem z komunikatami o błędach, takimi jak **Słowo kluczowe nie jest obsługiwane: właściwości konfiguracyjne. Nazwa parametru: słowo kluczowe**.
>
> Błędy z lokalnymi bramami danych w Customer Insights są często spowodowane problemami z konfiguracją. Więcej informacji na temat rozwiązywania problemów z bramami danych znajduje się w artykule [Rozwiązywanie problemów z lokalną bramą danych](/data-integration/gateway/service-gateway-tshoot).

## <a name="edit-power-query-data-sources"></a>Edytowanie źródeł danych edytora Power Query

> [!NOTE]
> Może nie być możliwe wprowadzanie zmian w źródłach danych, które są obecnie używane w jednym z procesów aplikacji (na przykład segmentacja lub ujednolicenie danych).
>
> Przy użyciu strony **Ustawienia** można śledzić postępy wszystkich aktywnych procesów. Po zakończeniu procesu można powrócić do strony **Źródła danych** i wprowadzić zmiany.

1. Przejdź do **Dane** > **Źródła danych**.

1. Obok źródła danych, które chcesz zaktualizować, wybierz **Edytuj**.

1. Zastosuj zmiany i przekształcenia w oknie dialogowym **Power Query — edytowanie zapytań** zgodnie z opisem w obszarze [Tworzenie nowego źródła danych](#create-a-new-data-source).

1. Wybierz przycisk **Zapisz**, aby zastosować zmiany i wrócić do strony **Źródła danych**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupt-data"></a>Typowe powody błędów pozyskiwania lub uszkodzonych danych

### <a name="data-type-does-not-match-data"></a>Typ danych nie jest zgodny z danymi

Najbardziej typowe niezgodności typów danych występują, gdy pole daty nie ma poprawnego formatu daty.

Dane można naprawić u źródła i ponownie je pozyskać. Można też poprawić transformację w aplikacji Customer Insights. Aby naprawić transformację:

1. Przejdź do **Dane** > **Źródła danych**.

1. Obok źródła danych z uszkodzonymi danymi, wybierz **Edytuj**.

1. Wybierz **Dalej**.

1. Wybierz każde zapytanie i przeszukaj przekształcenia zastosowane w niepoprawnych „Zastosowanych krokach” lub kolumnach daty, które nie zostały przekształcone przy użyciu formatu daty.

   :::image type="content" source="media/PQ_corruped_date.png" alt-text="Power Query— edycja z wyświetlaniem niepoprawnego formatu daty":::

1. Zmień typ danych, aby prawidłowo pasował do danych.

1. Wybierz pozycję **Zapisz**. To źródło danych jest odświeżane.

## <a name="troubleshoot-ppdf-power-query-based-data-source-refresh-issues"></a>Rozwiązywanie problemów z odświeżaniem i odświeżaniem źródła danych Power Query PPDF

Jeśli dane są nieaktualne lub po odświeżeniu źródło danych wystąpią błędy, należy wykonać następujące kroki:

1. Przejdź do [Power Platform](https://make.powerapps.com).

1. Wybierz **Środowisko** dla swojego wystąpienia usługi Customer Insights.

1. Przejdź do **Przepływy danych**.

1. Dla przepływu danych odpowiadającego danemu źródłu danych w programie Customer Insights wybierz z wielokropek pionowy (&vellip;), a następnie wybierz opcję **Pokaż historię odświeżania**.

1. Jeśli **Stan** przepływu danych to **Powodzenie**, własność opartego na Power Query źródła danych mogła zostać zmieniona:

   1. Przejrzyj harmonogram odświeżania z historii odświeżania.
   1. Ustaw nowy harmonogram właściciela i zapisz ustawienia.

1. Jeśli **Stan** przepływu danych **nie powiedzie się**:

   1. Pobierz plik odświeżenia historii.
   1. Sprawdź pobrany plik, aby poznać przyczynę niepowodzenia.
   1. Jeśli błąd nie może zostać rozwiązany, wybierz opcję **?**, aby otworzyć bilet pomocy technicznej. Podaj pobrany plik odświeżenia historii.


[!INCLUDE [footer-include](includes/footer-banner.md)]
