---
title: Użyj źródeł danych do pozyskiwania danych
description: Informacje na temat importowania danych z różnych źródeł.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: de31e1f25c08d0bcb5341c5f465b1999de48acf3
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645368"
---
# <a name="data-sources-overview"></a>Omówienie źródeł danych

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Funkcja wglądu w odbiorców w Dynamics 365 Customer Insights łączy się z danymi z szerokiego zestawu źródeł. Łączenie się ze źródłem danych jest często określane jako proces *pozyskiwania danych*. Po pozyskaniu danych można je [ujednolicić](data-unification.md) i podejmować na nich akcje.

## <a name="add-a-data-source"></a>Dodaj źródło danych

Zapoznaj się ze szczegółowymi artykułami dotyczącymi sposobu dodawania źródła danych w zależności od wybranej opcji.

Źródło danych można dodać na trzy podstawowe sposoby:

- [Za pomocą licznych łączników Power Query](connect-power-query.md)
- [Z folderu Common Data Model](connect-common-data-model.md)
- [Z własnego repozytorium tylu lake Microsoft Dataverse](connect-dataverse-managed-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Dodawanie danych z lokalnych źródeł danych

Przetwarzanie danych z lokalnych źródeł danych w programie Wynikach analiz odbiorców jest obsługiwane na podstawie przepływów danych Microsoft Power Platform. Przepływy danych można włączyć w funkcji Customer Insights, [podając adres URL środowiska Microsoft Dataverse](create-environment.md) podczas konfigurowania środowiska.

Źródła danych tworzone po skojarzeniu środowiska Dataverse z usługą Customer Insights domyślnie będą korzystać z [przepływów danych Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Przepływy danych obsługują lokalną łączność przy użyciu bramy danych. Należy usunąć i ponownie utworzyć źródła danych, które istniały, zanim środowisko Dataverse zostało skojarzone do użycia [lokalnych bram danych](/data-integration/gateway/service-gateway-app).

Brama danych z istniejącego lub środowiska Power BI lub Power Apps będzie widoczna i można jej użyć ponownie w usłudze Customer Insights. Na stronie źródeł danych znajdują się łącza umożliwiające przejście do środowiska Microsoft Power Platform, w którym można wyświetlić i skonfigurować lokalne bramy danych.

## <a name="review-ingested-data"></a>Przeglądanie pobranych danych

Zostanie wyświetlona nazwa każdego pozyskanego źródła danych, jego stan i data ostatniego odświeżenia danych dla tego źródła. Listę źródeł danych można posortować według każdej kolumny.

> [!div class="mx-imgBorder"]
> ![Dodano źródło danych.](media/configure-data-datasource-added.png "Dodano źródło danych")

|Status  |Opis  |
|---------|---------|
|Zakończone powodzeniem   |Źródło danych zostało pomyślnie przetworzone, jeśli w kolumnie **Odświeżono** podano godzinę.
|Nie rozpoczęto   |Źródło danych nie ma jeszcze pozyskanych danych lub nadal jest w trybie roboczym.         |
|Odświeżanie    |Pobieranie danych jest w toku. Aby anulować operację, można wybrać opcję **Zatrzymaj odświeżanie** w kolumnie **Czynności**. Zatrzymanie odświeżania źródła danych spowoduje przywrócenie jego ostatniego stanu odświeżania.       |
|Zakończone niepowodzeniem     |Pobieranie danych zostało napotkało błędy.         |

Wybierz wartość w kolumnie **Stan** dowolnego pola źródło danych, aby przejrzeć więcej szczegółów. W okienku **Szczegółów postępu** rozwiń pozycję **Źródła danych**. Wybierz opcję **Zobacz szczegółowe informacje**, aby uzyskać więcej informacji na temat stanu odświeżania, w tym szczegóły błędów i aktualizacje procesów podrzędnych.

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
