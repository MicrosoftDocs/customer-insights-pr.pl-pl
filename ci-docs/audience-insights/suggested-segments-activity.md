---
title: Sugerowane segmenty na podstawie aktywności.
description: Pozwól, aby uczenie maszynowe pomogło Ci znaleźć nowe i interesujące segmenty na podstawie aktywności klientów.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 46e8970f7fd116cb1654c94751923ce2a213ff87dd7bc7ee731a62bbd0093513
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7028419"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a>Sugerowane segmenty na podstawie danych aktywności (wersja zapoznawcza)

Odkryj interesujące segmenty klientów w oparciu o dane dotyczące aktywności klientów, które są wprowadzane do Customer Insights. Przykładami danych dotyczących aktywności są transakcje, czas trwania rozmów z działem pomocy technicznej, zakupy lub zwroty. Aby zasugerować segmenty, dane dotyczące aktywności są analizowane pod kątem powtarzalności, częstotliwości i wartości pieniężnej (lub czasu trwania). Można też wygenerować [sugerowane segmenty, aby udoskonalić miarę lub lepiej zrozumieć, co ma jaki wpływ na atrybut](suggested-segments.md).

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Zakładka Sugerowane segmenty zawierająca propozycje segmentów dla segmentów opartych na aktywności i segmentów opartych na atrybutach.":::

## <a name="categorize-customers-by-activity"></a>Dzielenie klientów na kategorie według działań

Dzięki dostępnym w aplikacji Customer Insights [danym z aktywności](activities.md) można tworzyć sugestie reprezentujące grupy klientów:

- najaktywniejsi klienci 
- klienci, którzy dokonali największej liczby zakupów 
- klienci, którzy wygenerowali największy przychód 
- klienci, którzy nie byli ostatnio aktywni 
- klienci, którzy często wchodzą w interakcje z Twoją firmą  

Jeśli prowadzisz biznes detaliczny, możesz dowiedzieć się, którzy klienci generują największe przychody i nagrodzić ich kuponem. Możesz też zidentyfikować okazjonalnych klientów i zaoferować im udział w programie nagród, dzięki któremu będą częściej odwiedzać Twoją firmę.
Jeśli prowadzisz firmę związaną z opieką zdrowotną i świadczysz publiczną opiekę zdrowotną, a Twoim celem jest zminimalizowanie wydatków dla indywidualnych pacjentów. Sposobem na to może być zmniejszenie liczby powtarzających się wizyt poprzez zapewnienie najlepszej możliwej opieki podczas jak najmniejszej liczby wizyt. W tym przypadku Twoim celem jest utrzymanie częstotliwości wizyt na niskim poziomie i zminimalizowanie powtarzających się kosztów dla pacjentów. Lub można zidentyfikować segmenty pacjentów, którzy mają częste wizyty i wysokie koszty powtarzające się i analizować te przypadki, aby poprawić leczenie poszczególnych osób. 

## <a name="required-data"></a>Wymagane dane

Propozycje są generowane na podstawie wybranych danych wejściowych. 

- Profile klientów: Wszyscy klienci lub członkowie określonego segmentu. 

- Okres czasu: Ostatni miesiąc, ostatni rok lub dowolny niestandardowy przedział czasowy.

- Typ aktywności: zakupy, transakcje detaliczne, transakcje online, sprawy związane z obsługą klienta, subskrypcje i tak dalej.  

- Encja w Customer Insights, który zawiera dane dotyczące aktywności: Encja UnifiedActivity lub encja dla konkretnej aktywności. 

- Wymiary do uwzględnienia: Niedawność, częstotliwość lub wymiar pieniężny, w zależności od wymagań biznesowych.

## <a name="generate-suggested-segments"></a>Generuj sugerowane segmenty

1. Przejdź do **Segmenty**.

1. Wybierz kartę **Sugestie (wersja zapoznawcza)**.

1. Wybierz opcję **Znajdź nowe sugestie** i wybierz opcję **Zobacz lub przewiduj zachowanie klienta**. Wybierz opcję **Start**, aby uruchomić tę opcję.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Pierwszy krok kreatora konfiguracji sugerowanego segmentu na podstawie aktywności.":::

1. Podaj wymagane dane wejściowe i wybierz przycisk **Dalej**.

   - Wybierz klientów: Uwzględnij wszystkich klientów lub określony segment.
   - Wybierz aktywność: Wybierz typ działania i jednostki opisujące działanie.
   - Preferencje: Ustaw okres czasu, który ma być brany pod uwagę, czynniki dla sugestii i mapuj atrybuty.

1. Przejrzyj dane wejściowe i wybierz opcję **Uruchom** w celu uruchomienia modelu i wygenerowania sugestii.

1. W zależności od liczby profili klientów i wybranych działań, może to zająć kilka minut. 

Po wygenerowaniu propozycji, możesz je filtrować według wymiaru lub wartości, która najbardziej Cię interesuje. 

## <a name="view-details-of-a-suggested-segment"></a>Wyświetl szczegóły sugerowanego segmentu

Po wygenerowaniu sugestii można je znaleźć w sekcji **Sugestie** > **Sugestie (wersja zapoznawcza)** w sekcji **Sugestie oparte na aktywności**.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Rozszerzony panel boczny pokazujący szczegółowe dane sugerowanego segmentu.":::

Wybierz opcję **Zobacz sugestię** dla sugerowanego segmentu, aby wyświetlić szczegółowe informacje o tym segmencie. W panelu bocznym znajdują się szczegóły, takie jak zakres każdego wymiaru w porównaniu z grupą docelową. Podkreślona jest również liczba potencjalnych członków w danym segmencie i odpowiadający im procent wszystkich klientów. Jeśli chcesz zachować sugestię jako segment, wybierz opcję **Utwórz segment**.    

## <a name="save-a-suggestion-as-a-segment"></a>Zapisz sugestię jako segment

1. Przejdź do **Segmenty** > **Sugestie (wersja zapoznawcza)**.

1. Wybierz segment, który chcesz zapisać. 

1. W okienku bocznym wybierz pozycję **Utwórz segment**. 

1. Po zapisaniu segmentu będzie on dostępny na liście segmentów na karcie **Wszystkie segmenty**. Można teraz go [odświeżyć lub usunąć, tak jak każdy inny segment](segments.md). Nie można edytować szczegółów segmentu. Można jednak zmienić kryteria wejściowe sugestii i generować różne sugestie.

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Odświeżanie i edytowanie zestawu sugestii

1. Przejdź do sekcji **Sugestie** > **Sugestie (wersja zapoznawcza)** i poszukać segmentu w sekcji **Sugestie oparte na aktywności**.

1. Wybierz opcję **Odśwież sugestie**, aby odświeżyć sugestie, zachowując skonfigurowane atrybuty. Można również wybrać opcję **Edytuj sugestie** w celu zmodyfikowania skonfigurowanych atrybutów. System ponownie uruchomi proces, wygeneruje sugestie dotyczące segmentu na podstawie najnowszych danych i zastąpi bieżące sugestie.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
