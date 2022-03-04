---
title: Bot dla Microsoft Teams
description: Wyszukaj ujednolicone profile klientów w Microsoft Teams za pomocą bota.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d6b016c1ec35e26ce6449333234edfd218bc9354
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232115"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Bot Teams dla Dynamics 365 Customer Insights (wersja zapoznawcza)

Połącz się z Microsoft Teams, aby umożliwić botom przeglądanie ujednoliconych profilów klientów w kanałach Teams.

> [!div class="mx-imgBorder"]
> ![Bot Teams ukazujący rekord klienta.](media/teams-bot.png "Bot Teams ukazujący rekord klienta")

## <a name="prerequisites"></a>Wymagania wstępne

Aby można było skonfigurować program bot muszą zostać spełnione następujące wymagania wstępne:

- Istnieje co najmniej jedno [dodane źródło danych](data-sources.md).
- Zakończono [proces unifikacji](data-unification.md).
- Pola są dodawane do [indeksu wyszukiwania i filtru](search-filter-index.md).
- Customer Insights i Teams są w tej samej organizacji.
- Środowisko ma podstawowych odbiorców docelowych ustawionych na indywidualnych klientów. Klienci biznesowi nie są obsługiwani.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]
## <a name="configure-the-bot"></a>Skonfiguruj program bot

1. W analizach odbiorców przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.
1. Na kafelku Microsoft Teams wybierz **Konfiguracja**.
1. Nastąpi przekierowanie do obszaru **Aplikacje** w Teams. Możesz również otworzyć Teams i wybrać **Aplikacje** w lewym dolnym rogu lub [pobrać je z AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).
1. Wyszukaj **Customer Insights** i wybierz aplikację.
1. Wybierz **Dodaj**.
1. Po zalogowaniu się w Customer Insights w Teams zobaczysz komunikat powitalny i będziesz mógł rozpocząć pracę.

## <a name="things-you-can-do-with-the-bot"></a>Rzeczy, które możesz zrobić za pomocą programu bot

Bot zawiera funkcje wyszukiwania ujednoliconych profilów klientów.

- Wprowadź **wyszukaj** a następnie nazwisko, adres e-mail lub dowolne inne pole w profilu ujednoliconego klienta, który jest dodawany do indeksu wyszukiwania i filtru.

  Zostanie wyświetlona karta zawierająca maksymalnie 15 pól z profilu wynikowego klienta. Wiele pasujących elementów zwraca listę wyników, w których można wybrać profil. Aby wyszukać dokładne dopasowanie można dodać termin wyszukiwania objęty znakami cudzysłowu.

- Jeśli Twoja organizacja utrzymuje wiele środowisk Customer Insights w tej samej organizacji, możesz wprowadzić **switchinstance**, aby wybrać środowisko, z którym chcesz połączyć bota.

- Wprowadź **pomoc**, aby wyświetlić listę dostępnych poleceń dla programu bot.  


[!INCLUDE[footer-include](../includes/footer-banner.md)]