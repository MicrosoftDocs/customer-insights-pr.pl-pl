---
title: Eksportowanie danych aplikacji Customer Insights do rozwiązania Adobe Campaign Standard
description: Dowiedz się, jak używać segmentów szczegółowych informacji o odbiorcach w rozwiązaniu Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: b6c010d84119c2fa8b3ef99017c65f9939bf28c4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760294"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="2af09-103">Korzystanie z segmentów aplikacji Customer Insights w rozwiązaniu Adobe Campaign Standard (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="2af09-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="2af09-104">Jako użytkownik szczegółowych informacji o odbiorcach dla aplikacji Dynamics 365 Customer Insights być może masz już segmenty utworzone po to, aby kampanie marketingowe były efektywniejsze dzięki możliwości łatwiejszego ukierunkowania ich na odpowiednich odbiorców.</span><span class="sxs-lookup"><span data-stu-id="2af09-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="2af09-105">Aby korzystać z segmentu szczegółowych o odbiorcach w rozwiązaniu Adobe Experience Platform i aplikacjach, takich jak Adobe Campaign Standard, należy wykonać kilka kroków opisanych w tym artykule.</span><span class="sxs-lookup"><span data-stu-id="2af09-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Diagram procesu przedstawiający kroki opisane w tym artykule.":::

## <a name="prerequisites"></a><span data-ttu-id="2af09-107">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="2af09-107">Prerequisites</span></span>

-   <span data-ttu-id="2af09-108">Licencja Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="2af09-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="2af09-109">Licencja rozwiązania Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="2af09-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="2af09-110">Konto usługi Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="2af09-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="2af09-111">Podgląd kampanii</span><span class="sxs-lookup"><span data-stu-id="2af09-111">Campaign Overview</span></span>

<span data-ttu-id="2af09-112">Aby lepiej zrozumieć, jak można używać segmentów szczegółowych informacji o odbiorcach w rozwiązaniu Adobe Experience Platform, przyjrzyjmy się przykładowej fikcyjnej kampanii.</span><span class="sxs-lookup"><span data-stu-id="2af09-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="2af09-113">Załóżmy, że firma oferuje swoim klientom w Stanach Zjednoczonych usługę opartą na comiesięcznej subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="2af09-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="2af09-114">Chcemy zidentyfikować klientów, których subskrypcje mają zostać odnowione w ciągu najbliższych ośmiu dni, ale którzy nie odnowili jeszcze tych subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="2af09-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="2af09-115">Aby utrzymać tych klientów, należy przesłać im ofertę promocyjną pocztą e-mail, używając platformy Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="2af09-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="2af09-116">W tym przykładzie chcemy raz uruchomić promocyjną kampanię e-mail.</span><span class="sxs-lookup"><span data-stu-id="2af09-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="2af09-117">Ten artykuł nie dotyczy przypadku użycia polegającego na uruchamianiu kampanii więcej niż raz.</span><span class="sxs-lookup"><span data-stu-id="2af09-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="2af09-118">Szczegółowe informacje o odbiorcach i rozwiązanie Adobe Campaign Standard można jednak skonfigurować tak, aby działały także w przypadku scenariusza kampanii cyklicznej.</span><span class="sxs-lookup"><span data-stu-id="2af09-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="2af09-119">Identyfikowanie odbiorców docelowych</span><span class="sxs-lookup"><span data-stu-id="2af09-119">Identify your target audience</span></span>

<span data-ttu-id="2af09-120">W naszym scenariuszu przyjęto założenie, że adresy e-mail klientów są dostępne w szczegółowych informacjach o odbiorcach, a ich preferencje promocyjne zostały przeanalizowane w celu zidentyfikowania członków segmentu.</span><span class="sxs-lookup"><span data-stu-id="2af09-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="2af09-121">[Segment zdefiniowany w szczegółowych informacjach o odbiorcach](segments.md) nosi nazwę **ChurnProneCustomers** i planujesz wysłanie tym klientom promocyjnej wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="2af09-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Zrzut ekranu przedstawiający stronę segmentów z utworzonym segmentem ChurnProneCustomers.":::

<span data-ttu-id="2af09-123">Wiadomość e-mail z ofertą, którą chcesz wysłać, będzie zawierać imię, nazwisko oraz datę zakończenia subskrypcji klienta.</span><span class="sxs-lookup"><span data-stu-id="2af09-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="2af09-124">Będzie ona informować klientów o rabatach, które otrzymają w przypadku odnowienia subskrypcji przed jej zakończeniem.</span><span class="sxs-lookup"><span data-stu-id="2af09-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="2af09-125">Eksportowanie odbiorców docelowych</span><span class="sxs-lookup"><span data-stu-id="2af09-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="2af09-126">Konfigurowanie połączenia</span><span class="sxs-lookup"><span data-stu-id="2af09-126">Configure a connection</span></span>

<span data-ttu-id="2af09-127">Po zidentyfikowaniu odbiorców docelowych można skonfigurować eksport ze szczegółowych informacji o odbiorcach do konta usługi Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="2af09-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="2af09-128">W analizie odbiorcy przejdź do pozycji **Admin** > **Połączenia**.</span><span class="sxs-lookup"><span data-stu-id="2af09-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="2af09-129">Wybierz opcję **Dodaj połączenie** i wybierz opcję **Adobe Campaign**, aby skonfigurować połączenie, lub wybierz opcję **Konfiguruj** w kafelku **Adobe Campaign**</span><span class="sxs-lookup"><span data-stu-id="2af09-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Kafelek konfiguracji dla rozwiązania Adobe Campaign Standard.":::

1. <span data-ttu-id="2af09-131">W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę.</span><span class="sxs-lookup"><span data-stu-id="2af09-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="2af09-132">Wyświetlana nazwa i typ połączenia opisują to połączenie.</span><span class="sxs-lookup"><span data-stu-id="2af09-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="2af09-133">Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.</span><span class="sxs-lookup"><span data-stu-id="2af09-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="2af09-134">Określ, kto może używać tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="2af09-134">Choose who can use this connection.</span></span> <span data-ttu-id="2af09-135">Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy.</span><span class="sxs-lookup"><span data-stu-id="2af09-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="2af09-136">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="2af09-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2af09-137">Wprowadź **Nazwę konta**, **Klucz konta** i **Kontener** dla konta magazynu Azure Blob Storage, do którego chcesz wyeksportować segment.</span><span class="sxs-lookup"><span data-stu-id="2af09-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Zrzut ekranu przedstawiający konfigurację konta magazynu. "::: 

   - <span data-ttu-id="2af09-139">Aby dowiedzieć się więcej o wyszukiwaniu klucza konta i nazwy konta magazynu Azure Blob, zobacz [Zarządzaj ustawieniami konta magazynu w portalu Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="2af09-139">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="2af09-140">Aby dowiedzieć się, jak utworzyć kontener, zobacz [Tworzenie kontenera](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="2af09-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="2af09-141">Aby zakończyć połączenie, wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="2af09-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="2af09-142">Konfigurowanie eksportu</span><span class="sxs-lookup"><span data-stu-id="2af09-142">Configure an export</span></span>

<span data-ttu-id="2af09-143">Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu.</span><span class="sxs-lookup"><span data-stu-id="2af09-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="2af09-144">Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="2af09-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2af09-145">Przejdź do **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="2af09-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2af09-146">Wybierz **Dodaj eksport**, aby utworzyć nowy eksport.</span><span class="sxs-lookup"><span data-stu-id="2af09-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="2af09-147">W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Adobe Campaign.</span><span class="sxs-lookup"><span data-stu-id="2af09-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="2af09-148">Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="2af09-148">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="2af09-149">Wybierz segment, który chcesz wyeksportować.</span><span class="sxs-lookup"><span data-stu-id="2af09-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="2af09-150">W tym przykładzie jest to segment **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="2af09-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Zrzut ekranu przedstawiający interfejs użytkownika służący do wybierania segmentu z wybranym segmentem ChurnProneCustomers.":::

1. <span data-ttu-id="2af09-152">Wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="2af09-152">Select **Next**.</span></span>

1. <span data-ttu-id="2af09-153">Teraz mapujemy pola **Źródło** z segmentu szczegółowych informacji o odbiorcach na nazwy pól **Cel** w schemacie profilu rozwiązania Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="2af09-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mapowanie pól dla łącznika rozwiązania Adobe Campaign Standard.":::

   <span data-ttu-id="2af09-155">Aby dodać więcej atrybutów, wybierz opcję **Dodaj atrybut**.</span><span class="sxs-lookup"><span data-stu-id="2af09-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="2af09-156">Nazwa docelowa może być inna niż nazwa pola źródłowego, dzięki czemu można mapować dane wyjściowe segmentu ze szczegółowych informacji o odbiorcach na rozwiązanie Adobe Campaign Standard, jeśli pola nie mają tej samej nazwy w obu systemach.</span><span class="sxs-lookup"><span data-stu-id="2af09-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2af09-157">Adres e-mail jest używany jako pole tożsamości, ale do mapowania danych na rozwiązanie Adobe Campaign Standard można użyć dowolnego innego identyfikatora z profilu klienta szczegółowych informacji o odbiorcach.</span><span class="sxs-lookup"><span data-stu-id="2af09-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="2af09-158">Wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="2af09-158">Select **Save**.</span></span>

<span data-ttu-id="2af09-159">Po zapisaniu docelowego eksportu znajdziesz go w **Dane** > **Eksporty**.</span><span class="sxs-lookup"><span data-stu-id="2af09-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="2af09-160">Możesz teraz [wyeksportować na żądanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="2af09-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="2af09-161">Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md).</span><span class="sxs-lookup"><span data-stu-id="2af09-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2af09-162">Upewnij się, że liczba rekordów w wyeksportowanych segmentach znajduje się w ramach dozwolonego limitu licencji rozwiązania Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="2af09-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="2af09-163">Wyeksportowane dane są przechowywane w skonfigurowanym powyżej kontenerze usługi Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="2af09-163">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="2af09-164">W kontenerze jest automatycznie tworzona następująca ścieżka do folderu:</span><span class="sxs-lookup"><span data-stu-id="2af09-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="2af09-165">*%ContainerName%/CustomerInsights_%instanceID%/% nazwa-lokalizacji-docelowej-eksportu%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="2af09-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="2af09-166">Przykład: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="2af09-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="2af09-167">Konfigurowanie rozwiązania Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="2af09-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="2af09-168">W przypadku eksportowania segmentu ze szczegółowych informacji o odbiorcach segment ten zawiera kolumny wybrane podczas definiowania miejsca docelowego eksportu w poprzednim kroku.</span><span class="sxs-lookup"><span data-stu-id="2af09-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="2af09-169">Tych danych można używać do [tworzenia profilów w rozwiązaniu Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="2af09-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="2af09-170">Aby korzystać z segmentu w rozwiązaniu Adobe Campaign Standard, musimy rozszerzyć schemat profilu w rozwiązaniu Adobe Campaign Standard o dwa dodatkowe pola.</span><span class="sxs-lookup"><span data-stu-id="2af09-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="2af09-171">Dowiedz się, jak [rozszerzyć zasób profilu](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) o nowe pola w rozwiązaniu Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="2af09-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="2af09-172">W naszym przykładzie te pola to *Nazwa segmentu i Data segmentu (opcjonalnie).*</span><span class="sxs-lookup"><span data-stu-id="2af09-172">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="2af09-173">Użyjemy tych pól do zidentyfikowania w rozwiązaniu Adobe Campaign Standard profilów, na które chcemy ukierunkować tę kampanię.</span><span class="sxs-lookup"><span data-stu-id="2af09-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="2af09-174">Jeśli w rozwiązaniu Adobe Campaign Standard nie ma innych rekordów niż importowane, można pominąć ten krok.</span><span class="sxs-lookup"><span data-stu-id="2af09-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="2af09-175">Importowanie danych do rozwiązania Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="2af09-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="2af09-176">Gdy wszystko jest już gotowe, należy zaimportować przygotowane dane odbiorców ze szczegółowych informacji o odbiorcach do rozwiązania Adobe Campaign Standard w celu utworzenia profilów.</span><span class="sxs-lookup"><span data-stu-id="2af09-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="2af09-177">Dowiedz się, [jak importować profile w rozwiązaniu Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) przy użyciu przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="2af09-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="2af09-178">Przepływ pracy importu na poniższej ilustracji został skonfigurowany tak, aby był uruchamiamy co 8 godzin i szukał wyeksportowanych segmentów szczegółowych informacji o odbiorcach (plik CSV w usłudze Azure Blob Storage).</span><span class="sxs-lookup"><span data-stu-id="2af09-178">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="2af09-179">Przepływ pracy wyodrębnia zawartość pliku CSV w kolumnach w określonej kolejności.</span><span class="sxs-lookup"><span data-stu-id="2af09-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="2af09-180">Ten przepływ pracy został zbudowany tak, aby wykonywać podstawową obsługę błędów i zapewniać, że każdy rekord ma adres e-mail przed rozpoczęciem przetwarzania danych w rozwiązaniu Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="2af09-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="2af09-181">Przepływ pracy wyodrębnia też nazwę segmentu z nazwy pliku przed przejściem do trybu upsert dla danych profilu usługi ACS.</span><span class="sxs-lookup"><span data-stu-id="2af09-181">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Zrzut ekranu przedstawiający przepływ pracy importu w interfejsie użytkownika rozwiązania Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="2af09-183">Pobieranie odbiorców w rozwiązaniu Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="2af09-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="2af09-184">Po zaimportowaniu danych do rozwiązania Adobe Campaign Standard [można utworzyć przepływ pracy](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) i [wykonać zapytanie](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) o klientów na podstawie pól *Nazwa segmentu* i *Data segmentu* w celu wybrania profilów zidentyfikowanych dla przykładowej kampanii.</span><span class="sxs-lookup"><span data-stu-id="2af09-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="2af09-185">Tworzenie i wysyłanie wiadomości e-mail przy użyciu rozwiązania Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="2af09-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="2af09-186">Utwórz zawartość wiadomości e-mail, a następnie [przetestuj i wyślij](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) wiadomość e-mail.</span><span class="sxs-lookup"><span data-stu-id="2af09-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Przykładowa wiadomość e-mail z ofertą odnowienia z rozwiązania Adobe Campaign Standard.":::
