---
title: Zaplanuj odświeżanie systemu
description: Planowanie czasu odświeżania systemu
ms.date: 09/27/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 4aac02b570357d2086f7a9d7340b0e4837157a0b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610341"
---
# <a name="schedule-system-refresh"></a>Zaplanuj odświeżanie systemu

Harmonogram automatyczne odświeża wszystkie [źródła pozyskanych danych](data-sources.md). Automatyczne odświeżanie ułatwia zagwarantowanie, że aktualizacje ze źródeł danych będą odzwierciedlone w ujednoliconych profilach klientów.

> [!NOTE]
> Źródła danych Power Query zarządzane przez odświeżanie według własnych harmonogramów. Aby zaplanować odświeżanie tych źródeł danych Power Query, należy skonfigurować ustawienia odświeżania dla tego źródła danych na stronie **Źródła danych**. Wyrównaj synchronizację z nadrzędnym harmonogramem odświeżania danych, by uniknąć odświeżania wszystkiego na raz.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Ustawienia odświeżania przepływu danych Power Platform.":::

## <a name="set-system-refresh-schedule"></a>Ustaw harmonogram odświeżania systemu

1. Przejdź do pozycji **Administracja** > **System** i wybierz kartę **Harmonogram**.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Karta Zaplanuj odświeżanie na stronie systemowej.":::

1. Stan domyślny dla planowanego odświeżenia to **Wyłączony**. Aby włączyć zaplanowane odświeżanie, należy zmienić przełącznik na górze ekranu na opcję **Włączony**.

1. Należy wybrać kolejno pozycje **Co tydzień** (domyślne) i **Codziennie** odświeżanie. Jeśli zamierzasz zaplanować cotygodniowe odświeżenie, wybierz jeden lub kilka dni, kiedy chcesz uruchomić odświeżanie.

1. Ustaw **Strefę czasową**, a następnie użyj listy rozwijanej **Czas**, aby ustawić czas odświeżania. Jeśli chcesz zaplanować wiele odświeżań w ciągu jednego dnia, wybierz opcję **Dodaj inną godzinę**. Można dodać maksymalnie cztery odświeżenia.

1. Wybierz pozycję **Zapisz**, aby zastosować zmiany.

[!INCLUDE [footer-include](includes/footer-banner.md)]
