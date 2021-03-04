---
title: Użyj źródeł danych do pozyskiwania danych
description: Informacje na temat importowania danych z różnych źródeł.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 68aa1b56fb634da80a0c64db72f778d57507104d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269711"
---
# <a name="data-sources-overview"></a>Omówienie źródeł danych

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Funkcja wglądu w odbiorców w Dynamics 365 Customer Insights łączy się z danymi z szerokiego zestawu źródeł. Łączenie się ze źródłem danych jest często określane jako proces *pozyskiwania danych*. Po pozyskaniu danych można je [ujednolicić](data-unification.md) i podejmować na nich akcje.

## <a name="add-a-data-source"></a>Dodaj źródło danych

Zapoznaj się ze szczegółowymi artykułami dotyczącymi sposobu dodawania źródła danych w zależności od wybranej opcji.

Źródło danych można dodać na trzy podstawowe sposoby:

- [Za pomocą licznych łączników Power Query](connect-power-query.md)
- [Z folderu Common Data Model](connect-common-data-model.md)
- [Z własnego repozytorium tylu lake Common Data Service](connect-common-data-service-lake.md)

> [!NOTE]
> Nie można jeszcze dodawać danych z lokalny źródeł danych.

## <a name="review-ingested-data"></a>Przeglądanie pobranych danych

Zostanie wyświetlona nazwa każdego pozyskanego źródła danych, jego stan i data ostatniego odświeżenia danych dla tego źródła. Listę źródeł danych można posortować według każdej kolumny.

> [!div class="mx-imgBorder"]
> ![Dodano źródło danych](media/configure-data-datasource-added.png "Dodano źródło danych")

|Status  |Opis  |
|---------|---------|
|Pomyślnie   |Źródło danych zostało pomyślnie przetworzone, jeśli w kolumnie **Odświeżono** podano godzinę.
|Nie rozpoczęto   |Źródło danych nie ma jeszcze pozyskanych danych lub nadal jest w trybie roboczym.         |
|Odświeżanie    |Pobieranie danych jest w toku. Aby anulować operację, można wybrać opcję **Zatrzymaj odświeżanie** w kolumnie **Czynności**. Zatrzymanie odświeżania źródła danych spowoduje przywrócenie jego ostatniego stanu odświeżania.       |
|Zakończone niepowodzeniem     |Pobieranie danych zostało napotkało błędy.         |

Wybierz wartość w kolumnie **Stan** dowolnego pola źródło danych, aby przejrzeć więcej szczegółów. W okienku **Szczegółów postępu** rozwiń pozycję **Źródła danych**. Wybierz opcję **Zobacz szczegółowe informacje**, aby uzyskać więcej informacji na temat stanu odświeżania, w tym szczegóły błędów i aktualizacje procesów podrzędnych.

Ładowanie danych może potrwać trochę czasu. Po pomyślnym odświeżeniu dane z pobierania można przejrzeć na stronie **Encji**. Aby uzyskać więcej informacji, zobacz [Encje](entities.md).

## <a name="refresh-a-data-source"></a>Odśwież źródło danych

Źródła danych mogą być odświeżane w harmonogramie automatycznym lub ręcznie odświeżane na żądanie. 

Przejdź do **Administrator** > **System** > [**Harmonogram**](system.md#schedule-tab), aby skonfigurować zaplanowane odświeżanie wszystkich spożywanych źródeł danych.

Aby odświeżyć źródło danych na żądanie, wykonaj następujące kroki:

1. W analizach odbiorców przejdź do **Dane** > **Źródła danych**

2. Zaznacz pionowy wielokropek obok źródło danych, który chcesz odświeżyć, i wybierz opcję **Odśwież** z listy rozwijanej.

3. Źródło danych jest teraz wyzwalane w celu ręcznego odświeżenia. Odświeżenie źródła danych spowoduje zaktualizowanie zarówno schematu jednostki, jak i danych dla wszystkich jednostek określonych w źródle danych.

4. Wybierz **Zatrzymaj odświeżanie**, aby anulować istniejące odświeżanie, a źródło danych przywróci do ostatniego stanu odświeżania.

## <a name="delete-a-data-source"></a>Usuń źródło danych

1. W analizach odbiorców przejdź do **Dane** > **Źródła danych**.

2. Zaznacz pionowy wielokropek obok źródła danych, które chcesz usunąć, i wybierz **Usuń** z menu rozwijanego.

3. Potwierdź usunięcie.


[!INCLUDE[footer-include](../includes/footer-banner.md)]