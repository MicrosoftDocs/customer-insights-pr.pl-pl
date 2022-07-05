---
title: Eksportowanie segmentów Customer Insights do kampanii Adobe Campaign Standard (wersja zapoznawcza)
description: Dowiedz się, jak używać segmentów funkcji Customer Insights w Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 9915591cd969bf825f5d1669de43ed4f9953f898
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081342"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Eksportowanie segmentów Customer Insights do kampanii Adobe Campaign Standard (wersja zapoznawcza)

Jako użytkownik usługi Dynamics 365 Customer Insights możesz tworzyć segmenty, aby kampanie marketingowe były efektywniejsze, ponieważ są przeznaczone dla odpowiednich odbiorców. Aby użyć segmentu funkcji Customer Insights w Adobe Experience Platform i takich aplikacjach, jak Adobe Campaign Standard, należy wykonać kilka kroków opisanych w tym artykule.

:::image type="content" source="media/ACS-flow.png" alt-text="Diagram procesu przedstawiający kroki opisane w tym artykule.":::

## <a name="prerequisites"></a>Wymagania wstępne

- Licencja Dynamics 365 Customer Insights
- Licencja Adobe Campaign Standard
- Konto usługi Azure Blob Storage

## <a name="campaign-overview"></a>Podgląd kampanii

Aby lepiej zrozumieć, jak możesz używać segmentów z funkcji Customer Insights w Adobe Experience Platform, przejmijmy fikcyjną przykładową kampanię.

Załóżmy, że firma oferuje swoim klientom w Stanach Zjednoczonych usługę opartą na comiesięcznej subskrypcji. Chcemy zidentyfikować klientów, których subskrypcje mają zostać odnowione w ciągu najbliższych ośmiu dni, ale którzy nie odnowili jeszcze tych subskrypcji. Aby zachować tych klientów, należy wysłać im ofertę promocyjną pocztą e-mail, używając standardu Adobe Campaign Standard.

W tym przykładzie chcemy raz uruchomić promocyjną kampanię e-mail. Ten artykuł nie dotyczy przypadku użycia polegającego na uruchamianiu kampanii więcej niż raz. Można jednak skonfigurować aplikację Customer Insights i Adobe Campaign Standard tak, aby działały także w przypadku scenariusza kampanii cyklicznej.

## <a name="identify-your-target-audience"></a>Identyfikowanie odbiorców docelowych

W naszym scenariuszu założono, że adresy e-mail klientów są dostępne, a ich preferencje promocyjne zostały przeanalizowane w celu zidentyfikowania członków segmentu.

[Segment zdefiniowany w uchwale Customer Insights](segments.md) to **ChurnProneCustomers** i planujesz wysłanie tych klientów do promocji poczty e-mail.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Zrzut ekranu przedstawiający stronę segmentów z utworzonym segmentem ChurnProneCustomers.":::

Wiadomość e-mail z ofertą, którą chcesz wysłać, będzie zawierać imię, nazwisko oraz datę zakończenia subskrypcji klienta. Będzie ona informować klientów o rabatach, które otrzymają w przypadku odnowienia subskrypcji przed jej zakończeniem.

## <a name="export-your-target-audience"></a>Eksportowanie odbiorców docelowych

### <a name="configure-a-connection"></a>Konfigurowanie połączenia

Po zidentyfikowaniu odbiorców docelowych można skonfigurować eksport do konta Azure Blob Storage.

1. W Customer Insights przejdź do strony **Administrator** > **Połączenia**.

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

1. Teraz zamapujemy pola **Źródło** z segmentu Customer Insights na nazwy pól **Cel** w schemacie Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mapowanie pola dla łącznika standardu Adobe Campaign Standard.":::

   Aby dodać więcej atrybutów, wybierz opcję **Dodaj atrybut**. Nazwa docelowa może być inna niż nazwa pola źródłowego, dzięki czemu można mapować wyniki wyjściowe segmentu z Customer Insights do Adobe Campaign Standard, jeśli pola nie mają tej samej nazwy w obu systemach.

   > [!NOTE]
   > Adres e-mail jest używany jako pole tożsamości, ale do mapowania danych do Adobe Campaign Standard można użyć dowolnego innego identyfikatora z profilu klienta.

1. Wybierz pozycję **Zapisz**.

Po zapisaniu docelowego eksportu znajdziesz go w **Dane** > **Eksporty**.

Możesz teraz [wyeksportować na żądanie](export-destinations.md#run-exports-on-demand). Eksportowanie będzie się również odbywało podczas każdego [zaplanowanego odświeżania](system.md).

> [!NOTE]
> Upewnij się, że liczba rekordów w wyeksportowanym segmencie znajduje się w dozwolonym limicie licencji Adobe Campaign Standard.

Wyeksportowane dane są przechowywane w skonfigurowanym powyżej kontenerze usługi Azure Blob Storage. W kontenerze jest automatycznie tworzona następująca ścieżka do folderu:

*%ContainerName%/CustomerInsights_%instanceID%/% nazwa-lokalizacji-docelowej-eksportu%_%segmentname%_%timestamp%.csv*

Przykład: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfiguracja standardu Adobe Campaign Standard

Wyeksportowane segmenty zawierają kolumny wybrane podczas definiowania miejsca docelowego eksportu w poprzednim kroku. Tych danych można używać do [tworzenia profilów w standardzie Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Aby korzystać z segmentu w standardzie Adobe Campaign Standard, należy rozszerzyć schemat profilu w standardzie Adobe Campaign Standard o dwa dodatkowe pola. Dowiedz się, [jak rozszerzyć zasób profilu](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) o nowe pola w standardzie Adobe Campaign Standard.

W naszym przykładzie te pola to *Nazwa segmentu i Data segmentu (opcjonalnie)*.

Użyjemy tych pól do zidentyfikowania profilów w standardzie Adobe Campaign Standard, do którego chcemy skierować kampanię.

Jeśli w standardzie Adobe Campaign Standard nie ma innych rekordów niż importowany, można pominąć ten krok.

## <a name="import-data-into-adobe-campaign-standard"></a>Importowanie danych do standardu Adobe Campaign Standard

Gdy wszystko jest już dostępne, należy zaimportować przygotowane dane z Customer Insights do Adobe Campaign Standard w celu utworzenia profilów. Dowiedz się, [jak importować profile w standardzie Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) przy użyciu przepływu pracy.

Przepływ pracy importu na poniższej ilustracji został skonfigurowany tak, aby działał co osiem godzin i był uruchamiany w celu wyszukiwania wyeksportowanych segmentów rozwiązania Customer Insights (plik CSV w usłudze Azure Blob Storage). Przepływ pracy wyodrębnia zawartość pliku CSV w kolumnach w określonej kolejności. Ten przepływ pracy został tak zbudowany, aby wykonywać podstawową obsługę błędów i zapewnić, że każdy rekord ma adres e-mail przed rozpoczęciem przetwarzania danych w standardzie Adobe Campaign Standard. Przepływ pracy wyodrębnia również nazwę segmentu z nazwy pliku przed wstawieniem jej do danych profilu standardu Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Zrzut ekranu przedstawiający przepływ pracy importu w interfejsie użytkownika standardu Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Pobieranie odbiorcy w standardzie Adobe Campaign Standard

Po zaimportowaniu danych do standardu Adobe Campaign Standard można [utworzyć przepływ pracy](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) i [zapytania](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) do klientów na podstawie *Nazwy segmentu* i *Daty segmentu* w celu wybrania profilów zidentyfikowanych dla kampanii przykładowej.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Tworzenie i wysyłanie wiadomości e-mail przy użyciu standardu Adobe Campaign Standard

Utwórz zawartość wiadomości e-mail, a następnie [przetestuj i wyślij](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) wiadomość e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Przykładowa wiadomość e-mail od Adobe Campaign Standard z ofertą odnowienia.":::
