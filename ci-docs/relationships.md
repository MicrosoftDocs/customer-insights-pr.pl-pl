---
title: Relacje między encjami i ścieżkami encji
description: Tworzenie relacji między encjami z wielu źródeł danych i zarządzanie nimi.
ms.date: 09/27/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-entities
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segments
- ci-segment-builder
- ci-measure-builder
- ci-measure-template
- ci-permissions
- customerInsights
ms.openlocfilehash: e622e5fa0b5738e31db1c668d95312adbc4f7d36
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183582"
---
# <a name="relationships-between-entities-and-entity-paths"></a>Relacje między encjami i ścieżkami encji

Relacje łączą encje i definiują graf Twoich danych, gdy encje posiadają wspólny identyfikator, klucz obcy. Do tego klucza obcego można się odwoływać z jednej encji do drugiej. Połączone podmioty umożliwiają definiowanie segmentów i miar w oparciu o wiele źródeł danych.

Istnieją trzy typy relacje: 
- Nieedytowalne relacje systemowe, tworzone przez system w ramach procesu ujednolicania danych
- Nieedytowalne relacje dziedziczone, które są tworzone automatycznie na podstawie pobieranych źródeł danych
- Edytowalne relacje niestandardowe, tworzone i konfigurowane przez użytkowników

## <a name="non-editable-system-relationships"></a>Nieedytowalne powiązania systemowe

Podczas ujednolicania danych relacje systemowe są tworzone automatycznie na podstawie inteligentnego dopasowania. Te relacje pomagają powiązać rekordy profilu klienta z odpowiadającymi im rekordami. Na poniższym diagramie przedstawiono tworzenie trzech baz danych opartych relacje. Encja klienta zostanie dopasowana do innych obiektów w celu uzyskania ujednoliconej encji *Klient*.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagram ze ścieżkami relacji dla encji klient z trzema relacjami 1-n.":::

- **Relacja *CustomerToContact*** jest utworzona między encją *klienta* i encją *kontaktu*. Encja *klienta* otrzymuje pole kluczowe **Contact_contactID** w celu powiązania jej z polem kluczowym encji *kontaktu* **contactID**.
- ***Relacja CustomerToAccount*** jest utworzona między encją *klienta* i encją *konta*. Encja *klienta* otrzymuje pole kluczowe **Account_accountID** w celu powiązania jej z polem kluczowym encji *konta* **accountID**.
- ***Relacja CustomerToWebAccount*** jest utworzona między encją *klienta* i encją *WebAccount*. Encja *klienta* otrzymuje pole kluczowe **WebAccount_webaccountID** w celu powiązania jej z polem kluczowym **webaccountID** encji *WebAccount*.

## <a name="non-editable-inherited-relationships"></a>Odziedziczone relacje nieedytowalne

Podczas procesu pozyskiwania danych system sprawdza źródła danych pod kątem istniejących relacji. Jeśli nie istnieje żadna relacja, system automatycznie je tworzy. Relacje te są również wykorzystywane w dalszych procesach.

## <a name="create-a-custom-relationship"></a>Utwórz niestandardową relację

Relacja składa się z *encji źródłowej* zawierającej klucz obcy i *encję docelową*, na którą wskazuje klucz obcy encji źródłowej. 

1. Przejdź do pozycji **Dane** > **Relacje**.

2. Wybierz **Nowa relacja**.

3. W okienku **Nowa relacja** podaj następujące informacje:

   :::image type="content" source="media/relationship-add.png" alt-text="Nowy panel boczny relacji z pustymi polami wejściowymi.":::

   - **Nazwa relacji**: nazwa odzwierciedlająca cel relacji. Przykład: CustomerToSupportCase.
   - **Opis**: opis relacji.
   - **Encja źródłowa**: Encja używana jako źródło w relacji. Przykład: SupportCase.
   - **Encja docelowa**: Encja używana jako cel w relacji. Przykład: Klient.
   - **Kardynalność źródła**: kardynalność encji źródłowej. Podobieństwo opisuje liczbę możliwych elementów w zestawie. Zawsze odnosi się do kardynalności docelowej. Można wybrać **Jedna** lub **Wiele**. Relacje obsługują tylko wiele-do-jednego i jeden-do-jednego.  
     - Wiele do jednego: wiele rekordów źródłowych może odnosić się do jednego rekordu docelowego. Przykład: wiele spraw pomocy technicznej od jednego klienta.
     - Jeden-do-jednego: pojedynczy rekord źródłowy odnosi się do rekordu jednego docelowego. Przykład: jeden identyfikator lojalnościowy dla pojedynczego klienta.

     > [!NOTE]
     > Relacje wiele-do-wielu można tworzyć przy użyciu dwóch relacji wiele-do-jednego i encji łączącej, która łączy encję źródłową i encję docelową.

   - **Kardynalność docelowa**: kardynalność rekordów encji docelowej.
   - **Pole klucza źródłowego**: pole klucza obcych w encji źródłowej. Przykład: SupportCase może użyć pola **CaseID** jako pola klucza obcych.
   - **Pole klucza docelowego**: pole kluczowe encji docelowej. Przykład: klient może użyć pola klucza **CustomerID**.

4. Wybierz pozycję **ZApisz**, aby utworzyć niestandardową relację.

## <a name="set-up-account-hierarchies"></a>Konfigurowanie hierarchii klientów

Środowiska, w których skonfigurowano używanie kont biznesowych jako podstawowych docelowych odbiorców, mogą konfigurować hierarchie kont dla pokrewnych kont biznesowych. Może to być na przykład firma z oddzielnymi jednostkami biznesowymi.

Organizacje tworzą hierarchie kont, aby lepiej zarządzać kontami i ich relacjami. Customer Insights obsługuje hierarchie kont nadrzędnych i podrzędnych, które już istnieją w pozyskanych danych klientów. Na przykład konta z aplikacji Dynamics 365 Sales. Te hierarchie można skonfigurować na stronie **Relacje**.

1. Przejdź do pozycji **Dane** > **Relacje**.
1. Wybierz kartę **Hierarchia klientów**.
1. Wybierz pozycję **Nowa hierarchia klientów**.
1. W okienku **Hierarchia klientów** podaj nazwę hierarchii. System tworzy nazwę obiektu wyjściowego, ale można go zmienić.
1. Wybierz encję zawierającą hierarchię klientów. Zazwyczaj znajduje się ona w tej samej encji, która zawiera klientów.
1. Wybierz **Identyfikator UID klienta** i **Identyfikator UID elementu nadrzędnego** z wybranej encji.
1. Kliknij **Zapisz**, aby sfinalizować hierarchię kont.

## <a name="manage-existing-relationships"></a>Zarządzaj istniejącymi relacjami

Przejdź do **Relacje**, aby wyświetlić wszystkie utworzone relacje, encję źródłową, encję docelową i podobieństwo.

:::image type="content" source="media/relationships-list.png" alt-text="Lista relacji i opcji na pasku akcji strony Relacje.":::

Użyj opcji **Filtruj według** lub **Relacje wyszukiwania** i znajdź określoną relację. Aby zobaczyć diagram sieciowy istniejących relacji i ich liczności, wybierz [**Wizualizator**](#explore-the-relationship-visualizer).

Wybierz relację, aby wyświetlić dostępne akcje:
- **Edycja**: Zaktualizuj właściwości relacji niestandardowych w okienku edycji i zapisz zmiany.
- **Usuń**: usuń niestandardowe relacje.
- **Widok**: Wyświetlanie utworzonych w systemie i dziedziczonych relacji.

### <a name="explore-the-relationship-visualizer"></a>Poznawanie wizualizacji relacji

Wizualizator relacji pokazuje diagram sieciowy istniejących relacji między połączonymi podmiotami i ich kardynalności. Także wizualizuje ścieżkę relacji.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Zrzut ekranu diagramu sieci wizualizatora relacji z połączeniami między powiązanymi podmiotami.":::

Aby dostosować widok, możesz zmienić położenie pól, przeciągając je na kanwę. Inne opcje obejmują: 
- **Eksportuj jako plik obrazu**: zapisz bieżący widok jako plik obrazu.
- **Zmień na układ poziomy/pionowy**: zmień wyrównanie encji i relacji.
- **Edycja**: Zaktualizuj właściwości relacji niestandardowych w okienku edycji i zapisz zmiany.

## <a name="relationship-paths"></a>Ścieżki relacji

Ścieżka relacji opisuje encje, które są połączone z relacjami między encją źródłową i encją docelową. Jest ona używana podczas tworzenia segmentu lub miary zawierającej inne encje niż encja ujednoliconego profilu i jest dostępnych wiele opcji, aby dotrzeć do ujednoliconej encji profilu. Różne ścieżki relacji mogą dostarczyć różnych wyników.

Na przykład obiekt, *eCommerce_eCommercePurchases* ma następujące relacje do encji ujednoliconego profilu *Klient*:

- eCommerce_eCommercePurchases > klient
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > klient
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > klient

Ścieżka relacji określa encje, których można używać podczas tworzenia reguł dla miar lub segmentów. Wybranie opcji z najdłuższa ścieżką relacji najprawdopodobniej dostarczy mniejszą liczbę wyników, ponieważ dopasowane rekordy muszą być częścią wszystkich encji. W tym przykładzie klient musi mieć zakupione towary za pośrednictwem handlu elektronicznego (eCommerce_eCommercePurchases) w punkcie sprzedaży (POS_posPurchases) i uczestniczyć w naszym programie lojalnościowym (loyaltyScheme_loyCustomers). Wybór pierwszej opcji spowoduje prawdopodobnie dodatkowe rezultaty, ponieważ klienci muszą istnieć tylko w jednej dodatkowej encji.

### <a name="direct-relationship"></a>Relacja bezpośrednia

Relacja jest klasyfikowana jako **relacja bezpośrednia**, gdy encja źródłowa jest powiązana z encją docelową przy użyciu tylko jednej relacji.

Na przykład jeśli encja działania o nazwie *eCommerce_eCommercePurchases* łączy się z encją docelową *eCommerce_eCommerceContacts* tylko za pośrednictwem elementu *ContactId*, jest to relacja bezpośrednia.

:::image type="content" source="media/direct_Relationship.png" alt-text="Encja źródłowa łączy się bezpośrednio z encją docelową.":::

#### <a name="multi-path-relationship"></a>Relacja z wieloma ścieżkami

**Relacja z wieloma ścieżkami** jest specjalnym typem relacji bezpośredniej łączącej encję źródłową z więcej niż jedną encją docelową.

Na przykład jeśli encja działania o nazwie *eCommerce_eCommercePurchases* jest powiązana z dwiema encjami docelowymi *eCommerce_eCommerceContacts* i *loyaltyScheme_loyCustomers*, jest to relacja z wieloma ścieżkami.

:::image type="content" source="media/multi-path_relationship.png" alt-text="Encja źródłowa łączy się bezpośrednio z więcej niż jedną encją docelową za pośrednictwem relacji z wieloma ścieżkami.":::

### <a name="indirect-relationship"></a>Relacja pośrednia

Relacja jest klasyfikowana jako **relacja pośrednia**, gdy encja źródłowa jest powiązana z co najmniej jedną encją dodatkową przed powiązaniem z encją docelową.

#### <a name="multi-hop-relationship"></a>Relacja z wieloma przeskokami

**Relacja z wieloma przeskokami** to *relacja pośrednia*, która umożliwia połączenie encji źródłowej z encją docelową za pośrednictwem co najmniej jednej encji pośredniczącej.

Na przykład jeśli encja działania o nazwie *eCommerce_eCommercePurchasesWest* łączy się z encją pośredniczącą o nazwie *eCommerce_eCommercePurchasesEast*, a następnie łączy się z encją docelową o nazwie *eCommerce_eCommerceContacts*, jest to relacja z wieloma przeskokami.

:::image type="content" source="media/multi-hop_relationship.png" alt-text="Encja źródłowa łączy się bezpośrednio z encją docelową z użyciem encji pośredniczącej.":::

### <a name="multi-hop-multi-path-relationship"></a>Relacja z wieloma przeskokami i wieloma ścieżkami

Relacji z wieloma przeskokami i wieloma ścieżkami można używać razem do tworzenia **relacji z wieloma przeskokami i wieloma ścieżkami**. Ten typ specjalny obejmuje funkcje **relacji z wieloma przeskokami** i **relacji z wieloma ścieżkami**. Umożliwia on nawiązywanie połączenia z więcej niż jedną encją docelową dzięki użyciu encji pośredniczących.

Na przykład jeśli encja działania o nazwie *eCommerce_eCommercePurchasesWest* łączy się z encją pośredniczącą o nazwie *eCommerce_eCommercePurchasesEast*, a następnie łączy się z dwiema encjami docelowymi *eCommerce_eCommerceContacts* i *loyaltyScheme_loyCustomers*, jest to relacja z wieloma przeskokami i wieloma ścieżkami.

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="Encja źródłowa łączy się bezpośrednio z jedną encją docelową, a następnie łączy się z inną encją docelową z użyciem encji pośredniczącej.":::

## <a name="next-step"></a>Następny krok

Relacje systemowe i niestandardowe są używane do [tworzenia segmentów](segments.md) i [miar](measures.md) opartych na wielu źródłach danych, które nie są już w silosach.

[!INCLUDE [footer-include](includes/footer-banner.md)]