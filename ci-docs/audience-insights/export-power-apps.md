---
title: Łącznik usługi Power Apps
description: Połącz z Power Apps i Power Automate.
ms.date: 08/21/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b6ec103e29e218b2f27bfc1193300ea793a6b30b
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406550"
---
# <a name="microsoft-power-apps-connector-preview"></a>Łącznik Microsoft Power Apps (wersja zapoznawcza)

Przenieś ujednolicone profile klientów do spersonalizowanych aplikacji za pomocą Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Tworzenie połączenia rozwiązania Power Apps z usługą Dynamics 365 Customer Insights

Funkcja Customer Insights jest jednym z wielu [dostępnych źródeł danych w Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).

Zapoznaj się z dokumentacją Power Apps, aby dowiedzieć się, jak [dodać połączenie danych z aplikacją](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection). Zaleca się również zapoznanie się z artykułem [jak Power Apps używają delegowania w celu obsługi dużych zestawów danych w aplikacjach kanwy](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Dostępne encje

Po dodaniu Customer Insights jako połączenia danych można wybrać następujące encje w Power Apps:

- Klient: aby korzystać z danych z [ujednoliconego profilu klienta](customer-profiles.md).
- Działanie ujednoliconego klienta: aby wyświetlić [oś czasu działania](activities.md) w aplikacji.

## <a name="limitations"></a>Ograniczenia

### <a name="retrievable-entities"></a>Encje, które można odzyskać

Można odzyskać tylko encje **Klient**, **UnifiedActivity**, i **Segmenty** za pośrednictwem łącznika Power Apps. Pozostałe encje są widoczne, ponieważ związany z nimi łącznik obsługuje je za pomocą wyzwalaczy w Power Automate.  

### <a name="delegation"></a>Delegowanie

Delegacja działa w przypadku encji Klient i UnifiedActivity. 

- Delegowanie dla encji **Klient**: Aby używać delegowania dla tej encji, pola muszą zostać zindeksowane w [Indeks wyszukiwania i filtrów](search-filter-index.md).  

- Delegowanie dla **UnifiedActivity**: Delegacja dla tej encji działa tylko dla pól **ActivityId** i **CustomerID**.  

- Więcej informacji na temat delegowania znajduje się w artykule [Delegowalne funkcje i operacje w Power Apps](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Przykładowy formant galerii

Można na przykład dodać profile klientów do [kontrolki galerii](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).

1. Dodaj formant **Galeria** do konstruowanej aplikacji.

> [!div class="mx-imgBorder"]
> ![Dodawanie elementu galerii](media/connector-powerapps9.png "Dodawanie elementu galerii")

1. Wybierz **Klienta** jako źródło danych dla elementów.

    > [!div class="mx-imgBorder"]
    > ![Wybierz źródło danych](media/choose-datasource-powerapps.png "Wybierz źródło danych")

1. Możesz zmienić panel danych po prawej stronie, aby wybrać pole, które encja klienta ma wyświetlać w galerii.

1. Aby wyświetlić dowolne pole z wybranego klienta w galerii, wypełnij właściwość tekstu etykiety:  **{Name_of_the_gallery}.Selected.{property_name}**

    Przykład: Gallery1.Selected.address1_city

1. Aby wyświetlić ujednoliconą oś czasu dla klienta, należy dodać element galerii i dodać właściwość elementu: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Przykład: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)
