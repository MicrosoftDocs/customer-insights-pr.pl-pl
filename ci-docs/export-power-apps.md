---
title: Łącznik Power Apps (wersja zapoznawcza)
description: Połącz z Power Apps i Power Automate.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 8807e82e65ea20d1a7f7dc07552229f377927eed
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196913"
---
# <a name="power-apps-connector-preview"></a>Łącznik Power Apps (wersja zapoznawcza)

Przenieś ujednolicone profile klientów do spersonalizowanych aplikacji za pomocą Microsoft Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Tworzenie połączenia rozwiązania Power Apps z usługą Dynamics 365 Customer Insights

Funkcja Customer Insights jest jednym z wielu [dostępnych źródeł danych w Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Zapoznaj się z dokumentacją Power Apps, aby dowiedzieć się, jak [dodać połączenie danych z aplikacją](/powerapps/maker/canvas-apps/add-data-connection). Zaleca się również zapoznanie się z artykułem [jak Power Apps używają delegowania w celu obsługi dużych zestawów danych w aplikacjach kanwy](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Dostępne encje

Po dodaniu Customer Insights jako połączenia danych można wybrać następujące encje w Power Apps:

- **Klient**: aby korzystać z danych z [ujednoliconego profilu klienta](customer-profiles.md).
- **UnifiedActivity**: aby wyświetlić [oś czasu działań](activities.md) w aplikacji.
- **ContactProfile**: w celu wyświetlenia kontaktów klienta. Ta encja jest tylko dostępna w środowiskach aplikacji Customer Insights dla klientów biznesowych.

## <a name="limitations"></a>Ograniczenia

### <a name="retrievable-entities"></a>Encje, które można odzyskać

Można pobierać wyłącznie encje **Klient**, **UnifiedActivity**, **Segmenty** i **ContactProfile** za pośrednictwem konektora Power Apps. Encja ContactProfile jest tylko dostępna w środowiskach Customer Insights dla klientów biznesowych. Pozostałe encje są widoczne, ponieważ związany z nimi łącznik obsługuje je za pomocą wyzwalaczy w Power Automate.

Możesz wykonać maksymalnie 100 rozmów na 60 sekund. Możesz wywołać punkt końcowy API wiele razy, używając parametru $skip. [Więcej informacji o parametrze $skip.](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Delegowanie

Delegowanie działa w przypadku encji **Klient** i **UnifiedActivity**.

- Delegowanie dla encji **Klient**: Aby używać delegowania dla tej encji, pola muszą zostać zindeksowane w [indeksie wyszukiwania i filtrów](search-filter-index.md).  
- Delegowanie dla **UnifiedActivity**: Delegacja dla tej encji działa tylko dla pól **ActivityId** i **CustomerID**.  
- Delegowanie dla encji **ContactProfile**: delegowanie dla tej encji działa tylko dla pól **ContactId** i **CustomerId**. Encja ContactProfile jest tylko dostępna w środowiskach Customer Insights dla klientów biznesowych.

Aby uzyskać więcej informacji na temat delegowania, przejdź do tematu [Funkcje i operacje usługi Power Apps z możliwością delegowania](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="example-gallery-control"></a>Przykładowy formant galerii

Możesz również dodawać profile klienta do [kontrolki galerii](/powerapps/maker/canvas-apps/add-gallery).

1. Dodaj kontrolkę **galerii** do konstruowanej aplikacji.
  
   :::image type="content" source="media/connector-powerapps9.png" alt-text="Dodawanie elementu galerii.":::

1. Wybierz **Klienta** jako źródło danych dla elementów.

   :::image type="content" source="media/choose-datasource-powerapps.png" alt-text="Wybierz źródło danych.":::

1. Możesz zmienić panel danych po prawej stronie, aby wybrać pole, które encja klienta ma wyświetlać w galerii.

1. Aby wyświetlić dowolne pole z wybranego klienta w galerii, wypełnij właściwość **tekstu** etykiety przy użyciu elementu **{Name_of_the_gallery}.Selected.{property_name}**  
    - Na przykład: _Gallery1.Selected.address1_city_

1. Aby wyświetlić ujednoliconą oś czasu dla klienta, należy dodać element galerii i dodać właściwość **Elementy** przy użyciu elementu **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Na przykład: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_

[!INCLUDE [footer-include](includes/footer-banner.md)]
