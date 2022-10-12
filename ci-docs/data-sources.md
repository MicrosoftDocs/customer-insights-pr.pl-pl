---
title: Omówienie źródeł danych
description: Dowiedz się, jak importować lub pozyskiwać dane z różnych źródeł.
ms.date: 09/29/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: f89da3cf5b56e367bd673740f80cd82ec0907b28
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610065"
---
# <a name="data-sources-overview"></a>Omówienie źródeł danych

Dynamics 365 Customer Insights oferuje połączenia, które łączą dane z szerokiego zakresu źródeł. Łączenie się ze źródłem danych jest często określane jako proces *pozyskiwania danych*. Po pozyskaniu danych można [ujednolicić](data-unification.md), generować informacje i aktywować dane w celu tworzenia spersonalizowanych doświadczeń.

## <a name="add-or-edit-data-sources"></a>Dodaj lub edytuj źródła danych

Źródła danych można dołączać lub importować do aplikacji Customer Insights. Poniższe linki zawierają instrukcje dotyczące dodawania i edytowania źródeł danych.

**Dołączanie źródła danych**

Jeśli masz dane przygotowane w jednej z usług danych Azure firmy Microsoft, aplikacja Customer Insights może łatwo połączyć się ze źródłem danych bez konieczności ponownego pozyskiwania danych. Wybierz jedną z następujących opcji:
- [Azure Data Lake Storage (pliki csv or parquet w folderze Common Data Model)](connect-common-data-model.md)
- [Azure Synapse Analytics (bazy danych Lake)](connect-synapse.md)
- [Baza data lake Microsoft Dataverse](connect-dataverse-managed-lake.md)

**Importowanie i przekształcenie**

Jeśli są wykorzystywane lokalne źródła danych, firmy Microsoft lub innej firmy, należy zaimportować i przekształcić dane za pomocą łączników Power Query.
- [Łączniki usługi Power Query](connect-power-query.md)

## <a name="review-data-sources"></a>Przejrzyj źródła danych

Jeśli w środowisku skonfigurowano użycie magazynu rozwiązania Customer Insights i są wykorzystywane lokalne źródła danych, używasz przepływów danych Power Platform. Korzystając z przepływów danych Power Platform, można wyświetlać udostępniane źródła danych i źródła danych zarządzane przez innych. Na stronie **Źródła danych** wymieniono źródła danych w trzech sekcjach:
- **Udostępnione**: źródła danych, których mogą zarządzać wszyscy administratorzy usługi Customer Insights. Przepływy danych Power Platform, własne konto magazynu i dołączanie do data lake zarządzanego przez Dataverse to przykłady udostępnionych źródeł danych.
- **Zarządzane przeze mnie**: utworzone przepływy danych Power Platform i zarządzane tylko przez użytkownika. Inni administratorzy Customer Insights mogą tylko wyświetlać te przepływy danych, ale nie mogą ich edytować, odświeżać ani usuwać.
- **Zarządzane przez innych**: przepływy danych Power Platform utworzone przez innych administratorów. Można je wyświetlić tylko. Zawiera listę właściciela przepływu danych, do którego należy się zwrócić w celu uzyskania pomocy.
> [!NOTE]
> Wszystkie encje mogą być przeglądane i używane przez innych użytkowników. W czasie, gdy właścicielem źródeł danych jest użytkownik, który je utworzył, encje wynikowe z pozyskiwania danych mogą być używane przez każdego użytkownika Customer Insights.

Jeśli w środowisku nie są wykorzystywane przepływy danych Power Platform, strona **Źródła danych** zawiera tylko listę wszystkich źródeł danych. Nie są wyświetlane żadne sekcje.

## <a name="manage-existing-data-sources"></a>Zarządzaj istniejącymi źródłami danych

Należy przejść do **Dane** > **Źródła danych**, aby wyświetlić nazwę poszczególnych pozyskanych źródeł danych, ich stan i czas ostatniego odświeżania danych dla tego źródła. Możesz posortować listę źródeł danych według dowolnej kolumny lub użyć pola wyszukiwania, aby znaleźć źródło danych, którym chcesz zarządzać.

Wybierz źródło danych, aby wyświetlić dostępne akcje.

:::image type="content" source="media/data_sources_showmore.png" alt-text="Dodano źródło danych.":::

- [**Edytuj**](#add-or-edit-data-sources) źródło danych, aby zmienić jego właściwości.
- [**Odśwież**](#refresh-data-sources) źródło danych, aby uwzględnić najnowsze dane.
- [**Wzbogać**](data-sources-enrichment.md) źródła danych przed unifikacją.
- **Usuń** źródło danych. Usunąć źródło danych można tylko wtedy, gdy dane nie są używane w przetwarzaniu, takim jak ujednolicanie, dane szczegółowe, aktywacje lub eksport.

## <a name="refresh-data-sources"></a>Odśwież źródła danych

Źródła danych mogą być odświeżane w harmonogramie automatycznym lub ręcznie odświeżane na żądanie. [Lokalne źródła danych](connect-power-query.md#add-data-from-on-premises-data-sources) są odświeżane według własnych harmonogramów, które są ustawiane podczas pozyskiwania danych. Aby uzyskać porady dotyczące rozwiązywania problemów, zobacz [Rozwiązywanie problemów PPDF związanych z odświeżaniem źródła danych opartego na Power Query](connect-power-query.md#troubleshoot-ppdf-power-query-based-data-source-refresh-issues).

W przypadku dołączonych źródeł danych, konsumują one najnowsze dane dostępne z tego źródła danych.

Przejdź do **Administrator** > **System** > [**Harmonogram**](schedule-refresh.md), aby skonfigurować zaplanowane w systemie odświeżanie pozyskanych źródeł danych.

Aby odświeżyć źródło danych na żądanie:

1. Przejdź do **Dane** > **Źródła danych**.

1. Wybierz źródło danych chcesz odświeżyć i wybierz opcję **Odśwież**. Źródło danych jest teraz wyzwalane w celu ręcznego odświeżenia. Odświeżenie źródła danych spowoduje zaktualizowanie schematu encji i danych dla wszystkich encji określonych w źródle danych.

1. Wybierz stan obok okienka **Szczegóły postępu**, aby wyświetlić postęp. Aby anulować zadanie, wybierz opcję **Anuluj zadanie** w dolnej części okienka.

## <a name="corrupt-data-sources"></a>Uszkodzone źródła danych

Pozyskiwane dane mogą spowodować uszkodzenie rekordów, co może spowodować zakończenie procesu pozyskiwania danych z błędami lub ostrzeżeniami.

> [!NOTE]
> Jeśli pozyskiwanie danych zakończy się błędami, kolejne przetwarzanie (takie jak ujednolicenie lub utworzenie działania), które będzie korzystać ze źródła danych zostanie pominięte. Jeśli pozyskiwane zostanie zakończone z ostrzeżeniami, kolejne przetwarzanie będzie trwać, ale niektóre rekordy nie zostaną uwzględnione.

Te błędy mogą być widoczne w szczegółach zadania.

:::image type="content" source="media/corrupt-task-error.png" alt-text="Szczegóły zadania prezentujące uszkodzony błąd danych.":::

Uszkodzone rekordy są pokazane w encjach utworzonych przez system.

### <a name="fix-corrupt-data"></a>Naprawianie uszkodzonych danych

1. Aby wyświetlić uszkodzone dane, przejdź do **Dane** > **Jednostki** i poszukaj uszkodzonych jednostek w sekcji **System**. Schemat nazewnictwa uszkodzonych jednostek: „DataSourceName_EntityName_corrupt”.

1. Wybierz uszkodzoną encję, a następnie kartę **Dane**.

1. Zidentyfikuj uszkodzone pola rekordu i przyczynę.

   :::image type="content" source="media/corruption-reason.png" alt-text="Przyczyna uszkodzenia." lightbox="media/corruption-reason.png":::

   > [!NOTE]
   > **Dane** > **Encje** pokazuje tylko część uszkodzonych rekordów. Aby wyświetlić wszystkie uszkodzone rekordy, należy wyeksportować pliki do kontenera na koncie magazynu przy użyciu [procesu eksportowania funkcji Customer Insights](export-destinations.md). Jeśli używasz własnego konta magazynu, możesz także sprawdzić folder Customer Insights w swoim koncie magazynu.

1. Naprawianie uszkodzonych danych. Na przykład w przypadku źródeł danych Azure Data Albo [popraw dane w magazynie Data Lake lub zaktualizuj typy danych w pliku manifest/model.json](connect-common-data-model.md#common-reasons-for-ingestion-errors-or-corrupt-data). W przypadku źródeł danych Power Query popraw dane w pliku źródłowym i [popraw typ danych w kroku transformacji](connect-power-query.md#data-type-does-not-match-data) na stronie **Power Query — Edytuj zapytania**.

Po następnym odświeżeniu źródła danych poprawione rekordy są pozyskiwane do usługi Customer Insights i przekazywane do procesów podrzędnych.

Na przykład kolumna „urodziny” ma typ danych ustawiony jako „data”. Rekord klienta ma jego urodziny wprowadzone jako „01/01/19777”. System oflaguje ten rekord jako uszkodzony. Zmień datę urodzin w systemie źródłowym na „1977”. Po automatycznym odświeżeniu źródeł danych pole ma teraz prawidłowy format, a rekord zostanie usunięty z uszkodzonej jednostki.

[!INCLUDE [footer-include](includes/footer-banner.md)]
