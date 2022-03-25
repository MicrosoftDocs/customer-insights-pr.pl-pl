---
title: Eksport danych z Customer Insights do Dynamics 365 Sales
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 4c1b5eaa3568b5c73013024d2da7e65276142f72
ms.sourcegitcommit: d168a738a08adb8b4b2e410bdaa3716d7b63cc9b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/17/2022
ms.locfileid: "8455875"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a>Używanie segmentów w usłudze Dynamics 365 Sales (wersja zapoznawcza)



Używając danych klientów, możesz tworzyć listy marketingowe oraz przepływy pracy kolejnych czynności, a także wysyłać materiały promocyjne z poziomu rozwiązania Dynamics 365 Sales.

## <a name="known-limitations"></a>Znane ograniczenia

- Operacje eksportu do aplikacji Dynamics 365 Sales są ograniczone do 100 000 członków na segment.
- Operacje eksportu segmentów do aplikacji Dynamics 365 Sales mogą potrwać do 3 godzin. 

## <a name="prerequisite-for-connection"></a>Wymaganie wstępne dla połączenia

1. Rekordy kontaktów muszą być obecne w Dynamics 365 Sales, zanim będzie można wyeksportować segment z Customer Insights do Sales. Przeczytaj więcej o tym, jak pozyskiwać kontakty z [Dynamics 365 Sales przy użyciu Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > Eksportowanie segmentów ze statystyk odbiorców do Sales nie spowoduje utworzenia nowych rekordów kontaktów w wystąpieniach Sales. Rekordy kontaktów z działu Sales muszą być pozyskiwane w statystykach odbiorców i używane jako źródło danych. Muszą również zostać uwzględnione w ujednoliconej encji Customer, aby zmapować identyfikatory klientów do identyfikatorów kontaktów, zanim segmenty będą mogły zostać wyeksportowane.

## <a name="set-up-the-connection-to-sales"></a>Skonfiguruj połączenie z usługą Sales

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Dynamics 365 Sales**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. W polu adres serwera **Adres serwera** wprowadź adres URL modułu Sales organizacji.

1. W sekcji **Konto Administratora serwera** wybierz **Zaloguj się** i wybierz konto Dynamics 365 Sales.

1. Zamapuj pole identyfikatora klienta na identyfikator kontaktu Dynamics 365.

1. Aby zakończyć połączenie, wybierz **Zapisz**. 

## <a name="configure-an-export"></a>Konfigurowanie eksportu

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Dynamics 365 Sales. Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.

1. Wybierz jeden lub więcej segmentów.

1. Wybierz pozycję **Zapisz**

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab). Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
