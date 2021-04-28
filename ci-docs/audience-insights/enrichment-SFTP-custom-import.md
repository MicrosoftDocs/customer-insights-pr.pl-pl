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
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="d8bd6-103">Wzbogacanie profili klientów za pomocą danych niestandardowych (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="d8bd6-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="d8bd6-104">Import niestandardowy za pomocą bezpiecznego protokołu transferu plików (SFTP) umożliwia zaimportowanie danych, które nie muszą przejść przez proces ich ujednolicenia.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that does not have to go through the process of data unification.</span></span> <span data-ttu-id="d8bd6-105">To elastyczny, bezpieczny i łatwy sposób podawania danych.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="d8bd6-106">Niestandardowy import SFTP może być używany w połączeniu z [eksportem SFTP](export-sftp.md), który umożliwia wyeksportowanie danych profilu klienta potrzebnych do wzbogacenia.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="d8bd6-107">Dane mogą być następnie przetwarzane, wzbogacane, a niestandardowy import SFTP może służyć do przywrócenia wzbogaconych danych do funkcji analiz odbiorców w Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d8bd6-108">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="d8bd6-108">Prerequisites</span></span>

<span data-ttu-id="d8bd6-109">Aby skonfigurować niestandardowy import SFTP, muszą być spełnione następujące wymagania wstępne:</span><span class="sxs-lookup"><span data-stu-id="d8bd6-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="d8bd6-110">Użytkownik ma nazwę pliku i lokalizację (ścieżkę) pliku, który ma zostać zaimportowany na hoście SFTP.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-110">You have the filename and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="d8bd6-111">Istnieje plik *model.json* określający [schemat Common Data Model](/common-data-model/) dla danych, które mają być importowane.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="d8bd6-112">Plik ten musi znajdować się w tym samym katalogu, co plik przeznaczony do zaimportowania.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="d8bd6-113">Połączenie z usługą SFTP jest już skonfigurowane przez administratora *lub* użytkownik ma uprawnienia [administratora](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="d8bd6-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="d8bd6-114">Potrzebne będą poświadczenia użytkownika, adres URL i numer portu dla lokalizacji SFTP, z której chcesz zaimportować dane.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="d8bd6-115">Konfigurowanie importu</span><span class="sxs-lookup"><span data-stu-id="d8bd6-115">Configure the import</span></span>

1. <span data-ttu-id="d8bd6-116">Przejdź do **Dane** > **Wzbogacenie** i wybierz kartę **Odkrywanie**.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="d8bd6-117">Na **Niestandardowym kafelku importu SFTP** wybierz opcję **Wzbogać dane**, a następnie wybierz opcję **Rozpocznij**.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Kafelek niestandardowego importu SFTP.":::

1. <span data-ttu-id="d8bd6-119">Wybierz [połączenie](connections.md) z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-119">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="d8bd6-120">Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="d8bd6-121">Jeśli użytkownik jest administratorem, może on utworzyć połączenie, wybierając z listy rozwijanej opcję **Dodaj połączenie** i wybierając pozycję **Import niestandardowy SFTP**.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the drop-down.</span></span>

1. <span data-ttu-id="d8bd6-122">Wybierz opcję **Połącz z importem niestandardowym**, aby potwierdzić wybrane połączenie.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="d8bd6-123">Wybierz opcję **Dalej** i wprowadź **Nazwę pliku** oraz **Ścieżkę** pliku danych, który chcesz zaimportować.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-123">Select **Next** and enter the **Filename** and **Path** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Zrzut ekranu przedstawiający wprowadzenie lokalizacji danych.":::

1. <span data-ttu-id="d8bd6-125">Wybierz opcję **Dalej** i podaj nazwę dla wzbogacania oraz nazwę encji wyjściowej.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="d8bd6-126">Wybierz opcję **Zapisz wzbogacenie** po przejrzeniu wybranych opcji.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="d8bd6-127">Konfigurowanie połączenia do niestandardowego importu SFTP</span><span class="sxs-lookup"><span data-stu-id="d8bd6-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="d8bd6-128">Aby skonfigurować połączenia, użytkownik musi być administratorem.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="d8bd6-129">Wybierz opcję **Dodaj połączenie** podczas konfigurowania wzbogacania *lub* wybierz pozycję **Admin** > **Połączenia** i wybierz opcję **Konfiguruj** na kafelku Import niestandardowy.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="d8bd6-130">Wprowadź nazwę połączenia w polu **Wyświetlana nazwa**.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="d8bd6-131">Wprowadź prawidłową nazwę użytkownika, hasło i adres URL hosta dla serwera SFTP, na którym znajdują się dane do zaimportowania.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-131">Enter valid user name, password, and host URL for the STFP server the data to be imported resides on.</span></span>

1. <span data-ttu-id="d8bd6-132">Sprawdź poprawność i wyraź zgodę na **Prywatność danych i zgodność z przepisami** zaznaczając pole wyboru **Zgadzam się**.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="d8bd6-133">Wybierz opcję **Weryfikuj**, aby sprawdzić poprawność konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="d8bd6-134">Po zakończeniu weryfikacji połączenie można zapisać, klikając przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-134">Once the verification has completed, the connection can be saved by clicking **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="d8bd6-135">![Strona konfiguracji połączenia programu Experian](media/enrichment-SFTP-connection.png "Strona konfiguracji połączenia programu Experian")</span><span class="sxs-lookup"><span data-stu-id="d8bd6-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="d8bd6-136">Definiowanie mapowań pól</span><span class="sxs-lookup"><span data-stu-id="d8bd6-136">Defining field mappings</span></span> 

<span data-ttu-id="d8bd6-137">Katalog zawierający plik, który ma zostać zaimportowany na serwerze SFTP, musi również zawierać plik typu *model.JSON*.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="d8bd6-138">Ten plik definiuje schemat, który ma być używany do importowania danych.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="d8bd6-139">Schemat musi mieć [Common Data Model](/common-data-model/), aby określać mapowanie pól.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-139">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="d8bd6-140">Prosty przykład pliku model.json wygląda następująco:</span><span class="sxs-lookup"><span data-stu-id="d8bd6-140">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="d8bd6-141">Wyniki wzbogacenia</span><span class="sxs-lookup"><span data-stu-id="d8bd6-141">Enrichment results</span></span>

<span data-ttu-id="d8bd6-142">Aby rozpocząć proces wzbogacania, wybierz **Uruchom** na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="d8bd6-143">Można również zezwolić, aby system automatycznie uruchamiał wzbogacenie w ramach [zaplanowanego odświeżenia](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d8bd6-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d8bd6-144">Czas przetwarzania zależy od rozmiaru danych do zaimportowania i połączenia z serwerem SFTP.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="d8bd6-145">Po zakończeniu procesu wzbogacania możesz przejrzeć nowo zaimportowane dane wzbogacenia niestandardowego w sekcji **Moje wzbogacenia**.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="d8bd6-146">Ponadto znajdziesz tam czas ostatniej aktualizacji i liczbę wzbogaconych profilów.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="d8bd6-147">Aby uzyskać dostęp do szczegółowego widoku poszczególnych wzbogaconych profilów, należy zaznaczyć **Wyświetl wzbogacone dane**.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d8bd6-148">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="d8bd6-148">Next steps</span></span>

<span data-ttu-id="d8bd6-149">Kompiluj na wierzchu wzbogaconych danych klientów.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="d8bd6-150">Można tworzyć [segmenty](segments.md), [miary](measures.md) i [eksportować dane](export-destinations.md), aby zapewnić klientom spersonalizowane doświadczenia.</span><span class="sxs-lookup"><span data-stu-id="d8bd6-150">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
