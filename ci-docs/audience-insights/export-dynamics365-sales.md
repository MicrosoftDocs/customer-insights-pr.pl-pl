---
title: Eksport danych z Customer Insights do Dynamics 365 Sales
description: Informacje o konfigurowaniu połączenia z Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643831"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Łącznik dla Dynamics 365 Sales (wersja zapoznawcza)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Używając danych klientów, możesz tworzyć listy marketingowe oraz przepływy pracy kolejnych czynności, a także wysyłać materiały promocyjne z poziomu rozwiązania Dynamics 365 Sales.

## <a name="prerequisite"></a>Warunek wstępny

Rekordy kontaktów [z Dynamics 365 Sales pozyskane przy użyciu Common Data Service](connect-power-query.md).

## <a name="configure-the-connector-for-sales"></a>Konfigurowanie łącznika do modułu Sales

1. W analizach odbiorców przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.

1. W obszarze **Dynamics 365 Sales** wybierz **Konfiguruj**.

1. W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej exportu rozpoznawalną nazwę.

1. W polu adres serwera **Adres serwera** wprowadź adres URL modułu Sales organizacji.

1. W sekcji **Konto Administratora serwera** wybierz **Zaloguj się** i wybierz konto Dynamics 365 Sales.

1. Zamapuj pole identyfikatora klienta na identyfikator kontaktu Dynamics 365.

1. Wybierz **Dalej**.

1. Wybierz jeden lub więcej segmentów.

1. Wybierz pozycję **Zapisz**.

## <a name="export-the-data"></a>Eksportowanie danych

Możesz [eksportować dane na żądanie](export-destinations.md). Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab).
