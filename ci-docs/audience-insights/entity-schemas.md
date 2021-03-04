---
title: Schematy encji Customer Insights w Common Data Model
description: Praca z encjami w Common Data Model.
ms.date: 04/17/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9e7a6e944d37d25f4c25846644278b39b3ddd08e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269297"
---
# <a name="entity-schemas-in-common-data-model"></a>Schematy encji w Common Data Model

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[Common Data Model](https://docs.microsoft.com/common-data-model/) to deklaratywna specyfikacja, i definicja standardowych encji reprezentujących powszechne koncepcje i działania stosowane w działalności biznesowej i aplikacjach dotyczących wydajności. Ten model jest rozszerzany również na dane z obserwacji i analiz. Common Data Model zawiera dobrze zdefiniowane, modułowe i rozszerzalne jednostki biznesowe, takie jak Konto, Jednostka, Sprawa, Kontakt, Potencjalny Klient, Szansa, czy Produkt, a także interakcje z dostawcami, pracownikami i klientami, na przykład działania i umowy dotyczące poziomu usług. Każdy użytkownik może tworzyć i rozszerzać definicje Common Data Model, aby zbierać dodatkowe pomysły dotyczące prowadzonej działalności.

Ten współużytkowany model danych umożliwia aplikacjom i integratorom danych łatwiejszą współpracę, udostępniając zunifikowaną definicję danych. Common Data Model zawiera bogaty system metadanych z standardowymi encjami, relacjami, hierarchiami, cechami i innymi elementami. Jego źródłem są aplikacje Dynamics 365 i można go znaleźć na GitHub wraz z ponad 260 standardowymi encjami. Duży system partnerów wewnętrznych i zewnętrznych wnosi pojęcia dotyczące przemysłu do Common Data Model.

Wiele systemów i platform implementuje obecnie Common Data Model, w tym przepływy danych Power BI i usługi Azure Data Services. Jest on już obsługiwany w Common Data Service, Dynamics 365, Power Apps, Power BI, i nadchodzących usługach danych Azure, bezpośrednio wzbogacając [Open Data Initiative](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Schematy encji Customer Insights

Aby ustanowić całościowy widok klienta i udostępnić modele Customer Insights w Common DAta Model dla rozszerzania, opublikowaliśmy następujące schematy encji:

| Encja | Opis |
|---------|---------|
|[CustomerActivity](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Działanie wykonywane przez użytkownika, które ma wartość obserwacyjną dla firmy. |
|[CustomerProfile](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Osoba lub organizacja, która albo wykonała, albo może zaangażować się w działalność biznesową. |
|[MeasureDefinition](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Definicja wskaźników KPI partycjonowanych przez zero lub więcej wymiarów (takich jak Aktywni użytkownicy miesięcznie, Całkowita kwota wydana przez klienta, Średni koszt nabycia klienta) |
|[Segment](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Definiuje grupę członków o wspólnych cechach. |
|[SegmentMembership](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Członkowie uczestniczący w danym segmencie. |

Więcej informacji można znaleźć w dokumentacji na temat [Schemat encji Customer Insights w Common Data Model](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Wyświetlanie encji przy użyciu nawigatora encji Common Data Model

Encje można wyświetlać w [Nawigatorze encji Common Data Model](https://microsoft.github.io/CDM/). Wybierz **Załaduj z GitHub!** i przejdź do **foundationCommon** > **crmCommon** > **rozwiązania** > **customerInsights**, gdzie znajdziesz listę encji Customer Insights i ich definicje.
> [!div class="mx-imgBorder"]
> ![Nawigator encji CDM pokazujący encję CustomerActivity](media/CDM-entity-navigator.png "Nawigator encji CDM pokazujący encję CustomerActivity")


[!INCLUDE[footer-include](../includes/footer-banner.md)]