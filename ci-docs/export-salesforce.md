---
title: Eksportowanie danych do usługi Salesforce Marketing Cloud (wersja zapoznawcza)
description: Dowiedz się, jak skonfigurować połączenie i wyeksportować je do usługi Salesforce Marketing Cloud.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197051"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Eksportowanie danych do usługi Salesforce Marketing Cloud (wersja zapoznawcza)

Wykorzystaj dane swoich klientów w Salesforce Marketing Cloud, eksportując je za pośrednictwem lokalizacji Secure File Transfer Protocol (SFTP).

## <a name="prerequisites"></a>Wymagania wstępne

- Host [platformy SFTP dla usługi Salesforce Marketing Cloud oraz](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) odpowiednie poświadczenia administratora.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Konfigurowanie połączenia z usługą Salesforce Marketing Cloud

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Salesforce Marketing Cloud**.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Domyślnie – tylko administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wprowadź **Nazwę użytkownika**, **Hasło**, **Nazwę hosta** i **Eksportuj folder** dla konta SFTP.

1. Wybierz **Zweryfikuj**, aby sprawdzić połączenie.

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz opcję **Dodaj eksport**.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji SFTP. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wpisz nazwę eksportu.

1. Określ, czy dane mają być eksportowane po spakowaniu **Gzip**, czy **Niespakowane**, oraz **ogranicznik pola** dla eksportowanych plików.

1. Wybierz encje, na przykład segmenty, które chcesz wyeksportować.

   > [!NOTE]
   > Po wyeksportowaniu każda wybrana encja zostanie podzielona na maksymalnie pięć plików wyjściowych.

1. Wybierz pozycję **Zapisz**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Import danych Customer Insights z lokalizacji SFTP do Salesforce Marketing Cloud

1. Utwórz [rozszerzenia danych w Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5), aby zaimportować plik danych Customer Insights z lokalizacji SFTP.

2. [Import danych z lokalizacji SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) do rozszerzenia danych Salesforce Marketing Cloud.

3. Skonfiguruj automatyzację do importu danych do rozszerzeń danych. Dowiedz się więcej o [automatyzacji przesyłania plików i planowanych zadaniach automatyzacji](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Zdefiniuj [automatyzację przesyłania plików](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) lub [zaplanowane zadania automatyzacji](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

Oto przykład [automatyzacji SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
