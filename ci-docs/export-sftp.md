---
title: Eksportuj dane do hostów SFTP (wersja zapoznawcza) (zawiera wideo)
description: Dowiedz się, jak skonfigurować połączenie i eksport do lokalizacji SFTP.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207242"
---
# <a name="export-data-to-sftp-hosts-preview"></a>Eksportowanie danych do hostów SFTP (wersja zapoznawcza)

Danych klientów można używać w aplikacjach innych firm, eksportując je do lokalizacji bezpiecznego protokołu transferu plików (SFTP).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>Wymagania wstępne

- Dostępność hosta SFTP i odpowiednie poświadczenia.

## <a name="known-limitations"></a>Znane ograniczenia

- Miejsca docelowe SFTP za zaporami nie są obecnie obsługiwane.
- Czas wykonania eksportu zależy od wydajności systemu. Zalecamy dwa rdzenie procesora i 1 GB pamięci jako minimalną konfigurację serwera.
- Do 100 milionów profili klientów, co może zająć 90 minut przy użyciu zalecanej minimalnej konfiguracji dwóch rdzeni procesora i 1 GB pamięci.
- Jeśli używasz klucza SSH do uwierzytelniania, upewnij się, że [utworzyłeś swój klucz prywatny](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) jako format PEM lub SSH.COM. Jeśli używasz Putty, skonwertuj swój klucz prywatny, eksportując go jako Open SSH. Obsługiwane są następujące formaty kluczy prywatnych:
  - RSA w formacie OpenSSL PEM i ssh.com
  - DSA w formacie OpenSSL PEM i ssh.com
  - ECDSA 256/384/521 w formacie OpenSSL PEM
  - ED25519 i RSA w formacie klucza OpenSSH

## <a name="set-up-connection-to-sftp"></a>Konfiguruj połączenie z SFTP

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **SFTP**.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Domyślnie – tylko administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wybierz, czy chcesz uwierzytelniać się przez SSH, czy nazwę użytkownika/hasło dla swojego połączenia i podaj niezbędne szczegóły. Jeśli używasz klucza SSH do uwierzytelniania, upewnij się, że [utworzyłeś swój klucz prywatny](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) jako format PEM lub SSH.COM. Jeśli używasz Putty, skonwertuj swój klucz prywatny, eksportując go jako Open SSH. Obsługiwane są następujące formaty kluczy prywatnych:
   - RSA w formacie OpenSSL PEM i ssh.com
   - DSA w formacie OpenSSL PEM i ssh.com
   - ECDSA 256/384/521 w formacie OpenSSL PEM
   - ED25519 i RSA w formacie klucza OpenSSH

1. Wybierz **Zweryfikuj**, aby sprawdzić połączenie.

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz opcję **Dodaj eksport**.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji SFTP. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wpisz nazwę eksportu.

1. Określ, czy dane mają być eksportowane po spakowaniu **Gzip**, czy **Niespakowane**, oraz **ogranicznik pola** dla eksportowanych plików.

1. Wybierz encje, na przykład segmenty, które chcesz wyeksportować.

   > [!NOTE]
   > Po wyeksportowaniu każda wybrana encja zostanie podzielona na maksymalnie pięć plików wyjściowych.

1. Wybierz pozycję **Zapisz**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!TIP]
> Eksportowanie encji zawierających dużą ilość danych może powodować wyeksportowanie wielu plików CSV w tym samym folderze dla każdego eksportu. Podział eksportu odbywa się ze względów wydajności w celu zminimalizowania czasu jego zakończenia.

[!INCLUDE [footer-include](includes/footer-banner.md)]
