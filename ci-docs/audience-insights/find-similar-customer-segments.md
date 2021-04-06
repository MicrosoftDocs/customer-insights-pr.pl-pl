---
title: Znajdź podobnych klientów z AI
description: Znajdź segmenty podobnych klientów za pomocą sztucznej inteligencji.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f588f45ed11efffbb335003642a4b92810153017
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596788"
---
# <a name="similar-customers-preview"></a>Podobni klienci (wersja zapoznawcza)

Dzięki tej funkcji można znaleźć podobnych klientów w bazie klientów, korzystając z sztucznej inteligencji. Aby można było korzystać z tej funkcji, musi być utworzony co najmniej jeden segment. Rozwijanie kryteriów istniejącego segmentu ułatwia znajdowanie klientów podobnych do tego segmentu.

> [!NOTE]
> *Znajdź podobnych klientów* używa zautomatyzowanego narzędzia do oceniania danych i tworzenia prognoz na podstawie tych danych i w może służyć jako metoda profilowania, ponieważ ten termin jest definiowany przez Ogólne rozporządzenie o ochronie danych ("GDPR"). Korzystanie z tej funkcji przez klienta do przetwarzania danych może podlegać RODO lub innym prawom lub rozporządzeniom. Użytkownik ma obowiązek zagwarantować, że użytkowanie Dynamics 365 Customer Insights wraz z przewidywaniami jest zgodne ze wszystkimi obowiązującymi przepisami prawnymi i wykonawczymi, w tym prawa związane z ochroną prywatności, danymi osobowymi, danymi biometrycznymi, ochroną danych i poufność informacji.

## <a name="finding-similar-customers"></a>Znajdowanie podobnych klientów

1. W statystykach odbiorców przejdź do **Segmenty** i wybierz segment, na którym chcesz oprzeć nowy segment. To Twój *segment źródłowy*.

1. Na pasku akcji wybierz **Znajdź podobnych klientów**.

1. Przejrzyj sugerowaną nazwę nowego segmentu i w razie potrzeby zmodyfikuj ją.

1. Przejrzyj pola definiujące nowy segment. Te pola określają podstawę, z poziomu której system ma próbować znaleźć klientów podobnych do segmentu źródłowego. Domyślnie system wybierze pola zalecane.
  Pola, które mogą znacznie zmniejszyć wydajność modelu, są automatycznie wykluczane:
  
   - Pola o następujących typach danych: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Pola z kardynalnością (liczbą elementów w polu) mniejszą niż 2 lub większą niż 30

1. Wybierz, jeśli chcesz uwzględnić **Wszystkich klientów** lub tylko klientów z **Określonego istniejącego segmentu** w nowym segmencie.

1. Wyłącz klientów w segmencie źródłowym, zaznaczając pole wyboru **Wyklucz wszystkie osoby w segmencie źródłowym**.

1. Domyślnie system sugeruje uwzględnienie tylko 20% wielkości odbiorców docelowych w danych wyjściowych. Edytuj ten próg zależnie od potrzeb. Zwiększenie progu zmniejszy dokładność.

1. Wybierz **Uruchom** u dołu strony, aby rozpocząć zadanie klasyfikacji dwuelementowej (metoda uczenia maszynowego), które analizuje zestaw danych.

## <a name="view-the-similar-segment"></a>Wyświetl podobny segment

Po przetworzeniu podobnego segmentu znajdziesz nowy segment na stronie **Segmenty**.

> [!div class="mx-imgBorder"]
> ![Segment Podobni klienci](media/expanded-segment.png "Segment Podobni klienci")

Wybierz **Widok** na pasku akcji, aby otworzyć Szczegóły segmentu. Ten widok zawiera informacje na temat rozkładu wyniku dla [wyników podobieństwa](#about-similarity-scores). Wartości wyników podobieństwa są również dostępne w **Podglądzie elementów członkowskich segmentu**.

## <a name="use-the-output-of-a-similar-segment"></a>Użyj wyniku podobnego segmentu

Użytkownik może [pracować z danymi wyjściowymi podobnego segmentu](segments.md) tak samo jak z innymi segmentami. Można na przykład wyeksportować segment lub utworzyć miarę.

## <a name="refresh-and-edit-a-similar-segment"></a>Odśwież i edytuj podobny segment

Aby odświeżyć podobny segment, wybierz go na stronie **Segmenty** i wybierz **Odśwież** na pasku akcji.

Edytowanie podobnego segmentu spowoduje przetwarzanie danych. Utworzony wcześniej segment jest aktualizowany odświeżonymi danymi.    
Aby edytować podobny segment, wybierz go na stronie **Segmenty** i wybierz **Edytuj** na pasku akcji. Zastosuj zmiany i wybierz **Uruchom**, aby rozpocząć przetwarzanie.

## <a name="delete-a-similar-segment"></a>Usuń podobny segment

Wybierz segment na stronie **Segmenty** i wybierz **Usuń** na pasku akcji. Następnie potwierdź usunięcie.

## <a name="about-similarity-scores"></a>Informacje na temat wyników podobieństwa

Model uczenia maszynowego klasyfikacji binarnych przypisuje wyniki do klientów w podobnym segmencie. Wynik jest uzależniony od podobieństwa do klientów w segmencie źródłowym.

- Wyniki podobieństwa poniżej 0,55 są klientami, których system klasyfikuje jako *niepodobny* do klientów w segmencie źródłowym
- Wyniki podobieństwa między 0,55 – 0,7 są klasyfikowane jako *nieco podobne*
- Wyniki podobieństwa między 0,7 – 0,85 są klasyfikowane jako *podobne*
- Wyniki podobieństwa między 0,85 – 1 to klienci, których system klasyfikuje jako *bardzo podobni*

Klienci o zbliżonych wynikach niższych niż 0,4 nie są uwzględnianiu w modelu wyjściowym. System nie uważa ich za wystarczająco podobnych do segmentu źródłowego.


[!INCLUDE[footer-include](../includes/footer-banner.md)]