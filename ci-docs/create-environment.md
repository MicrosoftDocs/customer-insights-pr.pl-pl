---
title: Instrukcje - Utwórz nowe środowisko
description: Kroki tworzenia środowisk dla dla Dynamics 365 Customer Insights.
ms.date: 05/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 6dfaa09cd80498e9a4e4dea6a07ce6e9d29105e2
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011624"
---
# <a name="how-to-create-a-new-environment"></a>Instrukcje: Utwórz nowe środowisko

Po [zakupieniu licencji subskrypcji usługi Dynamics 365 Customer Insights](paid-license.md) administrator globalny dzierżawy usługi Microsoft 365 otrzymuje wiadomość e-mail z zaproszeniem do utworzenia środowiska. Przejdź do [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start), aby rozpocząć. W tym scenariuszu można przejść bezpośrednio do [Krok 1: podaj podstawowe informacje](#step-1-provide-basic-information).

Po utworzeniu pierwszego środowiska administrator globalny dzierżawy Microsoft 365 może [dodawać użytkowników z ich organizacji jako administratorów](permissions.md). Administratorzy mogą dalej zarządzać użytkownikami i środowiskami. Jeśli Twoja organizacja kupi więcej niż jedną licencję na Customer Insights, [skontaktuj się z naszym zespołem pomocy technicznej](https://go.microsoft.com/fwlink/?linkid=2079641), aby zwiększyć liczbę dostępnych środowisk Aby uzyskać więcej informacji dotyczących wydajności i wydajności dodatku, przejrzyj przewodnik [licencjonowania usługi Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!TIP]
> Jeśli chcesz wypróbować tę usługę, zobacz [Konfigurowanie środowiska w wersji próbnej](trial-signup.md).

## <a name="prerequisites"></a>Wymagania wstępne

Aby tworzyć środowiska i zarządzać nimi, musisz mieć [uprawnienia administratora](permissions.md) w aplikacji Customer Insights.

## <a name="start-the-environment-creation-process"></a>Rozpoczynanie procesu tworzenia środowiska

1. Otwórz selektor środowiska i wybierz opcję **+ Nowy**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Wybierz selektor środowiska.":::

1. Postępuj zgodnie ze wskazówkami opisanymi w poniższych sekcjach, aby podać wszystkie wymagane informacje dotyczące nowego środowiska. Jeśli wcześniej skonfigurowano środowisko, można także [skopiować konfigurację](#copy-the-environment-configuration).

## <a name="step-1-provide-basic-information"></a>Krok 1: Podaj podstawowe informacje

W kroku **Podstawowe informacje** wybierz, czy chcesz utworzyć środowisko od podstaw, czy [skopiować dane z innego środowiska](#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Okno dialogowe, aby utworzyć nowe środowisko Customer Insights.":::

Podaj następujące szczegóły:

- **Nazwa**: Nazwa tego środowiska. To pole jest już wypełnione, jeśli skopiowano istniejące środowisko, ale można to zmienić.
- **Wybierz swoją firmę**: wybierz podstawowych odbiorców dla nowego środowiska. Można pracować z poszczególnymi konsumentami (B2C) lub [kontami biznesowymi (B2B)](work-with-business-accounts.md). Jeśli Twoja organizacja prowadzi interesy głównie z osobami, takimi jak sprzedawca detaliczny lub kawiarnia, wybierz indywidualnych konsumentów. Jeśli głównymi odbiorcami są inne firmy, takie jak producent samochodów lub firma papiernicza, wybierz konta biznesowe.
- **Wpisz**: Wybierz, czy chcesz utworzyć środowisko produkcyjne, czy piaskownicę. Środowiska piaskownicy nie zezwalają na zaplanowane odświeżanie danych i są przeznaczone do wstępnej implementacji i testowania. Środowiska piaskownicy używają tych samych podstawowych odbiorców co aktualnie wybrane środowisko produkcyjne.
- **Region**: Region, w którym usługa jest wdrażana i hostowana. Aby [korzystać z własnego konta Azure Data Lake Storage](own-data-lake-storage.md) lub [połączyć się z istniejącą organizacją Microsoft Dataverse](customer-insights-dataverse.md), środowisko Customer Insights musi być w tym samym regionie.

## <a name="step-2-configure-data-storage"></a>Krok 2. Skonfiguruj magazyn danych

W kroku **Magazyn danych** wybierz miejsce przechowywania danych z funkcji Customer Insights.

Do wyboru są dwie opcje:

- **Magazyn Customer Insights**: Przechowywaniem danych zarządza zespół Customer Insights. Jest to opcja domyślna i jeśli nie ma określonych wymagań dotyczących przechowywania danych na własnym koncie magazynu, zalecamy użycie tej opcji.
- **Azure Data Lake Storage**: Określ własne konto Azure Data Lake Storage do przechowywania danych, aby mieć pełną kontrolę nad miejscem przechowywania danych. Aby uzyskać więcej informacji, zobacz [Korzystanie z własnego konta Azure Data Lake Storage](own-data-lake-storage.md).

:::image type="content" source="media/data-storage-environment.png" alt-text="Wybierz preferowaną opcję przechowywania danych.":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>Krok 3. Nawiąż połączenie z funkcją Microsoft Dataverse

Krok **Microsoft Dataverse** umożliwia połączenie aplikacji Customer Insights ze środowiskiem Dataverse. Udostępniaj dane za pomocą Dataverse, aby używać ich z aplikacjami biznesowymi opartymi na Dataverse, takimi jak Dynamics 365 Marketing lub aplikacje oparte na modelach w Power Apps.


Pozostaw to pole puste, jeśli nie masz własnego środowiska Dataverse, a my je dla Ciebie utworzymy.

Aby uzyskać więcej informacji, zobacz [Praca z danymi usługi Customer Insights w Microsoft Dataverse](customer-insights-dataverse.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="udostępnianie danych z włączoną automatycznie obsługą Microsoft Dataverse dla nowych środowisk sieci.":::

### <a name="step-4-finalize-the-settings"></a>Krok 4. Sfinalizuj ustawienia

W kroku **Przegląd** przejdź przez wszystkie określone ustawienia. Kiedy wszystko wygląda na zakończone, wybierz opcję **Utwórz**, aby skonfigurować środowisko.

Niektóre ustawienia możesz zmienić później. Aby uzyskać więcej informacji, zobacz [Zarządzanie środowiskami](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Praca z nowym środowiskiem

Przejrzyj poniższe artykuły, aby ułatwić sobie pracę z konfigurowaniem aplikacji Customer Insights:

- [Dodawanie więcej użytkowników i przypisywanie uprawnień](permissions.md).
- [Pozyskuj źródła danych](data-sources.md) i uruchamiaj je w [procesie ujednolicenia danych](data-unification.md), aby uzyskać [ujednolicone profile klientów](customer-profiles.md).
- [Wzbogać ujednolicone profile klientów](enrichment-hub.md) lub [uruchom modele predykcyjne](predictions-overview.md).
- [Utwórz segmenty](segments.md) w celu grupowania klientów i [miary](measures.md) w celu przeglądania wskaźników KPI.
- [Konfiguruj połączenia](connections.md) i [eksporty](export-destinations.md) w celu przetwarzania podzbiorów danych w innych aplikacjach.

## <a name="copy-the-environment-configuration"></a>Kopiowanie konfiguracji środowiska

Jako administrator możesz skopiować konfigurację z istniejącego środowiska podczas tworzenia nowego.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Zrzut ekranu przedstawiający opcje ustawień w ustawieniach środowiska.":::

Zobaczysz listę wszystkich dostępnych środowisk w organizacji, z których można kopiować dane.

Kopiowane są następujące ustawienia konfiguracji:

- Źródła danych importowane przez Power Query
- Konfiguracja ujednolicania danych
- Segments
- Miary
- Relacje
- Działania
- Wyszukiwanie i indeks filtrów
- Eksporty
- Harmonogram odświeżania
- Wzbogacenia
- Modele przewidywania
- Przypisania ról

## <a name="set-up-a-copied-environment"></a>Skonfiguruj skopiowane środowisko

Podczas kopiowania konfiguracji środowiska musisz wykonać kilka dodatkowych kroków, aby potwierdzić poświadczenia:

- Profile klientów. Najpierw uwierzytelnij i pozyskaj źródła danych oraz uruchom ujednolicenie danych w celu odtworzenia profili klientów.
- Poświadczenia źródła danych. Aby ręcznie uwierzytelnić i odświeżyć źródła danych, musisz podać poświadczenia dla każdego źródła danych.
- Źródła danych z folderu Common Data Model i Dataverse. Musisz ręcznie utworzyć te źródła danych o tej samej nazwie, co w środowisku źródłowym.
- Sekrety połączeń używane do eksportowania i wzbogacania. Musisz ponownie uwierzytelnić połączenia, a następnie ponownie aktywować wzbogacanie i eksporty.

Po utworzeniu skopiowanego środowiska zobaczysz komunikat potwierdzający. Wybierz **Przejdź do źródeł danych**, aby wyświetlić listę źródeł danych.

Wszystkie źródła danych ukażą stan **Wymagane poświadczenia**. Dokonaj edycji źródeł danych i wprowadź poświadczenia, aby je odświeżyć.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lista źródeł danych, które zostały skopiowane i wymagają uwierzytelniania.":::

Po odświeżeniu źródeł danych przejdź do **Dane** > **Ujednolicanie**. W tym miejscu można znaleźć ustawienia z poziomu środowiska źródłowego. Edytuj je zgodnie z wymaganiami lub wybierz **Uruchom**, aby rozpocząć proces ujednolicania danych i utworzyć zunifikowaną encję klienta.

Po zakończeniu ujednolicania danych należy przejść do **Miary** i **Segmenty**, aby je również odświeżyć.

Zanim ponownie aktywujesz eksporty i wzbogacenia, przejdź do **Administrator** > **Połączenia**, aby ponownie uwierzytelnić połączenia w nowym środowisku.

[!INCLUDE [footer-include](includes/footer-banner.md)]
