---
title: Sugerowane segmenty na podstawie miar (wersja zapoznawcza)
description: Pozwól, aby uczenie maszynowe pomogło Ci znaleźć nowe i interesujące segmenty na podstawie atrybutów klientów.
ms.date: 10/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: e3f504827029afa12c65ec6f065a62606aaa823f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170970"
---
# <a name="suggested-segments-based-on-measures-preview"></a>Sugerowane segmenty na podstawie miar (wersja zapoznawcza)

Odkryj interesujące segmenty swoich klientów za pomocą modelu AI. Ta funkcja oparta na uczeniu maszynowym sugeruje segmenty na podstawie miar lub atrybutów klienta. Może pomóc ulepszyć kluczowe wskaźniki wydajności (KPI) lub lepiej zrozumieć wpływ atrybutów w kontekście innych atrybutów.

> [!NOTE]
> Funkcja sugerowanych segmentów wykorzystuje zautomatyzowane środki do oceny danych i tworzenia prognoz na podstawie tych danych. W związku z tym może być stosowany jako metoda profilowania, zgodnie z definicją tego terminu w Ogólnym Rozporządzeniu o Ochronie Danych („RODO”). Korzystanie z tej funkcji do przetwarzania danych może podlegać RODO lub innym prawom lub regulacjom. Użytkownik ma obowiązek zagwarantować, że użytkowanie Dynamics 365 Customer Insights wraz z tą funkcją jest zgodne ze wszystkimi obowiązującymi przepisami prawnymi i wykonawczymi, w tym prawa związane z ochroną prywatności, danymi osobowymi, danymi biometrycznymi, ochroną danych i poufność informacji.

:::image type="content" source="media/suggested-segments.png" alt-text="Strona sugerowanych segmentów, która zawiera szczegółowe sugestie w okienku bocznym.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Sugerowane segmenty w celu poprawy wskaźników KPI

Jeśli używasz miar [utworzonych](measures.md) w celu śledzenia wskaźników KPI, utwórz segmenty, aby wyświetlić wpływ wskaźników KPI na ten wskaźnik. Możesz wykorzystać te informacje do prowadzenia ściśle ukierunkowanej kampanii.

Na przykład można śledzić środek o nazwie *TotalSpendPerCustomer*. Jako firma chciałbyś, aby ta liczba rosła. Wybranie miary jako atrybutu podstawowego pozwala wybrać atrybuty, które chcesz ocenić pod kątem wpływu. Załóżmy na przykład *warstwy członkostwa*, *okres członkostwa* i *zawód*. Customer Insights może następnie zasugerować segment, który powie Ci, kto ma największy wpływ na ten środek. Na przykład *Księgowi*, którzy są członkami *Gold* i pracują w Twojej firmie od *co najmniej pięciu lat*, mają największy wpływ na *TotalSpendPerCustomer*. Dla każdej sugestii otrzymasz szacunkowy rozmiar segmentu. Możesz wykorzystać te informacje do tworzenia kampanii dla docelowych odbiorców.

## <a name="understand-what-influences-a-customer-attribute"></a>Dowiedz się, co wpływa na atrybut klienta

Jako atrybut podstawowy możesz wybrać atrybut klienta zamiast miary. W oparciu o wybór wpływających atrybutów model AI tworzy serię sugestii, które pokazują, jak wybrane atrybuty wpływają na atrybut podstawowy.

Na przykład jako atrybut podstawowy użytkownik wybiera *Członek nagrody (Tak/Nie)*. Dane dotyczące *Kadencja*, *Zawód* i *Liczba biletów pomocy technicznej* są ustawione jako inne atrybuty wpływające na rezultat. Model AI może sugerować segmenty, w których członkami są głównie specjaliści IT z stażem powyżej dwóch lat. Inna sugestia może podkreślić, że księgowi z stażem powyżej roku i mniej niż trzema biletami pomocy są członkami-nagrodami.

## <a name="artificial-intelligence-usage"></a>Wykorzystanie sztucznej inteligencji

Algorytm drzewa decyzyjnego sugeruje interesujące segmenty, korzystając z atrybutu podstawowego i wpływających na nie atrybutów. Sugestie są oparte na regułach lub wzorcach, które zostały wychwycone przez algorytm sztucznej inteligencji. Jako sugestie pokazane są tylko segmenty, które znacznie różnią się od średniej populacji. Porównanie ze średnią populacją odbywa się na podstawie wybranej miary lub podstawowego atrybutu.

### <a name="responsible-ai"></a>Odopowiedzialne AI

Za pomocą sugerowanych segmentów wybierasz atrybuty, aby tworzyć nowe segmenty i przetwarzać wybrane dane. Wybierając atrybuty, w tym wrażliwe atrybuty, takie jak rasa, orientacja seksualna lub płeć, musisz upewnić się, że możesz i powinieneś przetwarzać te dane. Jesteś odpowiedzialny za przestrzeganie wszelkich praw obowiązujących w Twojej organizacji oraz przestrzeganie zasad i polityki prywatności Twojej organizacji.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Różne wyniki dla atrybutów podstawowych z wartościami jakościowymi i liczbowymi

Sugestie dotyczące segmentów są inne, jeśli jako atrybut podstawowy wybierzesz atrybut liczbowy lub kategoryczny. Wartości w atrybucie kategorialnym zawierają co najmniej dwie kategorie lub typy. Atrybut liczbowy zawiera dane ilościowe i ma przypisany sens pomiaru.

Z atrybutem liczbowym, takim jak *roczny dochód* lub *okres członkostwa*, jako atrybutem podstawowym, system sugeruje segmenty, które mają wyższą lub niższą średnią wartość atrybutu liczbowego w porównaniu ze wszystkimi klientami.

Atrybut kategoryczny, taki jak *zadowolenie klienta* jako atrybut podstawowy, daje w wyniku sugerowane segmenty, które mają wyższy lub niższy odsetek klientów należących do określonej kategorii w porównaniu z odsetkiem wszystkich klientów należących do tej samej kategorii. Na przykład jako atrybut podstawowy wybierane jest *zadowolenie klienta* i składa się z trzech kategorii (*Niskie*, *Średnie* i *Wysokie*). W przypadku każdej będą sugerowane segmenty, które mają wyższy lub niższy procent klientów należących do tej kategorii w porównaniu do całkowitej liczby wszystkich klientów w tej samej kategorii. Jeśli 22% klientów ma *duże* zadowolenie, sugerowane są dla tej kategorii tylko segmenty, które mają wyższy lub niższy odsetek klientów z *dużym* zadowoleniem w porównaniu z 22%. W podobny sposób sugerowane są segmenty dla każdej z innych kategorii (*Niskie* i *Średnie*), jeśli są one istotne ze względu na dane statystyczne.

> [!NOTE]
> Obecnie obsługujemy tylko podstawowe atrybuty kategorialne, które mają maksymalnie 10 kategorii. Jeśli chcesz zobaczyć sugestie dotyczące segmentów oparte na podstawowym atrybucie zawierającym więcej niż 10 kategorii, zalecamy zgrupowanie niektórych kategorii w celu zmniejszenia liczby kategorii do 10 lub mniej. To ograniczenie dotyczy tylko atrybutów podstawowych. Obecnie obsługujemy maksymalnie 100 kategorii, aby wpływać na atrybuty kategorialne.

## <a name="generate-suggested-segments"></a>Generuj sugerowane segmenty

1. Przejdź do **Segmenty**, a następnie wybierz kartę **Sugestie (wersja zapoznawcza)**.

1. Wybierz opcję **Znajdź nowe sugestie** i wybierz opcję **Ulepsz miarę/metrykę**. Wybierz **Start**.

   :::image type="content" source="media/suggested-segments-measure.png" alt-text="Wybranie ulepszeń oceny sugerowanych segmentów.":::

1. Wybierz atrybut klienta lub miarę jako podstawowy atrybut i wybierz **Dalej**.

1. Wybierz atrybuty, które mają mieć wpływ, i wybierz opcję **Uruchom**.

   > [!TIP]
   > Wybór wielu wpływających atrybutów zwiększa szanse oceny ich wpływu na podstawowy atrybut. Nie uwzględniaj atrybutów, które nie mają wpływu na atrybut podstawowy. Na przykład, jeśli wszyscy Twoi klienci pochodzą z określonego kraju, nie podawaj atrybutu *kraju*, ponieważ nie będzie to miało żadnego wpływu na wynik.

W zależności od liczby profili klientów i wybranych atrybutów przetworzenie wybranych atrybutów może zająć kilka minut.

## <a name="manage-suggested-segments"></a>Zarządzaj sugerowanymi segmentami

Przejdź do programu **Segmenty** i wybierz kartę **Sugestie (wersja zapoznawcza)**. W sekcji **Sugestie dotyczące segmentu opartego** na atrybutach wybierz sugerowany segment, aby wyświetlić dostępne akcje.

- **Wyświetl** szczegóły sugerowanego segmentu oraz wartości atrybutów lub reguły poznane przez model AI.
- **Zapisz jako segment** sugestię jako segment. Jest on wyświetlany na karcie **Wszystkie segmenty** i może być [odświeżany, edytowany lub usuwany](segments.md).
- **Edytuj atrybuty** i zmodyfikuj skonfigurowane atrybuty, które zastąpią bieżące sugestie.
- Wybierz **Odśwież sugestie**, aby odświeżyć sugestie, zachowując skonfigurowane atrybuty.

## <a name="limitations"></a>Ograniczenia

1. Niezgodność szacowanego rozmiaru segmentu: Wybranie atrybutu podstawowego zawierającego puste wartości może mieć wpływ na szacowany rozmiar segmentu w sugestiach dotyczących segmentu. Podczas zapisywania takiego segmentu rzeczywisty rozmiar segmentu może różnić się od pierwotnego oszacowania.

2. Podstawowe atrybuty typu logicznego nie działają: obecnie jako atrybut podstawowy obsługujemy tylko dane typu ciąg i liczbowego.

3. Sugerowane segmenty nie są wystarczająco wyraźne: pamiętaj, że wybrane atrybuty i rozkład wartości tych atrybutów mają wpływ na wyniki. Możesz zmienić swoje wpływające atrybuty, a nawet swój główny atrybut, aby uzyskać inne wyniki.

[!INCLUDE [footer-include](includes/footer-banner.md)]