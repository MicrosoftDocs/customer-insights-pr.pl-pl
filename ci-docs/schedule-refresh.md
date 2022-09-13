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
ms.openlocfilehash: 949ea071ca41127b0c45488d5d7af3f6aa4e1c35
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2022
ms.locfileid: "9395969"
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

1. Ustaw **Strefę czasową**, a następnie użyj listy rozwijanej **Czas**, aby ustawić czas odświeżania. Jeśli chcesz zaplanować wiele odświeżań w ciągu jednego dnia, wybierz opcję **Dodaj inną godzinę**. Można dodać maksymalnie cztery odświeżenia.

1. Wybierz pozycję **Zapisz**, aby zastosować zmiany.

[!INCLUDE [footer-include](includes/footer-banner.md)]
