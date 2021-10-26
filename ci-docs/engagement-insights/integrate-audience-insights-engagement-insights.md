---
title: Utwórz łącze między wynikami analiz odbiorców i wynikami analiz interakcji
description: Utwórz łącze między wynikami analiz odbiorców i wynikami analiz interakcji, by umożliwić dwukierunkowe udostępnianie danych.
ms.date: 09/08/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: db38778c0da862e119f9b374e07c82ead0d3a4f2
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645595"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Utwórz łącze między wynikami analiz odbiorców i wynikami analiz interakcji

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Integracja między wynikami analiz interakcji i wynikami analiz odbiorców łączy środowiska z obu funkcji i umożliwia dwukierunkowe udostępnianie danych między nimi.

Użyj ujednoliconych profilów i segmentów z wyników analiz odbiorców, by uzyskać więcej opcji analiz w wynikach analiz interakcji. Eksportuj zdarzenia o wysokiej wartości biznesowej z wyników analiz interakcji. Użyj tych zdarzeń, by dodać dane do ujednoliconych profilów w wynikach analiz odbiorców.

## <a name="prerequisites"></a>Wymagania wstępne

- Wyniki analiz odbiorców muszą być przechowywane w kontach usługi Azure Data Lake Storage, których użytkownik jest właścicielem, lub w [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md) — zarządzanym repozytorium data lake. 
- Ponadto środowisko szczegółowych informacji o odbiorcach powinno mieć skojarzone środowisko Dataverse. Jeśli w tym środowisku jest również wykorzystywane miejsce do magazynowania danych w usłudze Dataverse, należy sprawdzić opcję **Włącz udostępnianie danych** w szczegółowych informacjach o odbiorcach. Aby uzyskać więcej informacji, zobacz temat [Tworzenie i konfigurowanie środowiska w aplikacji Wyniki analiz odbiorców](../audience-insights/create-environment.md).
- Musisz mieć uprawnienia administratora zarówno w wynikach analiz interakcji, jak i wynikach analiz odbiorców.
- Połączone środowiska muszą znajdować się w tym samym regionie geograficznym.

> [!NOTE]
> - Jeśli subskrypcja szczegółowych informacji o odbiorcach to wersja próbna, która używa szczegółowych informacji o odbiorcach wewnętrznie zarządzanych przez repozytorium data lake, skontaktuj się z [pirequest@microsoft.com](mailto:pirequest@microsoft.com) w celu uzyskania pomocy. 
> - Jeśli środowisko wyników analiz odbiorcy do przechowywania danych używa własnej usługi Azure Data Lake Storage, musisz dodać główną usługę Azure wyników analiz interakcji do swojego konta magazynu. Aby uzyskać szczegółowe informacje, przejdź do strony [Łączenie się z kontem Azure Data Lake Storage przy użyciu głównej usługi Azure dla wyników analiz odbiorców](../audience-insights/connect-service-principal.md). 


## <a name="create-an-environment-link"></a>Utwórz łącze środowiska

Łącze środowiska można utworzyć, aktualizując ustawienia **Administrator** > **Środowisko** w wynikach analiz interakcji.

**Ustanowienie aktywnego łącza między wynikami analiz odbiorców i wynikami analiz interakcji**

1. Na stronie **Administrator środowiska** wybierz kartę **Połącz środowiska**.

    :::image type="content" source="media/integrate1.png" alt-text="Konfiguruj środowisko.":::

1. Wybierz **Środowiska konfiguracji** w lewym górnym rogu lub u dołu ekranu.

     :::image type="content" source="media/integrate2.png" alt-text="Wybierz środowisko wyników analiz odbiorców.":::

1. Wybierz środowisko wyników analiz odbiorców, a następnie wybierz opcję ***Dalej**, aby zakończyć. Teraz możesz wybrać funkcje opcjonalne dla połączonych środowisk.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Włącz wyniki analiz odbiorcy ujednoliconych atrybutów i segmentów profilów

Po połączeniu środowisk możesz wybrać funkcje opcjonalne dla połączonych środowisk. Funkcje te umożliwiają ujednolicone atrybuty i segmenty profilu z wyników analiz odbiorcy dla interaktywnych analiz przeprowadzanych na danych klienta.

> [!IMPORTANT]
> Aby segmenty wyników analiz odbiorców wyświetlały się w wynikach analiz interakcji, należy [Uruchomić scalanie i procesy podrzędne](../audience-insights/merge-entities.md). Procesy podrzędne są ważne, ponieważ generują unikatową tabelę przygotowującą segmenty wyników analiz odbiorcy, które będą udostępniane wynikom analiz interakcji. (Jeśli zaplanowano odświeżanie sytemu, spowoduje to automatyczne uwzględnienie procesów podrzędnych.)

**Do analizowania danych internetowych w wynikach analiz interakcji**

1. Na stronie **Administrator środowiska** włącz przełącznik **Udostępniaj dane z wyników analiz odbiorców w celu użycia ich w wynikach analiz interakcji**, a następnie wybierz **Dalej**.

    :::image type="content" source="media/integrate4.png" alt-text="Wybierz funkcje.":::

1. Wybierz atrybuty ujednoliconych profilów, które staną się wymiarami w wynikach analiz interakcji. (Nie wszystkie atrybuty to użyteczne rozmiary. Na przykład nie jest prawdopodobne, aby **Imię** lub **Nazwisko** były przydatnymi atrybutami do analizy wydarzeń witryny internetowej.)

    :::image type="content" source="media/integrate5.png" alt-text="Selekcjonuj i filtruj wymiary.":::

   >[!NOTE]
   > Wszystkie atrybuty profilu wyników analiz odbiorcy reprezentujące identyfikatory (takie jak **identyfikator** i **alternatywny identyfikator**) są odfiltrowywane z dostępnych atrybutów i stają się wymiarami w wynikach analiz interakcji.

1. Po wybraniu atrybutów wybierz opcję **Dalej**.
1. Dodaj użytkowników, którzy mogą przeglądać wymiary i segmenty profilu wyników analiz odbiorców w wynikach analiz interakcji.

    :::image type="content" source="media/integrate6.png" alt-text="Zarządzaj dostępem do danych klientów.":::

   > [!IMPORTANT]
   > Jeśli jawnie nie dodasz użytkowników w tym kroku, dane zostaną ukryte przed użytkownikami w wynikach analiz interakcji.
   > Aby segmenty wyników analiz odbiorców wyświetlały się w wynikach analiz interakcji, należy [Uruchomić scalanie i procesy podrzędne](../audience-insights/merge-entities.md). Procesy podrzędne są ważne, ponieważ generują unikatową tabelę przygotowującą segmenty wyników analiz odbiorcy, które będą udostępniane wynikom analiz interakcji. (Jeśli zaplanowano odświeżanie sytemu, spowoduje to automatyczne uwzględnienie procesów podrzędnych.)

1. Sprawdź wybraną opcję, a następnie kliknij przycisk **Zakończ**.

    :::image type="content" source="media/integrate7.png" alt-text="Przejrzyj ustawienia danych klientów.":::

## <a name="export-refined-events-to-audience-insights"></a>Eksportuj ulepszone zdarzenia wynikom analiz odbiorców

Po utworzeniu łącza między środowiskami można wyeksportować ulepszone zdarzenia z wyników analiz interakcji do wyników analiz odbiorców i pozyskiwać je jako nowe źródło danych. 

Aby uzyskać więcej informacji, przejdź do [Integracji danych internetowych z wyników analiz interakcji z wynikami analiz odbiorców](../audience-insights/integrate-engagement-insights.md).

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
