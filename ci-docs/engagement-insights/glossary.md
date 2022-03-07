---
title: Analiza interakcji — słownik wydajności
description: Słownik terminów i pojęć.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 11/12/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: fd6513f66777f8be312c8b594d52836ac325f2825e9d019d2ba0f49c587cf8ca
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035749"
---
# <a name="engagement-insights-capability-glossary"></a>Analiza interakcji — słownik wydajności

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ta lista definiuje wybrane terminy wyświetlane w Dynamics 365 Customer Insights w ramach analizy interakcji i w dokumentacji wspierającej.

## <a name="base-event"></a>Zdarzenie podstawowe

Zdarzenie podstawowe to zestaw danych reprezentujący działanie w witrynie sieci Web, takie jak wyświetlenie strony lub kliknięcie. 

## <a name="dimensions"></a>Wymiary

Obszar to atrybuty zdarzeń, które mogą być opisane, odfiltrowane lub grupować dane. Można na przykład wybrać *system operacyjny (OS)*, *przeglądarkę* lub *nazwę strony* jako aspekt raportu.

## <a name="event"></a>Wydarzenie

W analizie cyfrowej zdarzenie reprezentuje zachowanie użytkownika. Zdarzenie staje się rekordem w momencie, gdy użytkownik wyświetla stronę (działanie Wyświetlanie) lub wchodzi w interakcję z treścią (działanie Akcja). Dane działań z witryny sieci Web są przechwytywane jako *zdarzenia podstawowe*. Do raportowania można wybrać właściwości danych, które mają być wyświetlane. Ten widok wirtualny danych jest nazywany *zdarzeniem opracowanym*. 

## <a name="environment"></a>Środowisko

 Środowisko to miejsce mogące zawierać jeden lub więcej obszarów roboczych. Środowisko pozwala zarządzać obszarami roboczymi i połączeniami z funkcją analizy odbiorców w Customer Insights.

## <a name="member"></a>Element członkowski

Członek obszaru roboczego to użytkownik, który ma dostęp do obszaru roboczego. Członkowie mogą mieć role, które umożliwiają użytkownikowi zarządzanie obszarem roboczym, jego danymi i wyświetlaniem raportów. Obecnie *właściciel* jest jedyną rolą dostępną w ramach funkcji wglądu w dane dotyczące interakcji.

## <a name="metric"></a>Metryka

Metryka to policzalna miara danych używana do śledzenia lub oceny procesu. Przykłady odpowiednich metryk to widoki stron i średni czas spędzony w witrynie.

## <a name="refined-event"></a>Zdarzenie opracowane

Zdarzenie opracowane to widok wirtualny zdarzenia podstawowego filtrowany przez określone właściwości danych. Użycie zdarzeń opracowanych w celu uproszczenia zdarzenia podstawowego podczas eksportu lub usunięcia właściwości ze zdarzenia, które nie jest niezbędne do wyeksportowania lub usunięcia.

## <a name="report"></a>Zgłoś

Raport jest zbiorem wizualizacji danych, które ułatwiają oceny i zrozumienia zachowania użytkownika. Funkcja obsługi funkcji analizy interakcji obejmuje kilka wstępnie zdefiniowanych raportów dotyczących projektów sieci Web. Można również tworzyć raporty niestandardowe. 

## <a name="workspace"></a>Obszar roboczy

Obszar roboczy to miejsce do przechowywania zdarzeń i raportów oraz zarządzania nimi. W tym miejscu można wyświetlać działania użytkownika w czasie rzeczywistym. Podczas tworzenia obszaru roboczego wybierasz typ danych przesyłanych do obszaru.


[!INCLUDE[footer-include](../includes/footer-banner.md)]