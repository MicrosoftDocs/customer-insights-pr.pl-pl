---
title: Eksportowanie segmentów do usługi Campaign Monitor (wersja zapoznawcza)
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi Campaign Monitor.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c04fc26dc690cf32b45913257e82b9a0f617185
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196315"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Eksportowanie segmentów do usługi Campaign Monitor (wersja zapoznawcza)

Wyeksportuj segmenty ujednoliconych profilów klientów do usługi Campaign Monitor i użyj ich w działaniach marketingowych.

## <a name="prerequisites"></a>Wymagania wstępne

- Konto [Kontakt administracyjny usługi Campaign Monitor](https://www.campaignmonitor.com/) i odpowiednie dane logowania administratora.
- [Identyfikator listy usługi Campaign Monitor](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- Najpierw [Wygeneruj klucz interfejsu API](https://www.campaignmonitor.com/api/getting-started/) na podstawie **Ustawień klienta** w usłudze Campaign Monitor, aby otrzymać identyfikator listy interfejsów API.
- [Skonfigurowane segmenty](segments.md) w Customer Insights.
- Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- Do 1 miliona profili klientów na eksport do Campaign Monitor, co może zająć do 20 minut. Liczba profilów klientów, które można eksportować do usługi Campaign Monitor, zależy od kontraktu z usługą Campaign Monitor.
- Tylko segmenty.

## <a name="set-up-connection-to-campaign-monitor"></a>Konfiguracja połączenia z usługą Campaign Monitor

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Campaign Monitor**.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Domyślnie – tylko administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Wybierz opcję **Połącz**, aby inicjować połączenie z usługą Campaign Monitor.

1. Wybierz opcję **Uwierzytelnij z usługą Campaign Monitor** i podaj swoje poświadczenia administratora dla usługi Campaign Monitor.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj eksport**, aby utworzyć nowy eksport.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Campaign Monitor. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wpisz nazwę eksportu.

1. Wprowadź swój **Identyfikator listy usługi Campaign Monitor**.

1. W sekcji **Dopasowywanie danych** w polu **E-mail** wybierz pole reprezentujące adres e-mail klienta. Wymagane jest wyeksportowanie segmentów do usługi Campaign Monitor.

1. Wybierz segmenty, które chcesz wyeksportować.

1. Wybierz pozycję **Zapisz**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
