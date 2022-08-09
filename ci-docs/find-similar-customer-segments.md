---
title: Znajdź podobnych klientów za pomocą AI (wersja zapoznawcza) (zawiera wideo)
description: Znajdź segmenty podobnych klientów za pomocą sztucznej inteligencji.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 09fe36a4da45d114cbfccf8dad1e7b80b4b7e320
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170740"
---
# <a name="find-similar-customers-with-ai-preview"></a>Znajdź podobnych klientów za pomocą AI (wersja zapoznawcza)

Znajdź podobnych klientów na bazie klientów przy użyciu sztucznej analizy. Aby można było korzystać z tej funkcji, musi być utworzony co najmniej jeden segment. Rozwijanie kryteriów istniejącego segmentu ułatwia znajdowanie klientów podobnych do tego segmentu.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Znajdź podobnych klientów* używa zautomatyzowanych środków do oceny danych i tworzenia prognoz na podstawie tych danych. W związku z tym może być stosowany jako metoda profilowania, zgodnie z definicją tego terminu w Ogólnym Rozporządzeniu o Ochronie Danych („RODO”). Korzystanie z tej funkcji przez klienta do przetwarzania danych może podlegać RODO lub innym prawom lub rozporządzeniom. Użytkownik ma obowiązek zagwarantować, że użytkowanie Dynamics 365 Customer Insights wraz z przewidywaniami jest zgodne ze wszystkimi obowiązującymi przepisami prawnymi i wykonawczymi, w tym prawa związane z ochroną prywatności, danymi osobowymi, danymi biometrycznymi, ochroną danych i poufność informacji.

## <a name="find-similar-customers"></a>Znajdź podobnych klientów

1. Wybierz **Segmenty** i wybierz segment, na którym chcesz bazować nowy segment. To Twój *segment źródłowy*.

1. Wybierz **Znajdź podobnych klientów**.

1. Przejrzyj sugerowaną nazwę nowego segmentu i w razie potrzeby zmodyfikuj ją.

1. Opcjonalnie dodaj [etykiety](work-with-tags-columns.md#manage-tags) do nowego segmentu.

1. Przejrzyj pola definiujące nowy segment. Te pola określają podstawę, z poziomu której system ma próbować znaleźć klientów podobnych do segmentu źródłowego. Domyślnie system wybierze pola zalecane. W razie potrzeby dodaj więcej pól.
  Pola, które mogą znacznie zmniejszyć wydajność modelu, są automatycznie wykluczane:
  
   - Pola o następujących typach danych: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Pola z kardynalnością (liczbą elementów w polu) mniejszą niż 2 lub większą niż 30

1. Wybierz, czy chcesz uwzględnić **Wszystkich klientów** z wyjątkiem segmentu źródłowego, czy tylko klientów z **różnego segmentu** w nowym segmencie.

1. Domyślnie system sugeruje uwzględnienie tylko 20% wielkości odbiorców docelowych w danych wyjściowych. Edytuj ten próg zależnie od potrzeb. Zwiększenie progu zmniejszy dokładność.

1. Uwzględnij klientów w swoim segmencie źródłowym, zaznaczając pole wyboru **Uwzględnij członków segmentu źródłowego oprócz klientów o podobnych cechach**.

1. Wybierz **Uruchom** u dołu strony, aby rozpocząć [zadanie klasyfikacji dwuelementowej](#about-similarity-scores) (metoda uczenia maszynowego), które analizuje zestaw danych.

## <a name="view-the-similar-segment"></a>Wyświetl podobny segment

Po przetworzeniu podobnego segmentu znajdziesz nowy segment na stronie **Segmenty** z typem **Rozszerzenie**.

Wybierz opcję **Widok**, aby zobaczyć rozsyłanie [wyników między podobnymi](#about-similarity-scores) wynikami i wartościami wyniku podobieństwa w obszarze **Podgląd członków segmentu**.

:::image type="content" source="media/expanded-segment.png" alt-text="Segment Podobni klienci.":::

## <a name="manage-a-similar-segment"></a>Zarządzaj podobnym segmentem

[Pracuj z podobnym segmentem i zarządzaj nim](segments.md#manage-existing-segments) tak jak w przypadku innych segmentów. Można na przykład wyeksportować segment lub utworzyć miarę.

Edytuj, odświeżaj, zmieniaj nazwę, pobieraj i usuwaj podobny segment. Edytowanie podobnego segmentu spowoduje przetwarzanie danych. Utworzony wcześniej segment jest aktualizowany odświeżonymi danymi.

## <a name="about-similarity-scores"></a>Informacje na temat wyników podobieństwa

Model uczenia maszynowego klasyfikacji binarnych przypisuje wyniki do klientów w podobnym segmencie. Wynik jest uzależniony od podobieństwa do klientów w segmencie źródłowym.

- Wyniki podobieństwa poniżej 0,55 są klientami, których system klasyfikuje jako *niepodobny* do klientów w segmencie źródłowym
- Wyniki podobieństwa między 0,55 – 0,7 są klasyfikowane jako *nieco podobne*
- Wyniki podobieństwa między 0,7 – 0,85 są klasyfikowane jako *podobne*
- Wyniki podobieństwa między 0,85 – 1 to klienci, których system klasyfikuje jako *bardzo podobni*

Klienci o zbliżonych wynikach niższych niż 0,4 nie są uwzględnianiu w modelu wyjściowym. System nie uważa ich za wystarczająco podobnych do segmentu źródłowego.

[!INCLUDE [footer-include](includes/footer-banner.md)]
