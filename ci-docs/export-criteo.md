---
title: Eksportuj segmenty do Criteo (podgląd)
description: Dowiedz się, jak skonfigurować połączenie i eksport do Criteo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d7c8d6f0121fe18a6c886ba3776109a1a592ef33
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195349"
---
# <a name="export-segments-to-criteo-preview"></a>Eksportuj segmenty do Criteo (podgląd)

Eksportuj segmenty ujednoliconych profili klientów w celu generowania kampanii, dostarczania e-mail marketingu i korzystania z określonych grup klientów za pomocą Criteo.

## <a name="prerequisites"></a>Wymagania wstępne

- [Konto Criteo Dynamics Retargeting](https://www.criteo.com/login/) i odpowiednie poświadczenia administratora.
- [Skonfigurowane segmenty](segments.md).
- Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole reprezentujące adres e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- Do 1 miliona profili klientów na eksport do Criteo, co może zająć do 30 minut. Liczba profilów klientów, które można eksportować do usługi Criteo, zależy od kontraktu z usługą Criteo i jest ograniczona.
- Tylko segmenty.

## <a name="set-up-connection-to-criteo"></a>Skonfiguruj połączenie z usługą Criteo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Criteo**.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Domyślnie – tylko administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Wybierz opcję **Połącz**, aby zainicjować połączenie.

1. Wybierz **Uwierzytelnij za pomocą Criteo** i podaj swoją nazwę użytkownika administratora oraz dane uwierzytelniające dla Criteo.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz opcję **Dodaj eksport**.

1. W polu **Połączenie do eksportu** wybierz połączenie z sekcji Criteo. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wpisz nazwę eksportu.

1. W sekcji **Dopasowywanie danych** w polu **E-mail** wybierz pole reprezentujące adres e-mail klienta.

1. Opcjonalnie możesz wyeksportować **identyfikator reklamodawcy** i **Nazwa**.

1. Wybierz segmenty, które chcesz wyeksportować.

1. Wybierz pozycję **Zapisz**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
