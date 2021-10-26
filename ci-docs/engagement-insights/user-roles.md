---
title: Uprawnienia i role
description: Omówienie dostępnych ról i uprawnień członków obszaru roboczego.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e28caf1c14c23acd506da5f7b441f1e3b72e8b
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645550"
---
# <a name="roles-and-permissions"></a>Uprawnienia i role

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Obszar roboczy to miejsce do przechowywania zdarzeń i raportów oraz zarządzania nimi. Aby uzyskać więcej informacji, zobacz temat [Tworzenie obszaru roboczego i dodawanie członków](create-workspace.md). 

Obszar roboczy może zawierać następujące role i uprawnienia:

- Role *Członek* to użytkownicy, którzy mają dostęp do obszaru roboczego. Członków można przypisać do obszaru roboczego oraz zdefiniować ich role i uprawnienia. 
- Role *Administrator* zarządzają obszarami roboczymi i środowiskami i konfigurują szczegółowe informacje o zaangażowaniu dla innych użytkowników. 
- Role *Współautor* zabezpieczeń są nakierowane na analityków, którzy nie muszą konfigurować wyników analiz interakcji, ale chcą tworzyć własne raporty, lejki lub segmenty.

## <a name="permissions"></a>Uprawnienia
  
W poniższej tabeli zidentyfikowano uprawnienia dla każdej roli. 

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
