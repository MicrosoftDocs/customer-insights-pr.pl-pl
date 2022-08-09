---
title: Eksportowanie segmentów do usługi LiveRamp (wersja zapoznawcza)
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi LiveRamp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196729"
---
# <a name="export-segments-to-liverampreg-preview"></a>Eksportowanie segmentów do usługi LiveRamp&reg; (wersja zapoznawcza)

Aktywuj dane w u usłudze LiveRamp, aby połączyć się z ponad 500 platformami za pośrednictwem mediów cyfrowych, społecznościowych i telewizji. Pracuj z danymi w LiveRamp, aby kierować, pomijać i personalizować kampanie reklamowe.

## <a name="prerequisites"></a>Wymagania wstępne

- Subskrypcja LiveRamp do korzystania z tego łącznika. Aby uzyskać subskrypcję, [skontaktuj się z LiveRamp](https://liveramp.com/contact/) bezpośrednio. [Dowiedz się więcej na temat dołączania do LiveRamp](https://liveramp.com/our-platform/data-onboarding/).

## <a name="known-limitations"></a>Znane ograniczenia

- W przypadku eksportu LiveRamp jest eksportowany z użyciem protokołu DOTP. Miejsca docelowe SFTP za zaporami nie są obecnie obsługiwane.
- Jeśli używasz klucza SSH do uwierzytelniania, upewnij się, że [utworzyłeś swój klucz prywatny](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) jako format PEM lub SSH.COM. Jeśli używasz Putty, skonwertuj swój klucz prywatny, eksportując go jako Open SSH. Obsługiwane są następujące formaty kluczy prywatnych:
  - RSA w formacie OpenSSL PEM i ssh.com
  - DSA w formacie OpenSSL PEM i ssh.com
  - ECDSA 256/384/521 w formacie OpenSSL PEM
  - ED25519 i RSA w formacie klucza OpenSSH
- Czas wykonania eksportu zależy od wydajności systemu. Zalecamy dwa rdzenie procesora i 1 GB pamięci jako minimalną konfigurację serwera.
- Eksportowanie jednostek z maksymalnie 100 milionami profili klientów może zająć 90 minut przy użyciu zalecanej minimalnej konfiguracji dwóch rdzeni procesora i 1 Gb pamięci.
- Rzeczywista liczba profili (lub danych), które można wyeksportować do LiveRamp, zależy od subskrypcji LiveRamp.

## <a name="set-up-connection-to-liveramp"></a>Skonfiguruj połączenie z usługą LiveRamp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **LiveRamp**.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Domyślnie – tylko administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wybierz, czy chcesz uwierzytelniać się przez SSH, czy nazwę użytkownika/hasło dla swojego połączenia i podaj niezbędne szczegóły.

1. Wybierz **Weryfikuj**, aby przetestować połączenie z LiveRamp.

1. Po pomyślnej weryfikacji przejrzyj [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz opcję **Dodaj eksport**.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi LiveRamp. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wpisz nazwę eksportu.

1. W polu **Połącz dane** wybierz **Email**, **Nazwisko i adres** lub **Telefon**, aby wysłać do LiveRamp w celu rozpoznania tożsamości.

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="Łącznik LiveRamp z mapowaniem atrybutu.":::

1. Mapuj odpowiednie atrybuty obiektu z encji *Klient* na wybrany identyfikator klucza.

1. Wybierz **Dodaj atrybut**, aby zamapować więcej atrybutów do usługi LiveRamp.

   > [!TIP]
   > Wysłanie większej liczby atrybutów z identyfikatorami kluczy do LiveRamp może pomóc uzyskać więcej dopasowań.

1. Wybierz segmenty, które chcesz wyeksportować.

1. Wybierz pozycję **Zapisz**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
