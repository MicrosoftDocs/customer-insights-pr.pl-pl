---
title: Tworzenie i konfigurowanie wersji próbnej usługi Customer Insights
description: Kroki, aby uzyskać wersję próbną usługi Dynamics 365 Customer Insights i ją skonfigurować.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 3a235e924395a606b9332de3d205289288a597a9
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558836"
---
# <a name="set-up-a-trial-environment"></a>Konfigurowanie wersji próbnej środowiska 

Wersja próbna Dynamics 365 Customer Insights umożliwia przeglądanie kluczowych funkcji i lepsze poznanie różnych funkcji. Subskrypcja próbna jest usuwana po wygaśnięciu. Środowiska próbne są tworzone przez indywidualnych użytkowników, którzy stają się administratorem środowiska próbnego. Mogą zaprosić więcej użytkowników do swojej wersji próbnej i konfigurować różne funkcje.

## <a name="create-a-trial-environment"></a>Utwórz środowisko próbne

Możesz zarejestrować się dla uzyskania środowiska próbnego na [stronie rejestracji wersji próbnej](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

1. Wybierz opcję **Zarejestruj się, aby skorzystać z wersji próbnej** i wybierz **Zarejestruj się teraz**.

1. Podaj służbowy adres e-mail, powiedz nam więcej o sobie i wybierz **Rozpocznij**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Okno dialogowe w celu rejestracji w wystąpieniu wersji próbnej":::

1. Przejrzyj postanowienia i wybierz **Kontynuuj**, by potwierdzić.

1. Wprowadź **Nazwę** nowego środowiska. 

1. Ustaw **Typ** środowiska jako **Wersję próbną**.

1. W polu **Wybierz wersję demonstracyjną branży** można opcjonalnie wybrać zestaw danych specyficzny dla branży. Można również [zmienić na wersję demonstracyjną branży](#use-industry-specific-demo-data-sets-in-audience-insights) później i rozpocząć z domyślnym zestawem danych.

1. Wybierz **Region** dla środowiska.

1. Opcjonalnie, jeśli jesteś administratorem organizacji Dynamics 365: wybierz **Ustawienia zaawansowane** i podaj adres URL organizacji, aby używać funkcji przewidywania, takich jak przewidywanie rezygnacji klienta. 

1. Wybierz pozycję **Utwórz**. 

Konfiguracja środowiska trwa kilka minut. Po zakończeniu nastąpi przekierowanie do środowiska demonstracyjnego lub wersji demonstracyjnej branży, którą wybrano w powyższym kroku. Teraz możesz eksplorować aplikację za pomocą danych demonstracyjnych tylko do odczytu. Aby dodać własne dane do środowiska, zobacz [Tworzenie danych demonstracyjnych specyficznych dla scenariusza we własnym środowisku](#create-scenario-specific-demo-data-in-your-own-environment).

:::image type="content" source="media/trial-environment.png" alt-text="Zrzut ekranu przedstawiający nowo utworzone środowisko próbne.":::

## <a name="use-industry-specific-demo-data-sets-in-audience-insights"></a>Korzystanie z branżowych zestawów danych demonstracyjnych w szczegółowych informacjach o odbiorcy

Łączenie rzeczywistych źródeł danych jest jednym z kluczowych kroków w korzystaniu z funkcji Customer Insights. Aby wypróbować funkcje bez zakłócania własnych danych, można opcjonalnie użyć danych demonstracyjnych specyficznych dla branży. Dostępnych jest kilka zestawów danych demonstracyjnych dla następujących branż: 

-   Motoryzacja
-   Bankowość
-   Towary konsumpcyjne
-   Instytucje rządowe
-   Ochrona zdrowia
-   Hotelarstwo
-   Ubezpieczenia
-   Wytwarzanie
-   Usługi profesjonalne
-   Handel detaliczny

### <a name="see-industry-specific-demo-data-in-trials"></a>Wyświetlanie danych demonstracyjnych specyficznych dla branży w wersjach próbnych

W przypadku wersji tylko do odczytu usługi Customer Insights dostosowanej do określonej branży lub scenariusza rozpocznij pracę w środowisku demonstracyjnym. 
 
1.  W szczegółowych informacjach odbiorcy wybierz środowisko **Demo** w selektorze środowiska.

2.  W **Menu głównym** wybierz opcję z menu rozwijanego Wybierz prezentację branżową.

:::image type="content" source="media/trial-select-industry-demo.png" alt-text="Wybierz branżę dla środowiska próbnego.":::

### <a name="create-scenario-specific-demo-data-in-your-own-environment"></a>Tworzenie danych demonstracyjnych specyficznych dla scenariusza we własnym środowisku

Jako administrator wybierz selektor środowiska w nagłówku aplikacji, aby utworzyć nowe środowisko. W nowym środowisku można skonfigurować własne źródła danych i skonfigurować aplikację zgodnie z wymaganiami. 

1.  W analizach odbiorców przejdź do **Dane** > **Źródła danych**.

2.  Aby zaimportować własne źródła danych, przejdź do [przewodnika po pozyskiwaniu danych](data-sources.md).     
   Jeśli wolisz pracować z przykładowymi danymi, które umożliwiają wypróbowanie pozyskiwania danych, możesz pozyskać dane demonstracyjne branży w danym środowisku. Wybierz opcję **Importuj z usługi Datahub** i wykonaj poniższe czynności.

3.  Wybierz kartę branżową, która odpowiada scenariuszowi. 

4.  Przejrzyj i opcjonalnie zaktualizuj sugerowaną nazwę źródła danych. 

5.  Wybierz przycisk **Dalej**, aby pochłonąć przykładowe dane. 

Teraz można użyć pozyskanych danych, aby dostosować Customer Insights do scenariusza. Aby wyświetlić środowisko specyficzne dla pozyskanych danych demonstracyjnych, wybierz opcję **Demo <Industry>** w selektorze środowiska.

## <a name="limitations-in-trials"></a>Ograniczenia w wersjach próbnych

- Wersje próbne są domyślnie aktywne przez 30 dni. Możesz je jednak przedłużyć po 23 dniu po zalogowaniu się do wersji próbnej.
- Nie można użyć własnego konta usługi Azure Data Lake Storage do przechowywania danych wyjściowych podczas wersji próbnej. Można jednak pozyskać dane z konta Data Lake Storage.
- W środowisku usługi Dataverse można przechowywać maksymalnie 3 GB danych, które są automatycznie aprowizowane po rozpoczęciu wersji próbnej aplikacji Customer Insights.

## <a name="copy-data-from-a-trial-to-a-paid-subscription"></a>Kopiowanie danych z wersji próbnej do płatnej subskrypcji

Ogólnie rzecz biorąc, zalecamy rozpoczęcie od początku z własnymi danymi podczas uaktualniania do płatnej wersji usługi Customer Insights. 

Opcjonalnie można skopiować dane ze środowiska próbnego, jeśli kupisz Customer Insights. Musisz być administratorem wersji próbnej Customer Insights i globalnym administratorem dzierżawcy Microsoft 365 lub administratorem usługi Dynamics 365 w organizacji, by migrować ustawienia ze środowiska próbnego do płatnego. 

Po zalogowaniu się do płatnego wystąpienia usługi Customer Insights po raz pierwszy zostaniesz poproszony o utworzenie nowego środowiska. W tym procesie można skopiować konfigurację z istniejącego środowiska i przeprowadzić migrację większości ustawień. Jeśli masz uprawnienia wymienione powyżej, środowisko próbne pojawi się na tej liście. Aby uzyskać więcej informacji, zobacz [Kopiowanie konfiguracji środowiska](manage-environments.md#copy-the-environment-configuration).

## <a name="next-steps"></a>Następne kroki

Zapoznaj się z poniższymi artykułami, aby ułatwić sobie rozpoczęcie konfigurowania usługi Customer Insights. 

- [Dodawanie więcej użytkowników i przypisywanie uprawnień](permissions.md).
- [Pozyskuj źródła danych](data-sources.md) i uruchamiaj je w [procesie ujednolicenia danych](data-unification.md), aby uzyskać [ujednolicone profile klientów](customer-profiles.md).
- [Wzbogać ujednolicone profile klientów](enrichment-hub.md) lub [uruchom modele predykcyjne](predictions-overview.md).
- Tworzenie [segmentów](segments.md) w celu grupowanie klientów i [mierzenie](measures.md) przeglądu wskaźników KPI.
- Konfiguruj [połączenia](connections.md) i [eksporty](export-destinations.md) do przetwarzania podzbiorów danych w innych aplikacjach.
