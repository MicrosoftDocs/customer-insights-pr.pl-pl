---
title: Eksportowanie opracowanych zdarzeń
description: Jak wyeksportować opracowane zdarzenia i zdarzenia podstawowe.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7881f8f63134170a7f76e3c75dcfc5fa8930754b
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606251"
---
# <a name="export-events"></a>Eksportowanie zdarzeń

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Zdarzenie reprezentuje zachowanie użytkownika. Działanie jest rekordem w momencie, gdy użytkownik wyświetla stronę (działanie Wyświetlanie) lub wchodzi w interakcję z treścią (działanie Akcja). W przypadku podjęcia decyzji o właściwościach danych, które mają być wyświetlane w raporcie, ten widok wirtualny danych jest nazywany *zdarzeniem opracowanym*. Aby uzyskać więcej informacji, zobacz temat [Tworzenie i modyfikowanie zdarzeń](refined-events.md).

- Zdarzenia i zdarzenia opracowane można eksportować do magazynu zewnętrznego. 
- Eksport jest strumieniem danych przesyłanych dalej. Nie można ponownie wypełnić strumienia. 
- Eksporty mają stałe schematy. Jeśli zostaną dodane do zdarzenia właściwości niestandardowe, nie zostaną one uwzględnione. Konieczne będzie utworzenie nowego eksportu.

## <a name="prerequisites"></a>Wymagania wstępne

Przed skonfigurowaniem eksportu musisz mieć dostęp i aktywną subskrypcję portalu Azure. Podczas procesu eksportowania potrzebne będą informacje o koncie magazynu. 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Utwórz konta Azure Data Lake Storage Gen 2

1. Zaloguj się do portalu Azure i [utwórz nowe konto magazynu](/azure/storage/common/storage-account-create). 

1. Upewnij się, że na karcie **Zaawansowane** jest włączany obszar **nazw hierarchicznych**. 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="Włącz na karcie Zaawansowane obszar nazw hierarchicznych.":::

1. Po wdrożeniu przejdź do nowo utworzonego konta magazynu. W okienku nawigacji wybierz pozycję **Ustawienia** > **Klucze dostępu**. 

1. Skopiuj **nazwę konta** i **klucz**, aby użyć ich podczas tworzenia nowego eksportu.
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="Klucze dostępu do konta magazynu.":::

## <a name="export-events"></a>Eksportuj zdarzenia

Istnieją dwa sposoby wyświetlania sesji dialogowej **Eksportowanie zdarzeń**: 
- Wybierz opcję **Dane** > **Eksporty** i wybierz opcję **Nowy**.
- Należy przejść do menu **Dane** > **Zdarzenia**, wybrać pozycję **Więcej [...]** obok zdarzenia, które chcesz wyeksportować, i wybrać polecenie **Eksportuj** z menu rozwijanego. 

:::image type="content" source="media/new-export.png" alt-text="Tworzenie nowego eksportu.":::

Program przeprowadzi Cię przez kolejne kroki tworzenia eksportu:

1. Podaj **nazwę eksportu**, a następnie wybierz opcję **Dalej**.

1. Z listy rozwijanej **Wybór zdarzeń** wybierz zdarzenia podstawowe i zdarzenia wzbogacone, które mają być uwzględniane w eksporcie. 

1. W sekcji **Struktura plików** wybierz czas (godzinowo lub dziennie), aby utworzyć nowe pliki w docelowym magazynie, a następnie wybierz opcję **Dalej**. Zdarzenia są eksportowane po przybyciu, bez przerwy.

1. W sesji dialogowej **Wybierz format** wybierz format eksportu. Wybierz format **Common Data Model**, **CSV** i **JSON**. Aby korzystać z eksportu z innymi aplikacjami usługi Dynamics 365, zalecamy użycie formatu **Common Data Model**.

1. W sesji dialogowej **Wybierz miejsce docelowe** określ lokalizację usługi Azure Data Lake Storage Gen 2.
    1. **Nazwa konta ADLS Gen 2** to nazwa konta magazynu, w którym chcesz zapisać eksport. 
    1. **Ścieżka folderu** definiuje miejsce eksportu w systemie plików i strukturze katalogowej konta magazynu.
    1. **Klucz udostępniony** jest dostępny w portalu Azure dla konta magazynu.

1. Sprawdź i potwierdź wybrane opcje, aby zakończyć.

## <a name="view-and-manage-exports"></a>Wyświetl eksporty i zarządzaj nimi

Po skonfigurowaniu eksportu przejdź do strony **Dane** > **Eksporty**, aby go wyświetlić. Wybierz opcję **Więcej [...]** dla każdego istniejącego eksportu, który ma być edytowany lub usuwany.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
