---
title: Omówienie źródeł danych
description: Dowiedz się, jak importować lub pozyskiwać dane z różnych źródeł.
ms.date: 07/26/2022
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
ms.openlocfilehash: 6ab97c535454e84c1bb18aca00bca2568eb65a2a
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207104"
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

Źródła danych mogą być odświeżane w harmonogramie automatycznym lub ręcznie odświeżane na żądanie. [Lokalne źródła danych](connect-power-query.md#add-data-from-on-premises-data-sources) są odświeżane według własnych harmonogramów, które są ustawiane podczas pozyskiwania danych. W przypadku dołączonych źródeł danych, konsumują one najnowsze dane dostępne z tego źródła danych.

Przejdź do **Administrator** > **System** > [**Harmonogram**](system.md#schedule-tab), aby skonfigurować zaplanowane w systemie odświeżanie pozyskanych źródeł danych.

Aby odświeżyć źródło danych na żądanie:

1. Przejdź do **Dane** > **Źródła danych**.

1. Wybierz źródło danych chcesz odświeżyć i wybierz opcję **Odśwież**. Źródło danych jest teraz wyzwalane w celu ręcznego odświeżenia. Odświeżenie źródła danych spowoduje zaktualizowanie schematu encji i danych dla wszystkich encji określonych w źródle danych.

1. Wybierz stan obok okienka **Szczegóły postępu**, aby wyświetlić postęp. Aby anulować zadanie, wybierz opcję **Anuluj zadanie** w dolnej części okienka.

[!INCLUDE [footer-include](includes/footer-banner.md)]
