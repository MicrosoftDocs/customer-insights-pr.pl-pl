---
title: Aktywowanie reguł zgody w poszczególnych segmentach w funkcji Wyniki analiz odbiorców
description: Kroki służące do łączenia danych zgody i aktywowania kontroli zgody w funkcji Wyniki analiz odbiorców.
ms.date: 11/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 33ec3a684c2ca47badb4e5461f069d1b2e4a4f3d
ms.sourcegitcommit: 2a0947cffb52eaf885aa2e50c95b3693f7e4c589
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/04/2021
ms.locfileid: "7753074"
---
# <a name="activate-consent-rules"></a>Aktywowanie reguł zgody

[Centrum zgody (wersja zapoznawcza)](../consent-management/overview.md) ułatwia grupowanie danych zgody z różnych źródeł. Użyj ujednoliconej encji *Zgoda* do stosowania domyślnych testów zgody. Po zaimportowaniu danych zgody w Centrum zgody i skonfigurowaniu reguł dla zaimportowanych danych zgody encja *Zgoda* jest automatycznie synchronizowana z funkcją Wyniki analiz odbiorców.

## <a name="enable-consent-checks"></a>Włącz sprawdzanie zgody

Jeśli dane zgody są importowane do Centrum zgody (wersja zapoznawcza) i ustawiono reguły, można włączyć sprawdzanie zgody w funkcji Wyniki analiz odbiorców. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Karta Zgoda w funkcji Wyniki analiz odbiorców z aktywowanymi danymi zgody.":::

1. W analizach odbiorców przejdź do **Administrator** > **System**.

1. Wybierz kartę **Zgoda (wersja zapoznawcza)**.

1. W sekcji **Włącz sprawdzanie zgody** ustaw przełącznik na obszar, który chcesz **włączyć**.

1. Zaznacz pole wyboru **Zezwalaj na zastępowanie domyślnych reguł wyrażania zgody**, aby usunąć domyślne sprawdzanie zgody wymuszane w określonym segmencie. 

1. W menu rozwijanym wybierz miejsce, w którym chcesz zezwalać na zastępowanie danych.     

1. W sekcji **Połącz zgodę z profilami klientów** wybierz atrybut używany jako identyfikator w celu łączenia danych zgody z danymi klienta. Najprawdopodobniej jest to numer telefonu lub adres e-mail. 

1. Wybierz pozycję **Zapisz**, aby zastosować swoje ustawienia.

## <a name="disable-consent-checks"></a>Wyłączanie sprawdzania zgody

Aby zatrzymać korzystanie z danych dotyczących zgody w funkcji Wyniki analiz odbiorców, administrator musi odpowiednio zaktualizować ustawienia systemu.

1. W analizach odbiorców przejdź do **Administrator** > **System**.

1. Wybierz kartę **Zgoda (wersja zapoznawcza)**.

1. W sekcji **Włącz sprawdzanie zgody** ustaw przełącznik się na **wyłączony**.
