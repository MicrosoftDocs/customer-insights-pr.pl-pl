---
title: Eksportowanie segmentów do usługi AdRoll (wersja zapoznawcza)
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi AdRoll.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8110eab199920ab8fc2ea15678139faf264a242a
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195763"
---
# <a name="export-segments-to-adroll-preview"></a>Eksportowanie segmentów do usługi AdRoll (wersja zapoznawcza)

Eksportuj segmenty ujednoliconych profilów klientów do rozwiązania AdRoll i używaj ich w celach reklamowych.

## <a name="prerequisites"></a>Wymagania wstępne

- [Konto rozwiązania AdRoll](https://www.adroll.com/) i odpowiadające mu poświadczenia administratora.
- [Identyfikator reklamodawcy w usłudze AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Skonfigurowane segmenty](segments.md) w Customer Insights.
- Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- Do 250 000 profili klientów na eksport do AdRoll, co może zająć do 10 minut. Liczba profilów klientów, które można eksportować do usługi AdRoll, zależy od kontraktu z usługą AdRoll i jest ograniczona.
- Tylko segmenty. Segment musi zawierać co najmniej 100 profilów klientów.

## <a name="set-up-connection-to-adroll"></a>Skonfiguruj połączenie z usługą AdRoll

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **AdRoll**.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Domyślnie – tylko administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Wybierz opcję **Połącz**, aby zainicjować połączenie.

1. Wybierz opcję **Uwierzytelnij za pomocą rozwiązania AdRoll** i podaj poświadczenia administratora dla rozwiązania AdRoll.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz opcję **Dodaj eksport**.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi AdRoll. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wpisz nazwę eksportu.

1. Wprowadź identyfikator **Reklamodawcy AdRoll**.

1. W sekcji **Dopasowywanie danych** w polu **E-mail** wybierz pole reprezentujące adres e-mail klienta.

1. Wybierz segmenty, które chcesz wyeksportować.

1. Wybierz pozycję **Zapisz**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
