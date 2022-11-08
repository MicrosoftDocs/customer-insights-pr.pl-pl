---
title: Eksportowanie segmentów do ActiveCampaign
description: Dowiedz się, jak skonfigurować połączenie i wyeksportować je do usługi ActiveCampaign.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e62888a6d618fb1154890e607d8c23d3767d35f7
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725413"
---
# <a name="export-segments-to-activecampaign-preview"></a>Eksportowanie segmentów do ActiveCampaign (wersja zapoznawcza)

Eksportuj segmenty ujednoliconych profili klientów do ActiveCampaign i wykorzystaj je w działaniach marketingowych.

## <a name="prerequisites"></a>Wymagania wstępne

- Konto [ActiveCampaign](https://www.activecampaign.com/) i odpowiednie uprawnienia administratora.
- [Identyfikator listy usługi ActiveCampaign](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).
- [Klucz interfejsu API ActiveCampaign i nazwę hosta REST punktu końcowego](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).
- [Skonfigurowane segmenty](segments.md) w Customer Insights.
- Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- Link prywatny w połączeniu z opcją BYOS (Bring your owne storage) nie jest obsługiwany.
- Do 1 miliona profili klientów na eksport do ActiveCampaign, co może zająć do 90 minut. Liczba profilów klientów, które można eksportować do usługi ActiveCampaign, zależy od kontraktu z usługą ActiveCampaign i jest ograniczona.
- Tylko segmenty.

## <a name="set-up-connection-to-activecampaign"></a>Skonfiguruj połączenie z aplikacjami usługi ActiveCampaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **ActiveCampaign**.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Domyślnie – tylko administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wprowadź klucz interfejsu API ActiveCampaign i nazwę hosta REST punktu końcowego. Nazwa hosta punktu końcowego REST jest tylko nazwą hosta, bez https://.

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Wybierz opcję **Połącz**, aby zainicjować połączenie.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz opcję **Dodaj eksport**.

1. W polu **Połączenie do eksportu** wybierz połączenie z sekcji ActiveCampaign. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wpisz nazwę eksportu.

1. Wprowadź **Identyfikator listy usługi ActiveCampaign**.

1. W sekcji **Dopasowywanie danych** w polu **E-mail** wybierz pole reprezentujące adres e-mail klienta.

1. Opcjonalnie możesz wyeksportować **Imię**, **Nazwisko** i **Telefon**, aby stworzyć bardziej spersonalizowane wiadomości e-mail. Wybierz opcję **Dodaj atrybut**, aby zamapować te pola.

1. Wybierz segmenty, które chcesz wyeksportować.

1. Wybierz pozycję **Zapisz**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
