---
title: Aktywowanie reguł wyrażania zgody dla segmentów
description: Wykonaj poniższej kroki, aby połączyć dane zgody i aktywować testy zgody w funkcji Wyniki analiz odbiorców. Administrator może także wyłączyć testy zgody.
ms.date: 11/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 552cb0739c4d17266dd028638df067f3384b738a
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2021
ms.locfileid: "7884087"
---
# <a name="activate-consent-rules"></a>Aktywowanie reguł zgody

[Centrum zgody (wersja zapoznawcza)](../consent-management/overview.md) ułatwia grupowanie danych zgody z różnych źródeł. Użyj ujednoliconej encji *Zgoda* do stosowania domyślnych testów zgody. Po zaimportowaniu danych zgody do Centrum zgody i skonfigurowaniu reguł dotyczących danych encja *Zgoda* jest automatycznie synchronizowana z funkcją Wyniki analiz odbiorców.

## <a name="enable-consent-checks"></a>Włącz sprawdzanie zgody

Jeśli dane zgody są importowane do Centrum zgody (wersja zapoznawcza) i skonfigurowano reguły, można włączyć testy zgody. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Karta Zgoda w funkcji Wyniki analiz odbiorców z aktywowanymi danymi zgody.":::

1. W analizach odbiorców przejdź do **Administrator** > **System**.

1. Wybierz kartę **Zgoda (wersja zapoznawcza)**.

1. W sekcji **Włącz sprawdzanie zgody** ustaw przełącznik na **Wł.** dla wszystkich obszarów do włączenia.

1. Zaznacz pole wyboru **Zezwalaj na zastępowanie domyślnych reguł wyrażania zgody**, aby usunąć domyślne sprawdzanie zgody wymuszane w określonym segmencie. 

1. W menu rozwijanym wybierz miejsce, w którym chcesz zezwalać na zastępowanie danych.     

1. W sekcji **Połącz zgodę z profilami klientów** wybierz atrybut używany jako identyfikator w celu łączenia danych zgody z danymi klienta. Będzie to prawdopodobnie numer telefonu lub adres e-mail. 

1. Wybierz pozycję **Zapisz**, aby zastosować swoje ustawienia.

## <a name="disable-consent-checks"></a>Wyłączanie sprawdzania zgody

Aby zatrzymać korzystanie z danych dotyczących zgody w funkcji Wyniki analiz odbiorców, administrator musi odpowiednio zaktualizować ustawienia systemu.

1. W analizach odbiorców przejdź do **Administrator** > **System**.

1. Wybierz kartę **Zgoda (wersja zapoznawcza)**.

1. W sekcji **Włącz sprawdzanie zgody** ustaw przełącznik na **Wył**.

> [!TIP]
> Aby przestać korzystać z możliwości zarządzania zgodami, zobacz [Ustawienia systemowe w Consent Center (podgląd)](../consent-management/system-settings.md).