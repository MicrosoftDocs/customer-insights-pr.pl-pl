---
title: Strona główna w statystykach odbiorców
description: Rozpocznij przeglądanie aplikacji na stronie głównej.
ms.date: 09/30/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: bd16966eabb126d9c9945ededc53273df02c3369
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406578"
---
# <a name="create-a-new-environment"></a>Utwórz nowe środowisko

## <a name="create-a-trial-environment"></a>Utwórz środowisko próbne

Możesz zarejestrować się dla uzyskania środowiska próbnego na [stronie rejestracji wersji próbnej](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Wersje próbne wygasają po 30 dniach.

1. Wybierz opcję **Zarejestruj się, aby skorzystać z wersji próbnej** i wybierz **Zarejestruj się teraz**.

1. Podaj służbowy i szkolny adres e-mail i przekaż nam więcej informacji o sobie i wybierz **Dalej**.

1. Wprowadź **Nazwę** nowego środowiska. 

1. Wybierz typ próbny.

1. Wybierz **Region** dla środowiska.

1. Opcjonalnie, dla administratorów organizacji Dynamics 365: Wybierz **Ustawienia zaawansowane** i wprowadź adres URL organizacji, aby używać funkcji przewidywania, takich jak rezygnacja klienta.

1. Wybierz pozycję **Utwórz**. 

Po utworzeniu środowiska zobaczysz środowisko **Demonstracyjne**, co umożliwi zapoznanie się z aplikacją z fikcyjnymi danymi. Możesz zmienić przykładowe dane, aby odpowiadały Twojej branży. Wybierz ikonę **Ustawienia** w nagłówku i wybierz **Ustawienia demonstracyjne**. Oprócz tego możesz zmienić motyw wizualny. 

Użytkownik [przechodzi do środowiska](#change-between-environments) utworzonego podczas procesu rejestracji, aby móc pracować z własnymi danymi.

## <a name="create-a-new-production-or-sandbox-environment"></a>Utwórz nowe środowisko produkcyjne lub środowisko piaskownicy

W środowisku wybierz ikonę **Ustawienia** w nagłówku i wybierz **Nowe środowisko**.

Wykonaj te kroki, jakbyś przeprowadzał [tworzenia środowiska próbnego](#create-a-trial-environment). Dodatkową opcję otrzymasz po wybraniu **Ustawienia zaawansowane**, aby przechowywać dane we własnym Azure Data Lake. Podaj nazwę konta i klucz konta, aby ustanowić połączenie z usługą Azure Data Lake. Domyślnie dane są przechowywane w repozytorium typu lake zarządzanym przez Customer Insights.

> [!IMPORTANT]
> Zapisując dane w Azure Data Lake Storage, zgadzasz się na przenoszenie danych do lokalizacji geograficznej odpowiedniej dla danego konta usługi Azure Storage i przechowywanie ich w tej lokalizacji, przy czym ta lokalizacja może być inna niż lokalizacja, w której są przechowywane dane zapisane w Dynamics 365 Customer Insights. [Więcej informacji znajduje się w centrum zaufania Microsoft.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Odkrywanie strony głównej

Dostęp do [środowiska Customer Insights](https://home.ci.ai.dynamics.com/) jest możliwy pod następującym adresem URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
**Strona główna** ukazuje przegląd bazy i kluczowych miar klienta w celu śledzenia kondycji firmy.

> [!div class="mx-imgBorder"] 
> ![Informacje na stronie głównej](media/home-page-insights.png "Informacje na stronie głównej")

W obszarze **Ostatnie segmenty** widoczne są grupy klientów oparte na zdefiniowanych przez użytkownika atrybutach demograficznych, behawioralnych lub transakcyjnych. [Tworzenie segmentów](segments.md) pomaga w lepszym ukierunkowywaniu działań biznesowych.

**Ostatnie miary** ukazuje kafelki z [miarami](measures.md). Miary są zdefiniowanymi kluczowymi wskaźnikami wydajności (KPI). Na przykład średnie prawdopodobieństwo rezygnacji klienta lub przeciętne wydatki online na klienta.

Sekcja **Ostatnie wzbogacenia** przedstawia wyniki wzbogaceń, które zakończyły się ostatnio. Wzbogacenia dodają informacje o bazie klientów. Na przykład dzięki zrozumieniu zainteresowań i marek, z którymi mają oni koligacje. Te informacje można odblokować, korzystając z funkcji [wzbogacania](enrichment-microsoft-graph.md), po ukończeniu etapów [mapowania](map-entities.md), [dopasowywania](match-entities.md) i [scalania](merge-entities.md).

## <a name="change-between-environments"></a>Zmiana między środowiskami

Po skonfigurowaniu [źródeł danych](data-sources.md) będziesz chciał przejść ze środowiska demonstracyjnego do środowiska na żywo. Korzystanie ze środowiska produkcyjnego pozwala pracować z danymi klientów. Wybierz kontrolkę **Środowiska** w prawym górnym rogu strony, aby zmienić środowiska.

> [!div class="mx-imgBorder"] 
> ![Przełącz środowiska](media/home-page-environment-switcher.png "Przełącz środowiska")

Administratorzy mogą tworzyć i zarządzać [wieloma środowiskami](manage-environments.md). Utrzymywanie więcej niż jednego środowiska może być przydatne, jeśli na przykład organizacja pracuje na płaszczyźnie międzynarodowej i w różny sposób trzeba posegregować dane i wyniki analiz.

## <a name="next-step"></a>Następny krok

Aby zobaczyć własne wyniki analiz na stronie głównej, musisz najpierw [dodać źródła danych](data-sources.md) i [ujednolicić](data-unification.md) dane w celu zbudowania profili klientów.
