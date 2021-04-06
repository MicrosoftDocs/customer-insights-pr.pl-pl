---
title: Eksport danych z Customer Insights do Dynamics 365 Marketing
description: Informacje o konfigurowaniu połączenia z Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597616"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Łącznik dla Dynamics 365 Marketing (wersja zapoznawcza)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Za pomocą [segmentów](segments.md) utworzonych w aplikacji Customer Insights możesz generować kampanie oraz nawiązać kontakt z wybranymi grupami klientów w rozwiązaniu Dynamics 365 Marketing. Aby uzyskać więcej informacji, zobacz [Korzystanie z segmentów w Dynamics 365 Customer Insights z Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Warunek wstępny

- Rekordy kontaktów muszą być obecne w Dynamics 365 Marketing, zanim będzie można wyeksportować segment z Customer Insights do Marketing. Przeczytaj więcej o tym, jak pozyskiwać kontakty w [Dynamics 365 Marketing, używając Common Data Services](connect-power-query.md).

  > [!NOTE]
  > Eksportowanie segmentów ze statystyk odbiorców do Marketingu nie spowoduje utworzenia nowych rekordów kontaktów w wystąpieniach Marketing. Rekordy kontaktów z działu Marketing muszą być pozyskiwane w statystykach odbiorców i używane jako źródło danych. Muszą również zostać uwzględnione w ujednoliconej encji Customer, aby zmapować identyfikatory klientów do identyfikatorów kontaktów, zanim segmenty będą mogły zostać wyeksportowane.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]