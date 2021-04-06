---
title: Scalanie encji w przypadku zjednoczenia danych
description: Scalanie encji w celu utworzenia ujednoliconych profili klientów.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 737c593353878a5e322488d00de5dc5db5befda9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597846"
---
# <a name="merge-entities"></a>Scalanie encji

Faza scalania jest ostatnią fazą procesu unifikacji danych. Jego zastosowanie powoduje uzgadnianie danych powodujących konflikty. Przykłady danych powodujących konflikty mogą zawierać nazwy klientów znalezione w dwóch zestawach danych, które są wyświetlane w różny sposób w każdym miejscu („Grant Marshall” i „Grant Marshal”) lub numery telefoniczne, który różnią się formatem (617-803-091X a 617803091X). Scalanie tych niezgodnych danych jest wykonywane na podstawie poszczególnych atrybutów.

Po zakończeniu [fazy dopasowania](match-entities.md) można rozpocząć fazę scalenia, zaznaczając kafelek **Scalanie** na stronie **Ujednolicanie**.

## <a name="review-system-recommendations"></a>Przejrzyj rekomendacje systemu

Na stronie **Scalanie** można wybrać atrybuty do scalenia w encji ujednoliconego profilu klienta (wynik procesu konfiguracji). Niektóre atrybuty są automatycznie scalane przez system.

### <a name="view-merged-attributes"></a>Zobacz scalone atrybuty

Aby wyświetlić atrybuty, które są uwzględnione w jednym z automatycznie scalanych atrybutów, wybierz atrybut, który ma zostać scalony. Dwa atrybuty składające się na ten scalony atrybut są wyświetlane w dwóch nowych wierszach pod atrybutem scalonym.

> [!div class="mx-imgBorder"]
> ![Wyszukaj scalony atrybut](media/configure-data-merge-profile-attributes.png "Wyszukaj scalony atrybut")

### <a name="separate-merged-attributes"></a>Oddziel scalone atrybuty

Aby wyodrębnić lub rozdzielić każdy z automatycznie scalonych atrybutów, znajdź atrybut w tabeli **Atrybuty profilu**.

1. Wybierz przycisk wielokropka (...).
  
2. Z listy rozwijanej wybierz **Rozdziel pola**.

### <a name="remove-merged-attributes"></a>Usuwanie scalonych atrybutów

Aby wykluczyć atrybut z ostatecznej encji profilu klienta, należy go znaleźć w tabeli **Atrybuty profilu**.

1. Wybierz przycisk wielokropka (...).
  
2. Z listy rozwijanej wybierz **Nie scalaj**.

   Atrybut zostanie przeniesiony do sekcji **Usunięto z rekordu klienta**.

## <a name="manually-add-a-merged-attribute"></a>Ręczne dodanie scalonego atrybutu

Aby dodać scalony atrybut, przejdź na stronę **Scalanie**.

1. Wybierz **Dodaj scalony atrybut**.

2. Podaj **Nazwę**, która będzie identyfikować go na stronie **Scalenie** później.

3. Opcjonalnie wprowadź **Nazwę wyświetlaną**, która będzie widoczna w encji ujednoliconego profilu klienta.

4. Konfigurowanie **Wybierz zduplikowane atrybuty** w celu wybrania atrybutów, które mają być scalane z dopasowanych encji. Istnieje również możliwość wyszukiwania atrybutów.

5. Ustaw **Klasyfikuj wg ważności**, aby nadać priorytety jednemu atrybutowi nad innym. Jeśli na przykład encja *WebAccountCSV* zawiera najbardziej dokładne dane o atrybucie *Pełna nazwa*, można przypisać tę encję ponad *ContactCSV*, wybierając pozycję *WebAccountCSV*. W efekcie *WebAccountCSV* przechodzi do pierwszego priorytetu, podczas gdy *ContactCSV* przechodzi do drugiego priorytetu podczas ściągania wartości atrybutu *Pełna nazwa*.

## <a name="run-your-merge"></a>Uruchamianie scalania

Niezależnie od tego, czy ręcznie scalono atrybuty, czy pozwolono, aby system je scalił, zawsze można uruchomić scalanie. Wybierz **Uruchom** na stronie **Scalanie**, aby zacząć proces.

> [!div class="mx-imgBorder"]
> ![Zapis i uruchomienie scalania danych](media/configure-data-merge-save-run.png "Zapis i uruchomienie scalania danych")

Aby dokonać dodatkowych zmian i ponownie uruchomić krok, można anulować trwający proces scalania. Wybierz **Odświeżanie...** i wybierz **Anuluj zadanie**  w pojawiającym się okienku bocznym.

Gdy tekst **Odświeżanie ...** zostanie zmieniony na **Pomyślne**, scalanie zakończyło się i rozwiązano sprzeczności w danych zgodnie z określonymi zasadami. Połączone i niepołączone atrybuty są zawarte w encji ujednolicony profil. Wykluczone atrybuty nie są zawarte w encji ujednolicony profil.

Jeśli nie było to pierwsze pomyślnie uruchomienie scalania, wszystkie procesy podrzędne, w tym wzbogacanie, segmentacja i miary, zostaną automatycznie uruchomione ponownie. Po ponownym uruchomieniu wszystkich procesów podrzędnych profile klienta odzwierciedlają wszelkie wprowadzone zmiany.

> [!TIP]
> Istnieje [sześć typów stanu](system.md#status-types) zadań/procesów. Ponadto większość procesów [zależy od innych procesów podrzędnych](system.md#refresh-policies). Istnieje możliwość wybrania stanu procesu w celu wyświetlenia szczegółowych informacji o postępie w całym zadaniu. Po wybraniu opcji **Zobacz szczegółowe informacje** dla jednego z zadań zadania, można znaleźć więcej informacji: czas przetwarzania, Data ostatniego przetwarzania oraz wszystkie błędy i ostrzeżenia skojarzone z zadaniem.

## <a name="next-step"></a>Następny krok

Skonfiguruj [działania](activities.md), [wzbogacenie](enrichment-microsoft-graph.md) lub [relacje](relationships.md), aby uzyskać dokładniejsze informacje o klientach.

Jeśli zostały już skonfigurowane działania, wzbogacenia lub relacje lub jeśli segmenty są zdefiniowane, zostaną one automatycznie przetworzone w celu korzystania z najnowszych danych klienta.




[!INCLUDE[footer-include](../includes/footer-banner.md)]