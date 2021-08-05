---
title: Schematy encji Customer Insights w Common Data Model
description: Praca z encjami w Common Data Model.
ms.date: 04/17/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: e21f8a9422357fbc5c9425f91f3ba241c9dec9d8
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692318"
---
# <a name="entity-schemas-in-common-data-model"></a>Schematy encji w Common Data Model

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[Common Data Model](/common-data-model/) to deklaratywna specyfikacja, i definicja standardowych encji reprezentujących powszechne koncepcje i działania stosowane w działalności biznesowej i aplikacjach dotyczących wydajności. Ten model jest rozszerzany również na dane z obserwacji i analiz. Common Data Model zawiera dobrze zdefiniowane, modułowe i rozszerzalne jednostki biznesowe, takie jak Konto, Jednostka, Sprawa, Kontakt, Potencjalny Klient, Szansa, czy Produkt, a także interakcje z dostawcami, pracownikami i klientami, na przykład działania i umowy dotyczące poziomu usług. Każdy użytkownik może tworzyć i rozszerzać definicje Common Data Model, aby zbierać dodatkowe pomysły dotyczące prowadzonej działalności.

Ten współużytkowany model danych umożliwia aplikacjom i integratorom danych łatwiejszą współpracę, udostępniając zunifikowaną definicję danych. Common Data Model zawiera bogaty system metadanych z standardowymi encjami, relacjami, hierarchiami, cechami i innymi elementami. Jego źródłem są aplikacje Dynamics 365 i można go znaleźć na GitHub wraz z ponad 260 standardowymi encjami. Duży system partnerów wewnętrznych i zewnętrznych wnosi pojęcia dotyczące przemysłu do Common Data Model.

Wiele systemów i platform implementuje obecnie Common Data Model, w tym przepływy danych Power BI i usługi Azure Data Services. Jest już obsługiwana w programach Microsoft Dataverse, Dynamics 365, Power Apps, Power BI i nadchodzących usługach danych platformy Azure, bezpośrednio naliczając wartość w ramach [inicjatywy Initiative Open Data](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Schematy encji Customer Insights

Aby ustanowić całościowy widok klienta i udostępnić modele Customer Insights w Common DAta Model dla rozszerzania, opublikowaliśmy następujące schematy encji:

| Encja | Opis |
|---------|---------|
|[CustomerActivity](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Działanie wykonywane przez użytkownika, które ma wartość obserwacyjną dla firmy. |
|[CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Osoba lub organizacja, która albo wykonała, albo może zaangażować się w działalność biznesową. |
|[MeasureDefinition](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Definicja wskaźników KPI partycjonowanych przez zero lub więcej wymiarów (takich jak Aktywni użytkownicy miesięcznie, Całkowita kwota wydana przez klienta, Średni koszt nabycia klienta) |
|[Segment](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Definiuje grupę członków o wspólnych cechach. |
|[SegmentMembership](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Członkowie uczestniczący w danym segmencie. |

Więcej informacji można znaleźć w dokumentacji na temat [Schemat encji Customer Insights w Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Wyświetlanie encji przy użyciu nawigatora encji Common Data Model

Encje można wyświetlać w [Nawigatorze encji Common Data Model](https://microsoft.github.io/CDM/). Wybierz **Załaduj z GitHub!** i przejdź do **foundationCommon** > **crmCommon** > **rozwiązania** > **customerInsights**, gdzie znajdziesz listę encji Customer Insights i ich definicje.
> [!div class="mx-imgBorder"]
> ![Nawigator encji CDM pokazujący encję CustomerActivity.](media/CDM-entity-navigator.png "Nawigator encji CDM pokazujący encję CustomerActivity")


[!INCLUDE[footer-include](../includes/footer-banner.md)]