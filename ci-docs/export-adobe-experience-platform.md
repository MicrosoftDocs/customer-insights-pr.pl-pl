---
title: Eksportowanie segmentów do usługi Adobe Experience Platform (wersja zapoznawcza)
description: Dowiedz się, jak używać segmentów funkcji Customer Insights w Adobe Experience Platform.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195303"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Eksportowanie segmentów do usługi Adobe Experience Platform (wersja zapoznawcza)

Eksportuj segmenty kierowane do odpowiednich odbiorców do Adobe Experience Platform.

:::image type="content" source="media/AEP-flow.png" alt-text="Diagram procesu przedstawiający kroki opisane w tym artykule.":::

## <a name="prerequisites"></a>Wymagania wstępne

- Licencja Adobe Experience Platform.
- Licencja Adobe Campaign Standard.
- Nazwa [konta Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account) klucz konta. Aby znaleźć nazwę i klucz, zobacz [Zarządzanie ustawieniami konta magazynu w portalu Azure Portal](/azure/storage/common/storage-account-manage).
- [Kontener Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

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

Skonfigurujemy eksport z Customer Insights do konta usługi Azure Blob Storage.

### <a name="set-up-connection-to-azure-blob-storage"></a>Skonfiguruj połączenie z usługą Azure Blob Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz pozycję **Azure Blob Storage**.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Domyślnie – tylko administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wprowadź **Nazwę konta**, **Klucz konta** i **Kontener** dla konta magazynu Blob Storage, do którego chcesz wyeksportować segment.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Zrzut ekranu przedstawiający konfigurację konta magazynu. ":::

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

### <a name="configure-an-export"></a>Konfigurowanie eksportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz opcję **Dodaj eksport**.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi Azure Blob Storage. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wpisz nazwę eksportu.

1. Wybierz segment, który chcesz wyeksportować. W tym przykładzie jest to segment **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Zrzut ekranu przedstawiający interfejs użytkownika służący do wybierania segmentu z wybranym segmentem ChurnProneCustomers.":::

1. Wybierz pozycję **Zapisz**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Upewnij się, że liczba rekordów w wyeksportowanym segmencie znajduje się w dozwolonym limicie licencji Adobe Campaign Standard.

Eksportowane dane są przechowywane w skonfigurowanym kontenerze Azure Blob Storage. W kontenerze są automatycznie tworzone następujące ścieżki folderów:

- Dla encji źródłowych i encji wygenerowanych przez system:  

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  Przykład: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- Element *model.json* dla eksportowanych encji znajduje się na poziomie *%ExportDestinationName%*.

  Przykład: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definiowanie modelu danych środowiska (XDM) w programie Adobe Experience Platform

Aby można było korzystać z danych wyeksportowanych z usługi Customer Insights w ramach usługi Adobe Experience Platform, należy zdefiniować schemat modelu danych doświadczeń i [skonfigurować dane dla profilu klienta w czasie rzeczywistym](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Dowiedz się, [co to jest XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) oraz zapoznaj się z [podstawami kompozycji schematu](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importowanie danych do Adobe Experience Platform

Zaimportuj odbiorcy danych z Customer Insights do Adobe Experience Platform.

1. [Utwórz połączenie źródłowe z usługą Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).

1. [Skonfiguruj przepływ danych](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) dla połączenia partiimagazynu w chmurze, aby zaimportować dane wyjściowe segmentu z rozwiązania Customer Insights do rozwiązania Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Tworzenie odbiorcy w standardzie Adobe Campaign Standard

Aby wysłać wiadomość e-mail dla tej kampanii, użyjemy standardu Adobe Campaign Standard.

1. [Utwórz odbiorców ](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) w Adobe Campaign Standard, korzystając z danych w programie Adobe Experience Platform.

1. [Używaj konstruktora segmentów](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) w standardzie Adobe Campaign Standard w celu definiowania odbiorcy na podstawie danych z funkcji Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Tworzenie i wysyłanie wiadomości e-mail przy użyciu standardu Adobe Campaign Standard

Utwórz zawartość wiadomości e-mail, a następnie [przetestuj i wyślij](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) wiadomość e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Przykładowa wiadomość e-mail od Adobe Campaign Standard z ofertą odnowienia.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
