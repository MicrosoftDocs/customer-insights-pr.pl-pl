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
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="02266-103">Wzbogacanie profili klientów za pomocą danych niestandardowych (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="02266-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="02266-104">Niestandardowy import protokołu Secure File Transfer Protocol (SFTP) umożliwia importowanie danych, które nie muszą przechodzić przez proces ujednolicania danych.</span><span class="sxs-lookup"><span data-stu-id="02266-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="02266-105">To elastyczny, bezpieczny i łatwy sposób podawania danych.</span><span class="sxs-lookup"><span data-stu-id="02266-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="02266-106">Niestandardowy import SFTP może być używany w połączeniu z [eksportem SFTP](export-sftp.md), który umożliwia wyeksportowanie danych profilu klienta potrzebnych do wzbogacenia.</span><span class="sxs-lookup"><span data-stu-id="02266-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="02266-107">Dane mogą być następnie przetwarzane i wzbogacane, a import SFTP może być użyty do sprowadzenia wzbogaconych danych z powrotem do analizy odbiorców w Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="02266-107">The data can then be processed and enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="02266-108">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="02266-108">Prerequisites</span></span>

<span data-ttu-id="02266-109">Aby skonfigurować niestandardowy import SFTP, muszą być spełnione następujące wymagania wstępne:</span><span class="sxs-lookup"><span data-stu-id="02266-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="02266-110">Masz nazwę pliku i lokalizację (ścieżkę) pliku, który ma być importowany na hosta SFTP.</span><span class="sxs-lookup"><span data-stu-id="02266-110">You have the file name and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="02266-111">Istnieje plik *model.json* określający [schemat Common Data Model](/common-data-model/) dla danych, które mają być importowane.</span><span class="sxs-lookup"><span data-stu-id="02266-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="02266-112">Plik ten musi znajdować się w tym samym katalogu, co plik przeznaczony do zaimportowania.</span><span class="sxs-lookup"><span data-stu-id="02266-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="02266-113">Połączenie z usługą SFTP jest już skonfigurowane przez administratora *lub* użytkownik ma uprawnienia [administratora](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="02266-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="02266-114">Potrzebne będą poświadczenia użytkownika, adres URL i numer portu dla lokalizacji SFTP, z której chcesz zaimportować dane.</span><span class="sxs-lookup"><span data-stu-id="02266-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="02266-115">Konfigurowanie importu</span><span class="sxs-lookup"><span data-stu-id="02266-115">Configure the import</span></span>

1. <span data-ttu-id="02266-116">Przejdź do **Dane** > **Wzbogacenie** i wybierz kartę **Odkrywanie**.</span><span class="sxs-lookup"><span data-stu-id="02266-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="02266-117">Na **Niestandardowym kafelku importu SFTP** wybierz opcję **Wzbogać dane**, a następnie wybierz opcję **Rozpocznij**.</span><span class="sxs-lookup"><span data-stu-id="02266-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Kafelek niestandardowego importu SFTP.":::

1. <span data-ttu-id="02266-119">Wybierz [połączenie](connections.md) z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="02266-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="02266-120">Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.</span><span class="sxs-lookup"><span data-stu-id="02266-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="02266-121">Jeśli jesteś administratorem, możesz utworzyć połączenie, wybierając **Dodaj połączenie** i wybierając **SFTP Custom Import** z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="02266-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the dropdown list.</span></span>

1. <span data-ttu-id="02266-122">Wybierz opcję **Połącz z importem niestandardowym**, aby potwierdzić wybrane połączenie.</span><span class="sxs-lookup"><span data-stu-id="02266-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="02266-123">Wybierz opcję **Dalej** i wprowadź **ścieżkę** i **nazwę pliku** dla danych, które chcesz zaimportować.</span><span class="sxs-lookup"><span data-stu-id="02266-123">Select **Next** and enter the **Path** and **Filename** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Zrzut ekranu przedstawiający wprowadzenie lokalizacji danych.":::

1. <span data-ttu-id="02266-125">Wybierz opcję **Dalej** i podaj nazwę dla wzbogacania oraz nazwę encji wyjściowej.</span><span class="sxs-lookup"><span data-stu-id="02266-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="02266-126">Wybierz opcję **Zapisz wzbogacenie** po przejrzeniu wybranych opcji.</span><span class="sxs-lookup"><span data-stu-id="02266-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="02266-127">Konfigurowanie połączenia do niestandardowego importu SFTP</span><span class="sxs-lookup"><span data-stu-id="02266-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="02266-128">Aby skonfigurować połączenia, użytkownik musi być administratorem.</span><span class="sxs-lookup"><span data-stu-id="02266-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="02266-129">Wybierz opcję **Dodaj połączenie** podczas konfigurowania wzbogacania *lub* wybierz pozycję **Admin** > **Połączenia** i wybierz opcję **Konfiguruj** na kafelku Import niestandardowy.</span><span class="sxs-lookup"><span data-stu-id="02266-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="02266-130">Wprowadź nazwę połączenia w polu **Wyświetlana nazwa**.</span><span class="sxs-lookup"><span data-stu-id="02266-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="02266-131">Wprowadź prawidłową nazwę użytkownika, hasło i adres URL hosta serwera SFTP, na którym znajdują się dane do zaimportowania.</span><span class="sxs-lookup"><span data-stu-id="02266-131">Enter a valid username, password, and host URL for the SFTP server that the data to be imported resides on.</span></span>

1. <span data-ttu-id="02266-132">Sprawdź poprawność i wyraź zgodę na **Prywatność danych i zgodność z przepisami** zaznaczając pole wyboru **Zgadzam się**.</span><span class="sxs-lookup"><span data-stu-id="02266-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="02266-133">Wybierz opcję **Weryfikuj**, aby sprawdzić poprawność konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="02266-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="02266-134">Po zakończeniu weryfikacji połączenie można zapisać, wybierając opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="02266-134">Once the verification has completed, the connection can be saved by selecting **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="02266-135">![Strona konfiguracji łączności Experian](media/enrichment-SFTP-connection.png "Strona konfiguracji łączności Experian")</span><span class="sxs-lookup"><span data-stu-id="02266-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="02266-136">Definiowanie mapowań pól</span><span class="sxs-lookup"><span data-stu-id="02266-136">Defining field mappings</span></span> 

<span data-ttu-id="02266-137">Katalog zawierający plik, który ma zostać zaimportowany na serwerze SFTP, musi również zawierać plik typu *model.JSON*.</span><span class="sxs-lookup"><span data-stu-id="02266-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="02266-138">Ten plik definiuje schemat, który ma być używany do importowania danych.</span><span class="sxs-lookup"><span data-stu-id="02266-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="02266-139">Do określenia mapowania pól schemat musi używać modelu [Common Data Model](/common-data-model/).</span><span class="sxs-lookup"><span data-stu-id="02266-139">The schema has to use [Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="02266-140">Prosty przykład pliku model.json wygląda następująco:</span><span class="sxs-lookup"><span data-stu-id="02266-140">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="02266-141">Wyniki wzbogacenia</span><span class="sxs-lookup"><span data-stu-id="02266-141">Enrichment results</span></span>

<span data-ttu-id="02266-142">Aby rozpocząć proces wzbogacania, wybierz **Uruchom** na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="02266-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="02266-143">Można również zezwolić, aby system automatycznie uruchamiał wzbogacenie w ramach [zaplanowanego odświeżenia](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="02266-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="02266-144">Czas przetwarzania zależy od rozmiaru danych do zaimportowania i połączenia z serwerem SFTP.</span><span class="sxs-lookup"><span data-stu-id="02266-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="02266-145">Po zakończeniu procesu wzbogacania możesz przejrzeć nowo zaimportowane dane wzbogacenia niestandardowego w sekcji **Moje wzbogacenia**.</span><span class="sxs-lookup"><span data-stu-id="02266-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="02266-146">Ponadto znajdziesz tam czas ostatniej aktualizacji i liczbę wzbogaconych profilów.</span><span class="sxs-lookup"><span data-stu-id="02266-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="02266-147">Aby uzyskać dostęp do szczegółowego widoku poszczególnych wzbogaconych profilów, należy zaznaczyć **Wyświetl wzbogacone dane**.</span><span class="sxs-lookup"><span data-stu-id="02266-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="02266-148">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="02266-148">Next steps</span></span>

<span data-ttu-id="02266-149">Kompiluj na wierzchu wzbogaconych danych klientów.</span><span class="sxs-lookup"><span data-stu-id="02266-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="02266-150">Twórz [segmenty](segments.md) i [miary](measures.md) oraz [eksportuj dane](export-destinations.md) w celu świadczenia klientom spersonalizowanych usług.</span><span class="sxs-lookup"><span data-stu-id="02266-150">Create [segments](segments.md) and [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
