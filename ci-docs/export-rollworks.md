---
title: Eksportowanie segmentów do usługi RollWorks (wersja zapoznawcza)
description: Dowiedz się, jak skonfigurować połączenie i eksport do programu RollWorks.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e13aeca4ee5309f85e7de2986cd1a2ba5d2992fb
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195625"
---
# <a name="export-segments-to-rollworks-preview"></a>Eksportowanie segmentów do usługi RollWorks (wersja zapoznawcza)

Wyeksportuj segmenty ujednoliconych profilów klientów do usługi RollWorks i użyj ich w celach reklamowych.

## <a name="prerequisites"></a>Wymagania wstępne

- [Kontakt administracyjny usługi RollWorks](https://www.rollworks.com/) i odpowiednie dane logowania administratora.
- [Identyfikator reklamodawcy w usłudze RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Skonfigurowane segmenty](segments.md) w Customer Insights.
- Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- Do 250 000 profili klientów na eksport do RollWorks, co może zająć do 10 minut. Liczba profilów klientów, które można eksportować do usługi RollWorks, zależy od kontraktu z usługą RollWorks i jest ograniczona.
- Tylko segmenty.

## <a name="set-up-connection-to-rollworks"></a>Skonfiguruj połączenie z usługą RollWorks

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **RollWorks**.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia.  Domyślnie – tylko administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Wybierz opcję **Połącz**, aby zainicjować połączenie.

1. Wybierz opcję **Uwierzytelnij za pomocą usługi RollWorks** i podaj swoje poświadczenia administratora dla usługi RollWorks.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz opcję **Dodaj eksport**.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi RollWorks. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wpisz nazwę eksportu.

1. Wprowadź **identyfikator reklamodawcy RollWorks**.

1. W sekcji **Dopasowywanie danych** w polu **E-mail** wybierz pole reprezentujące adres e-mail klienta.

1. Wybierz segmenty, które chcesz wyeksportować.

1. Wybierz pozycję **Zapisz**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
