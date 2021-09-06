---
title: Scalanie encji w przypadku zjednoczenia danych
description: Scalanie encji w celu utworzenia ujednoliconych profili klientów.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6e64154dc58f679d13033fa55a60cd0c306f62f31548b8ce98ea1ed5f423b3e9
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035015"
---
# <a name="merge-entities"></a>Scalanie encji

Faza scalania jest ostatnią fazą procesu unifikacji danych. Jego zastosowanie powoduje uzgadnianie danych powodujących konflikty. Przykłady danych powodujących konflikty mogą zawierać nazwy klientów znalezione w dwóch zestawach danych, które są wyświetlane w różny sposób w każdym miejscu („Grant Marshall” i „Grant Marshal”) lub numery telefoniczne, który różnią się formatem (617-803-091X a 617803091X). Scalanie tych niezgodnych danych jest wykonywane na podstawie poszczególnych atrybutów.

:::image type="content" source="media/merge-fields-page.png" alt-text="Strona scalania w procesie ujednolicania danych pokazująca tabelę z połączonymi polami definiującymi ujednolicony profil klienta.":::

Po zakończeniu [fazy dopasowania](match-entities.md) można rozpocząć fazę scalenia, zaznaczając kafelek **Scalanie** na stronie **Ujednolicanie**.

## <a name="review-system-recommendations"></a>Przejrzyj rekomendacje systemu

W **Dane** > **Ujednolić** > **Scal** wybierasz i wykluczasz atrybuty do połączenia w ramach ujednoliconej jednostki profilu klienta. Ujednolicony profil klienta jest wynikiem procesu unifikacji danych. Niektóre atrybuty są automatycznie scalane przez system.

Aby zobaczyć atrybuty, które są zawarte w jednym z twoich automatycznie połączonych atrybutów, wybierz ten połączony atrybut **Pola klienta** na zakładce tabeli. Dwa nowe wiersze tworzące scalony atrybut będą wyświetlane w dwóch nowych wierszach pod atrybutem scalonym.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Rozdzielanie, zmienianie nazw, wykluczanie i edytowanie pól scalonych

W celu wygenerowania ujednoliconego profilu klienta można zmienić sposób przetwarzania przez system scalonych atrybutów. Wybierz opcję **Pokaż więcej** i wybierz, co chcesz zmienić.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Opcje w menu rozwijanym Pokaż więcej, aby zarządzać połączonymi atrybutami.":::

Aby uzyskać więcej informacji, zobacz następną sekcję.

## <a name="separate-merged-fields"></a>Oddzielenie połączonych pól

Aby oddzielić połączone pola, znajdź atrybut w tabeli. Oddzielone pola są wyświetlane jako pojedyncze punkty danych na jednolitym profilu klienta. 

1. Zaznacz scalone pole.
  
1. Wybierz opcję **Pokaż więcej** i wybierz pozycję **Rozdziel pola**.
 
1. Potwierdź rozdział.

1. Wybierz opcję **Zapisz** i **Uruchom**, aby przetworzyć zmiany.

## <a name="rename-merged-fields"></a>Zmienianie nazw pól scalonych

Zmień wyświetlaną nazwę scalonych atrybutów. Nie można zmienić nazwy elementu wyjściowego.

1. Zaznacz scalone pole.
  
1. Wybierz opcję **Pokaż więcej** i wybierz pozycję **Zmień nazwę**.

1. Potwierdź zmienioną nazwę wyświetlania. 

1. Wybierz opcję **Zapisz** i **Uruchom**, aby przetworzyć zmiany.

## <a name="exclude-merged-fields"></a>Wykluczanie pól połączonych

Wykluczenie atrybutu z ujednoliconego profilu klienta. Jeśli pole jest wykorzystywane w innych procesach, np. w segmencie, usuń je z tych procesów, zanim wykluczysz je z profilu klienta. 

1. Zaznacz scalone pole.
  
1. Wybierz opcję **Pokaż więcej** i wybierz pozycję **Wyklucz**.

1. Potwierdź wykluczenie.

1. Wybierz opcję **Zapisz** i **Uruchom**, aby przetworzyć zmiany. 

Na stronie **Scalanie** wybierz pozycję **Wykluczone pola**, aby wyświetlić listę wszystkich pól wykluczonych. To okienko umożliwia dodawanie z powrotem wykluczonych pól.

## <a name="manually-combine-fields"></a>Ręczne łączenie pól

Określ ręcznie łączony atrybut. 

1. Na stronie **Scalanie** wybierz opcję **Połącz pola**.

1. Podaj **nazwę** i **nazwę pola wyjściowego**.

1. Wybierz pole, które chcesz dodać. Wybierz **Dodaj pola**, aby połączyć więcej pól.

1. Potwierdź wykluczenie.

1. Wybierz opcję **Zapisz** i **Uruchom**, aby przetworzyć zmiany. 

## <a name="change-the-order-of-fields"></a>Zmiana kolejności pól

Niektóre encje zawierają więcej szczegółów niż inne. Jeśli encja zawiera najnowsze dane o polu, możesz nadać jej priorytet nad innymi encjami podczas łączenia wartości.

1. Zaznacz scalone pole.
  
1. Wybierz opcję **Pokaż więcej** i wybierz pozycję **Edytuj**.

1. W okienku **Łączenie pól** wybierz opcję **Przenieś w górę/w dół**, aby ustawić kolejność lub przeciągnij je i upuść w żądanym miejscu.

1. Potwierdź zmianę.

1. Wybierz opcję **Zapisz** i **Uruchom**, aby przetworzyć zmiany.

## <a name="run-your-merge"></a>Uruchamianie scalania

Niezależnie od tego, czy ręcznie scalono atrybuty, czy pozwolono, aby system je scalił, zawsze można uruchomić scalanie. Wybierz **Uruchom** na stronie **Scalanie**, aby zacząć proces.

> [!div class="mx-imgBorder"]
> ![Zapis i uruchomienie scalania danych.](media/configure-data-merge-save-run.png "Zapis i uruchomienie scalania danych")

Wybierz opcję **Uruchom tylko scalanie**, jeśli chcesz, aby wyniki pracy zostały odzwierciedlone w ujednoliconej encji klienta. Procesy niższego szczebla zostaną odświeżone zgodnie [z definicją w harmonogramie odświeżania](system.md#schedule-tab).

Wybierz **Uruchom procesy scalania i procesy niższego rzędu**, aby odświeżyć system przy użyciu zmian. Wszystkie procesy, w tym wzbogacenie, segmenty i miary, zostaną automatycznie ponownie uruchomione. Po zakończeniu wszystkich dalszych procesów, profile klientów odzwierciedlają wszystkie wprowadzone zmiany.

Aby wprowadzić więcej zmian i ponownie uruchomić krok, można anulować trwające scalanie. Wybierz **Odświeżanie...** i wybierz **Anuluj zadanie**  w pojawiającym się okienku bocznym.

> [!TIP]
> Po uruchomieniu procesu scalania wybierz stan procesu, aby otworzyć okienko **Szczegóły zadania**. Zawiera przegląd czasu przetwarzania, daty ostatniego przetwarzania i wszystkich błędów i ostrzeżeń skojarzonych z zadaniem. Wybierz **Zobacz szczegóły**, aby zobaczyć, które jednostki uczestniczyły w procesie dopasowania, czy rozwiązanie konfliktu zakończyło się pomyślnie i czy aktualizacje zostały pomyślnie opublikowane.  
> Istnieje [sześć typów stanu](system.md#status-types) zadań/procesów. Ponadto większość procesów [zależy od innych procesów podrzędnych](system.md#refresh-policies).  
> :::image type="content" source="media/process-detail-path.png" alt-text="Ścieżka przechodzenia do szczegółów, aby uzyskać szczegółowe informacje z łącza stanu zadania.":::

## <a name="next-step"></a>Następny krok

Skonfiguruj [działania](activities.md), [wzbogacenie](enrichment-hub.md) lub [relacje](relationships.md), aby uzyskać dokładniejsze informacje o klientach.

Jeśli już skonfigurowałeś działania, wzbogacenia lub segmenty, zostaną one przetworzone automatycznie, aby wykorzystać najnowsze dane o klientach.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
