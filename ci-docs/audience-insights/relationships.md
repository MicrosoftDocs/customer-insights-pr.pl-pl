---
title: Relacje między encjami i ścieżkami encji
description: Tworzenie relacji między encjami z wielu źródeł danych i zarządzanie nimi.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 295c372bb452e7c40aa950506dc494d4a2de1108
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406594"
---
# <a name="relationships-between-entities"></a>Relacje między encjami

Relacje ułatwiają łączenie encji i generowanie wykresu danych w przypadku, gdy encje mają wspólny identyfikator (klucz obcy), który może być przywoływany między encjami. Połączone encje umożliwiają zdefiniowanie segmentów i miar na podstawie wielu źródeł danych.

Istnieją dwa typy relacji: Relacje systemowe, których nie można edytować i które są tworzone automatycznie, oraz niestandardowe relacje utworzone i skonfigurowane przez użytkowników.

Podczas procesów dopasowywania i scalania relacje systemu są tworzone w tle w zależności od inteligentnego dopasowania. Te relacje ułatwiają powiązanie rekordów Profilu klienta z innymi rekordami odpowiednich encji. Na poniższym diagramie pokazano, jak utworzyć trzy relacje systemowe w przypadku dopasowania obiektu klienta do dodatkowych encji w celu utworzenia ostatecznej encji Profilu klienta.

> [!div class="mx-imgBorder"]
> ![Tworzenie relacji](media/relationships-entities-merge.png "Tworzenie relacji")

- **Relacja *CustomerToContact*** jest utworzona między encją klienta i encją kontaktu. Encja klienta otrzymuje pole kluczowe **Contact_contactId** w celu powiązania jej z polem kluczowym encji kontaktu **contactId**.
- **Relacja _CustomerToAccount_** jest utworzona między encją klienta i encją konta. Encja klienta otrzymuje pole kluczowe **Account_accountId** w celu powiązania jej z polem kluczowym encji konta **accountId**.
- **Relacja _CustomerToWebAccount_** jest utworzona między encją klienta i encją konta sieci Web. Encja klienta otrzymuje pole kluczowe **WebAccount_webaccountId** w celu powiązania jej z polem kluczowym encji konta sieci Web **webaccountId**.

## <a name="create-a-relationship"></a>Utwórz relację

Relacje niestandardowe należy zdefiniować na stronie **Relacje**. Każda relacja składa się z encji źródłowej (encja przechowująca klucz obcy) i encji docelowej (encja, na którą wskazuje klucz obcy encji źródłowej).

1. W analizach odbiorców przejdź do **Dane** > **Relacje**.

2. Wybierz **Nowa relacja**.

3. W okienku **Dodaj relację** podaj następujące informacje:

   > [!div class="mx-imgBorder"]
   > ![Wprowadź szczegóły relacji](media/relationships-add.png "Wprowadź szczegóły relacji")

   - **Nazwa relacji**: nazwa, która odzwierciedla cel relacji (na przykład **AccountWebLogs**).
   - **Opis**: opis relacji.
   - **Encja źródłowa**: należy wybrać encję używaną jako źródło w relacji (np. dziennik sieci Web).
   - **Kardynalność**: wybierz kardynalność rekordów encji źródłowej. Na przykład „wiele” oznacza, że wiele rekordów dziennika sieci Web jest skojarzonych z jednym kontem sieci Web.
   - **Pole klucza źródłowego**: to pole oznacza klucz obcy w encji źródłowej. Na przykład dziennik sieci Web zawiera pole klucza obcego **accountId**.
   - **Encja docelowa**: należy wybrać encję używaną jako cel w relacji (np. konto sieci Web).
   - **Kardynalność docelowa**: wybierz kardynalność rekordów encji docelowej. Na przykład „jeden” oznacza, że wiele rekordów dziennika sieci Web jest skojarzonych z jednym kontem sieci Web.
   - **Pole klucza docelowego**: to pole reprezentuje pole klucza encji docelowej. Na przykład konto sieci Web zawiera pole klucza **accountId**.

> [!NOTE]
> Relacje obsługują tylko wiele-do-jednego i jeden-do-jednego. Relacje wiele-do-wielu można utworzyć przy użyciu dwóch relacji wiele-do-jednego i połączyć encje (encji, która jest używana do łączenia encji źródłowej i encji docelowej).

## <a name="delete-a-relationship"></a>Usuń relację

1. W analizach odbiorców przejdź do **Dane** > **Relacje**.

2. Zaznacz pole wyboru dla relacji, którą chcesz usunąć.

3. Wybierz **Usuń** na górze tabeli **Relacje**.

4. Potwierdź usunięcie.

## <a name="next-step"></a>Następny krok

System i relacje niestandardowe służą do tworzenia segmentów na podstawie wielu źródeł danych, które nie są już izolowane. Aby uzyskać więcej informacji, zobacz [Segmenty](segments.md).
