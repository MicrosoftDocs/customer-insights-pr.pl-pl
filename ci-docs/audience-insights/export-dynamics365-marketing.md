---
title: Eksport danych z Customer Insights do Dynamics 365 Marketing
description: Informacje o konfigurowaniu połączenia z Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643786"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Łącznik dla Dynamics 365 Marketing (wersja zapoznawcza)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Za pomocą [segmentów](segments.md) utworzonych w aplikacji Customer Insights możesz generować kampanie oraz nawiązać kontakt z wybranymi grupami klientów w rozwiązaniu Dynamics 365 Marketing. Aby uzyskać więcej informacji, zobacz [Korzystanie z segmentów w Dynamics 365 Customer Insights z Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Warunek wstępny

Rekordy kontaktów [z Dynamics 365 Marketing pozyskane przy użyciu Common Data Service](connect-power-query.md).

## <a name="configure-the-connector-for-marketing"></a>Konfigurowanie łącznika dla modułu Marketing

1. W analizach odbiorców przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.

1. W obszarze **Dynamics 365 Marketing** wybierz **Konfiguruj**.

1. W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej exportu rozpoznawalną nazwę.

1. W polu adres serwera **Adres serwera** wprowadź adres URL modułu Marketing organizacji.

1. W sekcji **Konto Administratora serwera** wybierz **Zaloguj się** i wybierz konto Dynamics 365 Marketing.

1. Zamapuj pole identyfikatora klienta na identyfikator kontaktu Dynamics 365.

1. Wybierz **Dalej**.

1. Wybierz jeden lub więcej segmentów.

1. Wybierz pozycję **Zapisz**.

## <a name="export-the-data"></a>Eksportowanie danych

Możesz [eksportować dane na żądanie](export-destinations.md). Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab).
