---
title: Tworzenie i konfigurowanie płatnej licencji usługi Customer Insights
description: Kroki, aby uzyskać licencjonowaną subskrypcję usługi Dynamics 365 Customer Insights i ją skonfigurować.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b5f76f4c468b88aaf7037dbd2ee3bed449fbeaa5f645d52278eee05b36b4e328
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034465"
---
# <a name="get-started-with-a-paid-subscription"></a>Rozpocznij z płatną subskrypcją

W tym artykule wyjaśniono, jak utworzyć nowe środowisko po zakupie subskrypcji usługi Dynamics 365 Customer Insights przez organizację. Jeśli chcesz kupić usługę Customer Insights, nasze opcje do kontaktu są wymienione na [stronie internetowej Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/). 

Jeśli chcesz wypróbować usługę i funkcje, zobacz [Konfigurowanie środowiska próbnego](get-started-trial.md).

## <a name="create-an-environment-in-an-existing-organization"></a>Tworzenie środowiska w istniejącej organizacji

Po zakupie licencji subskrypcyjnej dla usługi Customer Insights administrator globalny dzierżawcy usługi Microsoft 365 otrzymuje wiadomość e-mail z zaproszeniem do utworzenia środowiska. Przejdź do [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start), aby rozpocząć. 

Aplikacja Customer Insights nie jest licencjonowana na użytkownika, więc nie pojawi się w obszarze Licencje. Jeśli szukasz licencji w centrum administracyjnym usługi Microsoft 365, przejdź do **Twoje produkty**. 

> [!NOTE]
> Organizacje mogą utworzyć *dwa* środowiska dla każdej licencji usługi Customer Insights. Jeśli organizacja kupuje więcej niż jedną licencję, [skontaktuj się z zespołem pomocy technicznej](https://go.microsoft.com/fwlink/?linkid=2079641) w celu zwiększenia liczby dostępnych środowisk. Aby uzyskać więcej informacji na temat pojemności i pojemności dodatków, pobierz [przewodnik po licencjonowaniu usługi Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Aby utworzyć nowe środowisko:

1. W oknie dialogowym **Tworzenie środowiska** wybierz **nowe środowisko**.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Okno dialogowe, aby utworzyć nowe środowisko Customer Insights.":::

   Zalecamy rozpoczęcie konfigurowania środowiska od podstaw. Jeśli jednak jesteś administratorem lub członkiem środowiska próbnego, możesz [skopiować dane z innego środowiska](manage-environments.md#copy-the-environment-configuration), wybierając pozycję **Kopiuj z istniejącego środowiska**. Zobaczysz listę wszystkich dostępnych środowisk w organizacji, z których można kopiować dane.

1. Podaj następujące szczegóły:
   - **Nazwa**: Nazwa tego środowiska. To pole jest już wypełnione, jeśli skopiowano istniejące środowisko, ale można to zmienić.
   - **Region**: Region, w którym usługa jest wdrażana i hostowana.
   - **Wpisz**: Wybierz, czy chcesz utworzyć środowisko produkcyjne, czy piaskownicę. Środowiska piaskownicy nie zezwalają na zaplanowane odświeżanie danych i są przeznaczone do wstępnej implementacji i testowania.
   
1. Opcjonalnie możesz wybrać **Ustawienia zaawansowane**:

   - **Zapisz wszystkie dane do**: Określa miejsce, w którym mają być przechowywane dane wyjściowe uzyskane na podstawie danych dotyczących klienta. Dostępne są dwie opcje: **Magazyn rozwiązania Customer Insights** (magazyn Azure Data Lake, którym zarządza zespół rozwiązania Customer Insights) oraz **Azure Data Lake Storage** (własne Azure Data Lake Storage). Domyślnie jest zaznaczona opcja magazyn Customer Insights.

     > [!NOTE]
     > Zapisując dane w usłudze Azure Data Lake Storage, zgadzasz się na przenoszenie danych do lokalizacji geograficznej odpowiedniej dla danego konta usługi Azure Storage i przechowywanie ich w tej lokalizacji, która może być inna niż lokalizacja, w której są przechowywane dane w Dynamics 365 Customer Insights. [Więcej informacji znajduje się w centrum zaufania Microsoft.](https://www.microsoft.com/trust-center)
     >
     > Obecnie pozyskiwane encje z przepływu danych Power BI są zawsze przechowywane w data lake obsługiwanym przez Microsoft Dataverse. 
     > 
     > Obsługujemy tylko konta Azure Data Lake Storage z tego samego regionu Azure, który został wybrany podczas tworzenia środowiska. 
     > 
     > Obsługujemy tylko te konta Azure Data Lake Storage, w których włączono hierarchiczny obszar nazw.


   - W przypadku Azure Data Lake Storage można wybrać opcję opartą na zasobach i opartą na subskrypcji opcję uwierzytelniania. Aby uzyskać więcej informacji, zobacz temat [Połącz analizy odbiorców z kontem Azure Data Lake Storage Gen2 za pomocą głównej usługi platformy Azure](connect-service-principal.md). Nazwy **Kontenerów** nie można zmienić i będzie można zmienić na `customerinsights`.
   
   - Jeśli chcesz używać [modeli gotowych do użycia](predictions-overview.md#out-of-box-models), konfigurować udostępnianie danych za pomocą programu Microsoft Dataverse lub włączyć pozyskiwanie danych z lokalnych źródeł danych, podaj adres URL środowiska Microsoft Dataverse w obszarze **Konfigurowanie udostępniania danych i włączanie dodatkowych funkcji Microsoft Dataverse**. Wybierz opcję **Włącz udostępnianie danych**, aby udostępnić dane wyjściowe usługi Customer Insights daneom wyjściowym z zarządzanego Data Lake Microsoft Dataverse.

     > [!NOTE]
     > - Udostępnianie danych za pomocą usługi Microsoft Dataverse Zarządzanego Data Lake nie jest obecnie obsługiwane w przypadku zapisywania wszystkich danych we własnym Azure Data Lake Storage.
     > - [Przewidywanie brakujących wartości w encji](predictions.md) nie jest obecnie obsługiwane, jeśli włączone zostało udostępnianie danych zarządzanemu Data Lake Microsoft Dataverse.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Opcje konfiguracji umożliwiające udostępnianie danych funkcji Microsoft Dataverse.":::

   Po zakończeniu przetwarzanie procesów, takich jak pozyskiwanie danych, system tworzy odpowiednie foldery na określonym koncie magazynu. Pliki danych i pliki model.json są tworzone i dodawane do folderów na podstawie nazwy procesu.

   Jeśli utworzysz wiele środowisk Customer Insights i zdecydujesz się zapisać encje wyjściowe z tych środowisk na koncie magazynu, dla każdego środowiska zostaną utworzone osobne foldery z ci_<environmentid> w kontenerze.

1. Wybierz **Utwórz**, aby skonfigurować środowisko. 

## <a name="configure-an-environment"></a>Konfigurowanie środowiska

Zapoznaj się z poniższymi artykułami, aby ułatwić sobie rozpoczęcie konfigurowania usługi Customer Insights. 

- [Dodawanie więcej użytkowników i przypisywanie uprawnień](permissions.md).
- [Pozyskuj źródła danych](data-sources.md) i uruchamiaj je w [procesie ujednolicenia danych](data-unification.md), aby uzyskać [ujednolicone profile klientów](customer-profiles.md).
- [Wzbogać ujednolicone profile klientów](enrichment-hub.md) lub [uruchom modele predykcyjne](predictions-overview.md).
- Tworzenie [segmentów](segments.md) w celu grupowanie klientów i [mierzenie](measures.md) przeglądu wskaźników KPI.
- Konfiguruj [połączenia](connections.md) i [eksporty](export-destinations.md) do przetwarzania podzbiorów danych w innych aplikacjach.
