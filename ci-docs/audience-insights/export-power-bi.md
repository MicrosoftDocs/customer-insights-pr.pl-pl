---
title: Łącznik usługi Power BI
description: Dowiedz się, jak używać łącznika Dynamics 365 Customer Insights w Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406553"
---
# <a name="connector-for-power-bi-preview"></a>Łącznik dla Power BI (wersja zapoznawcza)

Utwórz wizualizacje danych za pomocą narzędzia Power BI Desktop. Tworzenie dodatkowych wyników analiz i raportów przy użyciu ujednoliconych danych klientów.

## <a name="prerequisites"></a>Wymagania wstępne

- Posiadasz ujednolicone profile klientów.
- Najnowsza wersja [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) jest zainstalowana na komputerze użytkownika. [Więcej informacji o Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konfigurowanie łącznika dla Power BI

1. W Power BI Desktop wybierz **Plik** > **Pobierz dane**.

1. Wybierz **Zobacz więcej** i wyszukaj **Dynamics 365 Customer Insights**

1. Wybierz wyniki i wybierz **Połącz**.

1. **Zaloguj się**, korzystając z tego samego konta organizacyjnego, które będzie używane dla Customer Insights i wybierz **Połącz**.
   > [!NOTE]
   > Konto wskazywane w tym kroku służy do pobierania danych z Customer Insights i nie musi być tym samym, do którego użytkownik jest zalogowany w programie Power BI. Aby zresetować konto używane do pobierania danych, otwórz Power BI i przejdź do **Plik** > **Opcje** > **Ustawienia** > **Ustawienia źródeł danych**. Z listy źródeł danych wybierz **Logowanie w Dynamics 365 Customer Insights** i wybierz **Wyczyść uprawnienia**.  

1. W oknie dialogowym **Nawigator**. zobaczysz listę wszystkich środowisk, do których masz dostęp. Rozwiń środowisko i otwórz dowolny z folderów (encje, miary, segmenty, wzbogacenia). Na przykład otwórz folder **Encje**, aby wyświetlić wszystkie encje, które można importować.

   ![Nawigator łącznika Power BI](media/power-bi-navigator.png "Nawigator łącznika Power BI")

1. Zaznacz pola wyboru obok encji, które mają zostać dodane i **Załaduj**. Możesz wybrać wiele encji z wielu środowisk.

1. Podczas ładowania encji zostanie wyświetlone okno dialogowe ładowania. Kiedy wszystkie wybrane encje zostaną załadowane, można użyć funkcji Power BI do wizualizacji danych.

## <a name="large-data-sets"></a>Duże zestawy danych

Łącznik Customer Insights dla Power BI jest przeznaczony do pracy z zestawami danych zawierającymi do 1.000.000 profilów klientów. Importowanie większych zestawów danych może się udać, ale zajmie dużo czasu. Ponadto proces może przekroczyć limit czasu z powodu ograniczeń Power BI. Aby uzyskać więcej informacji, zobacz [Power BI: Rekomendacje dotyczące dużych zestawów danych](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Praca z podzbiorem danych

Weź pod uwagę pracę z podzbiorem danych programu. Można na przykład utworzyć [segmenty](segments.md) zamiast eksportowania wszystkich rekordów klientów do Power BI.
