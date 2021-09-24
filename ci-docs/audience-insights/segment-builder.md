---
title: Tworzenie segmentów przy użyciu konstruktora segmentów
description: W celu pogrupowania klientów na podstawie różnych atrybutów można utworzyć ich segmenty.
ms.date: 09/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7f7bd0e7e581305836287bd503ef273a2d556bff
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494515"
---
# <a name="create-segments"></a>Utwórz segmenty

Zdefiniować złożone filtry dla ujednoliconej encji klienta i jej encji pokrewnych. Każdy segment, po przetworzeniu, tworzy zestaw rekordów klientów, który można eksportować i na którym można podejmować akcje. Segmenty są zarządzane na stronie **Segmenty**. Możesz [tworzyć nowe segmenty](#create-a-new-segment), korzystając z [konstruktora segmentów](#segment-builder), lub [tworzyć szybkie segmenty](#quick-segments) z innych obszarów aplikacji.

## <a name="segment-builder"></a>Konstruktor segmentów

Na poniższym obrazie przedstawiono różne aspekty konstruktora segmentów. Wskazuje segment, którego wynikiem jest grupa klientów. Klienci zamówili towary w określonym horyzoncie czasowym i zdobyli pewną liczbę punktów nagród lub wydali określoną kwotę pieniężną. 

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elementy konstruktora segmentów." lightbox="media/segment-builder-overview.png":::

1 — organizuj segmenty za pomocą reguł i reguł podrzędnych. Każda reguła lub reguła podrzędna składa się z warunków. Łączenie warunków z operatorami logicznymi

2 — wybierz [ścieżkę relacji](relationships.md) między jednostkami, która dotyczy reguły. Ścieżka relacji określa, które atrybuty mogą być używane w warunku.

3 — zarządzaj regułami i regułami podrzędnymi. Zmień pozycję reguły lub ją usuń.

4 — dodaj warunki i skonstruuj odpowiedni poziom zagnieżdżania przy użyciu reguł podrzędnych.

5 — zastosuj operacje zestawów do połączonych reguł.

6 — użyj okienka atrybutów do dodania dostępnych atrybutów encji lub utworzenia warunków na podstawie atrybutów. W okienku jest wyświetlona lista encji i atrybutów na podstawie wybranej ścieżki reguły, która jest dostępna dla wybranej reguły.

7 — dodaj warunki na podstawie atrybutów do istniejących reguł i reguł podrzędnych lub dodaj je do nowej reguły.

8 — cofnij i ponownie zastosuj zmiany podczas konstruowania segmentu.

W tym przykładzie przedstawiono możliwości w zakresie segmentacji. Definiujemy segment dla klientów, którzy kupili towary online za co najmniej 500 USD *i* są zainteresowani opracowaniem oprogramowania.

## <a name="create-a-new-segment"></a>Utwórz nowy segment

Istnieje wiele sposobów utworzenia nowego segmentu. W tej sekcji opisano sposób tworzenia własnego segmentu od podstaw. Można również utworzyć *krótki segment* na podstawie istniejących obiektów lub skorzystać z uczenia maszynowego, aby uzyskać *sugerowane segmenty*. Więcej informacji: [Omówienie segmentów](segments.md).

Podczas tworzenia segmentu można zapisać jego wersje robocze. Zostanie on zapisany jako nieaktywny segment i nie można go aktywować w ramach prawidłowej konfiguracji.

1. Przejdź do strony **Segmenty**.

1. Wybierz opcję **Nowy** > **Utwórz własne**.

1. Na stronie konstruktora segmentów definiuje się pierwszą regułę. Reguła składa się z jednego lub kilku warunków i definiuje zestaw klientów.

1. W sekcji **Reguła 1** wybierz atrybut obiektu, według którego klienci mają być filtrowani. Istnieją dwa sposoby wybierania atrybutów: 
   - Przejrzyj listę dostępnych obiektów i atrybutów w okienku **Dodaj do reguły** i wybierz ikonę **+** obok atrybutu, który chcesz dodać. Określ, czy atrybut ma zostać dodany do istniejącej reguły, czy podczas tworzenia nowej reguły.
   - Aby wyświetlić pasujące sugestie, wpisz nazwę atrybutu w sekcji reguły.

1. Wybierz operatory, aby określić odpowiadające wartości warunku. Atrybut może mieć jeden z czterech typów danych: wartość numeryczna, ciąg, data lub wartość logiczna. W zależności od typu danych atrybutu do określania warunku są dostępne różne operatory. 

1. Wybierz opcję **Dodaj warunek**, aby dodać więcej warunków do reguły. Aby utworzyć regułę na podstawie bieżącej reguły, wybierz opcję **Dodaj regułę podrzędną**.

1. Jeśli reguła używa encji innych niż encja *Klient*, należy ustawić ścieżkę relacji. Ścieżka relacji musi poinformować system, które relacja mają uzyskać dostęp do encji ujednoliconego klienta. Wybierz opcję **Ustaw ścieżkę relacji**, aby zamapować wybraną encję na ujednoliconą encję klienta. Jeśli jest dostępna tylko jedna ścieżka relacji, system wybierze ją automatycznie. Różne ścieżki relacji mogą dostarczyć różnych wyników. Każda reguła może mieć własną ścieżkę relacji.

   :::image type="content" source="media/relationship-path.png" alt-text="Potencjalna ścieżka relacji podczas tworzenia reguły opartej na encji zamapowanej na encję ujednoliconego klienta.":::

   Na przykład encja *eCommerce_eCommercePurchases* na zrzucie ekranu ma cztery opcje mapowania do encji *Klient*: 
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Klient
   - eCommerce_eCommercePurchases > klient
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > klient
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Klient Przy wyborze ostatniej opcji w warunkach reguły można uwzględnić atrybuty wszystkich wymienionych encji. Prawdopodobnie będzie mniej wyników, ponieważ pasujące rekordy klientów muszą być częścią wszystkich encji. W tym przykładzie klienci muszą mieć zakupione towary za pośrednictwem handlu elektronicznego (*eCommerce_eCommercePurchases*) w punkcie sprzedaży (*POS_posPurchases*) i uczestniczyć w naszym programie lojalnościowym (*loyaltyScheme_loyCustomers*). Przy wyborze drugiej opcji możemy wybrać tylko atrybuty z encji *eCommerce_eCommercePurchases* i *Klient*. Najprawdopodobniej powoduje to więcej profilów klientów.

1. Jeśli w regule istnieje kilka warunków, można wybrać operator logiczny, który je łączy.

   - Operator **I**: aby uwzględnić rekord w segmencie, muszą zostać spełnione wszystkie warunki. Ta opcja jest najbardziej przydatna podczas definiowania warunków między różnymi encjami.

   - Operator **LUB**: aby uwzględnić rekord w segmencie, musi zostać spełniony jeden z warunków. Ta opcja jest najbardziej przydatna podczas definiowania wielu warunków dla tej samej encji.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Reguła z dwoma warunkami I.":::

   Podczas używania operatora LUB wszystkie warunki muszą być oparte na encji w ścieżki relacji.

   1. Można utworzyć wiele reguł w celu utworzenia różnych zestawów rekordów klientów. Można łączyć grupy w celu uwzględnienia klientów wymaganych dla danego przypadku biznesowego. Aby utworzyć nową regułę, wybierz **Dodaj regułę**. W szczególności jeśli nie można uwzględnić encji w regule z powodu określonej ścieżki relacji, należy utworzyć nową regułę, aby wybrać wchodzące w jej skład atrybuty.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Dodaj nową regułę do segmentu i wybierz operator zestawu.":::

   1. Wybierz jeden z operatorów: **Związek**, **Część wspólna** lub **Z wyjątkiem**.

   - **Związek** łączy dwie grupy.

   - **Część wspólna** pokrywa się z dwiema grupami. Tylko dane, które *są wspólne* dla obu grup, są zachowywane w ujednoliconej grupie.

   - **Z wyjątkiem** łączy dwie grupy. Tylko dane w grupie A, które *nie są wspólne* dla grupy B, są zachowywane w ujednoliconej grupie.

1. Domyślnie segmenty generują encję wyjściową zawierającą wszystkie atrybuty profilów klientów zgodne ze zdefiniowanymi filtrami. Jeśli segment jest oparty na encjach innych niż encja *Klient*, do encji wyjściowej można dodać więcej atrybutów z tych encji. Wybierz pozycję **Atrybuty projektu**, aby wybrać atrybuty, które będą dołączane do encji wyjściowej.  

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Przykład projektowanych atrybutów wybranych w okienku bocznym, które mają zostać dodane do encji wyjściowej.":::
  
   Przykład: segment jest oparty na encji zawierającej dane dotyczące zakupu, która jest powiązana z encją *Klient*. Segment wyszukuje wszystkich klientów z Hiszpanii, którzy nabywali towary w bieżącym roku. Można dodać atrybuty, takie jak cena towarów lub data zakupu, do wszystkich pasujących rekordów klientów w encji wyjściowej. Te informacje mogą być przydatne do przeanalizowania skojarzeń z łącznymi wydatkami.

   > [!NOTE]
   > - Atrybuty projektu działają tylko w przypadku encji, które mają relację jeden do wielu z encją klienta. Na przykład jeden klient może mieć wiele subskrypcji.
   > - Atrybuty można projektować tylko z encji, która jest używana w każdej regule tworzonego zapytania segmentu.
   > - Atrybuty rzutowane są uwzględniane podczas używania operatorów zestawów.

1. Przed zapisaniem i uruchomieniem segmentu wybierz opcję **Edytuj szczegóły** obok nazwy segmentu. Podaj nazwę swojego segmentu i zaktualizuj sugerowaną **nazwę encji wyjściowej** dla tego segmentu. Można również dodać opis dla segmentu.

1. Wybierz opcję **Uruchom**, aby zapisać i przetworzyć segment, jeśli zostaną sprawdzone wszystkie wymagania. W przeciwnym razie będzie on zapisywany jako nieaktywna wersja robocza segmentu.

1. Wybierz **Wróć do segmentów**, aby wrócić do strony **Segmenty**.

> [!TIP]
> - Konstruktor segmentów nie zasugeruje prawidłowych wartości z encji podczas ustawiania operatorów na określonych warunkach. Można przejść do obszaru **Dane** > **Encje** i pobrać dane encji, aby sprawdzić, które wartości są dostępne.
> - Warunki oparte na datach umożliwiają przełączanie się między stałymi datami a zmiennoprzecinkowym zakresem dat.
> - Jeśli dla swojego segmentu masz wiele reguł, możesz znaleźć niebieski pasek wokół edytowanej reguły.
> - Reguły i warunki można przenieść do innych miejsc definicji segmentu. Wybierz pozycję [...] obok reguły lub warunku i wybierz sposób i miejsce jego przeniesienia.
> - Kontrolki **Cofnij** i **Ponów** na pasku poleceń umożliwiają wycofanie zmian.

## <a name="quick-segments"></a>Szybkie segmenty

Szybkie segmenty umożliwiają tworzenie prostych segmentów z jednym operatorem w celu szybszego wglądu w dane.

1. Na stronie **Segmentów** wybierz opcję **Nowy** > **Utwórz za pomocą**.

   - Wybierz opcję **profile**, aby zbudować segment utworzony na podstawie *ujednoliconej encji klienta*.
   - Wybierz opcję **Miary**, aby utworzyć segment na podstawie miar utworzonych wcześniej.
   - Wybierz opcję **Analizy**, aby utworzyć segment wokół jednej z encji wyjściowych wygenerowanych przy użyciu funkcji **Przewidywania** lub **Modele niestandardowe**.

2. W oknie dialogowym **Nowy szybki segment** wybierz atrybut z listy rozwijanej **Pole**.

3. System ten zapewnia więcej szczegółowych informacji, które pomogą utworzyć lepsze segmenty klientów.
   - W przypadku pól kategorii pokażemy 10 największych klientów. Wybierz **Wartość** i wybierz **Przejrzyj**.

   - W przypadku atrybutu numerycznego system pokaże, jaka wartość atrybutu mieści się w percentylu każdego klienta Wybierz **Operator** i **Wartość**, a następnie wybierz pozycję **Przeglądaj**.

4. System zaproponuje opcje **Szacowany rozmiar segmentu**. Użytkownik może wybrać, czy ma zostać wyświetlona definicja segmentu, czy też najpierw ją ponownie przejrzeć w celu uzyskania innego rozmiaru segmentu.

    > [!div class="mx-imgBorder"]
    > ![Nazwa i oszacowanie szybkiego segmentu.](media/quick-segment-name.png "Nazwa i oszacowanie szybkiego segmentu")

5. Podaj **Nazwę** segmentu. Opcjonalnie, podaj **Nazwę wyświetlaną**.

6. Wybierz opcję **Zapisz**, aby utworzyć segment.

7. Po zakończeniu przetwarzania segmentu można go wyświetlić tak samo, jak każdy inny segment utworzony przez użytkownika.

## <a name="next-steps"></a>Następne kroki

[Wyeksportuj segment](export-destinations.md) i zapoznaj się z [integracją karty klienta](customer-card-add-in.md), aby używać segmentów w innych aplikacjach.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
