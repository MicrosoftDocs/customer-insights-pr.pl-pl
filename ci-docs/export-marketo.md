---
title: Eksportowanie segmentów do programu Marketo (wersja zapoznawcza)
description: Dowiedz się, jak skonfigurować połączenie i eksport do programu Marketo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f57cdfbb24df8a8ffa1670b426d50dbba2c5f40f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195257"
---
# <a name="export-segments-to-marketo-preview"></a>Eksportowanie segmentów do programu Marketo (wersja zapoznawcza)

Eksportuj segmenty ujednoliconych profili klientów w celu generowania kampanii, prowadzenia marketingu e-mailowego i korzystania z określonych grup klientów w Marketo.

## <a name="prerequisites"></a>Wymagania wstępne

- [Konto usługi Marketo](https://login.marketo.com/) i odpowiadające mu poświadczenia administratora.
- [Identyfikator klienta Marketo, klucz tajny klienta i nazwa hosta punktu końcowego REST](https://developers.marketo.com/rest-api/authentication/).
- [Istniejące listy w Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) i odpowiednie identyfikatory.
- [Skonfigurowane segmenty](segments.md).
- Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- Do 1 miliona profili klientów na eksport do Marketo, co może zająć do 3 godzin. Liczba profilów klientów, które można eksportować do usługi Marketo, zależy od kontraktu z usługą Marketo.
- Tylko segmenty.

## <a name="set-up-connection-to-marketo"></a>Skonfiguruj połączenie z usługą Marketo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Marketo**.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Domyślnie – tylko administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wprowadź **Identyfikator klienta Marketo, klucz tajny klienta i nazwa hosta punktu końcowego REST**. Nazwa hosta punktu końcowego REST jest tylko nazwą hosta, bez https://. Przykład: xyz-abc-123.mktorest.com.

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Wybierz opcję **Połącz**, aby zainicjować połączenie.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz opcję **Dodaj eksport**.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Marketo. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wpisz nazwę eksportu.

1. Wprowadź **Identyfikator listy Marketo**. Identyfikator listy jest wartością wyłącznie numeryczną. Jeśli na przykład identyfikator listy Marketo to ST12345A7, usuń znak przed i po liczbach, a następnie wprowadź *12345*.

1. W sekcji **Dopasowywanie danych** wybierz co najmniej jedno pole reprezentujące adres e-mail klienta lub identyfikator Marketo klienta.

1. Opcjonalnie możesz wyeksportować **Imię**, **Nazwisko**, **Miejscowość**, **Województwo** i **Kraj/region**, aby utworzyć bardziej spersonalizowane wiadomości e-mail. Wybierz opcję **Dodaj atrybut**, aby zamapować te pola.

1. Wybierz segmenty, które chcesz wyeksportować.

1. Wybierz pozycję **Zapisz**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

W programie Marketo można znaleźć segmenty na [listach Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

[!INCLUDE [footer-include](includes/footer-banner.md)]
