---
title: Uprawnienia i role
description: Omówienie dostępnych ról i uprawnień członków obszaru roboczego.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 07/06/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6d7f4db4a130fc15a69b380c892538db5492d96d8e13f3c070c6a6b9bd098371
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036706"
---
# <a name="roles-and-permissions"></a>Uprawnienia i role

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Obszar roboczy to miejsce do przechowywania zdarzeń i raportów oraz zarządzania nimi. Członek obszaru roboczego to użytkownik, który ma dostęp do obszaru roboczego. Członków można przypisać do obszaru roboczego oraz zdefiniować ich role i uprawnienia. Role administratora zarządzają obszarami roboczymi i środowiskami i konfigurują szczegółowe informacje o zaangażowaniu dla innych użytkowników. Role współautora są skierowane do analityków, którzy nie muszą konfigurować szczegółowych informacji o zaangażowaniu, ale chcą tworzyć własne raporty, ścieżki lub segmenty.

## <a name="permissions"></a>Uprawnienia
  
Na poniższym wykresie podano uprawnienia każdej roli. 

| Uprawnienie | Administrator środowiska | Administrator obszaru roboczego | Współautor środowiska | Współautor obszaru roboczego | 
|--|--|--|--|--|
| Tworzenie środowisk (twórca automatycznie staje się administratorem środowiska) | X* | X* | X* | X* |  
| Konfigurowanie środowiska (członkowie środowiska, usuwanie środowiska) | X |  |  |  |  
| Tworzenie obszarów roboczych | X |  |  |  |  
| Konfigurowanie obszarów roboczych (elementy członkowskie obszaru roboczego, usuwanie obszaru roboczego) | X | X |  |  |  
| Konfigurowanie zdarzeń i zdarzenia opracowane | X | X | |  |  
| Wyświetlanie zdarzeń obszaru roboczego i zdarzeń opracowanych | X | X | |  |  
| Wyświetlanie zasobów obszaru roboczego (raporty, segmenty i metryka)| X | X | X | X |  
| Utwórz raporty niestandardowe i ścieżki | X | X | X | X |  
| Utwórz metryki podstawowe i wymiary| X | X |  |  |  
| Utwórz segmenty| X | X | X | X |  

*Środowiska próbne można tworzyć tylko w wersji zapoznawczej. 

## <a name="add-members"></a>Dodaj członków

Członków można dodawać i usuwać z obszarów roboczych i środowisk. Aby uzyskać więcej informacji, zobacz temat [Środowiska i obszary robocze](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
