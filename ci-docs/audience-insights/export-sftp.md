---
title: Eksportuj dane Customer Insights na serwer SFTP (zawiera wideo)
description: Dowiedz się, jak skonfigurować połączenie i eksport do lokalizacji SFTP.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7b09da093d6332c5081da1beadc1df59f63c31d2
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231167"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a>Eksportowanie segmentów i innych danych do SFTP (wersja zapoznawcza)

Danych klientów można używać w aplikacjach innych firm, eksportując je do lokalizacji bezpiecznego protokołu transferu plików (SFTP).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites-for-connection"></a>Wymagania wstępne dla połączenia

- Dostępność hosta SFTP i odpowiednie poświadczenia.

## <a name="known-limitations"></a>Znane ograniczenia

- Miejsca docelowe SFTP za zaporami nie są obecnie obsługiwane. 
- Czas wykonania eksportu zależy od wydajności systemu. Zalecamy dwa rdzenie procesora i 1 GB pamięci jako minimalną konfigurację serwera. 
- Eksportowanie jednostek z maksymalnie 100 milionami profili klientów może zająć 90 minut przy użyciu zalecanej minimalnej konfiguracji dwóch rdzeni procesora i 1 Gb pamięci. 

## <a name="set-up-connection-to-sftp"></a>Konfiguruj połączenie z SFTP

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **SFTP**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wprowadź **Nazwę użytkownika**, **Hasło**, **Nazwę hosta** i **Eksportuj folder** dla konta SFTP.

1. Wybierz **Zweryfikuj**, aby sprawdzić połączenie.

1. Określ, czy dane mają być eksportowane po spakowaniu **Gzip**, czy **Niespakowane**, oraz **ogranicznik pola** dla eksportowanych plików.

1. Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji SFTP. Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.

1. Wybierz encje, na przykład segmenty, które chcesz wyeksportować.

   > [!NOTE]
   > Po wyeksportowaniu każda wybrana encja zostanie podzielona na maksymalnie pięć plików wyjściowych. 

1. Wybierz pozycję **Zapisz**.

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab). Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu Dynamics 365 Customer Insights do transmisji danych za pomocą SFTP można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale odpowiadasz za zapewnienie, że miejsce docelowe eksportu spełnia wszelkie Twoje obowiązki w zakresie prywatności lub bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
