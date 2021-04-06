---
title: Eksportowanie danych aplikacji Customer Insights do rozwiązania Adobe Campaign Standard
description: Dowiedz się, jak używać segmentów szczegółowych informacji o odbiorcach w rozwiązaniu Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596328"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="93573-103">Korzystanie z segmentów aplikacji Customer Insights w rozwiązaniu Adobe Campaign Standard (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="93573-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="93573-104">Jako użytkownik szczegółowych informacji o odbiorcach dla aplikacji Dynamics 365 Customer Insights być może masz już segmenty utworzone po to, aby kampanie marketingowe były efektywniejsze dzięki możliwości łatwiejszego ukierunkowania ich na odpowiednich odbiorców.</span><span class="sxs-lookup"><span data-stu-id="93573-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="93573-105">Aby korzystać z segmentu szczegółowych o odbiorcach w rozwiązaniu Adobe Experience Platform i aplikacjach, takich jak Adobe Campaign Standard, należy wykonać kilka kroków opisanych w tym artykule.</span><span class="sxs-lookup"><span data-stu-id="93573-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Diagram procesu przedstawiający kroki opisane w tym artykule.":::

## <a name="prerequisites"></a><span data-ttu-id="93573-107">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="93573-107">Prerequisites</span></span>

-   <span data-ttu-id="93573-108">Licencja Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="93573-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="93573-109">Licencja rozwiązania Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="93573-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="93573-110">Konto usługi Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="93573-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="93573-111">Podgląd kampanii</span><span class="sxs-lookup"><span data-stu-id="93573-111">Campaign Overview</span></span>

<span data-ttu-id="93573-112">Aby lepiej zrozumieć, jak można używać segmentów szczegółowych informacji o odbiorcach w rozwiązaniu Adobe Experience Platform, przyjrzyjmy się przykładowej fikcyjnej kampanii.</span><span class="sxs-lookup"><span data-stu-id="93573-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="93573-113">Załóżmy, że firma oferuje swoim klientom w Stanach Zjednoczonych usługę opartą na comiesięcznej subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="93573-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="93573-114">Chcemy zidentyfikować klientów, których subskrypcje mają zostać odnowione w ciągu najbliższych ośmiu dni, ale którzy nie odnowili jeszcze tych subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="93573-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="93573-115">Aby utrzymać tych klientów, należy przesłać im ofertę promocyjną pocztą e-mail, używając platformy Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="93573-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="93573-116">W tym przykładzie chcemy raz uruchomić promocyjną kampanię e-mail.</span><span class="sxs-lookup"><span data-stu-id="93573-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="93573-117">Ten artykuł nie dotyczy przypadku użycia polegającego na uruchamianiu kampanii więcej niż raz.</span><span class="sxs-lookup"><span data-stu-id="93573-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="93573-118">Szczegółowe informacje o odbiorcach i rozwiązanie Adobe Campaign Standard można jednak skonfigurować tak, aby działały także w przypadku scenariusza kampanii cyklicznej.</span><span class="sxs-lookup"><span data-stu-id="93573-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="93573-119">Identyfikowanie odbiorców docelowych</span><span class="sxs-lookup"><span data-stu-id="93573-119">Identify your target audience</span></span>

<span data-ttu-id="93573-120">W naszym scenariuszu przyjęto założenie, że adresy e-mail klientów są dostępne w szczegółowych informacjach o odbiorcach, a ich preferencje promocyjne zostały przeanalizowane w celu zidentyfikowania członków segmentu.</span><span class="sxs-lookup"><span data-stu-id="93573-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="93573-121">[Segment zdefiniowany w szczegółowych informacjach o odbiorcach](segments.md) nosi nazwę **ChurnProneCustomers** i planujesz wysłanie tym klientom promocyjnej wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="93573-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Zrzut ekranu przedstawiający stronę segmentów z utworzonym segmentem ChurnProneCustomers.":::

<span data-ttu-id="93573-123">Wiadomość e-mail z ofertą, którą chcesz wysłać, będzie zawierać imię, nazwisko oraz datę zakończenia subskrypcji klienta.</span><span class="sxs-lookup"><span data-stu-id="93573-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="93573-124">Będzie ona informować klientów o rabatach, które otrzymają w przypadku odnowienia subskrypcji przed jej zakończeniem.</span><span class="sxs-lookup"><span data-stu-id="93573-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="93573-125">Eksportowanie odbiorców docelowych</span><span class="sxs-lookup"><span data-stu-id="93573-125">Export your target audience</span></span>

<span data-ttu-id="93573-126">Po zidentyfikowaniu odbiorców docelowych można skonfigurować eksport ze szczegółowych informacji o odbiorcach do konta usługi Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="93573-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="93573-127">W analizach odbiorców przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.</span><span class="sxs-lookup"><span data-stu-id="93573-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="93573-128">Na kafelku **Adobe Campaign** wybierz opcję **Konfiguruj**.</span><span class="sxs-lookup"><span data-stu-id="93573-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Kafelek konfiguracji dla rozwiązania Adobe Campaign Standard.":::

1. <span data-ttu-id="93573-130">Podaj **nazwę wyświetlaną** dla nowego miejsca docelowego eksportu, a następnie wprowadź **nazwę konta**, **klucz konta** i **kontener** konta usługi Azure Blob Storage, do którego chcesz wyeksportować segment.</span><span class="sxs-lookup"><span data-stu-id="93573-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Zrzut ekranu przedstawiający konfigurację konta magazynu. "::: 

   - <span data-ttu-id="93573-132">Aby dowiedzieć się więcej o wyszukiwaniu klucza konta i nazwy konta magazynu Azure Blob, zobacz [Zarządzaj ustawieniami konta magazynu w portalu Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="93573-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="93573-133">Aby dowiedzieć się, jak utworzyć kontener, zobacz [Tworzenie kontenera](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="93573-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="93573-134">Wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="93573-134">Select **Next**.</span></span>

1. <span data-ttu-id="93573-135">Wybierz segment, który chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="93573-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="93573-136">W tym przykładzie jest to segment **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="93573-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Zrzut ekranu przedstawiający interfejs użytkownika służący do wybierania segmentu z wybranym segmentem ChurnProneCustomers.":::

1. <span data-ttu-id="93573-138">Wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="93573-138">Select **Next**.</span></span>

1. <span data-ttu-id="93573-139">Teraz mapujemy pola **Źródło** z segmentu szczegółowych informacji o odbiorcach na nazwy pól **Cel** w schemacie profilu rozwiązania Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="93573-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mapowanie pól dla łącznika rozwiązania Adobe Campaign Standard.":::

   <span data-ttu-id="93573-141">Aby dodać więcej atrybutów, wybierz opcję **Dodaj atrybut**.</span><span class="sxs-lookup"><span data-stu-id="93573-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="93573-142">Nazwa docelowa może być inna niż nazwa pola źródłowego, dzięki czemu można mapować dane wyjściowe segmentu ze szczegółowych informacji o odbiorcach na rozwiązanie Adobe Campaign Standard, jeśli pola nie mają tej samej nazwy w obu systemach.</span><span class="sxs-lookup"><span data-stu-id="93573-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="93573-143">Adres e-mail jest używany jako pole tożsamości, ale do mapowania danych na rozwiązanie Adobe Campaign Standard można użyć dowolnego innego identyfikatora z profilu klienta szczegółowych informacji o odbiorcach.</span><span class="sxs-lookup"><span data-stu-id="93573-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="93573-144">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="93573-144">Select **Save**.</span></span>

<span data-ttu-id="93573-145">Zapisane miejsce docelowe eksportu można znaleźć w obszarze **Administrator** > **Eksporty** > **Moje lokalizacje docelowe eksportu**.</span><span class="sxs-lookup"><span data-stu-id="93573-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Zrzut ekranu z listą eksportów i wyróżnionym przykładowym segmentem.":::

<span data-ttu-id="93573-147">Możesz teraz [wyeksportować na żądanie](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="93573-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="93573-148">Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md).</span><span class="sxs-lookup"><span data-stu-id="93573-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="93573-149">Upewnij się, że liczba rekordów w wyeksportowanych segmentach znajduje się w ramach dozwolonego limitu licencji rozwiązania Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="93573-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="93573-150">Wyeksportowane dane są przechowywane w skonfigurowanym powyżej kontenerze usługi Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="93573-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="93573-151">W kontenerze jest automatycznie tworzona następująca ścieżka do folderu:</span><span class="sxs-lookup"><span data-stu-id="93573-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="93573-152">*%ContainerName%/CustomerInsights_%instanceID%/% nazwa-lokalizacji-docelowej-eksportu%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="93573-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="93573-153">Przykład: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="93573-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="93573-154">Konfigurowanie rozwiązania Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="93573-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="93573-155">W przypadku eksportowania segmentu ze szczegółowych informacji o odbiorcach segment ten zawiera kolumny wybrane podczas definiowania miejsca docelowego eksportu w poprzednim kroku.</span><span class="sxs-lookup"><span data-stu-id="93573-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="93573-156">Tych danych można używać do [tworzenia profilów w rozwiązaniu Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="93573-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="93573-157">Aby korzystać z segmentu w rozwiązaniu Adobe Campaign Standard, musimy rozszerzyć schemat profilu w rozwiązaniu Adobe Campaign Standard o dwa dodatkowe pola.</span><span class="sxs-lookup"><span data-stu-id="93573-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="93573-158">Dowiedz się, jak [rozszerzyć zasób profilu](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) o nowe pola w rozwiązaniu Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="93573-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="93573-159">W naszym przykładzie te pola to *Nazwa segmentu i Data segmentu (opcjonalnie).*</span><span class="sxs-lookup"><span data-stu-id="93573-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="93573-160">Użyjemy tych pól do zidentyfikowania w rozwiązaniu Adobe Campaign Standard profilów, na które chcemy ukierunkować tę kampanię.</span><span class="sxs-lookup"><span data-stu-id="93573-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="93573-161">Jeśli w rozwiązaniu Adobe Campaign Standard nie ma innych rekordów niż importowane, można pominąć ten krok.</span><span class="sxs-lookup"><span data-stu-id="93573-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="93573-162">Importowanie danych do rozwiązania Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="93573-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="93573-163">Gdy wszystko jest już gotowe, należy zaimportować przygotowane dane odbiorców ze szczegółowych informacji o odbiorcach do rozwiązania Adobe Campaign Standard w celu utworzenia profilów.</span><span class="sxs-lookup"><span data-stu-id="93573-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="93573-164">Dowiedz się, [jak importować profile w rozwiązaniu Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) przy użyciu przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="93573-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="93573-165">Przepływ pracy importu na poniższej ilustracji został skonfigurowany tak, aby był uruchamiamy co 8 godzin i szukał wyeksportowanych segmentów szczegółowych informacji o odbiorcach (plik CSV w usłudze Azure Blob Storage).</span><span class="sxs-lookup"><span data-stu-id="93573-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="93573-166">Przepływ pracy wyodrębnia zawartość pliku CSV w kolumnach w określonej kolejności.</span><span class="sxs-lookup"><span data-stu-id="93573-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="93573-167">Ten przepływ pracy został zbudowany tak, aby wykonywać podstawową obsługę błędów i zapewniać, że każdy rekord ma adres e-mail przed rozpoczęciem przetwarzania danych w rozwiązaniu Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="93573-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="93573-168">Przepływ pracy wyodrębnia też nazwę segmentu z nazwy pliku przed przejściem do trybu upsert dla danych profilu usługi ACS.</span><span class="sxs-lookup"><span data-stu-id="93573-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Zrzut ekranu przedstawiający przepływ pracy importu w interfejsie użytkownika rozwiązania Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="93573-170">Pobieranie odbiorców w rozwiązaniu Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="93573-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="93573-171">Po zaimportowaniu danych do rozwiązania Adobe Campaign Standard [można utworzyć przepływ pracy](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) i [wykonać zapytanie](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) o klientów na podstawie pól *Nazwa segmentu* i *Data segmentu* w celu wybrania profilów zidentyfikowanych dla przykładowej kampanii.</span><span class="sxs-lookup"><span data-stu-id="93573-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="93573-172">Tworzenie i wysyłanie wiadomości e-mail przy użyciu rozwiązania Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="93573-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="93573-173">Utwórz zawartość wiadomości e-mail, a następnie [przetestuj i wyślij](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) wiadomość e-mail.</span><span class="sxs-lookup"><span data-stu-id="93573-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Przykładowa wiadomość e-mail z ofertą odnowienia z rozwiązania Adobe Campaign Standard.":::