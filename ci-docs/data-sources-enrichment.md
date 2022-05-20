---
title: Wzbogacanie źródeł danych
description: Wzbogać źródła danych przed przejściem przez proces ujednolicania danych.
ms.date: 03/02/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: d1e14d2d4e718d71ccbd2afd259a350ad5c9e69a
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755699"
---
# <a name="enrichment-for-data-sources-preview"></a>Wzbogacanie źródeł danych (wersja zapoznawcza)

Wykorzystaj dane ze źródeł takich jak Microsoft i inni partnerzy, aby wzbogacić dane o klientach przed ich ujednoliceniem. Wzbogacenie źródeł danych pomaga w uzyskaniu większej kompletności i jakości danych, co może pomóc w osiągnięciu lepszych wyników po ujednoliceniu danych. Na przykład używanie znormalizowanego i ujednoliconego formatu adresów zwiększa jakość wyników dopasowania. Listę obsługiwanych elementów wzbogacających znajdziesz na stronie [obsługiwane opcje wzbogacania źródła danych](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Wzbogacanie źródła danych

Aby tworzyć lub edytować wzbogacenia, musisz mieć uprawnienia współautora lub administratora. Aby uzyskać więcej informacji, zobacz [Uprawnienia](permissions.md).  

1. Przejdź do sekcji **Dane** > **Ujednolicanie**. Wybierz encję, którą chcesz wzbogacić i wybierz jeden atrybut jako klucz główny dla tej encji. Aby uzyskać więcej informacji, zobacz [Wybierz klucz główny](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Przejdź do **Dane** > **Źródła danych**.

1. Zaznacz pionową elipsę obok źródła danych, które chcesz wzbogacić i wybierz **Wzbogać**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Strona wzbogacania źródeł danych.":::

   Na karcie **Poznaj** są wyświetlane [obsługiwane źródła danych wzbogacania](#supported-data-source-enrichments).

1. Wybierz opcję **Wzbogać dane**, aby skonfigurować wzbogacanie źródła danych. Nazwa encji wyjściowej jest uzupełniana automatycznie.

## <a name="supported-data-source-enrichments"></a>Obsługiwane wzbogacenia źródeł danych

Obecnie dla źródeł danych dostępne są następujące wzbogacenia. Zapoznaj się ze szczegółowymi krokami dotyczącymi wzbogacenia, aby dowiedzieć się, jak je skonfigurować.

- [Rozszerzone adresy](enrichment-enhanced-addresses.md)
- [Rozszerzone dane firm](enrichment-enhanced-company-data.md)

## <a name="manage-existing-data-source-enrichments"></a>Zarządzaj wzbogacaniem istniejących źródeł danych

Przejdź do karty **Moje wzbogacenia**, aby zobaczyć wszystkie skonfigurowane wzbogacania.

Wybierz wzbogacenie, aby wyświetlić dostępne opcje. Aby wyświetlić opcje, wybierz wielokropek (...) na elemencie listy. Jeśli skonfigurowano kilka wzbogaceń, można użyć pola wyszukiwania, aby szybko je znaleźć.

Możesz przeglądać, edytować, uruchamiać lub usuwać wzbogacenie źródła danych. Aby uzyskać więcej informacji, zobacz [Zarządzaj istniejącymi wzbogaceniami](enrichment-hub.md).
