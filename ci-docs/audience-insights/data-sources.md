---
title: Użyj źródeł danych do pozyskiwania danych
description: Informacje na temat importowania danych z różnych źródeł.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 9cf97c3e30d7501ba1f188a0e25a1a103299aa7f
ms.sourcegitcommit: a8e99cf8b23ccc00d76c1dee22afd808a160a5c8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/22/2022
ms.locfileid: "8464087"
---
# <a name="data-sources-overview"></a>Omówienie źródeł danych



Funkcja wglądu w odbiorców w Dynamics 365 Customer Insights łączy się z danymi z szerokiego zestawu źródeł. Łączenie się ze źródłem danych jest często określane jako proces *pozyskiwania danych*. Po pozyskaniu danych można je [ujednolicić](data-unification.md) i podejmować na nich akcje.

## <a name="add-a-data-source"></a>Dodaj źródło danych

Zapoznaj się ze szczegółowymi artykułami, aby dowiedzieć się, jak dodać źródło danych, w zależności od wybranej opcji.

Możesz dodać następujące źródła danych:

- [Za pośrednictwem dziesiątek łączników usługi Power Query](connect-power-query.md)
- [Z folderu Common Data Model](connect-common-data-model.md)
- [Z własnego repozytorium tylu lake Microsoft Dataverse](connect-dataverse-managed-lake.md)
- [Z bazy danej usługi Azure Synapse Analytics](connect-synapse.md)

> [!NOTE]
> Jeśli korzystasz z wersji testowej, w sekcji Metody importu znajdziesz opcję **Biblioteka danych Customer Insights**. Wybierz tę opcję, aby wybrać przykładowy zbiór danych dostępny dla różnych branż. Aby uzyskać więcej informacji, zobacz [Wersja próbna Dynamics 365 Customer Insights](../trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Dodawanie danych z lokalnych źródeł danych

Przetwarzanie danych z lokalnych źródeł danych w programie Wynikach analiz odbiorców jest obsługiwane na podstawie przepływów danych Microsoft Power Platform. Możesz włączyć przepływy danych w Customer Insights poprzez [podanie adresu URL środowiska Microsoft Dataverse](create-environment.md) podczas konfigurowania środowiska.

Źródła danych, które są tworzone po powiązaniu środowiska Dataverse z Customer Insights domyślnie używają [przepływów danych Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Przepływy danych obsługują lokalną łączność przy użyciu bramy danych. Możesz usunąć i odtworzyć źródła danych, które istniały przed powiązaniem środowiska Dataverse [używając lokalnych bram danych](/data-integration/gateway/service-gateway-app).

Brama danych z istniejącego lub środowiska Power BI lub Power Apps będzie widoczna i można jej użyć ponownie w usłudze Customer Insights. Na stronie źródeł danych znajdują się łącza umożliwiające przejście do środowiska Microsoft Power Platform, w którym można wyświetlić i skonfigurować lokalne bramy danych.

> [!IMPORTANT]
> Upewnij się, że portale zostały zaktualizowane do najnowszej wersji. Możesz zainstalować aktualizację i ponownie skonfigurować bramę z monitu wyświetlanego bezpośrednio na ekranie bramy lub [pobierz najnowszą wersję](https://powerapps.microsoft.com/downloads/). Jeśli nie używasz najnowszej wersji bramy, odświeżanie przepływu danych kończy się niepowodzeniem z komunikatami o błędach, takimi jak **Słowo kluczowe nie jest obsługiwane: właściwości konfiguracyjne. Nazwa parametru: słowo kluczowe**.

## <a name="review-ingested-data"></a>Przeglądanie pobranych danych
Jeśli środowisko zawiera przepływy danych Power Platform, na stronie **Źródła danych** są znajdują się trzy sekcje: 
- **Udostępnione**: źródła danych, których mogą zarządzać wszyscy administratorzy usługi Customer Insights. Przepływy danych Power BI, własne konto magazynu i dołączanie do data lake zarządzanego przez Dataverse to przykłady udostępnionych źródeł danych.
- **Zarządzane przeze mnie**: utworzone przepływy danych Power Platform i mogą być zarządzane tylko przez użytkownika. Inni administratorzy Customer Insights mogą tylko wyświetlać te przepływy danych, ale nie mogą ich edytować, odświeżać ani usuwać.
- **Zarządzane przez innych**: przepływy danych Power Platform utworzone przez innych administratorów. Można je wyświetlić tylko. Zawiera listę właściciela przepływu danych, do którego należy się zwrócić w celu uzyskania pomocy.
> [!NOTE]
> Wszystkie encje mogą być przeglądane i używane przez innych użytkowników. Kontekstowość użytkownika dotyczy tylko źródeł danych, a nie jednostek, które wynikają z tych przepływów danych.

Jeśli nie są używane żadne przepływy danych Power Platform, nie zobaczysz żadnych grup ani sekcji. Strona **Źródła danych** zawiera tylko listę wszystkich źródeł danych.

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
