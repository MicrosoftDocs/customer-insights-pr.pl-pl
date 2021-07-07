---
title: Eksportowanie danych aplikacji Customer Insights do rozwiązania Adobe Experience Platform
description: Dowiedz się, jak korzystać z analizy segmentów odbiorców w Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 1045d0e373fd5ea8987684e51bd9a07b7b535ee3
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305537"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="53950-103">Korzystanie z segmentów aplikacji Customer Insights w rozwiązaniu Adobe Experience Platform (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="53950-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="53950-104">Jako użytkownik funkcji analizy odbiorców w Dynamics 365 Customer Insights, być może tworzyłeś segmenty, aby zwiększyć skuteczność kampanii marketingowych poprzez kierowanie ich do odpowiednich odbiorców.</span><span class="sxs-lookup"><span data-stu-id="53950-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="53950-105">Aby korzystać z segmentu szczegółowych o odbiorcach w rozwiązaniu Adobe Experience Platform i aplikacjach, takich jak Adobe Campaign Standard, należy wykonać kilka kroków opisanych w tym artykule.</span><span class="sxs-lookup"><span data-stu-id="53950-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Diagram procesu przedstawiający kroki opisane w tym artykule.":::

## <a name="prerequisites"></a><span data-ttu-id="53950-107">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="53950-107">Prerequisites</span></span>

-   <span data-ttu-id="53950-108">Licencja Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="53950-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="53950-109">Licencja rozwiązania Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="53950-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="53950-110">Licencja rozwiązania Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="53950-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="53950-111">Konto usługi Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="53950-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="53950-112">Podgląd kampanii</span><span class="sxs-lookup"><span data-stu-id="53950-112">Campaign Overview</span></span>

<span data-ttu-id="53950-113">Aby lepiej zrozumieć, jak można używać segmentów szczegółowych informacji o odbiorcach w rozwiązaniu Adobe Experience Platform, przyjrzyjmy się przykładowej fikcyjnej kampanii.</span><span class="sxs-lookup"><span data-stu-id="53950-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="53950-114">Załóżmy, że firma oferuje swoim klientom w Stanach Zjednoczonych usługę opartą na comiesięcznej subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="53950-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="53950-115">Chcemy zidentyfikować klientów, których subskrypcje mają zostać odnowione w ciągu najbliższych ośmiu dni, ale którzy nie odnowili jeszcze tych subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="53950-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="53950-116">Aby utrzymać tych klientów, należy przesłać im ofertę promocyjną pocztą e-mail, używając platformy Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="53950-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="53950-117">W tym przykładzie chcemy raz uruchomić promocyjną kampanię e-mail.</span><span class="sxs-lookup"><span data-stu-id="53950-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="53950-118">Ten artykuł nie dotyczy przypadku użycia polegającego na uruchamianiu kampanii więcej niż raz.</span><span class="sxs-lookup"><span data-stu-id="53950-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="53950-119">Identyfikowanie odbiorców docelowych</span><span class="sxs-lookup"><span data-stu-id="53950-119">Identify your target audience</span></span>

<span data-ttu-id="53950-120">W naszym scenariuszu przyjęto założenie, że adresy e-mail klientów są dostępne w szczegółowych informacjach o odbiorcach, a ich preferencje promocyjne zostały przeanalizowane w celu zidentyfikowania członków segmentu.</span><span class="sxs-lookup"><span data-stu-id="53950-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="53950-121">[Segment zdefiniowany w szczegółowych informacjach o odbiorcach](segments.md) nosi nazwę **ChurnProneCustomers** i planujesz wysłanie tym klientom promocyjnej wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="53950-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Zrzut ekranu przedstawiający stronę segmentów z utworzonym segmentem ChurnProneCustomers.":::

<span data-ttu-id="53950-123">Wiadomość e-mail z ofertą, którą chcesz wysłać, będzie zawierać imię, nazwisko oraz datę zakończenia subskrypcji klienta.</span><span class="sxs-lookup"><span data-stu-id="53950-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="53950-124">Będzie ona informować klientów o rabatach, które otrzymają w przypadku odnowienia subskrypcji przed jej zakończeniem.</span><span class="sxs-lookup"><span data-stu-id="53950-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="53950-125">Eksportowanie odbiorców docelowych</span><span class="sxs-lookup"><span data-stu-id="53950-125">Export your target audience</span></span>

<span data-ttu-id="53950-126">Po zidentyfikowaniu odbiorców docelowych można skonfigurować eksport ze szczegółowych informacji o odbiorcach do konta usługi Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="53950-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="53950-127">Konfigurowanie połączenia</span><span class="sxs-lookup"><span data-stu-id="53950-127">Configure a connection</span></span>

1. <span data-ttu-id="53950-128">Przejdź do **Admin** > **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="53950-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="53950-129">Wybierz **Dodaj połączenie** i wybierz **Azure Blob Storage** lub wybierz **Skonfiguruj** w **Azure Blob Storage**, aby skonfigurować połączenie.</span><span class="sxs-lookup"><span data-stu-id="53950-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile to configure the connection.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Kafelek konfiguracji dla usługi Azure Blob Storage."::: 

1. <span data-ttu-id="53950-131">W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="53950-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="53950-132">Wyświetlana nazwa i typ połączenia opisują to połączenie.</span><span class="sxs-lookup"><span data-stu-id="53950-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="53950-133">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.</span><span class="sxs-lookup"><span data-stu-id="53950-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="53950-134">Określ, kto może używać tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="53950-134">Choose who can use this connection.</span></span> <span data-ttu-id="53950-135">Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy.</span><span class="sxs-lookup"><span data-stu-id="53950-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="53950-136">Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="53950-136">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="53950-137">Wprowadź **Nazwę konta**, **Klucz konta** i **Kontener** dla konta magazynu Blob Storage, do którego chcesz wyeksportować segment.</span><span class="sxs-lookup"><span data-stu-id="53950-137">Enter **Account name**, **Account key**, and **Container** for your Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Zrzut ekranu przedstawiający konfigurację konta magazynu. "::: 
   
    - <span data-ttu-id="53950-139">Aby dowiedzieć się, jak znaleźć nazwę i klucz klienta konta Blob Storage, zobacz [Zarządzanie ustawieniami konta magazynu w portalu Azure Portal](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="53950-139">To learn more about how to find the Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="53950-140">Aby dowiedzieć się, jak utworzyć kontener, zobacz [Tworzenie kontenera](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="53950-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="53950-141">Aby zakończyć połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="53950-141">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="53950-142">Konfigurowanie eksportu</span><span class="sxs-lookup"><span data-stu-id="53950-142">Configure an export</span></span>

<span data-ttu-id="53950-143">Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="53950-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="53950-144">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="53950-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="53950-145">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="53950-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="53950-146">Wybierz **Dodaj eksport**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="53950-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="53950-147">W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="53950-147">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="53950-148">Jeśli nie widzisz tej nazwy sekcji, to znaczy, że nie masz dostępu do żadnych połączeń tego typu.</span><span class="sxs-lookup"><span data-stu-id="53950-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="53950-149">Wybierz segment, który chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="53950-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="53950-150">W tym przykładzie jest to segment **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="53950-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Zrzut ekranu przedstawiający interfejs użytkownika służący do wybierania segmentu z wybranym segmentem ChurnProneCustomers.":::

1. <span data-ttu-id="53950-152">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="53950-152">Select **Save**.</span></span>

<span data-ttu-id="53950-153">Po zapisaniu docelowego eksportu znajdziesz go w **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="53950-153">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="53950-154">Możesz teraz [wyeksportować na żądanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="53950-154">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="53950-155">Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md).</span><span class="sxs-lookup"><span data-stu-id="53950-155">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="53950-156">Upewnij się, że liczba rekordów w wyeksportowanych segmentach znajduje się w ramach dozwolonego limitu licencji rozwiązania Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="53950-156">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="53950-157">Wyeksportowane dane są przechowywane w skonfigurowanym powyżej kontenerze usługi Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="53950-157">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="53950-158">W kontenerze jest automatycznie tworzona następująca ścieżka do folderu:</span><span class="sxs-lookup"><span data-stu-id="53950-158">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="53950-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="53950-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="53950-160">Przykład: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="53950-160">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="53950-161">Element *model.json* dla eksportowanych encji znajduje się na poziomie *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="53950-161">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="53950-162">Przykład: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="53950-162">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="53950-163">Definiowanie modelu danych środowiska (XDM) w rozwiązaniu Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="53950-163">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="53950-164">Aby można było korzystać z wyeksportowanych danych ze szczegółowych informacji o odbiorcach w rozwiązaniu Adobe Experience Platform, należy zdefiniować schemat modelu danych środowiska i [skonfigurować dane dla profilu klienta w czasie rzeczywistym](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="53950-164">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="53950-165">Dowiedz się, [co to jest XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) oraz zapoznaj się z [podstawami kompozycji schematu](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="53950-165">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="53950-166">Importowanie danych do rozwiązania Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="53950-166">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="53950-167">Gdy wszystko jest już gotowe, należy zaimportować przygotowane dane odbiorców ze szczegółowych informacji o odbiorcach do rozwiązania Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="53950-167">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="53950-168">Najpierw [utwórz połączenie źródłowe z usługą Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="53950-168">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="53950-169">Po zdefiniowaniu połączenia źródłowego [skonfiguruj przepływ danych](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) dla połączenia wsadowego magazynu w chmurze, aby zaimportować dane wyjściowe segmentu ze szczegółowych informacjach o odbiorcach do rozwiązania Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="53950-169">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="53950-170">Tworzenie odbiorców w rozwiązaniu Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="53950-170">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="53950-171">Aby wysłać e-mail dla tej kampanii, użyjemy Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="53950-171">To send the email for this campaign, we'll use Adobe Campaign Standard.</span></span> <span data-ttu-id="53950-172">Po zaimportowaniu danych do platformy Adobe Experience Platform należy [utworzyć odbiorców](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) w rozwiązaniu Adobe Campaign Standard przy użyciu danych z rozwiązania Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="53950-172">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>


<span data-ttu-id="53950-173">Dowiedz się, jak [używać konstruktora segmentów](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) w rozwiązaniu Adobe Campaign Standard do definiowania odbiorców na podstawie danych z rozwiązania Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="53950-173">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="53950-174">Tworzenie i wysyłanie wiadomości e-mail przy użyciu rozwiązania Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="53950-174">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="53950-175">Utwórz zawartość wiadomości e-mail, a następnie [przetestuj i wyślij](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) wiadomość e-mail.</span><span class="sxs-lookup"><span data-stu-id="53950-175">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Przykładowa wiadomość e-mail z ofertą odnowienia z rozwiązania Adobe Campaign Standard.":::
