---
title: Wyświetlanie i tworzenie rozmiarów
description: Jak tworzyć, edytować i usuwać wymiary.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b575c5e84197d76f53a722bac60c5af928c917f9671720ede1de38c4a7478be4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034010"
---
# <a name="view-and-create-dimensions"></a>Wyświetlanie i tworzenie rozmiarów

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Wymiar jest atrybutem zdarzenia, który może opisywać, filtrować lub grupować dane. Jeśli prowadzisz promocję marketingową na swojej stronie, możesz użyć wymiarów, aby posortować odwiedzających według nowych i powracających użytkowników.  

Wgląd w zaangażowanie obejmuje obecnie rozmiary właściwości zdarzenia. Przykłady obejmują:

- Nazwa przeglądarki
- Nazwa strony
- Model urządzenia
- System operacyjny
- Kraj

## <a name="view-dimensions"></a>Nowy wymiar

Wymiary są oparte na istniejących właściwościach zdarzenia. Kiedy używasz kodu śledzenia dla analiz zaangażowania, wymiary systemowe są tworzone automatycznie.

1. Przejdź do **Dane** lewym okienku nawigacji. 
1. Wybierz **Wymiary**, aby wyświetlić listę wszystkich rozmiarów w obszarze roboczym. 
   > [!NOTE]
   > Wymiary generowane przez system są tylko do odczytu. Nie można ich edytować. Możliwe jest tworzenie i edytowanie wyłącznie rozmiarów niestandardowych.

## <a name="create-a-dimension"></a>Utwórz wymiar

Oprócz wymiarów generowanych przez system, administratorzy środowisk i obszarów roboczych mogą tworzyć wymiary niestandardowe. Wymiary niestandardowe są oparte na domyślnych właściwościach zdarzeń bazowych lub mogą wykorzystywać [niestandardowe właściwości zdarzenia](advanced-SDK-implementation.md).

1. Przejdź do **Dane** > **Wymiary**.
1. Wybierz **Dodaj wymiar**.

   :::image type="content" source="media/add-dimension.png" alt-text="Dodawanie wymiarów do zdarzenia.":::

1. W okienku **Tworzenie wymiaru** wybierz właściwość, która ma stanowić podstawę wymiarów. Lista właściwości pokaże wszystkie właściwości w obszarze roboczym, które nie są przypisane do wymiaru.
1. Wprowadź nazwę w polu **Nazwa wyświetlana**. Opcjonalnie można dodać opis.
1. Wybierz pozycję **Utwórz przepływ**, aby zapisać wymiar. Zanim będzie można użyć wymiaru w [raporcie niestandardowym](custom-reports.md) lub [segmencie](segments.md), może upłynąć do jednej minuty. 

## <a name="edit-a-dimension"></a>Edytuj wymiar

Można zmienić nazwę i opis wymiaru.

1. Przejdź do **Dane** > **Wymiary**.
1. Wybierz wymiar, który chcesz usunąć.
1. W okienku **Edytuj wymiar** zaktualizuj odpowiedni wymiar.
1. Wybierz pozycję **Zastosuj**, aby zapisać zmiany.

## <a name="delete-a-dimension"></a>Usuń wymiar

Możesz usunąć tylko wymiary utworzone przez użytkownika, ale nie możesz usunąć wymiarów systemowych.

Usuwanie wymiarów jest trwałe. Raporty i segmenty, które używają usuniętego wymiaru nie będą już działać. 

1. Przejdź do **Dane** > **Wymiary**.
1. Wybierz wymiar, który chcesz usunąć.
1. W okienku **Edytuj wymiar** wybierz **Usuń wymiar**.

   :::image type="content" source="media/delete-dimension.png" alt-text="Usuwanie wymiarów ze zdarzenia.":::

1. Wprowadź **POTWIERDŹ USUNIĘCIE** (dużymi literami), aby potwierdzić usunięcie. 
1. Wybierz **Usuń**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
