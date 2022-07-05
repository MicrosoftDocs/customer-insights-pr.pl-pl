---
title: Eksportowanie danych do usługi Salesforce Marketing Cloud (wersja zapoznawcza)
description: Dowiedz się, jak skonfigurować połączenie i wyeksportować je do usługi Salesforce Marketing Cloud.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c3a6a40d9b9f08c8ebca8cb4a9196a1a79f03afa
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081465"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Eksportowanie danych do usługi Salesforce Marketing Cloud (wersja zapoznawcza)

Wykorzystaj dane swoich klientów w Salesforce Marketing Cloud, eksportując je za pośrednictwem lokalizacji Secure File Transfer Protocol (SFTP).

## <a name="prerequisites-for-connection"></a>Wymagania wstępne dla połączenia

- Dostępność hosta SFTP i odpowiednich danych uwierzytelniających administratora. [Jak skonfigurować lokalizacje platformy SFTP dla usługi Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Konfigurowanie połączenia z usługą Salesforce Marketing Cloud

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Salesforce Marketing Cloud**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wprowadź **Nazwę użytkownika**, **Hasło**, **Nazwę hosta** i **Eksportuj folder** dla konta SFTP.

1. Wybierz **Zweryfikuj**, aby sprawdzić połączenie.

1. Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji SFTP. Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.

1. Określ, czy dane mają być eksportowane po spakowaniu **Gzip**, czy **Niespakowane**, oraz **ogranicznik pola** dla eksportowanych plików.

1. Wybierz encje, na przykład segmenty, które chcesz wyeksportować.

   > [!NOTE]
   > Po wyeksportowaniu każda wybrana encja zostanie podzielona na maksymalnie pięć plików wyjściowych. 

1. Wybierz pozycję **Zapisz**.

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab). Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Import danych Customer Insights z lokalizacji SFTP do Salesforce Marketing Cloud

1. Utwórz [rozszerzenia danych w Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5), aby zaimportować plik danych Customer Insights z lokalizacji SFTP.

2. [Import danych z lokalizacji SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) do rozszerzenia danych Salesforce Marketing Cloud. 

3. Skonfiguruj automatyzację do importu danych do rozszerzeń danych. Dowiedz się więcej o [automatyzacji przesyłania plików i planowanych zadaniach automatyzacji](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Zdefiniuj [automatyzację przesyłania plików](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) lub [zaplanowane zadania automatyzacji](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

Oto przykład [automatyzacji SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu Dynamics 365 Customer Insights do transmisji danych za pomocą SFTP można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale odpowiadasz za zapewnienie, że miejsce docelowe eksportu spełnia wszelkie Twoje obowiązki w zakresie prywatności lub bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.

[!INCLUDE [footer-include](includes/footer-banner.md)]
