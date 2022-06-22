---
title: Użyj źródeł danych do pozyskiwania danych
description: Informacje na temat importowania danych z różnych źródeł.
ms.date: 05/31/2022
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
ms.openlocfilehash: e22977107565a0b28b74f41576a1c7ccc74f6dc1
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011762"
---
# <a name="data-sources-overview"></a>Omówienie źródeł danych

Dynamics 365 Customer Insights oferuje połączenia, które łączą dane z szerokiego zakresu źródeł. Łączenie się ze źródłem danych jest często określane jako proces *pozyskiwania danych*. Po pozyskaniu danych można [ujednolicić](data-unification.md), generować informacje i aktywować dane w celu tworzenia spersonalizowanych doświadczeń.

## <a name="add-data-sources"></a>Dodaj źródła danych

Źródła danych można dołączać lub importować do aplikacji Customer Insights. Poniższe łącza zawierają instrukcje dodawania źródeł danych.

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

Należy przejść do **Dane** > **Źródła danych**, aby wyświetlić nazwę poszczególnych pozyskanych źródeł danych, ich stan i czas ostatniego odświeżania danych dla tego źródła. Listę źródeł danych można posortować według każdej kolumny.

:::image type="content" source="media/configure-data-datasource-added.png" alt-text="Dodano źródło danych.":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Ładowanie danych może zająć czas. Po pomyślnym odświeżeniu dane z pobierania można przejrzeć na stronie **Encji**. Aby uzyskać więcej informacji, zobacz [Encje](entities.md).

## <a name="refresh-data-sources"></a>Odśwież źródła danych

Źródła danych mogą być odświeżane w harmonogramie automatycznym lub ręcznie odświeżane na żądanie. [Lokalne źródła danych](connect-power-query.md#add-data-from-on-premises-data-sources) są odświeżane według własnych harmonogramów, które są ustawiane podczas pozyskiwania danych. W przypadku dołączonych źródeł danych, konsumują one najnowsze dane dostępne z tego źródła danych.

Przejdź do **Administrator** > **System** > [**Harmonogram**](system.md#schedule-tab), aby skonfigurować zaplanowane w systemie odświeżanie pozyskanych źródeł danych.

Aby odświeżyć źródło danych na żądanie, wykonaj następujące kroki:

1. Przejdź do **Dane** > **Źródła danych**.

1. Wybierz wielokropek pionowy (&vellip;) obok źródła danych, które chcesz odświeżyć, i z menu rozwijanego wybierz pozycję **Odśwież**. Źródło danych jest teraz wyzwalane w celu ręcznego odświeżenia. Odświeżenie źródła danych spowoduje zaktualizowanie schematu encji i danych dla wszystkich encji określonych w źródle danych.

1. Wybierz **Zatrzymaj odświeżanie**, aby anulować istniejące odświeżanie, a źródło danych przywróci do ostatniego stanu odświeżania.

## <a name="delete-a-data-source"></a>Usuń źródło danych

Usunąć źródło danych można tylko wtedy, gdy dane nie są używane w przetwarzaniu, takim jak ujednolicanie, dane szczegółowe, aktywacje lub eksport.

1. Przejdź do **Dane** > **Źródła danych**.

2. Wybierz wielokropek pionowy (&vellip;) obok źródła danych, które chcesz usunąć, i z menu rozwijanego wybierz pozycję **Usuń**.

3. Potwierdź usunięcie.


[!INCLUDE [footer-include](includes/footer-banner.md)]
