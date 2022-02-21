---
title: Tworzenie środowisk w aplikacji Customer Insights
description: Kroki tworzenia środowisk z licencjonowaną subskrypcją aplikacji Dynamics 365 Customer Insights.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: d29992c88bd54fcfcf5e6429a89a34b6f73148c8
ms.sourcegitcommit: b7189b8621e66ee738e4164d4b3ce2af0def3f51
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2022
ms.locfileid: "8088126"
---
# <a name="create-an-environment-in-audience-insights"></a>Tworzenie środowiska w aplikacji Wyniki analiz odbiorców

W tym artykule wyjaśniono, jak utworzyć nowe środowisko po zakupie subskrypcji usługi Dynamics 365 Customer Insights przez organizację. 

Organizacje mogą utworzyć *dwa* środowiska dla każdej licencji usługi Customer Insights. Jeśli organizacja kupi więcej niż jedną licencję, [skontaktuj się z zespołem pomocy technicznej](https://go.microsoft.com/fwlink/?linkid=2079641), aby zwiększyć liczbę dostępnych środowisk. Aby uzyskać więcej informacji na temat pojemności i pojemności dodatków, pobierz [przewodnik po licencjonowaniu usługi Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Jeśli chcesz wypróbować tę usługę, zobacz [Konfigurowanie środowiska w wersji próbnej](../trial-signup.md).

## <a name="create-a-new-environment"></a>Utwórz nowe środowisko

Po zakupieniu licencji subskrypcji aplikacji Customer Insights administrator globalny dzierżawcy platformy Microsoft 365 otrzymuje wiadomość e-mail z zaproszeniem do utworzenia środowiska. Przejdź do [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start), aby rozpocząć. 

Środowisko nadzorowane pomaga w zbieraniu wszystkich wymaganych informacji na temat nowego środowiska. Aby tworzyć środowiska i zarządzać nimi, musisz mieć [uprawnienia administratora](permissions.md) w aplikacji Wyniki analiz odbiorców.

1. W aplikacji Wyniki analiz odbiorców otwórz selektor środowiska i wybierz opcję **+ Nowy**.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="Wybierz selektor środowiska.":::

1. Wykonaj czynności nadzorowane opisane w poniższych sekcjach.

### <a name="step-1-provide-environment-information"></a>Krok 1. Podaj informacje o środowisku

W kroku **Podstawowe informacje** wybierz, czy chcesz utworzyć środowisko od podstaw, czy [skopiować dane z innego środowiska](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Okno dialogowe, aby utworzyć nowe środowisko Customer Insights.":::

Podaj następujące szczegóły:
   - **Nazwa**: Nazwa tego środowiska. To pole jest już wypełnione, jeśli skopiowano istniejące środowisko, ale można to zmienić.
   - **Wybierz swoją firmę**: wybierz podstawowych odbiorców dla nowego środowiska. Można pracować z poszczególnymi konsumentami (B2C) lub [kontami biznesowymi (B2B)](work-with-business-accounts.md).
   - **Wpisz**: Wybierz, czy chcesz utworzyć środowisko produkcyjne, czy piaskownicę. Środowiska piaskownicy nie zezwalają na zaplanowane odświeżanie danych i są przeznaczone do wstępnej implementacji i testowania. Środowiska piaskownicy używają tych samych podstawowych odbiorców co aktualnie wybrane środowisko produkcyjne.
   - **Region**: Region, w którym usługa jest wdrażana i hostowana.

### <a name="step-2-configure-data-storage"></a>Krok 2. Skonfiguruj magazyn danych

W kroku **Magazyn danych** wybierz miejsce przechowywania danych z funkcji Wyniki analiz odbiorców.

Dostępne są dwie opcje: **Magazyn rozwiązania Customer Insights** (magazyn data lake usługi Azure, którym zarządza zespół rozwiązania Customer Insights) oraz **Azure Data Lake Storage** (własne Azure Data Lake Storage). Domyślnie jest zaznaczona opcja magazyn Customer Insights.

:::image type="content" source="media/data-storage-environment.png" alt-text="Wybierz pozycję Azure Data Lake Storage, aby przechowywać w niej dane funkcji Wyniki analiz odbiorców.":::

Zapisując dane w usłudze Azure Data Lake Storage, wyrażasz zgodę na to, że dane będą przesyłane do i przechowywane w odpowiedniej lokalizacji geograficznej dla tego konta magazynu platformy Azure. Ta lokalizacja może różnić się od miejsca, w którym są przechowywane dane aplikacji Dynamics 365 Customer Insights. Więcej informacji znajduje się w [Centrum zaufania Microsoft](https://www.microsoft.com/trust-center).

> [!NOTE]
> Obecnie program Customer Insights obsługuje następujące elementy:
> - Pozyskane encje z przepływów danych usługi Power BI przechowywane usłudze Data Lake zarządzanej przez funkcję Microsoft Dataverse.  
> - Konta usługi Azure Data Lake Storage z tego samego regionu platformy Azure, który został wybrany podczas tworzenia środowiska.
> - Konta usługi Azure Data Lake Storage Gen2 z włączoną *hierarchiczną przestrzenią nazw*. Konta magazynu usługi Azure Data Lake Gen1 nie są obsługiwane.

W przypadku Azure Data Lake Storage można wybrać opcję opartą na zasobach i opartą na subskrypcji opcję uwierzytelniania. Aby uzyskać więcej informacji, zobacz [Łączenie z kontem Azure Data Lake Storage przy użyciu głównej usługi Azure](connect-service-principal.md). Nazwą **kontenera** będzie `customerinsights` i nie będzie można jej zmienić.

Po zakończeniu procesów systemowych, takich jak pozyskiwanie danych, system tworzy odpowiednie foldery w określonym koncie magazynu. Pliki danych i pliki *model.json* są tworzone i dodawane do folderów na podstawie nazwy procesu.

W przypadku utworzenia kilku środowisk usługi Customer Insights i zapisania encji wyjściowych z tych środowisk do konta magazynu aplikacja Customer Insights utworzy oddzielne foldery dla każdego środowiska z elementem `ci_environmentID` w kontenerze.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Krok 3. Nawiąż połączenie z funkcją Microsoft Dataverse
   
Krok **Microsoft Dataverse** umożliwia połączenie aplikacji Customer Insights ze środowiskiem Dataverse.

Aby używać [gotowych modeli przewidywania](predictions-overview.md#out-of-box-models), skonfiguruj udostępnianie danych w funkcji Dataverse. Można też włączyć pozyskiwanie danych z lokalnych źródeł danych, udostępniając adres URL środowiska funkcji Microsoft Dataverse, którym administruje Twoja organizacja. Wybierz opcję **Włącz udostępnianie danych**, aby udostępnić dane wyjściowe usługi Customer Insights danym data lake zarządzanym przez usługę Dataverse.

> [!IMPORTANT]
> Customer Insights i Dataverse muszą znajdować się w tym samym regionie, aby umożliwić wymianę danych.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Opcje konfiguracji umożliwiające udostępnianie danych funkcji Microsoft Dataverse.":::

> [!NOTE]
> Aplikacja Customer Insights nie obsługuje następujących scenariuszy udostępniania danych:
> - Po zapisaniu wszystkich danych we własnej usłudze Azure Data Lake Storage nie będzie można włączyć udostępniania danych danym data lake zarządzanym przez funkcję Dataverse.
> - W przypadku włączenia udostępniania usłudze Dataverse, nie będzie można [tworzyć przewidywanych lub brakujących wartości w encji](predictions.md).

### <a name="step-4-finalize-the-settings"></a>Krok 4. Sfinalizuj ustawienia

W kroku **Przegląd** przejdź przez wszystkie określone ustawienia. Kiedy wszystko wygląda na zakończone, wybierz opcję **Utwórz**, aby skonfigurować środowisko. 

Większość ustawień można też zmienić później. Aby uzyskać więcej informacji, zobacz [Zarządzanie środowiskami](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Praca z nowym środowiskiem

Przejrzyj poniższe artykuły, aby ułatwić sobie pracę z konfigurowaniem aplikacji Customer Insights: 

- [Dodawanie więcej użytkowników i przypisywanie uprawnień](permissions.md).
- [Pozyskuj źródła danych](data-sources.md) i uruchamiaj je w [procesie ujednolicenia danych](data-unification.md), aby uzyskać [ujednolicone profile klientów](customer-profiles.md).
- [Wzbogać ujednolicone profile klientów](enrichment-hub.md) lub [uruchom modele predykcyjne](predictions-overview.md).
- [Utwórz segmenty](segments.md) w celu grupowania klientów i [miary](measures.md) w celu przeglądania wskaźników KPI.
- [Konfiguruj połączenia](connections.md) i [eksporty](export-destinations.md) w celu przetwarzania podzbiorów danych w innych aplikacjach.
