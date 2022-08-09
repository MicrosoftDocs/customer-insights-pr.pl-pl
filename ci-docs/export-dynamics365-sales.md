---
title: Eskportowanie segmentów do rozwiązania Dynamics 365 Sales (wersja zapoznawcza)
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi Dynamics 365 Sales.
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
ms.openlocfilehash: c3497f4625cada49ae33c6987e58994a15536f9b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195994"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Eskportowanie segmentów do rozwiązania Dynamics 365 Sales (wersja zapoznawcza)

Używając danych klientów, możesz tworzyć listy marketingowe oraz przepływy pracy kolejnych czynności, a także wysyłać materiały promocyjne z poziomu rozwiązania Dynamics 365 Sales.

## <a name="prerequisites"></a>Wymagania wstępne

Rekordy kontaktów muszą być obecne w Dynamics 365 Sales, zanim będzie można wyeksportować segment z Customer Insights do Sales. Przeczytaj więcej o tym, jak pozyskiwać kontakty z [Dynamics 365 Sales przy użyciu Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > Wyeksportowanie segmentów z usługi Customer Insights do Sales nie spowoduje utworzenia nowych rekordów kontaktów w wystąpieniach Sales. Rekordy kontaktów z usługi Sales muszą być używane w programie Customer Insights i używane jako źródło danych. Muszą również zostać uwzględnione w ujednoliconej encji Customer, aby zmapować identyfikatory klientów do identyfikatorów kontaktów, zanim segmenty będą mogły zostać wyeksportowane.

## <a name="known-limitations"></a>Znane ograniczenia

Eksport do Dynamics 365 Sales jest ograniczony do 100 000 na segment, co może zająć do 3 godzin.

## <a name="set-up-connection-to-sales"></a>Skonfiguruj połączenie z usługą Sales

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Dynamics 365 Sales**.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Domyślnie – tylko administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. W polu adres serwera **Adres serwera** wprowadź adres URL modułu Sales organizacji.

1. W sekcji **Konto Administratora serwera** wybierz **Zaloguj się** i wybierz konto Dynamics 365 Sales.

1. Zamapuj pole identyfikatora klienta na identyfikator kontaktu Dynamics 365.

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz opcję **Dodaj eksport**.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Dynamics 365 Sales. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wpisz nazwę eksportu.

1. Wybierz pole Identyfikator kontaktu w encji Klient, które odpowiada identyfikatorowi kontaktu Dynamics 365.

1. Wybierz segmenty, które chcesz wyeksportować.

1. Wybierz pozycję **Zapisz**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
