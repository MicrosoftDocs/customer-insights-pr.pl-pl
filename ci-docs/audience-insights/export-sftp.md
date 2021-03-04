---
title: Eksportowanie danych Customer Insights do hostów SFTP
description: Informacje o konfigurowaniu połączenia z hostem SFTP.
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268011"
---
# <a name="connector-for-sftp-preview"></a>Łącznik dla SFTP (wersja zapoznawcza)

Korzystaj z danych klientów w aplikacjach innych firm, eksportując je do hosta Secure File Transfer Protocol (SFTP).

## <a name="prerequisites"></a>Wymagania wstępne

- Dostępność hosta SFTP i odpowiednie poświadczenia.

## <a name="connect-to-sftp"></a>Połącz z usługą SFTP

1. Przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.

1. W **SFTP**, wybierz **Skonfiguruj**.

1. W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej rozpoznawalną nazwę.

1. Wprowadź **Nazwę użytkownika**, **Hasło**, **Nazwę hosta** i **Eksportuj folder** dla konta SFTP.

1. Wybierz **Zweryfikuj**, aby sprawdzić połączenie.

1. Po pomyślnej weryfikacji wybierz, czy chcesz wyeksportować dane **spakowane**, czy **rozpakowane**, i wybierz **ogranicznik pól** dla eksportowanych plików.

1. Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.

1. Wybierz **Dalej**, aby rozpocząć konfigurowanie eksportu.

## <a name="configure-the-export"></a>Skonfiguruj eksport

1. Wybierz encje, na przykład segmenty, które chcesz wyeksportować.

   > [!NOTE]
   > Każda wybrana encja będzie miała do pięciu plików wyjściowych po wyeksportowaniu. 

1. Wybierz pozycję **Zapisz**.

## <a name="export-the-data"></a>Eksportowanie danych

Możesz [eksportować dane na żądanie](export-destinations.md). Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab).

## <a name="known-limitations"></a>Znane ograniczenia

- Czas wykonania eksportu zależy od wydajności systemu. Zalecamy dwa rdzenie procesora i 1 GB pamięci jako minimalną konfigurację serwera. 
- Eksportowanie jednostek z maksymalnie 100 milionami profili klientów może zająć 90 minut przy użyciu zalecanej minimalnej konfiguracji dwóch rdzeni procesora i 1 Gb pamięci. 

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu Dynamics 365 Customer Insights do transmisji danych za pomocą SFTP można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale odpowiadasz za zapewnienie, że miejsce docelowe eksportu spełnia wszelkie Twoje obowiązki w zakresie prywatności lub bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.


[!INCLUDE[footer-include](../includes/footer-banner.md)]