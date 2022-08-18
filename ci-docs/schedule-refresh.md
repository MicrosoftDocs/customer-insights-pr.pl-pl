---
title: Zaplanuj odświeżanie systemu
description: Planowanie czasu odświeżania systemu
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: ce10fcfe9906d33209270f8f6930a51b045b13e2
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246346"
---
# <a name="schedule-system-refresh"></a>Zaplanuj odświeżanie systemu

Harmonogram automatyczne odświeża wszystkie [źródła pozyskanych danych](data-sources.md). Automatyczne odświeżanie ułatwia zagwarantowanie, że aktualizacje ze źródeł danych będą odzwierciedlone w ujednoliconych profilach klientów.

> [!NOTE]
> Źródła danych Power Query zarządzane przez odświeżanie według własnych harmonogramów. Aby zaplanować odświeżanie tych źródeł danych Power Query, należy skonfigurować ustawienia odświeżania dla tego źródła danych na stronie **Źródła danych**.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Ustawienia odświeżania przepływu danych Power Platform.":::

## <a name="set-system-refresh-schedule"></a>Ustaw harmonogram odświeżania systemu

1. Przejdź do pozycji **Administracja** > **System** i wybierz kartę **Harmonogram**.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Karta Zaplanuj odświeżanie na stronie systemowej.":::

1. Stan domyślny dla planowanego odświeżenia to **Wyłączony**. Aby włączyć zaplanowane odświeżanie, należy zmienić przełącznik na górze ekranu na opcję **Włączony**.

1. Należy wybrać kolejno pozycje **Co tydzień** (domyślne) i **Codziennie** odświeżanie. Jeśli zamierzasz zaplanować cotygodniowe odświeżenie, wybierz jeden lub kilka dni, kiedy chcesz uruchomić odświeżanie.

1. Ustaw **Strefę czasową**, a następnie użyj listy rozwijanej **Czas**, aby ustawić czas odświeżania. Jeśli chcesz zaplanować wiele odświeżań w ciągu jednego dnia, wybierz opcję **Dodaj inną godzinę**.

1. Wybierz pozycję **Zapisz**, aby zastosować zmiany.

[!INCLUDE [footer-include](includes/footer-banner.md)]
