---
title: Lokalizacje docelowe eksportu
description: Eksportuj dane i zarządzaj miejscami docelowymi eksportu.
ms.date: 07/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5557442983f8c48cd46387009e0060beb6e764bb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596098"
---
# <a name="export-destinations-preview-overview"></a>Omówienie miejsc docelowych eksportu (podgląd)

Strona **Lokalizacje docelowe eksportu** ukazuje wszystkie lokalizacje, w których skonfigurowano eksportowanie danych do programu. Można również dodać nowe miejsca docelowe dla eksportu. Dodatkowo pokazuje aktualnie dostępne opcje eksportu. Pobierz szybki przegląd, opis i dowiedz się, co możesz zrobić z poszczególnymi opcjami rozszerzania. Wyeksportuj zunifikowane profile, miary i segmenty do obsługiwanych aplikacji przydatnych w prowadzonej działalności.

Przejdź do **Administracja** > **Lokalizacje docelowe eksportu**, aby znaleźć następujące opcje rozszerzania:

- [Adobe Campaign Standard](export-adobe-campaign-standard.md)
- [Adobe Experience Platform](export-adobe-experience-platform.md)
- [AdRoll](export-adroll.md)
- [Autopilot](export-autopilot.md)
- [Azure Blob Storage](export-azure-blob-storage.md)
- [Azure Data Lake Storage Gen2](export-azure-data-lake-storage-gen2.md)
- [Bot dla Microsoft Teams](export-teams-bot.md)
- [Customer Insights API](apis.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Customer Service (dodatek kart klientów)](customer-card-add-in.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Centrum sprzedaży Dynamics 365 (dodatek kart klientów)](customer-card-add-in.md)
- [Menedżer reklam w serwisie Facebook](export-facebook.md)
- [Google Ads](export-google-ads.md)
- [LiveRamp&reg;](export-liveramp.md)
- [Mailchimp](export-mailchimp.md)
- [Marketo](export-marketo.md)
- [Power Automate](export-power-automate.md)
- [Power Apps](export-power-apps.md)
- [Power BI](export-power-bi.md)
- [SendGrid](export-sendgrid.md)
- [SFTP](export-sftp.md)

## <a name="add-a-new-export-destination"></a>Dodaj nową lokalizację docelową eksportu

Aby dodać docelowe lokalizacje eksportu, użytkownik musi mieć [uprawnienia administratora](permissions.md). W przypadku eksportu do usług Microsoft należy założyć, że obie usługi znajdują się w tej samej organizacji.

1. Przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.

1. Przejdź do karty **Moje lokalizacje docelowe eksportu**.

1. Wybierz **Dodaj lokalizację**, aby utworzyć nową lokalizację docelową eksportu.

1. W okienku **Dodawaj lokalizację** wybierz **Typ** lokalizacji docelowej eksportu z listy rozwijanej.

1. Wprowadź wymagane informacje i wybierz **Dalej**, aby utworzyć lokalizację docelową eksportu.

Możesz również wybrać **Konfiguruj** na kafelku na karcie **Odnajdź**.

## <a name="view-export-destinations"></a>Wyświetl lokalizacje docelowe eksportu

Po utworzeniu miejsc docelowych eksportowania można je znaleźć w tabeli na karcie **Moje lokalizacje docelowe eksportu**. Ta tabela zawiera trzy kolumny:

- **Wyświetlana nazwa**: Nazwa wprowadzana podczas tworzenia lokalizacji docelowej.
- **Typ**: Typ lokalizacji docelowej eksportu, który ustawisz podczas tworzenia lokalizacji docelowej.
- **Utworzono**: Data utworzenia lokalizacji docelowej.

## <a name="edit-an-export-destination"></a>Edytuj lokalizację docelową eksportu

1. Wybierz pionowy wielokropek dla lokalizacji docelowej eksportu, którą chcesz edytować.

   > [!div class="mx-imgBorder"]
   > ![Wielokropek pionowy](media/export-destinations-page-ellipsis.png "Wielokropek pionowy")

1. Wybierz **Edytuj** z menu rozwijanego.

1. Zmień wartości, które wymagają aktualizacji, i wybierz **Zapisz**.

## <a name="export-data-on-demand"></a>Eksportuj dane na żądanie

Po skonfigurowaniu łącznika dla docelowej lokalizacji eksportu eksporty będą wykonywane podczas wszystkich [zaplanowanych odświeżeń](system.md#schedule-tab).

Aby wyeksportować dane bez czekania na zaplanowane odświeżanie, przejdź do karty **Moje lokalizacje docelowe eksportowania** na **Administracja** > **Eksportowanie lokalizacji docelowych**.

> [!div class="mx-imgBorder"]
> ![Wielokropek pionowy](media/export-destinations-page-ellipsis.png "Wielokropek pionowy")

- Wybierz **Eksportuj** nad listą, aby uruchomić eksportowanie do wszystkich miejsc docelowych jednocześnie.
- Wybierz wielokropek (...) przy pozycji na liście a następnie wybierz opcję **Eksportuj**, aby uruchomić eksportowanie dla pojedynczej lokalizacji docelowej eksportu.

## <a name="remove-an-export-destination"></a>Usuń lokalizację docelową eksportu

Aby usunąć lokalizację docelową eksportu, zacznij na stronie głównej **Lokalizacje docelowe eksportu**.

1. Wybierz pionowy wielokropek dla lokalizacji docelowej eksportu, którą chcesz usunąć.

   > [!div class="mx-imgBorder"]
   > ![Wielokropek pionowy](media/export-destinations-page-ellipsis.png "Wielokropek pionowy")

2. Wybierz **Usuń** z menu rozwijanego.

3. Potwierdź usuwanie, zaznaczając pole **Usuń** na ekranie potwierdzenia.


[!INCLUDE[footer-include](../includes/footer-banner.md)]