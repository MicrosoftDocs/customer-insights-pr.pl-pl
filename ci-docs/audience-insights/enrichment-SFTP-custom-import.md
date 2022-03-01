---
title: Wzbogacenie za pomocą niestandardowego importu SFTP
description: Ogólne informacje o wzbogacaniu importu niestandardowego SFTP.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f92b36ac5364ea8586f9cbba7ba03178641555c0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304663"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Wzbogacanie profili klientów za pomocą danych niestandardowych (wersja zapoznawcza)

Niestandardowy import protokołu Secure File Transfer Protocol (SFTP) umożliwia importowanie danych, które nie muszą przechodzić przez proces ujednolicania danych. To elastyczny, bezpieczny i łatwy sposób podawania danych. Niestandardowy import SFTP może być używany w połączeniu z [eksportem SFTP](export-sftp.md), który umożliwia wyeksportowanie danych profilu klienta potrzebnych do wzbogacenia. Dane mogą być następnie przetwarzane i wzbogacane, a import SFTP może być użyty do sprowadzenia wzbogaconych danych z powrotem do analizy odbiorców w Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Wymagania wstępne

Aby skonfigurować niestandardowy import SFTP, muszą być spełnione następujące wymagania wstępne:

- Masz nazwę pliku i lokalizację (ścieżkę) pliku, który ma być importowany na hosta SFTP.
- Istnieje plik *model.json* określający [schemat Common Data Model](/common-data-model/) dla danych, które mają być importowane. Plik ten musi znajdować się w tym samym katalogu, co plik przeznaczony do zaimportowania.
- Połączenie z usługą SFTP jest już skonfigurowane przez administratora *lub* użytkownik ma uprawnienia [administratora](permissions.md#administrator). Potrzebne będą poświadczenia użytkownika, adres URL i numer portu dla lokalizacji SFTP, z której chcesz zaimportować dane.


## <a name="configure-the-import"></a>Konfigurowanie importu

1. Przejdź do **Dane** > **Wzbogacenie** i wybierz kartę **Odkrywanie**.

1. Na **Niestandardowym kafelku importu SFTP** wybierz opcję **Wzbogać dane**, a następnie wybierz opcję **Rozpocznij**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Kafelek niestandardowego importu SFTP.":::

1. Wybierz [połączenie](connections.md) z listy rozwijanej. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie. Jeśli jesteś administratorem, możesz utworzyć połączenie, wybierając **Dodaj połączenie** i wybierając **SFTP Custom Import** z listy rozwijanej.

1. Wybierz opcję **Połącz z importem niestandardowym**, aby potwierdzić wybrane połączenie.

1.  Wybierz opcję **Dalej** i wprowadź **ścieżkę** i **nazwę pliku** dla danych, które chcesz zaimportować.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Zrzut ekranu przedstawiający wprowadzenie lokalizacji danych.":::

1. Wybierz opcję **Dalej** i podaj nazwę dla wzbogacania oraz nazwę encji wyjściowej. 

1. Wybierz opcję **Zapisz wzbogacenie** po przejrzeniu wybranych opcji.

## <a name="configure-the-connection-for-sftp-custom-import"></a>Konfigurowanie połączenia do niestandardowego importu SFTP 

Aby skonfigurować połączenia, użytkownik musi być administratorem. Wybierz opcję **Dodaj połączenie** podczas konfigurowania wzbogacania *lub* wybierz pozycję **Admin** > **Połączenia** i wybierz opcję **Konfiguruj** na kafelku Import niestandardowy.

1. Wprowadź nazwę połączenia w polu **Wyświetlana nazwa**.

1. Wprowadź prawidłową nazwę użytkownika, hasło i adres URL hosta serwera SFTP, na którym znajdują się dane do zaimportowania.

1. Sprawdź poprawność i wyraź zgodę na **Prywatność danych i zgodność z przepisami** zaznaczając pole wyboru **Zgadzam się**.

1. Wybierz opcję **Weryfikuj**, aby sprawdzić poprawność konfiguracji.

1. Po zakończeniu weryfikacji połączenie można zapisać, wybierając opcję **Zapisz**.

   > [!div class="mx-imgBorder"]
   > ![Strona konfiguracji łączności Experian](media/enrichment-SFTP-connection.png "Strona konfiguracji łączności Experian")


## <a name="defining-field-mappings"></a>Definiowanie mapowań pól 

Katalog zawierający plik, który ma zostać zaimportowany na serwerze SFTP, musi również zawierać plik typu *model.JSON*. Ten plik definiuje schemat, który ma być używany do importowania danych. Do określenia mapowania pól schemat musi używać modelu [Common Data Model](/common-data-model/). Prosty przykład pliku model.json wygląda następująco:

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a>Wyniki wzbogacenia

Aby rozpocząć proces wzbogacania, wybierz **Uruchom** na pasku poleceń. Można również zezwolić, aby system automatycznie uruchamiał wzbogacenie w ramach [zaplanowanego odświeżenia](system.md#schedule-tab). Czas przetwarzania zależy od rozmiaru danych do zaimportowania i połączenia z serwerem SFTP.

Po zakończeniu procesu wzbogacania możesz przejrzeć nowo zaimportowane dane wzbogacenia niestandardowego w sekcji **Moje wzbogacenia**. Ponadto znajdziesz tam czas ostatniej aktualizacji i liczbę wzbogaconych profilów.

Aby uzyskać dostęp do szczegółowego widoku poszczególnych wzbogaconych profilów, należy zaznaczyć **Wyświetl wzbogacone dane**.

## <a name="next-steps"></a>Następne kroki

Kompiluj na wierzchu wzbogaconych danych klientów. Twórz [segmenty](segments.md) i [miary](measures.md) oraz [eksportuj dane](export-destinations.md) w celu świadczenia klientom spersonalizowanych usług.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
