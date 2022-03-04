---
title: Eksportowanie danych usługi Customer Insights do standardzie Adobe Campaign Standard
description: Dowiedz się, jak używać segmentów wyników analiz odbiorców w standardzie Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 6b90ee53236fdd601ecdfd8e6117a15269a08084
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227771"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Korzystanie z segmentów usługi Customer Insights w standardzie Adobe Campaign Standard (wersja zapoznawcza)

Jako użytkownik funkcji analizy odbiorców w Dynamics 365 Customer Insights, być może tworzyłeś segmenty, aby zwiększyć skuteczność kampanii marketingowych poprzez kierowanie ich do odpowiednich odbiorców. Aby używać segmentu z wyników analiz odbiorców w programie Adobe Experience Platform i takich aplikacjach, jak Adobe Campaign Standard, należy wykonać kilka kroków opisanych w tym artykule.

:::image type="content" source="media/ACS-flow.png" alt-text="Diagram procesu przedstawiający kroki opisane w tym artykule.":::

## <a name="prerequisites"></a>Wymagania wstępne

-   Licencja Dynamics 365 Customer Insights
-   Licencja Adobe Campaign Standard
-   Konto usługi Azure Blob Storage

## <a name="campaign-overview"></a>Podgląd kampanii

Aby lepiej zrozumieć, jak można używać segmentów z wyników analiz odbiorców w Adobe Experience Platform, zapoznajmy się z przykładową fikcyjną kampanią.

Załóżmy, że firma oferuje swoim klientom w Stanach Zjednoczonych usługę opartą na comiesięcznej subskrypcji. Chcemy zidentyfikować klientów, których subskrypcje mają zostać odnowione w ciągu najbliższych ośmiu dni, ale którzy nie odnowili jeszcze tych subskrypcji. Aby zachować tych klientów, należy wysłać im ofertę promocyjną pocztą e-mail, używając standardu Adobe Campaign Standard.

W tym przykładzie chcemy raz uruchomić promocyjną kampanię e-mail. Ten artykuł nie dotyczy przypadku użycia polegającego na uruchamianiu kampanii więcej niż raz. Jednakże wyniki analiz odbiorców i standard Adobe Campaign Standard mogą być skonfigurowane tak, aby działały także w przypadku scenariusza kampanii cyklicznej.

## <a name="identify-your-target-audience"></a>Identyfikowanie odbiorców docelowych

W naszym scenariuszu przyjęto założenie, że adresy e-mail klientów są dostępne w szczegółowych informacjach o odbiorcach, a ich preferencje promocyjne zostały przeanalizowane w celu zidentyfikowania członków segmentu.

[Segment zdefiniowany w szczegółowych informacjach o odbiorcach](segments.md) nosi nazwę **ChurnProneCustomers** i planujesz wysłanie tym klientom promocyjnej wiadomości e-mail.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Zrzut ekranu przedstawiający stronę segmentów z utworzonym segmentem ChurnProneCustomers.":::

Wiadomość e-mail z ofertą, którą chcesz wysłać, będzie zawierać imię, nazwisko oraz datę zakończenia subskrypcji klienta. Będzie ona informować klientów o rabatach, które otrzymają w przypadku odnowienia subskrypcji przed jej zakończeniem.

## <a name="export-your-target-audience"></a>Eksportowanie odbiorców docelowych

### <a name="configure-a-connection"></a>Konfigurowanie połączenia

Po zidentyfikowaniu odbiorców docelowych można skonfigurować eksport ze szczegółowych informacji o odbiorcach do konta usługi Azure Blob Storage.

1. W analizie odbiorcy przejdź do pozycji **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Adobe Campaign**, aby skonfigurować połączenie, lub wybierz opcję **Konfiguruj** w kafelku **Adobe Campaign**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Kafelek konfiguracji dla standardu Adobe Campaign Standard.":::

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Wprowadź **Nazwę konta**, **Klucz konta** i **Kontener** dla konta magazynu Azure Blob Storage, do którego chcesz wyeksportować segment.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Zrzut ekranu przedstawiający konfigurację konta magazynu. "::: 

   - Aby dowiedzieć się więcej o wyszukiwaniu klucza konta i nazwy konta magazynu Azure Blob, zobacz [Zarządzaj ustawieniami konta magazynu w portalu Azure](/azure/storage/common/storage-account-manage).

   - Aby dowiedzieć się, jak utworzyć kontener, zobacz [Tworzenie kontenera](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Aby zakończyć połączenie, wybierz **Zapisz**.

### <a name="configure-an-export"></a>Konfigurowanie eksportu

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj eksport**, aby utworzyć nowy eksport.

1. W polu **Połączenie do eksportu** wybierz połączenie z sekcji Adobe Campaign. Jeśli nie widzisz tej nazwy sekcji, to znaczy, że nie masz dostępu do żadnych połączeń tego typu.

1. Wybierz segment, który chcesz wyeksportować. W tym przykładzie jest to segment **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Zrzut ekranu przedstawiający interfejs użytkownika służący do wybierania segmentu z wybranym segmentem ChurnProneCustomers.":::

1. Wybierz **Dalej**.

1. Teraz zamapujemy pola **Źródło** z segmentu wyniki analiz odbiorców do nazw pola **Wartość docelowa** w schemacie profilu standardu Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mapowanie pola dla łącznika standardu Adobe Campaign Standard.":::

   Aby dodać więcej atrybutów, wybierz opcję **Dodaj atrybut**. Nazwa docelowa może być inna niż nazwa pola źródłowego, dzięki czemu można mapować segmenty wyjściowe z wyników analiz odbiorcy do standardu Adobe Campaign Standard, jeśli pola nie mają tej samej nazwy w obu systemach.

   > [!NOTE]
   > Adres e-mail jest używany jako pole tożsamości, ale do mapowania danych do standardu Adobe Campaign Standard można użyć dowolnego innego identyfikatora z profilu wyników analiz odbiorców.

1. Wybierz pozycję **Zapisz**.

Po zapisaniu docelowego eksportu znajdziesz go w **Dane** > **Eksporty**.

Możesz teraz [wyeksportować na żądanie](export-destinations.md#run-exports-on-demand). Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md).

> [!NOTE]
> Upewnij się, że liczba rekordów w wyeksportowanym segmencie znajduje się w dozwolonym limicie licencji Adobe Campaign Standard.

Wyeksportowane dane są przechowywane w skonfigurowanym powyżej kontenerze usługi Azure Blob Storage. W kontenerze jest automatycznie tworzona następująca ścieżka do folderu:

*%ContainerName%/CustomerInsights_%instanceID%/% nazwa-lokalizacji-docelowej-eksportu%_%segmentname%_%timestamp%.csv*

Przykład: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfiguracja standardu Adobe Campaign Standard

W przypadku eksportowania segmentu ze szczegółowych informacji o odbiorcach segment ten zawiera kolumny wybrane podczas definiowania miejsca docelowego eksportu w poprzednim kroku. Tych danych można używać do [tworzenia profilów w standardzie Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Aby korzystać z segmentu w standardzie Adobe Campaign Standard, należy rozszerzyć schemat profilu w standardzie Adobe Campaign Standard o dwa dodatkowe pola. Dowiedz się, [jak rozszerzyć zasób profilu](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) o nowe pola w standardzie Adobe Campaign Standard.

W naszym przykładzie te pola to *Nazwa segmentu i Data segmentu (opcjonalnie)*.

Użyjemy tych pól do zidentyfikowania profilów w standardzie Adobe Campaign Standard, do którego chcemy skierować kampanię.

Jeśli w standardzie Adobe Campaign Standard nie ma innych rekordów niż importowany, można pominąć ten krok.

## <a name="import-data-into-adobe-campaign-standard"></a>Importowanie danych do standardu Adobe Campaign Standard

Gdy wszystko jest już na swoim miejscu, musisz zaimportować przygotowane dane odbiorców z wyników analiz odbiorców do standardu Adobe Campaign Standard w celu utworzenia profilów. Dowiedz się, [jak importować profile w standardzie Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) przy użyciu przepływu pracy.

Przepływ importu na poniższym obrazku został skonfigurowany tak, aby uruchamiał się co osiem godzin i szukał wyeksportowanych segmentów analizy odbiorców (plik .csv w Azure Blob Storage). Przepływ pracy wyodrębnia zawartość pliku CSV w kolumnach w określonej kolejności. Ten przepływ pracy został tak zbudowany, aby wykonywać podstawową obsługę błędów i zapewnić, że każdy rekord ma adres e-mail przed rozpoczęciem przetwarzania danych w standardzie Adobe Campaign Standard. Przepływ pracy wyodrębnia również nazwę segmentu z nazwy pliku przed wstawieniem jej do danych profilu standardu Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Zrzut ekranu przedstawiający przepływ pracy importu w interfejsie użytkownika standardu Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Pobieranie odbiorcy w standardzie Adobe Campaign Standard

Po zaimportowaniu danych do standardu Adobe Campaign Standard można [utworzyć przepływ pracy](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) i [zapytania](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) do klientów na podstawie *Nazwy segmentu* i *Daty segmentu* w celu wybrania profilów zidentyfikowanych dla kampanii przykładowej.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Tworzenie i wysyłanie wiadomości e-mail przy użyciu standardu Adobe Campaign Standard

Utwórz zawartość wiadomości e-mail, a następnie [przetestuj i wyślij](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) wiadomość e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Przykładowa wiadomość e-mail od Adobe Campaign Standard z ofertą odnowienia.":::
