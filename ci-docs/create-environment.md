---
title: Utwórz nowe środowisko
description: Kroki do tworzenia środowisk w rozwiązaniu Dynamics 365 Customer Insights.
ms.date: 08/15/2022
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
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304257"
---
# <a name="create-a-new-environment"></a>Utwórz nowe środowisko

Po [zakupieniu licencji subskrypcji usługi Dynamics 365 Customer Insights](paid-license.md) administrator globalny dzierżawy usługi Microsoft 365 otrzymuje wiadomość e-mail z zaproszeniem do utworzenia środowiska. Przejdź do [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start), aby rozpocząć. W tym scenariuszu zacznij od [Krok 1: podaj podstawowe informacje](#step-1-provide-basic-information).

Po utworzeniu pierwszego środowiska administrator globalny dzierżawy Microsoft 365 może [dodawać użytkowników z ich organizacji jako administratorów](permissions.md). Administratorzy ci mogą następnie zarządzać użytkownikami i środowiskami. Jeśli Twoja organizacja kupi więcej niż jedną licencję na Customer Insights, [skontaktuj się z naszym zespołem pomocy technicznej](https://go.microsoft.com/fwlink/?linkid=2079641), aby zwiększyć liczbę dostępnych środowisk Aby uzyskać więcej informacji dotyczących wydajności i wydajności dodatku, przejrzyj przewodnik [licencjonowania usługi Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544). Po utworzeniu dodatkowych środowisk przejdź [do procesu tworzenia środowiska](#start-the-environment-creation-process).

> [!TIP]
> Jeśli chcesz wypróbować tę usługę, zobacz [Konfigurowanie środowiska w wersji próbnej](trial-signup.md).

## <a name="prerequisites"></a>Wymagania wstępne

[Uprawnienia administratora](permissions.md) w Customer Insights

## <a name="start-the-environment-creation-process"></a>Rozpoczynanie procesu tworzenia środowiska

1. Otwórz selektor środowiska i wybierz opcję **+ Nowy**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Wybierz selektor środowiska.":::

1. Postępuj zgodnie ze wskazówkami opisanymi w poniższych sekcjach, aby podać wszystkie wymagane informacje dotyczące nowego środowiska.

## <a name="step-1-provide-basic-information"></a>Krok 1: Podaj podstawowe informacje

1. Wybierz, czy chcesz utworzyć środowisko od podstaw, czy skopiować dane z innego środowiska. [Kopiowanie danych z innego środowiska](#copy-the-environment-configuration) wymaga dodatkowych kroków.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Okno dialogowe, aby utworzyć nowe środowisko Customer Insights.":::

1. Podaj następujące szczegóły:

   - **Nazwa**: Nazwa tego środowiska. To pole jest już wypełnione, jeśli skopiowano istniejące środowisko, ale można to zmienić.
   - **Wybierz swoją firmę**: główni odbiorcy w nowym środowisku: indywidualni konsumenci (B-do-C) lub [konta firmowe](work-with-business-accounts.md) (B-to-B). Jeśli Twoja organizacja prowadzi interesy głównie z osobami, takimi jak sprzedawca detaliczny lub kawiarnia, wybierz indywidualnych konsumentów. Jeśli głównymi odbiorcami są inne firmy, takie jak producent samochodów lub firma papiernicza, wybierz konta biznesowe.
   - **Typ**: Rodzaj środowiska: produkcja lub piaskownica. Środowiska piaskownicy nie zezwalają na zaplanowane odświeżanie danych i są przeznaczone do wstępnej implementacji i testowania. Środowiska piaskownicy używają tych samych podstawowych odbiorców co aktualnie wybrane środowisko produkcyjne.
   - **Region**: Region, w którym usługa jest wdrażana i hostowana. Aby [korzystać z własnego konta Azure Data Lake Storage](own-data-lake-storage.md) lub [połączyć się z istniejącą organizacją Microsoft Dataverse](customer-insights-dataverse.md), środowisko Customer Insights musi być w tym samym regionie.

1. Wybierz **Dalej**.

## <a name="step-2-configure-data-storage"></a>Krok 2. Skonfiguruj magazyn danych

1. Wybierz miejsce przechowywania danych Customer Insights:

   - **Magazyn Customer Insights**: Przechowywanie danych jest zarządzane automatycznie. Jest to opcja domyślna i jeśli nie ma określonych wymagań dotyczących przechowywania danych na własnym koncie magazynu, zalecamy użycie tej opcji.
   - **Azure Data Lake Storage**: własne konto Azure Data Lake Storage do przechowywania danych, aby mieć pełną kontrolę nad miejscem przechowywania danych. Wykonaj kroki opisane w [Korzystanie z własnego konta Azure Data Lake Storage](own-data-lake-storage.md).

   :::image type="content" source="media/data-storage-environment.png" alt-text="Wybierz preferowaną opcję przechowywania danych.":::

1. Wybierz **Dalej**.

## <a name="step-3-connect-to-microsoft-dataverse"></a>Krok 3. Nawiąż połączenie z funkcją Microsoft Dataverse

Jeśli masz środowisko Dataverse, połącz Customer Insights. Udostępniaj dane za pomocą Dataverse, aby używać ich z aplikacjami biznesowymi opartymi na Dataverse, takimi jak Dynamics 365 Marketing lub aplikacje oparte na modelach w Power Apps.

1. Wykonaj kroki opisane w tece [Praca z danymi aplikacji Customer Insights w programie Microsoft Dataverse](customer-insights-dataverse.md).

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="udostępnianie danych z włączoną automatycznie obsługą Microsoft Dataverse dla nowych środowisk sieci.":::

1. Wybierz **Dalej**.

## <a name="step-4-finalize-the-settings"></a>Krok 4. Sfinalizuj ustawienia

Przejrzyj podane ustawienia. Kiedy wszystko wygląda na zakończone, wybierz opcję **Utwórz**, aby skonfigurować środowisko.

Aby zmienić niektóre ustawienia później, zobacz temat [Zarządzanie środowiskami](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Praca z nowym środowiskiem

Przejrzyj poniższe artykuły, aby ułatwić sobie pracę z konfigurowaniem aplikacji Customer Insights:

- [Dodawanie więcej użytkowników i przypisywanie uprawnień](permissions.md).
- [Pozyskuj źródła danych](data-sources.md) i uruchamiaj je w [procesie ujednolicenia danych](data-unification.md), aby uzyskać [ujednolicone profile klientów](customer-profiles.md).
- [Wzbogać ujednolicone profile klientów](enrichment-hub.md) lub [uruchom modele predykcyjne](predictions-overview.md).
- [Utwórz segmenty](segments.md) w celu grupowania klientów i [miary](measures.md) w celu przeglądania wskaźników KPI.
- [Konfiguruj połączenia](connections.md) i [eksporty](export-destinations.md) w celu przetwarzania podzbiorów danych w innych aplikacjach.

## <a name="copy-the-environment-configuration"></a>Kopiowanie konfiguracji środowiska

Jako administrator, jeśli zdecydujesz się skopiować konfigurację z istniejącego środowiska, wybierz z listy wszystkich dostępnych środowisk w Twojej organizacji.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Zrzut ekranu przedstawiający opcje ustawień w ustawieniach środowiska.":::

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

### <a name="set-up-a-copied-environment"></a>Skonfiguruj skopiowane środowisko

Podczas kopiowania konfiguracji środowiska, po utworzeniu skopiowanego środowiska wyświetlany jest komunikat potwierdzający. Wykonaj następujące kroki, aby potwierdzić poświadczenia.

1. Wybierz **Przejdź do źródeł danych**, aby wyświetlić listę źródeł danych. Wszystkie źródła danych ukażą stan **Wymagane poświadczenia**.

   :::image type="content" source="media/data-sources-copied.png" alt-text="Lista źródeł danych, które zostały skopiowane i wymagają uwierzytelniania.":::

1. Dokonaj edycji źródeł danych i wprowadź poświadczenia, aby je odświeżyć. Źródła danych z folderu Common Data Model i Dataverse muszą być tworzone ręcznie z taką samą nazwą jak w środowisku źródłowym.

1. Po odświeżeniu źródeł danych przejdź do **Dane** > **Ujednolicanie**. W tym miejscu można znaleźć ustawienia z poziomu środowiska źródłowego. Edytuj je w razie potrzeby lub wybierz **Ujednolicić** > **Ujednolicić profile i zależności klientów**, aby rozpocząć proces ujednolicenia danych i utworzyć ujednoliconą jednostkę klienta.

   > [!TIP]
   > W przypadku kont i kontaktów wybierz **Ujednolicenie kont** > **Ujednolicenie profili i zależności**.

1. Po zakończeniu ujednolicania danych należy przejść do **Miary** i **Segmenty**, aby je również odświeżyć.

1. Przejdź do **Administrator** > **Połączenia**, aby ponownie uwierzytelnić połączenia w nowym środowisku.

1. Przejdź do **Dane** > **Wzbogacenie** i **Dane** > **Eksporty** w celu ponownej aktywacji.

[!INCLUDE [footer-include](includes/footer-banner.md)]
