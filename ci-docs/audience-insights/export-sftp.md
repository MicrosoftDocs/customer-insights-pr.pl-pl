---
title: Eksportowanie danych Customer Insights do hostów SFTP
description: Informacje o konfigurowaniu połączenia z hostem SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643516"
---
# <a name="connector-for-sftp-preview"></a>Łącznik dla SFTP (wersja zapoznawcza)

Korzystaj z danych klientów w aplikacjach innych firm, eksportując je do hosta Secure File Transfer Protocol (SFTP).

## <a name="prerequisites"></a>Wymagania wstępne

- Dostępność hosta SFTP i odpowiednich poświadczeń.

## <a name="connect-to-sftp"></a>Połącz z SFTP

1. Przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.

1. W **SFTP**, wybierz **Skonfiguruj**.

1. W polu **Wyświetlana nazwa** nadaj lokalizacji docelowej rozpoznawalną nazwę.

1. Wprowadź **Nazwę użytkownika**, **Hasło** i **Nazwę hosta** dla konta SFTP. Przykład: jeśli folder główny serwera SFTP to /root/folder i chcesz, aby dane zostały wyeksportowane do /root/folder/ci_export_destination_folder, hostem powinien być sftp://<server_address>/ci_export_destination_folder".

1. Wybierz **Zweryfikuj**, aby sprawdzić połączenie.

1. Po pomyślnej weryfikacji wybierz, czy chcesz eksportować dane **Spakowane** lub **Niespakowane**, i wybierz **ogranicznik pola** dla eksportowanych plików.

1. Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.

1. Wybierz **Dalej**, aby rozpocząć konfigurowanie eksportu.

## <a name="configure-the-connection"></a>Konfigurowanie połączenia

1. Wybierz **atrybuty klienta**, które chcesz eksportować. Istnieje możliwość wyeksportowania jednego lub wielu atrybutów.

1. Wybierz **Dalej**.

1. Wybierz segmenty, które chcesz wyeksportować.

1. Wybierz pozycję **Zapisz**.

## <a name="export-the-data"></a>Eksportowanie danych

Możesz [eksportować dane na żądanie](export-destinations.md). Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu Dynamics 365 Customer Insights do transmisji danych za pomocą SFTP można przesyłać dane spoza granicy zgodności dla Dynamics 365 Customer Insights, w tym również dane osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale odpowiadasz za zapewnienie, że miejsce docelowe eksportu spełnia wszelkie Twoje obowiązki w zakresie prywatności lub bezpieczeństwa. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.
