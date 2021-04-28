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
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896294"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Wzbogacanie profili klientów za pomocą danych niestandardowych (wersja zapoznawcza)

Import niestandardowy za pomocą bezpiecznego protokołu transferu plików (SFTP) umożliwia zaimportowanie danych, które nie muszą przejść przez proces ich ujednolicenia. To elastyczny, bezpieczny i łatwy sposób podawania danych. Niestandardowy import SFTP może być używany w połączeniu z [eksportem SFTP](export-sftp.md), który umożliwia wyeksportowanie danych profilu klienta potrzebnych do wzbogacenia. Dane mogą być następnie przetwarzane, wzbogacane, a niestandardowy import SFTP może służyć do przywrócenia wzbogaconych danych do funkcji analiz odbiorców w Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Wymagania wstępne

Aby skonfigurować niestandardowy import SFTP, muszą być spełnione następujące wymagania wstępne:

- Użytkownik ma nazwę pliku i lokalizację (ścieżkę) pliku, który ma zostać zaimportowany na hoście SFTP.
- Istnieje plik *model.json* określający [schemat Common Data Model](/common-data-model/) dla danych, które mają być importowane. Plik ten musi znajdować się w tym samym katalogu, co plik przeznaczony do zaimportowania.
- Połączenie z usługą SFTP jest już skonfigurowane przez administratora *lub* użytkownik ma uprawnienia [administratora](permissions.md#administrator). Potrzebne będą poświadczenia użytkownika, adres URL i numer portu dla lokalizacji SFTP, z której chcesz zaimportować dane.


## <a name="configure-the-import"></a>Konfigurowanie importu

1. Przejdź do **Dane** > **Wzbogacenie** i wybierz kartę **Odkrywanie**.

1. Na **Niestandardowym kafelku importu SFTP** wybierz opcję **Wzbogać dane**, a następnie wybierz opcję **Rozpocznij**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Kafelek niestandardowego importu SFTP.":::

1. Wybierz [połączenie](connections.md) z listy rozwijanej. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie. Jeśli użytkownik jest administratorem, może on utworzyć połączenie, wybierając z listy rozwijanej opcję **Dodaj połączenie** i wybierając pozycję **Import niestandardowy SFTP**.

1. Wybierz opcję **Połącz z importem niestandardowym**, aby potwierdzić wybrane połączenie.

1.  Wybierz opcję **Dalej** i wprowadź **Nazwę pliku** oraz **Ścieżkę** pliku danych, który chcesz zaimportować.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Zrzut ekranu przedstawiający wprowadzenie lokalizacji danych.":::

1. Wybierz opcję **Dalej** i podaj nazwę dla wzbogacania oraz nazwę encji wyjściowej. 

1. Wybierz opcję **Zapisz wzbogacenie** po przejrzeniu wybranych opcji.

## <a name="configure-the-connection-for-sftp-custom-import"></a>Konfigurowanie połączenia do niestandardowego importu SFTP 

Aby skonfigurować połączenia, użytkownik musi być administratorem. Wybierz opcję **Dodaj połączenie** podczas konfigurowania wzbogacania *lub* wybierz pozycję **Admin** > **Połączenia** i wybierz opcję **Konfiguruj** na kafelku Import niestandardowy.

1. Wprowadź nazwę połączenia w polu **Wyświetlana nazwa**.

1. Wprowadź prawidłową nazwę użytkownika, hasło i adres URL hosta dla serwera SFTP, na którym znajdują się dane do zaimportowania.

1. Sprawdź poprawność i wyraź zgodę na **Prywatność danych i zgodność z przepisami** zaznaczając pole wyboru **Zgadzam się**.

1. Wybierz opcję **Weryfikuj**, aby sprawdzić poprawność konfiguracji.

1. Po zakończeniu weryfikacji połączenie można zapisać, klikając przycisk **Zapisz**.

> [!div class="mx-imgBorder"]
   > ![Strona konfiguracji połączenia programu Experian](media/enrichment-SFTP-connection.png "Strona konfiguracji połączenia programu Experian")


## <a name="defining-field-mappings"></a>Definiowanie mapowań pól 

Katalog zawierający plik, który ma zostać zaimportowany na serwerze SFTP, musi również zawierać plik typu *model.JSON*. Ten plik definiuje schemat, który ma być używany do importowania danych. Schemat musi mieć [Common Data Model](/common-data-model/), aby określać mapowanie pól. Prosty przykład pliku model.json wygląda następująco:

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

[!INCLUDE[footer-include](../includes/footer-banner.md)]
