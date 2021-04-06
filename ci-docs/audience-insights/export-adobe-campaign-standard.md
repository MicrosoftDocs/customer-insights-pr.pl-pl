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
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Korzystanie z segmentów aplikacji Customer Insights w rozwiązaniu Adobe Campaign Standard (wersja zapoznawcza)

Jako użytkownik szczegółowych informacji o odbiorcach dla aplikacji Dynamics 365 Customer Insights być może masz już segmenty utworzone po to, aby kampanie marketingowe były efektywniejsze dzięki możliwości łatwiejszego ukierunkowania ich na odpowiednich odbiorców. Aby korzystać z segmentu szczegółowych o odbiorcach w rozwiązaniu Adobe Experience Platform i aplikacjach, takich jak Adobe Campaign Standard, należy wykonać kilka kroków opisanych w tym artykule.

:::image type="content" source="media/ACS-flow.png" alt-text="Diagram procesu przedstawiający kroki opisane w tym artykule.":::

## <a name="prerequisites"></a>Wymagania wstępne

-   Licencja Dynamics 365 Customer Insights
-   Licencja rozwiązania Adobe Campaign Standard
-   Konto usługi Azure Blob Storage

## <a name="campaign-overview"></a>Podgląd kampanii

Aby lepiej zrozumieć, jak można używać segmentów szczegółowych informacji o odbiorcach w rozwiązaniu Adobe Experience Platform, przyjrzyjmy się przykładowej fikcyjnej kampanii.

Załóżmy, że firma oferuje swoim klientom w Stanach Zjednoczonych usługę opartą na comiesięcznej subskrypcji. Chcemy zidentyfikować klientów, których subskrypcje mają zostać odnowione w ciągu najbliższych ośmiu dni, ale którzy nie odnowili jeszcze tych subskrypcji. Aby utrzymać tych klientów, należy przesłać im ofertę promocyjną pocztą e-mail, używając platformy Adobe Campaign Standard.

W tym przykładzie chcemy raz uruchomić promocyjną kampanię e-mail. Ten artykuł nie dotyczy przypadku użycia polegającego na uruchamianiu kampanii więcej niż raz. Szczegółowe informacje o odbiorcach i rozwiązanie Adobe Campaign Standard można jednak skonfigurować tak, aby działały także w przypadku scenariusza kampanii cyklicznej.

## <a name="identify-your-target-audience"></a>Identyfikowanie odbiorców docelowych

W naszym scenariuszu przyjęto założenie, że adresy e-mail klientów są dostępne w szczegółowych informacjach o odbiorcach, a ich preferencje promocyjne zostały przeanalizowane w celu zidentyfikowania członków segmentu.

[Segment zdefiniowany w szczegółowych informacjach o odbiorcach](segments.md) nosi nazwę **ChurnProneCustomers** i planujesz wysłanie tym klientom promocyjnej wiadomości e-mail.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Zrzut ekranu przedstawiający stronę segmentów z utworzonym segmentem ChurnProneCustomers.":::

Wiadomość e-mail z ofertą, którą chcesz wysłać, będzie zawierać imię, nazwisko oraz datę zakończenia subskrypcji klienta. Będzie ona informować klientów o rabatach, które otrzymają w przypadku odnowienia subskrypcji przed jej zakończeniem.

## <a name="export-your-target-audience"></a>Eksportowanie odbiorców docelowych

Po zidentyfikowaniu odbiorców docelowych można skonfigurować eksport ze szczegółowych informacji o odbiorcach do konta usługi Azure Blob Storage.

1. W analizach odbiorców przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.

1. Na kafelku **Adobe Campaign** wybierz opcję **Konfiguruj**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Kafelek konfiguracji dla rozwiązania Adobe Campaign Standard.":::

1. Podaj **nazwę wyświetlaną** dla nowego miejsca docelowego eksportu, a następnie wprowadź **nazwę konta**, **klucz konta** i **kontener** konta usługi Azure Blob Storage, do którego chcesz wyeksportować segment.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Zrzut ekranu przedstawiający konfigurację konta magazynu. "::: 

   - Aby dowiedzieć się więcej o wyszukiwaniu klucza konta i nazwy konta magazynu Azure Blob, zobacz [Zarządzaj ustawieniami konta magazynu w portalu Azure](/azure/storage/common/storage-account-manage).

   - Aby dowiedzieć się, jak utworzyć kontener, zobacz [Tworzenie kontenera](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Wybierz **Dalej**.

1. Wybierz segment, który chcesz wyeksportować. W tym przykładzie jest to segment **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Zrzut ekranu przedstawiający interfejs użytkownika służący do wybierania segmentu z wybranym segmentem ChurnProneCustomers.":::

1. Wybierz **Dalej**.

1. Teraz mapujemy pola **Źródło** z segmentu szczegółowych informacji o odbiorcach na nazwy pól **Cel** w schemacie profilu rozwiązania Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mapowanie pól dla łącznika rozwiązania Adobe Campaign Standard.":::

   Aby dodać więcej atrybutów, wybierz opcję **Dodaj atrybut**. Nazwa docelowa może być inna niż nazwa pola źródłowego, dzięki czemu można mapować dane wyjściowe segmentu ze szczegółowych informacji o odbiorcach na rozwiązanie Adobe Campaign Standard, jeśli pola nie mają tej samej nazwy w obu systemach.

   > [!NOTE]
   > Adres e-mail jest używany jako pole tożsamości, ale do mapowania danych na rozwiązanie Adobe Campaign Standard można użyć dowolnego innego identyfikatora z profilu klienta szczegółowych informacji o odbiorcach.

1. Wybierz pozycję **Zapisz**.

Zapisane miejsce docelowe eksportu można znaleźć w obszarze **Administrator** > **Eksporty** > **Moje lokalizacje docelowe eksportu**.

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Zrzut ekranu z listą eksportów i wyróżnionym przykładowym segmentem.":::

Możesz teraz [wyeksportować na żądanie](export-destinations.md#export-data-on-demand). Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md).

> [!NOTE]
> Upewnij się, że liczba rekordów w wyeksportowanych segmentach znajduje się w ramach dozwolonego limitu licencji rozwiązania Adobe Campaign Standard.

Wyeksportowane dane są przechowywane w skonfigurowanym powyżej kontenerze usługi Azure Blob Storage. W kontenerze jest automatycznie tworzona następująca ścieżka do folderu:

*%ContainerName%/CustomerInsights_%instanceID%/% nazwa-lokalizacji-docelowej-eksportu%_%segmentname%_%timestamp%.csv*

Przykład: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfigurowanie rozwiązania Adobe Campaign Standard

W przypadku eksportowania segmentu ze szczegółowych informacji o odbiorcach segment ten zawiera kolumny wybrane podczas definiowania miejsca docelowego eksportu w poprzednim kroku. Tych danych można używać do [tworzenia profilów w rozwiązaniu Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Aby korzystać z segmentu w rozwiązaniu Adobe Campaign Standard, musimy rozszerzyć schemat profilu w rozwiązaniu Adobe Campaign Standard o dwa dodatkowe pola. Dowiedz się, jak [rozszerzyć zasób profilu](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) o nowe pola w rozwiązaniu Adobe Campaign Standard.

W naszym przykładzie te pola to *Nazwa segmentu i Data segmentu (opcjonalnie).*

Użyjemy tych pól do zidentyfikowania w rozwiązaniu Adobe Campaign Standard profilów, na które chcemy ukierunkować tę kampanię.

Jeśli w rozwiązaniu Adobe Campaign Standard nie ma innych rekordów niż importowane, można pominąć ten krok.

## <a name="import-data-into-adobe-campaign-standard"></a>Importowanie danych do rozwiązania Adobe Campaign Standard

Gdy wszystko jest już gotowe, należy zaimportować przygotowane dane odbiorców ze szczegółowych informacji o odbiorcach do rozwiązania Adobe Campaign Standard w celu utworzenia profilów. Dowiedz się, [jak importować profile w rozwiązaniu Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) przy użyciu przepływu pracy.

Przepływ pracy importu na poniższej ilustracji został skonfigurowany tak, aby był uruchamiamy co 8 godzin i szukał wyeksportowanych segmentów szczegółowych informacji o odbiorcach (plik CSV w usłudze Azure Blob Storage). Przepływ pracy wyodrębnia zawartość pliku CSV w kolumnach w określonej kolejności. Ten przepływ pracy został zbudowany tak, aby wykonywać podstawową obsługę błędów i zapewniać, że każdy rekord ma adres e-mail przed rozpoczęciem przetwarzania danych w rozwiązaniu Adobe Campaign Standard. Przepływ pracy wyodrębnia też nazwę segmentu z nazwy pliku przed przejściem do trybu upsert dla danych profilu usługi ACS.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Zrzut ekranu przedstawiający przepływ pracy importu w interfejsie użytkownika rozwiązania Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Pobieranie odbiorców w rozwiązaniu Adobe Campaign Standard

Po zaimportowaniu danych do rozwiązania Adobe Campaign Standard [można utworzyć przepływ pracy](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) i [wykonać zapytanie](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) o klientów na podstawie pól *Nazwa segmentu* i *Data segmentu* w celu wybrania profilów zidentyfikowanych dla przykładowej kampanii.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Tworzenie i wysyłanie wiadomości e-mail przy użyciu rozwiązania Adobe Campaign Standard

Utwórz zawartość wiadomości e-mail, a następnie [przetestuj i wyślij](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) wiadomość e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Przykładowa wiadomość e-mail z ofertą odnowienia z rozwiązania Adobe Campaign Standard.":::