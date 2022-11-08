---
title: Eksportowanie segmentów do usługi Google Ads (wersja zapoznawcza)
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi Google Ads.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a46623e609665f8031f223593a6644147e5209d8
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725091"
---
# <a name="export-segments-to-google-ads-preview"></a>Eksportowanie segmentów do usługi Google Ads (wersja zapoznawcza)

Wyeksportuj segmenty ujednoliconych profili klientów do listy odbiorców Google Ads i wykorzystaj je do reklam w wyszukiwarce Google, poczcie Gmail, serwisie YouTube i sieci reklamowej Google Display Network.

## <a name="prerequisites"></a>Wymagania wstępne

- [Konto usługi Google Ads](https://ads.google.com/) i odpowiadające mu poświadczenia administratora.
- [Identyfikator klienta usługi Google Ads](https://support.google.com/google-ads/answer/1704344).
- Spełnione są wymagania [zasad Customer Match](https://support.google.com/adspolicy/answer/6299717).
- Spełnione są wymagania [rozmiarów list marketingowych](https://support.google.com/google-ads/answer/7558048).
- [Skonfigurowane segmenty](segments.md).
- Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pola reprezentujące adres e-mail, telefon, identyfikator reklamodawcy mobilnego, identyfikator użytkownika innej firmy lub adres.

## <a name="known-limitations"></a>Znane ograniczenia

- Link prywatny w połączeniu z opcją BYOS (Bring your owne storage) nie jest obsługiwany.
- Eksportuj do 1 miliona profili klientów na eksport do Google Ads, co może potrwać do 30 minut ze względu na ograniczenia po stronie dostawcy.
- Tylko segmenty.
- Dopasowanie w usłudze Google Ads może potrwać do 48 godzin.

## <a name="set-up-connection-to-google-ads"></a>Konfiguruj połączenie z usługą Google Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Google Ads**.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Domyślnie – tylko administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wpisz Identyfikator klienta usługi Google Ads.

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Wybierz **Uwierzytelnianie za pomocą usługi Google Ads** i przekaż swoje poświadczenia w usłudze Google AD.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz opcję **Dodaj eksport**.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Google Ads. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wpisz nazwę eksportu.

1. Wybierz, czy chcesz użyć istniejącej listy odbiorców, czy utworzyć nową:
   - Aby zaktualizować istniejące reklamy Google odbiorcy, wprowadź swój [identyfikator odbiorcy Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns).
   - Aby utworzyć nową grupę odbiorców, pozostaw pole identyfikatora odbiorców Google puste. Customer Insights automatycznie utworzy nowy adres odbiorcy koncie Google Ads i użyjemy nazwy wyeksportowanego segmentu.

1. W sekcji **Dopasowywanie danych** wybierz co najmniej jedno pole danych do wyeksportowania i wybierz pole reprezentujące odpowiednie pola danych w obszarze Customer Insights.

1. Wybierz segmenty, które chcesz wyeksportować.

1. Wybierz pozycję **Zapisz**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
