---
title: Żądania podmiotów danych osobowych (DSR) w kontekście rozporządzenia RODO | Microsoft Docs
description: Odpowiadaj na żądania osób, których dotyczą dane, dotyczące możliwości wglądu odbiorców w Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350282"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Żądania osób, których dotyczą dane, w kontekście rozporządzenia RODO

Ogólne rozporządzenie o ochronie danych (RODO) w Unii Europejskiej obowiązuje od 25 maja 2018 roku. Daje istotne prawa osobom w odniesieniu do ich danych. Zasadniczo przepisy GDPR dotyczą ochrony i zapewnienia prawa do prywatności osób fizycznych. Więcej informacji na temat zaangażowania firmy Microsoft w kwestie bezpieczeństwa i zgodności można znaleźć na stronie [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Dokładamy wszelkich starań, aby pomóc klientom w spełnianiu ich wymagań dotyczących rozporządzenia RODO. Obejmuje prawo usuwania i eksportowania danych, które zawierają dane osobowe, takie jak identyfikatory użytkowników, numery telefonów i adresy e-mail. Administratorzy mogą implementować żądania użytkowników w celu usuwania lub eksportowania danych osobowych.

## <a name="audience-insights"></a>Wyniki analiz odbiorców

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Odpowiadanie na żądania usunięcia przez osobę, której dane dotyczą, dotyczące RODO dotyczące możliwości wglądu odbiorców w Dynamics 365 Customer Insights

„Prawo do usunięcia danych osobowych” poprzez usunięcie prywatnych danych klienta organizacji jest kluczową ochroną w Ogólnym rozporządzeniu o ochronie danych (RODO). Usuwanie danych osobowych polega na usunięciu wszystkich danych osobowych i dzienników generowanych przez system, poza informacjami dotyczącymi dziennika inspekcji.

#### <a name="manage-data-subject-delete-requests"></a>Zarządzanie żądaniami usuwania danych

Analiza odbiorców oferuje następujące doświadczenia w produkcie, które usuwają dane osobowe dotyczące konkretnego użytkownika lub klienta:

- **Zarządzanie żądaniami usuwania danych klienta**: dane klienta w Customer Insights są pobierane z oryginalnych źródeł danych spoza Customer Insights. Wszystkie żądania dotyczące usuwania danych według RODO muszą zostać wykonane w oryginalnym źródle danych.
- **Zarządzanie żądaniami usunięcia danych użytkownika Customer Insights**: Dane dla użytkowników są tworzone przez Customer Insights. Wszystkie żądania dotyczące usuwania danych według RODO muszą zostać wykonane w Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Zarządzanie żądaniami usunięcia danych klienta

Administrator Customer Insights może wykonać poniższe kroki w celu usunięcia danych klienta, które zostały usunięte ze źródła danych:

1. Zaloguj się w Dynamics 365 Customer Insights.
2. W analizach odbiorców przejdź do **Dane** > **Źródła danych**
3. Dla każdego źródła danych z listy, które zawiera usunięte dane klienta:
   1. Wybierz (...) i wybierz **Odśwież**.
   2. Sprawdź status źródła danych w **Stan**. Znacznik wyboru oznacza, że odświeżanie zakończyło się powodzeniem. Trójkąt ostrzegawczy oznacza, że wystąpił problem. Jeśli zostanie wyświetlony trójkąt ostrzegawczy, skontaktuj się z D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Zarządzanie żądaniami usunięcia danych klienta według RODO.](audience-insights/media/gdpr-data-sources.png "Zarządzanie żądaniami usunięcia danych klienta według RODO")

##### <a name="manage-delete-requests-for-user-data"></a>Zarządzanie żądaniami usunięcia danych użytkownika

Administrator Customer Insights może wykonać poniższe kroki w celu usunięcia danych użytkownika Customer Insights:

1. Zaloguj się w Dynamics 365 Customer Insights.
2. W analizach odbiorców przejdź do **Administrator** > **Uprawnienia**.
3. Zaznacz pole wyboru dla użytkownika, którego chcesz usunąć.
4. Wybierz **Usuń**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Odpowiadanie na żądania podmiotów o eksport danych osobowych zgodnie z RODO

W ramach naszych starań, aby wspierać użytkowników w trakcie wdrażania Ogólnego rozporządzenia o ochronie danych (RODO), opracowano dokumentację ułatwiającą przygotowanie. W tej dokumentacji opisano kroki, które możesz podjąć dzisiaj, aby zapewnić zgodność z RODO podczas korzystania ze statystyk odbiorców.

#### <a name="manage-export-and-view-requests"></a>Zarządzanie żądaniami eksportowania i wyświetlania

Prawo do przenoszenia danych osobowych pozwala podmiotowi danych składać wniosek o kopię danych osobowych w formacie elektronicznym („struktura, powszechnie stosowana, czytelna i wieloprogramowa”), który może być przekazywany innemu kontrolerowi danych.

##### <a name="export-customer-data-tenant-admin"></a>Eksportowanie danych klienta (Administrator dzierżawcy)

W celu wyeksportowania danych administrator dzierżawy może wykonać następujące kroki:

1. Wysłąć wiadomość e-mail na adres D365CI@microsoft.com określając adres e-mail klienta w żądaniu. Zespół Customer Insights wyśle wiadomość e-mail na adres e-mail zarejestrowanego administratora dzierżawcy, pytając o potwierdzenie wyeksportowania danych.
2. Zatwierdź potwierdzenie wyeksportowania danych dla żądanego klienta.
3. Pobierz eksportowane dane za pomocą adresu e-mail administratora dzierżawcy.

##### <a name="export-user-data-tenant-admin"></a>Eksportuj dane użytkownika (administrator dzierżawy)

1. Wysłąć wiadomość e-mail na adres D365CI@microsoft.com określając adres e-mail użytkownika w żądaniu. Zespół Customer Insights wyśle wiadomość e-mail na adres e-mail zarejestrowanego administratora dzierżawcy, pytając o potwierdzenie wyeksportowania danych.
2. Zatwierdź potwierdzenie wyeksportowania danych dla żądanego użytkownika.
3. Pobierz eksportowane dane za pomocą adresu e-mail administratora dzierżawcy.

## <a name="consent-management-preview"></a>Zarządzanie zgodami (wersja zapoznawcza)

Funkcja zarządzania zgodami nie umożliwia bezpośredniego zbierania danych użytkowników. Importuje i przetwarza ona tylko dane zgody podane przez użytkowników w innych aplikacjach.

Aby usunąć dane zgody dotyczące określonych użytkowników, należy usunąć je w źródłach danych, z których pozyskano je dla funkcji zarządzania zgodami. Po odświeżeniu źródła danych dane zostaną również usunięte w Centrum zgody. Aplikacje, które korzystają z encji zgody, będą również usuwać dane, które zostały usunięte ze źródła po [odświeżeniu](audience-insights/system.md#refresh-processes). Zaleca my odświeżenie źródeł danych niedługo po reakcji na żądanie podmiotu danych dotyczącego usunięcia danych użytkownika ze wszystkich innych procesów i aplikacji.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]