---
title: Eksport danych z Customer Insights do Dynamics 365 Marketing
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi Dynamics 365 Marketing.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b8e63a738abaf4fbb902e3edbf83f5a815978478
ms.sourcegitcommit: 8e89575fe2acb4b289fc157fa7c4c29caf9be967
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/24/2021
ms.locfileid: "7417218"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Używanie segmentów w usłudze Dynamics 365 Marketing (wersja zapoznawcza)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Za pomocą [segmentów](segments.md) utworzonych w aplikacji Customer Insights możesz generować kampanie oraz nawiązać kontakt z wybranymi grupami klientów w rozwiązaniu Dynamics 365 Marketing. Aby uzyskać więcej informacji, zobacz [Korzystanie z segmentów w Dynamics 365 Customer Insights z Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Jeśli używasz nowych funkcji usługi Dynamics 365 Marketing w celu aranżacji pozyskiwanie klientów w organizacji Dataverse, nie trzeba tworzyć standardowych eksportów do usługi Dynamics 365 Marketing. Kontakty i segmenty wyników analiz odbiorców są dostępne bezpośrednio w usłudze Dynamics 365 Marketing po połączeniu z programem Marketing i Customer Insights. Przed usunięciem istniejących eksportów należy zapoznać się z dokumentacją dotyczącą [łączenia wyników analiz odbiorców i aranżacji pozyskiwania klientów usługi Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>Wymaganie wstępne dla połączenia

- Rekordy kontaktów muszą być obecne w Dynamics 365 Marketing, zanim będzie można wyeksportować segment z Customer Insights do Marketing. Przeczytaj więcej o tym, jak pozyskiwać kontakty w [Dynamics 365 Marketing, używając Microsoft Dataverse](connect-power-query.md).

  > [!NOTE]
  > Eksportowanie segmentów ze statystyk odbiorców do Marketingu nie spowoduje utworzenia nowych rekordów kontaktów w wystąpieniach Marketing. Rekordy kontaktów z działu Marketing muszą być pozyskiwane w statystykach odbiorców i używane jako źródło danych. Muszą również zostać uwzględnione w ujednoliconej encji Customer, aby zmapować identyfikatory klientów do identyfikatorów kontaktów, zanim segmenty będą mogły zostać wyeksportowane.

## <a name="set-up-connection-to-marketing"></a>Skonfiguruj połączenie z usługą Marketing

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Dynamics 365 Marketing**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. W polu adres serwera **Adres serwera** wprowadź adres URL modułu Marketing organizacji.

1. W sekcji **Konto Administratora serwera** wybierz **Zaloguj się** i wybierz konto Dynamics 365 Marketing.

1. Zamapuj pole identyfikatora klienta na identyfikator kontaktu Dynamics 365.

1. Aby zakończyć połączenie, wybierz **Zapisz**. 

## <a name="configure-an-export"></a>Konfigurowanie eksportu

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Dynamics 365 Marketing. Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.

1. Wybierz jeden lub więcej segmentów.

1. Wybierz pozycję **Zapisz**.

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab). Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
