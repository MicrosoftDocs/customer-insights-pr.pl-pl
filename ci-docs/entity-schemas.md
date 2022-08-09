---
title: Schematy encji w Common Data Model
description: Praca z encjami w Common Data Model.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: cc65314f1b083694b60ac0a2625bea906be7272b
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183506"
---
# <a name="entity-schemas-in-common-data-model"></a>Schematy encji w Common Data Model

[Common Data Model](/common-data-model/) to deklaratywna specyfikacja, i definicja standardowych encji reprezentujących powszechne koncepcje i działania stosowane w działalności biznesowej i aplikacjach dotyczących wydajności. Ten model jest rozszerzany również na dane z obserwacji i analiz. Common Data Model zawiera dobrze zdefiniowane, modułowe i rozszerzalne jednostki biznesowe, takie jak Konto, Jednostka, Sprawa, Kontakt, Potencjalny Klient, Szansa, czy Produkt, a także interakcje z dostawcami, pracownikami i klientami, na przykład działania i umowy dotyczące poziomu usług. Każdy użytkownik może tworzyć i rozszerzać definicje Common Data Model, aby zbierać dodatkowe pomysły dotyczące prowadzonej działalności.

Ten współużytkowany model danych umożliwia aplikacjom i integratorom danych łatwiejszą współpracę, udostępniając zunifikowaną definicję danych. Common Data Model zawiera bogaty system metadanych z standardowymi encjami, relacjami, hierarchiami, cechami i innymi elementami. Jego źródłem są aplikacje Dynamics 365 i można go znaleźć na GitHub wraz z ponad 260 standardowymi encjami. Duży system partnerów wewnętrznych i zewnętrznych wnosi pojęcia dotyczące przemysłu do Common Data Model.

Wiele systemów i platform implementuje obecnie Common Data Model, w tym przepływy danych Power BI i usługi Azure Data Services. Jest już obsługiwana w programach Microsoft Dataverse, Dynamics 365, Power Apps, Power BI i nadchodzących usługach danych platformy Azure, bezpośrednio naliczając wartość w ramach [inicjatywy Initiative Open Data](https://dynamics.microsoft.com/en-us/open-data-initiative/).

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

Wyświetl encje w [Nawigatorze encji Common Data Model](https://microsoft.github.io/CDM/). Wybierz encję z sekcji aplikacji szczegółowych informacji, aby uzyskać listę encji rozwiązania Customer Insights i ich definicje.

:::image type="content" source="media/CDM-entity-navigator.png" alt-text="Nawigator encji CDM pokazujący encję CustomerActivity.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
