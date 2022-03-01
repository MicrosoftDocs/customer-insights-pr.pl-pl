---
title: Włączanie gotowych raportów profili
description: Jak tworzyć gotowe raporty profilowe pogrupowane według płci, wieku oraz hrabstwa lub regionu pochodzenia.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 3aa9599fc780098a2f7f31f0210d76ed2ef27ece774dd6212b5cb2a599ad537e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033965"
---
# <a name="out-of-box-profile-reports"></a>Gotowe raporty profili

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Raport jest zbiorem wizualizacji danych, które ułatwiają oceny i zrozumienia zachowania użytkownika. Dzięki połączeniu z usługą analizy odbiorców Customer Insights, analiza interakcji może pokazywać raporty z informacjami o ujednoliconych profilach klientów. Ten raport zawiera liczbę posiadanych profilów pogrupowane według wieku, wieku i położenia geograficznego.

## <a name="prerequisites"></a>Wymagania wstępne

Środowisko analizy odbiorców musi przechowywać dane w koncie zarządzanym przez konto Azure Data Lake Storage.

W przypadku korzystania z wersji próbnej oprogramowania analizy odbiorców lub środowiska z Customer Insights zarządzanym przez data lake [skontaktuj się z nami](https://go.microsoft.com/fwlink/?linkid=2145734), aby uzyskać pomoc.  


## <a name="enable-the-customer-profile-report"></a>Włączanie raportu o profilu klienta

Administrator środowiska musi [utworzyć połączenie z analizą odbiorców](configure-connections.md).

Po określeniu szczegółów połączenia administrator może przyznać dostęp do innych osób w organizacji, aby zobaczyć raport. Administrator środowiska konfigurujący połączenie ma automatycznie dostęp do raportu profilu klienta. 

Po zakończeniu połączenia funkcja **Profile** będzie dostępna w lewym okienku nawigacji. 

- Aby wyświetlić raport o profilach klientów, przejdź do **Odkrywaj** > **Profile**.

Raport **Profile** zawiera wizualizacje dotyczące lokalizacji, wieku i położenia geograficznego połączonych profilów klientów.

:::image type="content" source="media/customer-profiles.png" alt-text="Raport profilu klienta.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]