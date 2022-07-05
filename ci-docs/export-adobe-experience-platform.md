---
title: Eksportowanie segmentów do usługi Adobe Experience Platform (wersja zapoznawcza)
description: Dowiedz się, jak używać segmentów funkcji Customer Insights w Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: c29b8264019669ffd954a298ce3a633c852477fa
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052524"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Eksportowanie segmentów do usługi Adobe Experience Platform (wersja zapoznawcza)

Jako użytkownik usługi Dynamics 365 Customer Insights możesz tworzyć segmenty, aby kampanie marketingowe były efektywniejsze, ponieważ są przeznaczone dla odpowiednich odbiorców. Aby użyć segmentu funkcji Customer Insights w Adobe Experience Platform i takich aplikacjach, jak Adobe Campaign Standard, należy wykonać kilka kroków opisanych w tym artykule.

:::image type="content" source="media/AEP-flow.png" alt-text="Diagram procesu przedstawiający kroki opisane w tym artykule.":::

## <a name="prerequisites"></a>Wymagania wstępne

-   Licencja Dynamics 365 Customer Insights
-   Licencja Adobe Experience Platform
-   Licencja Adobe Campaign Standard
-   Konto usługi Azure Blob Storage

## <a name="campaign-overview"></a>Podgląd kampanii

Aby lepiej zrozumieć, jak możesz używać segmentów z funkcji Customer Insights w Adobe Experience Platform, przejmijmy fikcyjną przykładową kampanię.

Załóżmy, że firma oferuje swoim klientom w Stanach Zjednoczonych usługę opartą na comiesięcznej subskrypcji. Chcemy zidentyfikować klientów, których subskrypcje mają zostać odnowione w ciągu najbliższych ośmiu dni, ale którzy nie odnowili jeszcze tych subskrypcji. Aby zachować tych klientów, należy wysłać im ofertę promocyjną pocztą e-mail, używając Adobe Experience Platform.

W tym przykładzie chcemy raz uruchomić promocyjną kampanię e-mail. Ten artykuł nie dotyczy przypadku użycia polegającego na uruchamianiu kampanii więcej niż raz.

## <a name="identify-your-target-audience"></a>Identyfikowanie odbiorców docelowych

W naszym scenariuszu założono, że adresy e-mail klientów są dostępne w usłudze Customer Insights, a ich preferencje promocyjne zostały przeanalizowane w celu zidentyfikowania członków segmentu.

[Segment zdefiniowany w uchwale Customer Insights](segments.md) to **ChurnProneCustomers** i planujesz wysłanie tych klientów do promocji poczty e-mail.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Zrzut ekranu przedstawiający stronę segmentów z utworzonym segmentem ChurnProneCustomers.":::

Wiadomość e-mail z ofertą, którą chcesz wysłać, będzie zawierać imię, nazwisko oraz datę zakończenia subskrypcji klienta. Będzie ona informować klientów o rabatach, które otrzymają w przypadku odnowienia subskrypcji przed jej zakończeniem.

## <a name="export-your-target-audience"></a>Eksportowanie odbiorców docelowych

Po zidentyfikowaniu odbiorców docelowych można skonfigurować eksport z Customer Insights do konta Azure Blob Storage.

### <a name="configure-a-connection"></a>Konfigurowanie połączenia

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz **Dodaj połączenie** i wybierz **Azure Blob Storage** lub wybierz **Skonfiguruj** w **Azure Blob Storage**, aby skonfigurować połączenie.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Kafelek konfiguracji dla usługi Azure Blob Storage."::: 

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wprowadź **Nazwę konta**, **Klucz konta** i **Kontener** dla konta magazynu Blob Storage, do którego chcesz wyeksportować segment.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Zrzut ekranu przedstawiający konfigurację konta magazynu. "::: 
   
    - Aby dowiedzieć się, jak znaleźć nazwę i klucz klienta konta Blob Storage, zobacz [Zarządzanie ustawieniami konta magazynu w portalu Azure Portal](/azure/storage/common/storage-account-manage).
    - Aby dowiedzieć się, jak utworzyć kontener, zobacz [Tworzenie kontenera](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Aby zakończyć połączenie, wybierz **Zapisz**. 

### <a name="configure-an-export"></a>Konfigurowanie eksportu

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj eksport**, aby utworzyć nowy eksport.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Azure Blob Storage. Jeśli nie widzisz tej nazwy sekcji, to znaczy, że nie masz dostępu do żadnych połączeń tego typu.

1. Wybierz segment, który chcesz wyeksportować. W tym przykładzie jest to segment **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Zrzut ekranu przedstawiający interfejs użytkownika służący do wybierania segmentu z wybranym segmentem ChurnProneCustomers.":::

1. Wybierz pozycję **Zapisz**.

Po zapisaniu docelowego eksportu znajdziesz go w **Dane** > **Eksporty**.

Możesz teraz [wyeksportować na żądanie](export-destinations.md#run-exports-on-demand). Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md).

> [!NOTE]
> Upewnij się, że liczba rekordów w wyeksportowanym segmencie znajduje się w dozwolonym limicie licencji Adobe Campaign Standard.

Wyeksportowane dane są przechowywane w skonfigurowanym powyżej kontenerze usługi Azure Blob Storage. W kontenerze jest automatycznie tworzona następująca ścieżka do folderu:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Przykład: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

Element *model.json* dla eksportowanych encji znajduje się na poziomie *%ExportDestinationName%*.

Przykład: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definiowanie modelu danych środowiska (XDM) w programie Adobe Experience Platform

Aby można było korzystać z danych wyeksportowanych z usługi Customer Insights w ramach usługi Adobe Experience Platform, należy zdefiniować schemat modelu danych doświadczeń i [skonfigurować dane dla profilu klienta w czasie rzeczywistym](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Dowiedz się, [co to jest XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) oraz zapoznaj się z [podstawami kompozycji schematu](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importowanie danych do Adobe Experience Platform

Gdy wszystko jest już dostępne, należy zaimportować przygotowane dane z Customer Insights do Adobe Experience Platform.

Najpierw [utwórz połączenie źródłowe z usługą Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Po zdefiniowaniu połączenia źródłowego [skonfiguruj przepływ danych](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) dla połączenia partiimagazynu w chmurze, aby zaimportować dane wyjściowe segmentu z rozwiązania Customer Insights do rozwiązania Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Tworzenie odbiorcy w standardzie Adobe Campaign Standard

Aby wysłać wiadomość e-mail dla tej kampanii, użyjemy standardu Adobe Campaign Standard. Po zaimportowaniu danych do programu Adobe Experience Platform, należy [utworzyć odbiorcę](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) w standardzie Adobe Campaign Standard, używając danych w programie Adobe Experience Platform.


Dowiedz się, jak [używać konstruktora segmentów](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) w standardzie Adobe Campaign Standard w celu definiowania odbiorcy na podstawie danych z funkcji Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Tworzenie i wysyłanie wiadomości e-mail przy użyciu standardu Adobe Campaign Standard

Utwórz zawartość wiadomości e-mail, a następnie [przetestuj i wyślij](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) wiadomość e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Przykładowa wiadomość e-mail od Adobe Campaign Standard z ofertą odnowienia.":::
