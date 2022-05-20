---
title: Aktywowanie reguł wyrażania zgody dla segmentów
description: Wykonaj poniższej kroki, aby połączyć dane zgody i aktywować testy zgody w funkcji Dynamics 365 Customer Insights. Administrator może także wyłączyć testy zgody.
ms.date: 04/27/2022
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f82e3a4031fee8bcaa88575cbd68b37385a7fffb
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755183"
---
# <a name="activate-consent-rules"></a>Aktywowanie reguł zgody

[Centrum zgody (wersja zapoznawcza)](consent-management/overview.md) ułatwia grupowanie danych zgody z różnych źródeł. Użyj ujednoliconej encji *Zgoda* do stosowania domyślnych testów zgody. Po zaimportowaniu danych dotyczących zgody i skonfigurowaniu reguł mapowania, encja *Zgoda* jest automatycznie synchronizowana z Dynamics 365 Customer Insights.

## <a name="enable-consent-checks"></a>Włącz sprawdzanie zgody

Jeśli dane zgody są importowane do Centrum zgody (wersja zapoznawcza) i skonfigurowano reguły, można włączyć testy zgody. 

:::image type="content" source="consent-management/media/enable-consent-checks.png" alt-text="Karta Zgoda w funkcji Customer Insights z aktywowanymi danymi zgody.":::

1. W Customer Insights przejdź do **Administrator** > **System**.

1. Wybierz kartę **Zgoda (wersja zapoznawcza)**.

1. W sekcji **Włącz sprawdzanie zgody** ustaw przełącznik na **Wł.** dla wszystkich obszarów do włączenia.

1. Zaznacz pole wyboru **Zezwalaj na zastępowanie domyślnych reguł wyrażania zgody**, aby usunąć domyślne sprawdzanie zgody wymuszane w określonym segmencie. 

1. W menu rozwijanym wybierz miejsce, w którym chcesz zezwalać na zastępowanie danych.     

1. W sekcji **Połącz zgodę z profilami klientów** wybierz atrybut używany jako identyfikator w celu łączenia danych zgody z danymi klienta. Będzie to prawdopodobnie numer telefonu lub adres e-mail. 

1. Wybierz pozycję **Zapisz**, aby zastosować swoje ustawienia.

## <a name="disable-consent-checks"></a>Wyłączanie sprawdzania zgody

Aby zatrzymać korzystanie z danych dotyczących zgody w funkcji Customer Insights, administrator musi odpowiednio zaktualizować ustawienia systemu.

1. W Customer Insights przejdź do **Administrator** > **System**.

1. Wybierz kartę **Zgoda (wersja zapoznawcza)**.

1. W sekcji **Włącz sprawdzanie zgody** ustaw przełącznik na **Wył**.

> [!TIP]
> Aby przestać korzystać z możliwości zarządzania zgodami, zobacz [Ustawienia systemowe w Consent Center (podgląd)](consent-management/system-settings.md).
