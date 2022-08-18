---
title: Wzbogacanie profilów klientów za pomocą niestandardowego importu SFTP (wersja zapoznawcza)
description: Ogólne informacje o wzbogacaniu importu niestandardowego SFTP.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 831d1d3d3045379bbc5bcdcd4b05b8a147221f31
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237779"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>Wzbogacanie profilów klientów za pomocą niestandardowego importu SFTP (wersja zapoznawcza)

Niestandardowy import protokołu Secure File Transfer Protocol (SFTP) umożliwia importowanie danych, które nie muszą przechodzić przez proces ujednolicania danych. To elastyczny, bezpieczny i łatwy sposób podawania danych. Niestandardowy import SFTP może być używany w połączeniu z [eksportem SFTP](export-sftp.md), który umożliwia wyeksportowanie danych profilu klienta potrzebnych do wzbogacenia. Dane te można następnie przetwarzać i wzbogacać, a import niestandardowy (SFDP) może zostać użyty w celu zwrócenia wzbogacanych danych do Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Wymagania wstępne

- Znana jest nazwa i lokalizacja pliku (ścieżka), które mają być zaimportowane na hoście SFTP.

- Dostępny jest plik *model.json* określający schemat Common Data Model dla importowanych danych. Plik ten musi znajdować się w tym samym katalogu, co plik przeznaczony do zaimportowania.

- [Połączenie](connections.md) SFTP jest [skonfigurowane](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Przykład schematu pliku

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
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
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

## <a name="configure-the-connection-for-sftp-custom-import"></a>Konfigurowanie połączenia do niestandardowego importu SFTP

Użytkownik musi być [administratorem](permissions.md#admin) w Customer Insights, a także mieć poświadczenia, adres URL i numer portu dla lokalizacji SFTP, z której mają zostać zaimportowane dane.

1. Wybierz opcję **Dodaj połączenie** podczas konfigurowania wzbogacania lub wybierz pozycję **Administrator** > **Połączenia** i wybierz opcję **Konfiguruj** na kafelku Import niestandardowy.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Strona konfiguracji połączenia Import niestandardowy.":::

1. Wprowadź nazwę połączenia.

1. Wprowadź prawidłową nazwę użytkownika, hasło i adres URL hosta serwera SFTP, na którym znajdują się dane do zaimportowania.

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Wybierz **Weryfikuj**, aby sprawdzić poprawność konfiguracji, a następnie wybierz opcję **Zapisz**.

## <a name="configure-the-import"></a>Konfigurowanie importu

1. Przejdź do **Dane** > **Wzbogacenie** i wybierz kartę **Odkrywanie**.

1. Wybierz opcję **Wzbogać moje dane** na kafelku **Import niestandardowy SFTP**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Kafelek niestandardowego importu SFTP.":::

1. Przejrzyj omówienie, a następnie wybierz **Dalej**.

1. Wybierz połączenie. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wybierz **Zestaw danych klienta** i wybierz profil i segment, który chcesz wzbogacić. Można wybrać encję *Klient*, aby wzbogacić wszystkie profile klientów, lub wybierz jednostkę segmentu, aby wzbogacić tylko profile klientów zawarte w tym segmencie.

1. Wybierz **Dalej**.

1. Wprowadź **ścieżkę** i **nazwę pliku** danych, który chcesz zaimportować.

1. Wybierz **Dalej**.

1. Podaj **Nazwę** dla wzbogacenia oraz **Nazwa encji wyjściowej**.

1. Wybierz opcję **Zapisz wzbogacenie** po przejrzeniu wybranych opcji.

1. Wybierz przycisk **Uruchom**, aby rozpocząć proces wzbogacenia lub zamknąć, aby powrócić do strony **Wzbogacanie**.

## <a name="view-enrichment-results"></a>Wyświetlanie wyników wzbogacenia

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Następne kroki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
