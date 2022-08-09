---
title: Wzbogacanie źródeł danych (wersja zapoznawcza)
description: Wzbogać źródła danych przed przejściem przez proces ujednolicania danych.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 98e9e330e7ef9cf085caa94a506fa788cebdd67b
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207196"
---
# <a name="enrichment-for-data-sources-preview"></a>Wzbogacanie źródeł danych (wersja zapoznawcza)

Wykorzystaj dane ze źródeł takich jak Microsoft i inni partnerzy, aby wzbogacić dane o klientach przed ich ujednoliceniem. Wzbogacenie źródeł danych pomaga w uzyskaniu większej kompletności i jakości danych, co może pomóc w osiągnięciu lepszych wyników po ujednoliceniu danych. Na przykład używanie znormalizowanego i ujednoliconego formatu adresów zwiększa jakość wyników dopasowania. Listę obsługiwanych elementów wzbogacających znajdziesz na stronie [obsługiwane opcje wzbogacania źródła danych](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Wzbogacanie źródła danych

Aby tworzyć lub edytować wzbogacenia, musisz mieć [uprawnienia](permissions.md) współautora lub administratora.  

1. Przejdź do sekcji **Dane** > **Ujednolicanie**. Wybierz encję, którą chcesz wzbogacić i wybierz jeden atrybut jako [klucz główny](map-entities.md#select-primary-key-and-semantic-type-for-attributes) dla tej encji.

1. Przejdź do **Dane** > **Źródła danych**.

1. Zaznacz pionową elipsę (&vellip;) obok źródła danych, które chcesz wzbogacić i wybierz **Wzbogać**.

   :::image type="content" source="media/data_sources_enrich.png" alt-text="Strona Źródła danych z wyróżnionym Wzbogać":::

   Na karcie **Poznaj** są wyświetlane [obsługiwane źródła danych wzbogacania](#supported-data-source-enrichments).

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Strona wzbogacania źródeł danych.":::

1. Wybierz opcję **Wzbogać dane**, aby skonfigurować wzbogacanie źródła danych. Nazwa encji wyjściowej jest uzupełniana automatycznie.

## <a name="supported-data-source-enrichments"></a>Obsługiwane wzbogacenia źródeł danych

Obecnie dla źródeł danych dostępne są następujące wzbogacenia. Zapoznaj się ze szczegółowymi krokami dotyczącymi wzbogacenia, aby dowiedzieć się, jak je skonfigurować.

- [Rozszerzone adresy](enrichment-enhanced-addresses.md)
- [Rozszerzone dane firm](enrichment-enhanced-company-data.md)
- [Dane tożsamości z LiveRamp](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Zarządzaj wzbogacaniem istniejących źródeł danych

Przejdź do **Dane** > **Wzbogacanie**. Na karcie **Moje wzbogacenia** wyświetl skonfigurowane wzbogacania, ich stan, liczbę wzbogaconych klientów i czas ostatniego odświeżania danych. Listę wzbogacań można posortować według dowolnej kolumny lub użyć pola wyszukiwania, aby znaleźć wzbogacanie, którym chcesz zarządzać.

Wybierz wzbogacenie, aby wyświetlić dostępne opcje. Aby wyświetlić opcje, można także wybrać wielokropek pionowy (&vellip;) na pozycji listy.

Możesz przeglądać, edytować, uruchamiać lub usuwać wzbogacenie źródła danych. Aby uzyskać więcej informacji, zobacz [Zarządzaj istniejącymi wzbogaceniami](enrichment-hub.md#manage-existing-enrichments).
