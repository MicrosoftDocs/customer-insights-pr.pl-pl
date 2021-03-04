---
title: Działania klienta
description: Zdefiniować działania klienta i wyświetlić je na osiach czasu na klientach.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: dcef8f0547009e1488f1abe91423fa0bf5b061de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267445"
---
# <a name="customer-activities"></a>Działania klienta

Połącz działania klientów z [różnych źródeł danych](data-sources.md) w Dynamics 365 Customer Insights, aby utworzyć oś czasu klienta, która wymienia działania w porządku chronologicznym. Można umieścić oś czasu w aplikacjach dotyczących zaangażowania klientów w Dynamics 365 za pośrednictwem [dodatku Karta klienta](customer-card-add-in.md) lub na pulpicie nawigacyjnym Power BI.

## <a name="define-an-activity"></a>Definiuj działanie

Źródła danych zawierają encje z danymi transakcyjnymi i danymi działań z wielu źródeł danych. Zidentyfikuj te encje i wybierz działania, które mają być wyświetlane na osi czasu klienta. Wybierz encję zawierającą docelowe działanie lub działania.

1. W analizach odbiorców przejdź do **Dane** > **Działania**.

1. Wybierz **Dodaj działanie**.

   > [!NOTE]
   > Encja musi zawierać co najmniej jeden atrybut typu **Data**, który ma zostać uwzględniony na osi czasu klienta, i nie można dodawać encji bez pól **Data**. Formant **Dodaj działanie** jest wyłączany jeśli nie zostanie znaleziona taka encja.

1. W okienku **Dodaj działanie** ustaw wartości dla następujących pól:

   - **Encja**: Wybierz encję zawierającą dane transakcyjne lub działania.
   - **Klucz podstawowy**: Wybierz pole, które jednoznacznie identyfikuje rekord. Nie może ono zawierać żadnych powielonych wartości, pustych wartości ani brakujących wartości.
   - **Sygnatura czasowa**: Wybierz pole reprezentujące godzinę rozpoczęcia działania.
   - **Zdarzenie**: Zaznacz pole, które jest zdarzeniem dla działania.
   - **Adres sieci Web**: Wybierz pole reprezentujące adres URL zawierający dodatkowe informacje o działaniu. Na przykład system transakcyjny, który zawiera źródło tego działania. Ten adres URL może być dowolnym polem ze źródła danych lub może być skonstruowany jako nowe pole przy użyciu przekształcenia Power Query. Te dane URL będą przechowywane w encji Działanie ujednolicone, która może być używana w programie przy użyciu interfejsów API.
   - **Szczegóły**: Opcjonalnie wybierz pole, dodawane, aby uzyskać dodatkowe szczegóły.
   - **Ikona**: Opcjonalnie wybierz ikonę reprezentującą to działanie.
   - **Typ działania**: Zdefiniuj odwołanie typu działania do Common Data Model, który najlepiej opisuje definicję semantyczną działania.

1. W sekcji **Konfigurowanie relacji** skonfiguruj szczegóły, aby połączyć dane działania z odpowiednim klientem.

    - **Pole encji działania**: Wybierz pole w encji działanie, które będzie używane do ustanawiania relacji z inną encją.
    - **Encja klienta**: Wybierz odpowiednią encję źródłową klienta, z którą encja działania będzie w relacji. Relacje można powiązać tylko z encjami źródłowymi klienta używanymi w procesie zjednoczenia danych.
    - **Pole encja klienta**: To pole zawiera klucz podstawowy źródłowej encji klienta wybrany w procesie mapowania. To pole klucz podstawowy w encji źródłowej klienta jest używane do ustanawiania relacji z encją działanie.
    - **Nazwa**: Jeśli relacja między tą encją działania a wybraną encją źródłową klienta już istnieje, nazwa relacji zostanie wyświetlona w trybie tylko do odczytu. Jeśli taka relacja nie istnieje, zostanie utworzona nowa relacja z nazwą podaną w tym miejscu.
   
   > [!div class="mx-imgBorder"]
   > ![Definiowanie relacji encji](media/activities-entities-define.png "Definiowanie relacji encji")

1. Wybierz pozycję **Zapisz**, aby zastosować zmiany.

1. Na stronie **Działania** wybierz **Uruchom**.

> [!TIP]
> Istnieje [sześć typów stanu](system.md#status-types) zadań/procesów. Ponadto większość procesów [zależy od innych procesów podrzędnych](system.md#refresh-policies). Istnieje możliwość wybrania stanu procesu w celu wyświetlenia szczegółowych informacji o postępie w całym zadaniu. Po wybraniu opcji **Zobacz szczegółowe informacje** dla jednego z zadań zadania, można znaleźć więcej informacji: czas przetwarzania, Data ostatniego przetwarzania oraz wszystkie błędy i ostrzeżenia skojarzone z zadaniem.

## <a name="edit-an-activity"></a>Edytuj działanie

1. W analizach odbiorców przejdź do **Dane** > **Działania**.

2. Wybierz encję działania, którą chcesz edytować i wybierz **Edytuj**. Możesz również umieścić kursor nad wierszem encji i wybrać ikonę **Edytuj**.

3. Kliknij ikonę **Edytuj**.

4. W okienku **Edytuj działanie** zaktualizuj wartości i wybierz **Zapisz**.

5. Na stronie **Działania** wybierz **Uruchom**.

## <a name="delete-an-activity"></a>Usuń działanie

1. W analizach odbiorców przejdź do **Dane** > **Działania**.

2. Wybierz encję działania, którą chcesz usunąć i wybierz **Usuń**. Możesz również umieścić kursor nad wierszem encji i wybrać ikonę **Usuń**. Oprócz tego można wybrać wiele encji działań, które mają zostać usunięte jednocześnie.
   > [!div class="mx-imgBorder"]
   > ![Edytuj lub usuń relację między encjami](media/activities-entities-edit-delete.png "Edytuj lub usuń relację między encjami")

3. Wybierz ikonę **Usuń**.

4. Potwierdź usunięcie.


[!INCLUDE[footer-include](../includes/footer-banner.md)]