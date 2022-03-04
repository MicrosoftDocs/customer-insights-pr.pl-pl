---
title: Raporty dot. lejka
description: Sposób korzystania z raportów dot. lejka w celu zrozumienia, jak odbiorcy podejmują decyzje.
ms.reviewer: mhart
ms.author: kamacdon
author: kamacdon
ms.date: 09/21/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7bb961c5ba8d42f704eefe0dcb22e561367f3efb
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226274"
---
# <a name="create-and-manage-funnel-reports"></a>Tworzenie i zarządzanie raportami lejkowymi

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Raport lejka zbiera informacje o krokach, które występują podczas podróży klienta przez Twoją stronę internetową lub aplikację mobilną. Pomaga zrozumieć, w jaki sposób odbiorcy przechodzą przez proces i identyfikuje punkty rezygnacji. Na przykład można użyć raportu lejkowego w celu zidentyfikowania ścieżek, którymi podążają Twoi klienci zanim dokonają zakupu. Raport dot. lejka zawiera dane służące do podejmowania decyzji oraz identyfikowania obszarów, w których usprawnia się i udoskonala proces.

## <a name="create-a-funnel-report"></a>Tworzenie raportu dot. lejka

Aby utworzyć raport dot. lejka, określ kroki, które ma obejmować, oraz działanie dla każdego kroku. Działanie to [zdarzenie](glossary.md) reprezentujące zachowanie użytkownika. W raporcie dot. lejka jest wyświetlana liczba użytkowników, którzy ukończyli każdy zdefiniowany krok. 

1. Przejdź do **Lejek** i wybierz opcję **+Nowy lejek**, aby uruchomić raport dot. lejka.

1. W **Edytorze lejków** w obszarze **Kroki** wybierz **+Dodaj krok.** 

1. Wprowadź nazwę w **tytule kroku**.

   :::image type="content" source="media/new-funnel-report.png" alt-text="Nowy raport dot. lejka.":::

1. Wybierz **Działanie**. Działanie jest rekordem w momencie, gdy użytkownik wyświetla stronę (Działanie **Wyświetlanie**) lub wchodzi w interakcję z treścią (Działanie **Akcja**).

1. Użyj **Kryteriów kroku** do określenia obszaru działania. [Wymiary](dimensions.md) to atrybuty, które mogą być opisane, odfiltrowane lub grupować dane.

1. Opcjonalnie można skonfigurować kroki lejka wielowęgotowego. Wybierz opcję **Dodaj warunek**, aby określić w kroku więcej rozmiarów. Dodatkowe kryteria muszą korzystać z tego samego typu działania. Można określić, czy warunki są połączone z operatorem AND (ORAZ), czy OPERATOREM OR (LUB).

   :::image type="content" source="media/funnel-add-condition.png" alt-text="Edytor lejków pokazujący konfigurację kroków z wieloma warunkami.":::

1. Wybierz opcję **Dodaj krok**, aż zakończysz wszystkie kroki, które chcesz wykonać w raporcie.

1. Wybierz opcję **Zapisz**, nazwij raport i **Zapisz ponownie**. 

### <a name="example-fourth-coffee-company-funnel-report"></a>Przykład: raport dot. lejka firmy Fourth Coffee

W następującym scenariuszu pokazano jeden sposób korzystania z raportu dot. lejka. Analityk firmy Fourth Coffee chce zrozumieć wpływ ostatniej promocji na ceny subskrypcji. Analityk tworzy raport dot. lejka identyfikujący działanie klienta. Rozpoczyna się w momencie, gdy przybędziemy do strony głównej firmy i trwa do momentu użycia przez klienta kodu promocyjnego subskrypcji. Analityk tworzy raport dot. lejka o następujących krokach:

Krok 1: Klienci, którzy trafiają na stronę główną   
Krok 2: Klienci, którzy dokonują zakupu   
Krok 3: Klienci, którzy korzystają z kodu promocyjnego w celu uzyskania rabatu za subskrypcję   
Krok 4: Rejestracja subskrypcji   

:::image type="content" source="media/funnel-report-example.png" alt-text="przykład raportu dot. lejka.":::
  
Ten lejek pozwala zobaczyć liczbę użytkowników, którzy użyli kodu promocyjnego po jednorazowym zakupie, aby zapisać się do programu abonamentowego.

### <a name="configure-advanced-settings"></a>Konfigurowanie ustawień zaawansowanych 

Raporty lejków pozwalają na określenie limitu czasu potrzebnego do ukończenia lejka. Można na przykład ustawić czas, kiedy lejek ma zostać ukończony na cztery dni. To ustawienie będzie zliczać tylko udane zapisy do subskrypcji, które nastąpiły w ciągu czterech dni od odwiedzenia strony głównej przez użytkownika.

1. Przejdź do **Lejek**, aby otworzyć **bibliotekę lejków**.

1. Wybierz nazwę raportu, aby go otworzyć. 

1. W okienku **Edytor lejkowy** wybierz opcję **Ustawienia zaawansowane**. 

1. Ustaw opcję Ogranicz czas tworzenia lejka na **Włączony**.

   :::image type="content" source="media/funnel-limit-time.png" alt-text="Edytor lejków pokazujący zaawansowane ustawienia i opcje ograniczające czas na ukończenie lejka.":::

1. Wybierz czas, przez który lejek musi zostać ukończony, na liście rozwijanej **Ustaw limit**.

1. Wybierz pozycję **Zapisz**, aby zastosować zmiany.


## <a name="cross-channel-funnel-reports"></a>Raporty lejka między kanałami 

Analiza zaangażowania może również służyć do zbierania danych behawioralnych o klientach w Twojej aplikacji mobilnej. Gdy utworzysz aplikację mobilną za pomocą analizy zaangażowania w [Android SDK](get-started-android.md) lub [iOS SDK](get-started-ios.md), możesz tworzyć raporty lejka między kanałami. 

### <a name="create-a-cross-channel-funnel-report"></a>Stwórz raport dotyczący lejka międzykanałowego 

1. Wykonaj kroki, aby [utworzyć raport lejka](#create-a-funnel-report).    

1. Aby śledzić, w jaki sposób klienci wchodzą w interakcje z Twoją marką zarówno na stronie internetowej, jak i w aplikacji mobilnej, lub na wielu stronach internetowych, użyj przełącznika obszarów roboczych do tworzenia kroków lejka z danymi z innych obszarów roboczych. W **edytorze lejka** w obszarze **Kroki** wybierz obszar roboczy, z którego mają pochodzić dane dla kroku lejka.

## <a name="manage-funnel-reports"></a>Zarządzaj raportami dot. lejka

Możesz przeglądać raporty dot. lejka, aby analizować dane, śledzić wydajność i zbierać spostrzeżenia.

> [!NOTE]
> - Raporty lejka analizy interakcji obsługują obecnie scenariusze, w których wszyscy użytkownicy w lejku są anonimowi lub wszyscy użytkownicy są uwierzytelnieni. 
> - Dane historyczne w raportach lejka są dostępne z ostatnich 30 dni.

### <a name="view-funnel-reports"></a>Wyświetl raporty dot. lejka

1. Przejdź do **Lejek**, aby otworzyć **bibliotekę lejków**.
1. Wybierz nazwę raportu, aby go otworzyć.    

### <a name="see-the-data-collected-for-a-report"></a>Wyświetlanie danych zebranych dla raportu   

Aby wyświetlić informacje o etapie

- Wskaż krok raportu.

:::image type="content" source="media/funnel-step-data.png" alt-text="dane lejka.":::

### <a name="change-the-date-range-for-the-funnel-report"></a>Zmiana zakresu dat raportu lejka

1. Przejdź do **Lejek**, aby otworzyć **bibliotekę lejków**.

1. Wybierz nazwę raportu, aby go otworzyć.

1. Otwórz **zakres czasu** i wybierz nowy okres z listy lub **Stały zakres dat**, aby określić zakres dat.

## <a name="edit-or-delete-funnel-reports"></a>Edytowanie lub usuwanie raportów dot. lejka

Można zmienić nazwę raportu dot. lejka, usunąć go lub zmodyfikować kroki raportu.

### <a name="rename-or-delete-a-funnel-report"></a>Zmienianie nazwy raportu dot. lejka lub usuwanie go

1. Przejdź do **Lejek**, aby otworzyć **bibliotekę lejków**. 

1. Wybierz opcję **Więcej** obok raportu, który chcesz zmienić, i wybierz opcję **Edytuj nazwę** lub **Usuń**.

### <a name="edit-a-funnel-step"></a>Edytowanie kroku lejka  

1. Przejdź do **Lejek**, aby otworzyć **bibliotekę lejków**. 

1. Wybierz nazwę raportu, aby go otworzyć.

1. Wybierz krok, który chcesz edytować.

1. Zaznacz **Edytuj**.

1. W **Edytorze lejków** zaktualizuj informacje, które chcesz zmienić.  

1. Wybierz pozycję **Zapisz**.

### <a name="reorder-a-funnel-step"></a>Zmienianie kolejności dla kroku lejka

1. Przejdź do **Lejek**, aby otworzyć **bibliotekę lejków**. 

1. Wybierz nazwę raportu, aby go otworzyć.

1. Wybierz krok, którego kolejność chcesz edytować.

1. Wybierz opcję **Przenieś**, a następnie **w górę**, **w dół**, **Na górę** lub **Na dół**, aby przenieść krok.

### <a name="delete-a-funnel-step"></a>Usuwanie kroku lejka

1. Przejdź do **Lejek**, aby otworzyć **bibliotekę lejków**. 

1. Wybierz nazwę raportu, aby go otworzyć.

1. Wybierz krok, który chcesz usunąć, a następnie wybierz opcję **Usuń**.

## <a name="funnel-insights"></a>Szczegółowe informacje dotyczące lejka 

Szczegółowe informacje o klientach oferują obecnie szczegółowe informacje dotyczące lejka dla klientów. Dzięki funkcji szczegółowych informacji dotyczących lejka można uzyskać głębsze dane na temat zachowań klientów w ramach kroków raportu lejka. Podczas tworzenia i zapisywania nowego raportu dotyczące lejka szczegółowe informacje o lejku są automatycznie generowane dla raportu. 

:::image type="content" source="media/funnel-insights.png" alt-text="Szczegółowe informacje dotyczące lejka.":::

> [!NOTE]
> Szczegółowe informacje dotyczące lejka można generować tylko dla kroków lejka, które **nie** uwzględniają niestandardowych wymiarów. Do generowania szczegółowych informacji dotyczących lejka dla wszystkich kroków należy użyć gotowych wymiarów z wyników analiz interakcji do utworzenia kroków lejka. 

Szczegółowe informacje dotyczące lejka można wyświetlać w następujących kategoriach na poziomie głównym i kroku: 

 - Współczynnik konwersji
 -    Współczynnik konwersji między krokiem realizacji i krokiem zakupu wynosi 22%.
 - Czas przejścia 
 -    Średni czas przejścia między krokiem koszyka i krokiem realizacji wynosi 23 minuty. 
 - Czas ukończenia 
 -    Średni czas, przez który klienci są w stanie ukończyć lejek, wynosi 47 minut. 

Dzięki szczegółowym informacjom można poznać sposób zachowania klientów oraz lepiej poznać punkty zwrotu i konwersje dla raportu lejka. 

Aby porównywać szczegółowe informacje z różnych kroków, wybierz pozycję **Zobacz podział kroków** lub **Porównaj z innymi krokami** na kartach szczegółowych informacji. Spowoduje to wyświetlenie wykresu słupkowego porównującego metryki dla każdego kroku lejka. 

Szczegółowe informacje dotyczące lejka są ponownie przeliczane co 24 godziny lub podczas **zapisywania** raportu lejka. 

> [!NOTE]
> Aby wyświetlić szczegółowe informacje dotyczące lejka, należy zapisać raport przy każdym wprowadzeniu zmian. 

