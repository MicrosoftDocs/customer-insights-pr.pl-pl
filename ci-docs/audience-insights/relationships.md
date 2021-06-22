---
title: Relacje między encjami i ścieżkami encji
description: Tworzenie relacji między encjami z wielu źródeł danych i zarządzanie nimi.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171177"
---
# <a name="relationships-between-entities"></a>Relacje między encjami

Relacje łączą encje i definiują graf Twoich danych, gdy encje posiadają wspólny identyfikator, klucz obcy. Do tego klucza obcego można się odwoływać z jednej encji do drugiej. Połączone podmioty umożliwiają definiowanie segmentów i miar w oparciu o wiele źródeł danych.

Istnieją trzy typy relacje: 
- Nieedytowalne relacje systemowe, tworzone przez system w ramach procesu ujednolicania danych
- Nieedytowalne relacje dziedziczone, które są tworzone automatycznie na podstawie pobieranych źródeł danych 
- Edytowalne relacje niestandardowe, tworzone i konfigurowane przez użytkowników

## <a name="non-editable-system-relationships"></a>Nieedytowalne powiązania systemowe

Podczas ujednolicania danych relacje systemowe są tworzone automatycznie na podstawie inteligentnego dopasowania. Te relacje pomagają powiązać rekordy profilu klienta z odpowiadającymi im rekordami. Na poniższym diagramie przedstawiono tworzenie trzech baz danych opartych relacje. Encja klienta zostanie dopasowana do innych obiektów w celu uzyskania ujednoliconej encji *Klient*.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagram ze ścieżkami relacji dla encji klient z trzema relacjami 1-n.":::

- **Relacja *CustomerToContact*** jest utworzona między encją *klienta* i encją *kontaktu*. Encja *klienta* otrzymuje pole kluczowe **Contact_contactID** w celu powiązania jej z polem kluczowym encji *kontaktu* **contactID**.
- **Relacja *CustomerToAccount*** jest utworzona między encją *klienta* i encją *konta*. Encja *klienta* otrzymuje pole kluczowe **Account_accountID** w celu powiązania jej z polem kluczowym encji *konta* **accountID**.
- **Relacja *CustomerToWebAccount*** jest utworzona między encją *klienta* i encją *WebAccount*. Encja *klienta* otrzymuje pole kluczowe **WebAccount_webaccountID** w celu powiązania jej z polem kluczowym **webaccountID** encji *WebAccount*.

## <a name="non-editable-inherited-relationships"></a>Odziedziczone relacje nieedytowalne

Podczas procesu pozyskiwania danych system sprawdza źródła danych pod kątem istniejących relacji. Jeśli nie istnieje żadna relacja, system automatycznie je tworzy. Relacje te są również wykorzystywane w dalszych procesach.

## <a name="create-a-custom-relationship"></a>Utwórz niestandardową relację

Relacja składa się z *encji źródłowej* zawierającej klucz obcy i *encję docelową*, na którą wskazuje klucz obcy encji źródłowej. 

1. W analizach odbiorców przejdź do **Dane** > **Relacje**.

2. Wybierz **Nowa relacja**.

3. W okienku **Nowa relacja** podaj następujące informacje:

   :::image type="content" source="media/relationship-add.png" alt-text="Nowy panel boczny relacji z pustymi polami wejściowymi.":::

   - **Nazwa relacji**: nazwa odzwierciedlająca cel relacji. Przykład: CustomerToSupportCase.
   - **Opis**: opis relacji.
   - **Encja źródłowa**: Encja używana jako źródło w relacji. Przykład: SupportCase.
   - **Encja docelowa**: Encja używana jako cel w relacji. Przykład: Klient.
   - **Kardynalność źródła**: Określ kardynalność encji źródłowej. Podobieństwo opisuje liczbę możliwych elementów w zestawie. Zawsze odnosi się do kardynalności docelowej. Można wybrać **Jedna** lub **Wiele**. Relacje obsługują tylko wiele-do-jednego i jeden-do-jednego.  
     - Wiele do jednego: wiele rekordów źródłowych może odnosić się do jednego rekordu docelowego. Przykład: wiele spraw pomocy technicznej od jednego klienta.
     - Jeden-do-jednego: pojedynczy rekord źródłowy odnosi się do rekordu jednego docelowego. Przykład: jeden identyfikator lojalnościowy dla pojedynczego klienta.

     > [!NOTE]
     > Relacje wiele-do-wielu można tworzyć przy użyciu dwóch relacji wiele-do-jednego i encji łączącej, która łączy encję źródłową i encję docelową.

   - **Kardynalność docelowa**: wybierz kardynalność rekordów encji docelowej. 
   - **Pole klucza źródłowego**: pole klucza obcych w encji źródłowej. Przykład: SupportCase może użyć pola CaseID jako pola klucza obcych.
   - **Pole klucza docelowego**: Pole kluczowe encji docelowej. Przykład klient może użyć pola klucza **CustomerID**.

4. Wybierz pozycję **ZApisz**, aby utworzyć niestandardową relację.

## <a name="view-relationships"></a>Widok relacji

Strona Relacje zawiera listę wszystkich utworzonych relacji. Każdy wiersz reprezentuje relację, która zawiera również szczegółowe informacje o encji źródłowej, encji docelowej i kardynalności. 

:::image type="content" source="media/relationships-list.png" alt-text="Lista relacji i opcji na pasku akcji strony Relacje.":::

Ta strona oferuje zestaw opcji dla istniejących i nowych relacji: 
- **Nowa rezerwacji:** [Utwórz niestandardową relację](#create-a-custom-relationship).
- **Wizualizacja**: [poznaj wizualizację relacji](#explore-the-relationship-visualizer) w celu odszukania diagramu sieciowego istniejącego relacje i ich podobieństwa.
- **Filtruj według**: wybierz typ relacje, które mają być wyświetlane na liście.
- **Wyszukiwanie relacje**: Użyj wyszukiwania tekstowego według właściwości relacji.

### <a name="explore-the-relationship-visualizer"></a>Poznawanie wizualizacji relacji

Wizualizator relacji pokazuje diagram sieciowy istniejących relacji między połączonymi podmiotami i ich kardynalności.

Aby dostosować widok, możesz zmienić położenie pól, przeciągając je na kanwę.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Zrzut ekranu diagramu sieci wizualizatora relacji z połączeniami między powiązanymi podmiotami.":::

Dostępne opcje: 
- **Eksportuj jako plik obrazu**: zapisz bieżący widok jako plik obrazu.
- **Zmień na układ poziomy/pionowy**: zmień wyrównanie encji i relacji.
- **Edycja**: Zaktualizuj właściwości relacji niestandardowych w okienku edycji i zapisz zmiany.

## <a name="manage-existing-relationships"></a>Zarządzaj istniejącymi relacjami 

Na stronie Relacje każda relacja jest reprezentowana przez wiersz. 

Wybierz relację i wybierz jedną z następujących opcji: 
 
- **Edycja**: Zaktualizuj właściwości relacji niestandardowych w okienku edycji i zapisz zmiany.
- **Usuń**: usuń niestandardowe relacje.
- **Widok**: Wyświetlanie utworzonych w systemie i dziedziczonych relacji. 

## <a name="next-step"></a>Następny krok

System i relacje niestandardowe służą do [tworzenia segmentów](segments.md) na podstawie wielu źródeł danych, które nie są już izolowane.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
