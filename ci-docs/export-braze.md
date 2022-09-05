---
title: Eksportowanie segmentów do Braze (wersja zapoznawcza)
description: Dowiedz się, jak skonfigurować połączenie i eksportować do programu Braze.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 84dc7f13f30e0334d431fe5b5866c7f87e82ab27
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195120"
---
# <a name="export-segments-to-braze-preview"></a>Eksportowanie segmentów do Braze (wersja zapoznawcza)

Eksportuj segmenty ujednoliconych profili klientów do Braze i wykorzystuj je do działań marketingowych.

## <a name="prerequisites"></a>Wymagania wstępne

- [Konto Braze](https://www.braze.com/) i odpowiednie poświadczenia administratora.
- [Klucz interfejsu API braze](https://www.braze.com/docs/api/basics/)
- [Skonfigurowane segmenty](segments.md) w Customer Insights.
- Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail i identyfikator klienta Braze.

## <a name="known-limitations"></a>Znane ograniczenia

- Przenieś milion profili klientów do Braze, co może zająć do 40 minut. Liczba profilów klientów, które można eksportować do usługi Braze, zależy od kontraktu z usługą Braze.
- Tylko segmenty.

## <a name="set-up-connection-to-braze"></a>Skonfiguruj połączenie z usługą Braze

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Braze**.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Domyślnie – tylko administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Podaj klucz interfejsu Braze API, aby kontynuować logowanie.

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Wybierz opcję **Połącz**, aby zainicjować połączenie.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz opcję **Dodaj eksport**.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji Braze. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wpisz nazwę eksportu.

1. W sekcji **Dopasowywanie danych** w polu **E-mail** wybierz pole reprezentujące adres e-mail klienta. W polu **Identyfikator klienta** wybierz pole reprezentujące identyfikator Braze klienta. Segmenty w Braze zostaną utworzone z taką samą nazwą segmentu jak w Dynamics 365 Customer Insights. Można wybrać dodatkowe, opcjonalne pola służące do dopasowania danych.

1. Wybierz encje lub segmenty, które chcesz wyeksportować.

1. Wybierz pozycję **Zapisz**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]