---
title: Wzbogacenie za pomocą niestandardowego importu SFTP
description: Ogólne informacje o wzbogacaniu importu niestandardowego SFTP.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 59f7f05ca0825ba147e9e93f10fa3508ec3a16dd
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568483"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Wzbogacanie profili klientów za pomocą danych niestandardowych (wersja zapoznawcza)

Niestandardowy import protokołu Secure File Transfer Protocol (SFTP) umożliwia importowanie danych, które nie muszą przechodzić przez proces ujednolicania danych. To elastyczny, bezpieczny i łatwy sposób podawania danych. Niestandardowy import SFTP może być używany w połączeniu z [eksportem SFTP](export-sftp.md), który umożliwia wyeksportowanie danych profilu klienta potrzebnych do wzbogacenia. Dane mogą być następnie przetwarzane, wzbogacane, a niestandardowy import SFTP może służyć do przywrócenia wzbogaconych danych do funkcji analiz odbiorców w Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Wymagania wstępne

Aby skonfigurować niestandardowy import SFTP, muszą być spełnione następujące wymagania wstępne:

- Masz poświadczenia użytkownika (nazwa użytkownika i hasło) do lokalizacji SFTP, z której mają zostać zaimportowane dane.
- Adres URL i numer portu (zazwyczaj 22) znajduje się na hoście programu STFP.
- Masz nazwę pliku i lokalizację pliku do zaimportowania na hoście SFTP.
- Istnieje plik typu *model.JSON* określający schemat danych przeznaczony do zaimportowania. Plik ten musi znajdować się w tym samym katalogu, co plik przeznaczony do zaimportowania.
- Masz uprawnienia [Administratora](permissions.md#administrator).

## <a name="configuration"></a>Konfiguracja

1. Przejdź do **Dane** > **Wzbogacenie** i wybierz kartę **Odkrywanie**.

1. Na **kafelku importu niestandardowego SFTP** wybierz pozycję **Wzbogacanie danych**.

   > [!div class="mx-imgBorder"]
   > ![Kafelek niestandardowego importu SFTP](media/SFTP_Custom_Import_tile.png "Kafelek niestandardowego importu SFTP")

1. Zaznacz pole wyboru **Rozpocznij** i wprowadź poświadczenia oraz adres serwera SFTP. Na przykład sftp://mysftpserver.com:22.

1. Wprowadź nazwę pliku, który zawiera dane i ścieżkę do pliku na serwerze SFTP, jeśli nie znajduje się on w folderze głównym.

1. Potwierdzenie wszystkich składników we wszystkich elementach, wybierając opcję **Połącz z importem niestandardowym**.

   > [!div class="mx-imgBorder"]
   > ![Menu wysuwane konfiguracji niestandardowego importu SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Menu wysuwane konfiguracji niestandardowego importu SFTP")

## <a name="defining-field-mappings"></a>Definiowanie mapowań pól 

Katalog zawierający plik, który ma zostać zaimportowany na serwerze SFTP, musi również zawierać plik typu *model.JSON*. Ten plik definiuje schemat, który ma być używany do importowania danych. Schemat musi mieć [Common Data Model](https://docs.microsoft.com/common-data-model/), aby określać mapowanie pól. Prosty przykład pliku model.json wygląda następująco:

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

Kompiluj na wierzchu wzbogaconych danych klientów. Można tworzyć [segmenty](segments.md), [miary](measures.md) i [eksportować dane](export-destinations.md), aby zapewnić klientom spersonalizowane doświadczenia.


