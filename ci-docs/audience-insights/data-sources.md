---
title: Użyj źródeł danych do pozyskiwania danych
description: Informacje na temat importowania danych z różnych źródeł.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ca979527c9cb8418e12af4a74513033047e4901c
ms.sourcegitcommit: 3807202283dd116a30f900a163d8141db621e5a8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/28/2022
ms.locfileid: "8046607"
---
# <a name="data-sources-overview"></a>Omówienie źródeł danych



Funkcja wglądu w odbiorców w Dynamics 365 Customer Insights łączy się z danymi z szerokiego zestawu źródeł. Łączenie się ze źródłem danych jest często określane jako proces *pozyskiwania danych*. Po pozyskaniu danych można je [ujednolicić](data-unification.md) i podejmować na nich akcje.

## <a name="add-a-data-source"></a>Dodaj źródło danych

Zapoznaj się ze szczegółowymi artykułami, aby dowiedzieć się, jak dodać źródło danych, w zależności od wybranej opcji.

Możesz dodać następujące źródła danych:

- [Łączniki usługi Power Query](connect-power-query.md)
- [Common Data Model](connect-common-data-model.md)
- [Microsoft Dataverse lake](connect-dataverse-managed-lake.md)

> [!NOTE]
> Jeśli korzystasz z wersji testowej, w sekcji Metody importu znajdziesz opcję **Biblioteka danych Customer Insights**. Wybierz tę opcję, aby wybrać przykładowy zbiór danych dostępny dla różnych branż. Aby uzyskać więcej informacji, zobacz [Wersja próbna Dynamics 365 Customer Insights](../trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Dodawanie danych z lokalnych źródeł danych

Przetwarzanie danych z lokalnych źródeł danych w programie Wynikach analiz odbiorców jest obsługiwane na podstawie przepływów danych Microsoft Power Platform. Możesz włączyć przepływy danych w Customer Insights poprzez [podanie adresu URL środowiska Microsoft Dataverse](create-environment.md) podczas konfigurowania środowiska.

Źródła danych, które są tworzone po powiązaniu środowiska Dataverse z Customer Insights domyślnie używają [przepływów danych Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Przepływy danych obsługują lokalną łączność przy użyciu bramy danych. Możesz usunąć i odtworzyć źródła danych, które istniały przed powiązaniem środowiska Dataverse [używając lokalnych bram danych](/data-integration/gateway/service-gateway-app).

Brama danych z istniejącego lub środowiska Power BI lub Power Apps będzie widoczna i można jej użyć ponownie w usłudze Customer Insights. Na stronie źródeł danych znajdują się łącza umożliwiające przejście do środowiska Microsoft Power Platform, w którym można wyświetlić i skonfigurować lokalne bramy danych.

## <a name="review-ingested-data"></a>Przeglądanie pobranych danych

Zostanie wyświetlona nazwa każdego pozyskanego źródła danych, jego stan i data ostatniego odświeżenia danych dla tego źródła. Listę źródeł danych można posortować według każdej kolumny.

> [!div class="mx-imgBorder"]
> ![Dodano źródło danych.](media/configure-data-datasource-added.png "Dodano źródło danych")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

Ładowanie danych może zająć czas. Po pomyślnym odświeżeniu dane z pobierania można przejrzeć na stronie **Encji**. Aby uzyskać więcej informacji, zobacz [Encje](entities.md).

## <a name="refresh-a-data-source"></a>Odśwież źródło danych

Źródła danych mogą być odświeżane w harmonogramie automatycznym lub ręcznie odświeżane na żądanie. 

Przejdź do **Administrator** > **System** > [**Harmonogram**](system.md#schedule-tab), aby skonfigurować zaplanowane odświeżanie wszystkich spożywanych źródeł danych.

Aby odświeżyć źródło danych na żądanie, wykonaj następujące kroki:

1. W analizach odbiorców przejdź do **Dane** > **Źródła danych**.

2. Wybierz wielokropek pionowy obok źródła danych, które chcesz odświeżyć, i z menu rozwijanego wybierz pozycję **Odśwież**.

3. Źródło danych jest teraz wyzwalane w celu ręcznego odświeżenia. Odświeżenie źródła danych spowoduje zaktualizowanie schematu encji i danych dla wszystkich encji określonych w źródle danych.

4. Wybierz **Zatrzymaj odświeżanie**, aby anulować istniejące odświeżanie, a źródło danych przywróci do ostatniego stanu odświeżania.

## <a name="delete-a-data-source"></a>Usuń źródło danych

1. W analizach odbiorców przejdź do **Dane** > **Źródła danych**.

2. Wybierz wielokropek pionowy obok źródła danych, które chcesz usunąć, i z menu rozwijanego wybierz pozycję **Usuń**.

3. Potwierdź usunięcie.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
