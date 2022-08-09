---
title: Eskportowanie segmentów do rozwiązania Dynamics 365 Marketing (wersja zapoznawcza)
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi Dynamics 365 Marketing.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196637"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Eskportowanie segmentów do rozwiązania Dynamics 365 Marketing (wersja zapoznawcza)

Za pomocą [segmentów](segments.md) utworzonych w aplikacji Customer Insights możesz generować kampanie oraz nawiązać kontakt z wybranymi grupami klientów w rozwiązaniu [Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Jeśli używasz nowych funkcji usługi Dynamics 365 Marketing w celu aranżacji pozyskiwanie klientów w organizacji Dataverse, nie trzeba tworzyć standardowych eksportów do usługi Dynamics 365 Marketing. Kontakty i segmenty danych z usługi Customer Insights są dostępne bezpośrednio w usłudze Dynamics 365 Marketing po połączeniu z usługą Marketing i Customer Insights. Przed usunięciem istniejących eksportów należy zapoznać się z dokumentacją dotyczącą [łączenia rozwiązania Customer Insights i orkiestracji pozyckiwania klientów usługi Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>Warunek wstępny

Rekordy kontaktów muszą być obecne w Dynamics 365 Marketing, zanim będzie można wyeksportować segment z Customer Insights do Marketing. Przeczytaj więcej o tym, jak pozyskiwać kontakty w [Dynamics 365 Marketing, używając Microsoft Dataverse](connect-dataverse-managed-lake.md).

> [!NOTE]
> Wyeksportowanie segmentów z usługi Customer Insights do Marketing nie spowoduje utworzenia nowych rekordów kontaktów w wystąpieniach Marketing. Rekordy kontaktów z usługi Marketing muszą być używane w programie Customer Insights i używane jako źródło danych. Muszą również zostać uwzględnione w ujednoliconej encji Customer, aby zmapować identyfikatory klientów do identyfikatorów kontaktów, zanim segmenty będą mogły zostać wyeksportowane.

## <a name="set-up-connection-to-marketing"></a>Skonfiguruj połączenie z usługą Marketing

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Dynamics 365 Marketing**.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Domyślnie – tylko administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. W polu adres serwera **Adres serwera** wprowadź adres URL modułu Marketing organizacji.

1. W sekcji **Konto Administratora serwera** wybierz **Zaloguj się** i wybierz konto Dynamics 365 Marketing.

1. Zamapuj pole Identyfikator kontaktu w encji Klient na identyfikator kontaktu usługi Dynamics 365.

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz opcję **Dodaj eksport**.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Dynamics 365 Marketing. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wpisz nazwę eksportu.

1. Wybierz pole Identyfikator kontaktu w encji Klient, które odpowiada identyfikatorowi kontaktu Dynamics 365.

1. Wybierz segmenty, które chcesz wyeksportować.

1. Wybierz pozycję **Zapisz**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
