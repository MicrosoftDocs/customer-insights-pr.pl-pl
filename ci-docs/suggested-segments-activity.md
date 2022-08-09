---
title: Sugerowane segmenty na podstawie działania (wersja zapoznawcza)
description: Pozwól, aby uczenie maszynowe pomogło Ci znaleźć nowe i interesujące segmenty na podstawie aktywności klientów.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: df4f5f4b5c9a3ad66d57a6b349e18a0d714aff62
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170602"
---
# <a name="suggested-segments-based-on-activity-preview"></a>Sugerowane segmenty na podstawie działania (wersja zapoznawcza)

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
Jeśli zapewniasz publiczną opiekę zdrowotną, a Twoim celem jest zminimalizowanie wydatków dla poszczególnych pacjentów, możesz spróbować ograniczyć powtarzające się wizyty, zapewniając najlepszą możliwą opiekę w jak najmniejszej liczbie wizyt. W tym przypadku Twoim celem jest utrzymanie częstotliwości wizyt na niskim poziomie i zminimalizowanie powtarzających się kosztów dla pacjentów. Lub można zidentyfikować segmenty pacjentów, którzy mają częste wizyty i wysokie koszty powtarzające się i analizować te przypadki, aby poprawić leczenie poszczególnych osób.

## <a name="required-data"></a>Wymagane dane

Propozycje są generowane na podstawie wybranych danych wejściowych.

- Profile klientów: Wszyscy klienci lub członkowie określonego segmentu.

- Okres czasu: Ostatni miesiąc, ostatni rok lub dowolny niestandardowy przedział czasowy.

- Typ aktywności: zakupy, transakcje detaliczne, transakcje online, sprawy związane z obsługą klienta, subskrypcje i tak dalej.  

- Encja w Customer Insights, który zawiera dane dotyczące aktywności: Encja UnifiedActivity lub encja dla konkretnej aktywności.

- Wymiary do uwzględnienia: Niedawność, częstotliwość lub wymiar pieniężny, w zależności od wymagań biznesowych.

## <a name="generate-suggested-segments"></a>Generuj sugerowane segmenty

1. Przejdź do **Segmenty**, a następnie wybierz kartę **Sugestie (wersja zapoznawcza)**.

1. Wybierz opcję **Znajdź nowe sugestie** i wybierz opcję **Zobacz lub przewiduj zachowanie klienta**. Wybierz **Start**.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Pierwszy krok kreatora konfiguracji sugerowanego segmentu na podstawie aktywności.":::

1. Podaj wymagane dane wejściowe i wybierz **Dalej**.

   - Wybierz klientów: Uwzględnij wszystkich klientów lub określony segment.
   - Wybierz aktywność: Wybierz typ działania i jednostki opisujące działanie.
   - Preferencje: Ustaw okres czasu, który ma być brany pod uwagę, czynniki dla sugestii i mapuj atrybuty.

1. Przejrzyj dane wejściowe i wybierz opcję **Uruchom** w celu uruchomienia modelu i wygenerowania sugestii.

W zależności od liczby profili klientów i wybranych działań, może to zająć kilka minut.

Po wygenerowaniu propozycji, możesz je filtrować według wymiaru lub wartości, która najbardziej Cię interesuje.

## <a name="manage-suggested-segments"></a>Zarządzaj sugerowanymi segmentami

Przejdź do programu **Segmenty** i wybierz kartę **Sugestie (wersja zapoznawcza)**. W sekcji **Sugestie oparte na działaniu** wybierz sugerowany segment, aby wyświetlić dostępne akcje.

- **Zobacz sugestię**, aby wyświetlić szczegóły tego segmentu, takie jak zasięg każdego wymiaru w porównaniu z grupą docelową. Podkreślona jest również liczba potencjalnych członków w danym segmencie i odpowiadający im procent wszystkich klientów.
- **Utwórz segment**, aby zapisać sugerowane jako segment. Jest on wyświetlany na karcie **Wszystkie segmenty** i może być [odświeżany lub usuwany](segments.md). Nie można edytować szczegółów segmentu. Można jednak zmienić kryteria wejściowe sugestii i generować różne sugestie.
- **Edytuj sugestie** i zmodyfikuj skonfigurowane atrybuty, które zastąpią bieżące sugestie.
- Wybierz **Odśwież sugestie**, aby odświeżyć sugestie, zachowując skonfigurowane atrybuty.

[!INCLUDE [footer-include](includes/footer-banner.md)]
