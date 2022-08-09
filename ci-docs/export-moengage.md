---
title: Eksportuj segmenty do rozwiązania MoEngage
description: Dowiedz się, jak skonfigurować połączenie i eksportować do programu MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ffc591c01a5a9434cde41f2da25fa930a515b8c1
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9199154"
---
# <a name="export-segments-to-moengage-preview"></a>Eksportowanie segmentów do programu MoEngage (wersja zapoznawcza)

Eksportuj segmenty ujednoliconych profili klientów do MoEngage i używaj ich do marketingu e-mailowego w MoEngage.

## <a name="prerequisites-for-a-connection"></a>Wymagania wstępne dla połączenia

- [Konto MoEngage](https://www.moengage.com/) i odpowiednie poświadczenia administratora.
- Klucz interfejsu API MoEngage z Ustawienia > API w MoEngage.
- [Skonfigurowane segmenty](segments.md) w Customer Insights.

## <a name="known-limitations"></a>Znane ograniczenia

- Do 100 000 profili klientów na eksport do MoEngage, co może zająć do 15 minut. Liczba profilów klientów, które można eksportować do usługi MoEngage, zależy od kontraktu z usługą MoEngage i jest ograniczona.
- Tylko segmenty.

## <a name="set-up-connection-to-moengage"></a>Skonfiguruj połączenie z usługą MoEngage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **MoEngage**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wpisz swój [identyfikator i klucz API MoEngage Data API](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Wybierz opcję **Połącz**, aby inicjować połączenie z usługą MoEngage.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj eksport**, aby utworzyć nowy eksport.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi MoEngage. Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.

1. W sekcji **Dopasowywanie danych** w polu **E-mail** wybierz pole reprezentujące adres e-mail klienta. Powtórz te same kroki w przypadku innych pól opcjonalnych.

1. Wybierz segmenty, które chcesz wyeksportować. Utworzymy co najmniej jeden segment o tej samej nazwie, co wybrane segmenty w MoEngage w sekcji **Segmenty** > **Segmenty niestandardowe**.

1. Wybierz pozycję **Zapisz**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
