---
title: Wzbogacenie za pomocą niestandardowego importu SFTP
description: Ogólne informacje o wzbogacaniu importu niestandardowego SFTP.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d9e095ef793cbd25415864f76a541dce68fafe47
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595868"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="de6df-103">Wzbogacanie profili klientów za pomocą danych niestandardowych (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="de6df-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="de6df-104">Niestandardowy import protokołu Secure File Transfer Protocol (SFTP) umożliwia importowanie danych, które nie muszą przechodzić przez proces ujednolicania danych.</span><span class="sxs-lookup"><span data-stu-id="de6df-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="de6df-105">To elastyczny, bezpieczny i łatwy sposób podawania danych.</span><span class="sxs-lookup"><span data-stu-id="de6df-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="de6df-106">Niestandardowy import SFTP może być używany w połączeniu z [eksportem SFTP](export-sftp.md), który umożliwia wyeksportowanie danych profilu klienta potrzebnych do wzbogacenia.</span><span class="sxs-lookup"><span data-stu-id="de6df-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="de6df-107">Dane mogą być następnie przetwarzane, wzbogacane, a niestandardowy import SFTP może służyć do przywrócenia wzbogaconych danych do funkcji analiz odbiorców w Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="de6df-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="de6df-108">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="de6df-108">Prerequisites</span></span>

<span data-ttu-id="de6df-109">Aby skonfigurować niestandardowy import SFTP, muszą być spełnione następujące wymagania wstępne:</span><span class="sxs-lookup"><span data-stu-id="de6df-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="de6df-110">Masz poświadczenia użytkownika (nazwa użytkownika i hasło) do lokalizacji SFTP, z której mają zostać zaimportowane dane.</span><span class="sxs-lookup"><span data-stu-id="de6df-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="de6df-111">Adres URL i numer portu (zazwyczaj 22) znajduje się na hoście programu STFP.</span><span class="sxs-lookup"><span data-stu-id="de6df-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="de6df-112">Masz nazwę pliku i lokalizację pliku do zaimportowania na hoście SFTP.</span><span class="sxs-lookup"><span data-stu-id="de6df-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="de6df-113">Istnieje plik typu *model.JSON* określający schemat danych przeznaczony do zaimportowania.</span><span class="sxs-lookup"><span data-stu-id="de6df-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="de6df-114">Plik ten musi znajdować się w tym samym katalogu, co plik przeznaczony do zaimportowania.</span><span class="sxs-lookup"><span data-stu-id="de6df-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="de6df-115">Masz uprawnienia [Administratora](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="de6df-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="de6df-116">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="de6df-116">Configuration</span></span>

1. <span data-ttu-id="de6df-117">Przejdź do **Dane** > **Wzbogacenie** i wybierz kartę **Odkrywanie**.</span><span class="sxs-lookup"><span data-stu-id="de6df-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="de6df-118">Na **kafelku importu niestandardowego SFTP** wybierz pozycję **Wzbogacanie danych**.</span><span class="sxs-lookup"><span data-stu-id="de6df-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="de6df-119">![Kafelek niestandardowego importu SFTP](media/SFTP_Custom_Import_tile.png "Kafelek niestandardowego importu SFTP")</span><span class="sxs-lookup"><span data-stu-id="de6df-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="de6df-120">Zaznacz pole wyboru **Rozpocznij** i wprowadź poświadczenia oraz adres serwera SFTP.</span><span class="sxs-lookup"><span data-stu-id="de6df-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="de6df-121">Na przykład sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="de6df-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="de6df-122">Wprowadź nazwę pliku, który zawiera dane i ścieżkę do pliku na serwerze SFTP, jeśli nie znajduje się on w folderze głównym.</span><span class="sxs-lookup"><span data-stu-id="de6df-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="de6df-123">Potwierdzenie wszystkich składników we wszystkich elementach, wybierając opcję **Połącz z importem niestandardowym**.</span><span class="sxs-lookup"><span data-stu-id="de6df-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="de6df-124">![Menu wysuwane konfiguracji niestandardowego importu SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Menu wysuwane konfiguracji niestandardowego importu SFTP")</span><span class="sxs-lookup"><span data-stu-id="de6df-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="de6df-125">Definiowanie mapowań pól</span><span class="sxs-lookup"><span data-stu-id="de6df-125">Defining field mappings</span></span> 

<span data-ttu-id="de6df-126">Katalog zawierający plik, który ma zostać zaimportowany na serwerze SFTP, musi również zawierać plik typu *model.JSON*.</span><span class="sxs-lookup"><span data-stu-id="de6df-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="de6df-127">Ten plik definiuje schemat, który ma być używany do importowania danych.</span><span class="sxs-lookup"><span data-stu-id="de6df-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="de6df-128">Schemat musi mieć [Common Data Model](/common-data-model/), aby określać mapowanie pól.</span><span class="sxs-lookup"><span data-stu-id="de6df-128">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="de6df-129">Prosty przykład pliku model.json wygląda następująco:</span><span class="sxs-lookup"><span data-stu-id="de6df-129">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="de6df-130">Wyniki wzbogacenia</span><span class="sxs-lookup"><span data-stu-id="de6df-130">Enrichment results</span></span>

<span data-ttu-id="de6df-131">Aby rozpocząć proces wzbogacania, wybierz **Uruchom** na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="de6df-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="de6df-132">Można również zezwolić, aby system automatycznie uruchamiał wzbogacenie w ramach [zaplanowanego odświeżenia](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="de6df-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="de6df-133">Czas przetwarzania zależy od rozmiaru danych do zaimportowania i połączenia z serwerem SFTP.</span><span class="sxs-lookup"><span data-stu-id="de6df-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="de6df-134">Po zakończeniu procesu wzbogacania możesz przejrzeć nowo zaimportowane dane wzbogacenia niestandardowego w sekcji **Moje wzbogacenia**.</span><span class="sxs-lookup"><span data-stu-id="de6df-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="de6df-135">Ponadto znajdziesz tam czas ostatniej aktualizacji i liczbę wzbogaconych profilów.</span><span class="sxs-lookup"><span data-stu-id="de6df-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="de6df-136">Aby uzyskać dostęp do szczegółowego widoku poszczególnych wzbogaconych profilów, należy zaznaczyć **Wyświetl wzbogacone dane**.</span><span class="sxs-lookup"><span data-stu-id="de6df-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="de6df-137">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="de6df-137">Next steps</span></span>

<span data-ttu-id="de6df-138">Kompiluj na wierzchu wzbogaconych danych klientów.</span><span class="sxs-lookup"><span data-stu-id="de6df-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="de6df-139">Można tworzyć [segmenty](segments.md), [miary](measures.md) i [eksportować dane](export-destinations.md), aby zapewnić klientom spersonalizowane doświadczenia.</span><span class="sxs-lookup"><span data-stu-id="de6df-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]