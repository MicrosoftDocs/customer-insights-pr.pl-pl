---
title: Twórz proste segmenty za pomocą szybkich segmentów
description: Twórz proste segmenty klientów, aby grupować ich na podstawie różnych atrybutów.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171140"
---
# <a name="create-simple-segments-with-quick-segments"></a>Twórz proste segmenty za pomocą szybkich segmentów

Szybkie segmenty umożliwiają tworzenie prostych segmentów z jednym operatorem w celu szybszego wglądu w dane. Szybkie segmenty są obsługiwane tylko w środowiskach dla **poszczególnych klientów**.

## <a name="create-a-new-segment-with-quick-segments"></a>Utwórz nowy segment za pomocą szybkich segmentów

1. Przejdź do **Segmenty**.

1. Wybierz pozycję **Nowy** > **Utwórz z**.
   - Wybierz opcję **profile**, aby zbudować segment utworzony na podstawie *ujednoliconej encji klienta*.
   - Wybierz opcję **Miary**, aby utworzyć segment na podstawie miar utworzonych wcześniej.
   - Wybierz opcję **Analizy**, aby utworzyć segment wokół jednej z encji wyjściowych wygenerowanych przy użyciu funkcji **Przewidywania** lub **Modele niestandardowe**.

1. W oknie dialogowym **Nowy szybki segment** wybierz atrybut z listy rozwijanej **Pole**. W zależności od wyboru system udostępnia różne wartości.
   - W przypadku pól kategorycznych wyświetlanych jest 10 najważniejszych liczników klientów. Wybierz **Wartość** i wybierz **Przejrzyj**.
   - W przypadku atrybutu numerycznego system pokaże, jaka wartość atrybutu mieści się w percentylu każdego klienta Wybierz **Operator** i **Wartość**, a następnie wybierz pozycję **Przeglądaj**.

1. System zaproponuje opcje **Szacowany rozmiar segmentu**. Wybierz, czy chcesz wygenerować zdefiniowany segment, czy wróć, aby wybrać inne pole.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Nazwa i oszacowanie szybkiego segmentu.":::

1. Podaj **Nazwę** i **Nazwę podmiotu wyjściowego** dla twojego segmentu. Opcjonalnie dodaj [etykiety](work-with-tags-columns.md#manage-tags).

1. Wybierz opcję **Zapisz**, aby utworzyć segment. Zostanie wyświetlona strona **Segmenty**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>Następne kroki

[Wyeksportuj segment](export-destinations.md) i zapoznaj się z [integracją karty klienta](customer-card-add-in.md), aby używać segmentów w innych aplikacjach.

[!INCLUDE [footer-include](includes/footer-banner.md)]
