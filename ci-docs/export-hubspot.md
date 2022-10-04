---
title: Eksportowanie danych Customer Insights do usługi HubSpot
description: Dowiedz się, jak skonfigurować połączenie i wyeksportować je do usługi HubSpot.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0281be288b2c4d9e5da7ad8e2ed25f7b51b8498e
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588912"
---
# <a name="export-segments-to-hubspot-preview"></a>Eksportowanie segmentów do programu HubSpot (wersja zapoznawcza)

Eksportuj segmenty ujednoliconych profili klientów do HubSpot i wykorzystuj je do e-mail marketingu.

## <a name="prerequisites-for-a-connection"></a>Wymagania wstępne dla połączenia

- Użytkownik ma [konto usługi HubSpot](https://www.hubspot.com/) i odpowiadające mu poświadczenia administratora.
- [Klucz interfejsu API](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) z centrum HubSpot.
- [Skonfigurowane segmenty](segments.md) w Customer Insights.

## <a name="known-limitations"></a>Znane ograniczenia

- Do 100 000 profili klientów na eksport do HubSpot, co może zająć do 15 minut. Liczba profilów klientów, które można eksportować do usługi HubSpot, zależy od kontraktu z usługą HubSpot i jest ograniczona.
- Tylko segmenty.

## <a name="set-up-connection-to-hubspot"></a>Skonfiguruj połączenie z usługą HubSpot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **HubSpot**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Po wyświetleniu monitu wprowadź swoje dane uwierzytelniające HubSpot.

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Wybierz opcję **Połącz**, aby inicjować połączenie z usługą HubSpot.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj eksport**, aby utworzyć nowy eksport.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi HubSpot. Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.

1. W sekcji **Dopasowywanie danych** w polu **E-mail** wybierz pole reprezentujące adres e-mail klienta. Powtórz te same kroki w przypadku innych pól opcjonalnych.

1. Wybierz segmenty, które chcesz wyeksportować.

1. Wybierz pozycję **Zapisz**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
