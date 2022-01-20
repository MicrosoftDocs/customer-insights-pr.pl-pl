---
title: Niestandardowe modele Uczenie maszynowe | Microsoft Docs
description: Praca z modelami niestandardowymi z Uczenie maszynowe Azure w Dynamics 365 Customer Insights.
ms.date: 12/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 8ca30193ae4f4ef3ed9c60f2d694cd11fad46c76
ms.sourcegitcommit: 15b1521041149716f8031cfa6d0dc61a56a5e2ff
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/13/2022
ms.locfileid: "7967668"
---
# <a name="custom-machine-learning-models"></a>Niestandardowe modele Uczenie maszynowe

> [!NOTE]
> Wsparcie dla Machine Learning Studio (classic) zakończy się 31 sierpnia 2024 roku. Zalecamy przejście na [Azure Machine Learning](/azure/machine-learning/overview-what-is-azure-machine-learning) do tej daty.
>
> Od 1 grudnia 2021 roku nie będzie można tworzyć nowych zasobów Machine Learning Studio (klasycznego). Do 31 sierpnia 2024 roku możecie nadal korzystać z istniejących zasobów Machine Learning Studio (classic). Aby uzyskać więcej informacji, zobacz [Migracja do Azure Machine Learning](/azure/machine-learning/migrate-overview).


**Analizy** > **Modele niestandardowe** umożliwia zarządzanie przepływami pracy na podstawie modeli Uczenie maszynowe platformy Azure. Przepływy pracy pomagają wybrać dane, z których chcesz generować szczegółowe informacje, i odwzorować wyniki na ujednolicone dane klientów. Aby uzyskać więcej informacji na temat budowania niestandardowych modeli ML, zobacz [Korzystanie z modeli opartych na Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Odopowiedzialne AI

Przewidywania umożliwiają zwiększanie komfortu obsługi klienta, poprawianie funkcji biznesowych i strumienia przychodów. Stanowczo zaleca się, aby zrównoważyć wartość przewidywanie w stosunku do oddziaływania i skutków, które można wprowadzić w sposób etyczny. Dowiedz się więcej o tym, jak firma Microsoft [zajmuje się odpowiedzialną sztuczną inteligencją](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Użytkownik może również zapoznać się [z technikami i procesami dotyczącymi odpowiedzialności za uczenie maszynowe](/azure/machine-learning/concept-responsible-ml) dotyczące usługi Azure Machine Learning.

## <a name="prerequisites"></a>Wymagania wstępne

- Ta funkcja wspiera usługi webowe publikowane przez [partie w potoku Azure Machine Learning](/azure/machine-learning/concept-ml-pipelines).

- Aby korzystać z tej funkcji, potrzebujesz konta magazynu Azure Data Lake Gen2 skojarzonego z wystąpieniem usługi Azure Studio. Aby uzyskać więcej informacji, zobacz [Tworzenie konta magazynu Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-quickstart-create-account).

- W przypadku obszarów roboczych usługi Azure Machine Learning z potokami musisz mieć uprawnienia dostępu administratora typu Właściciel lub Użytkownik do obszaru roboczego usługi Azure Machine Learning.

   > [!NOTE]
   > Dane są przesyłane między wystąpieniami rozwiązania Customer Insights a wybranymi usługami internetowymi lub potokami platformy Azure w przepływie pracy. Podczas przesyłania danych do usługi platformy Azure upewnij się, że usługa jest skonfigurowana do przetwarzania danych w sposób (oraz w lokalizacji) umożliwiający zachowanie zgodności z wymaganiami prawnymi lub regulacyjnymi dotyczącymi danych Twojej organizacji.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

## <a name="add-a-new-workflow"></a>Dodaj nowy przepływ pracy

1. Przejdź do **Analizy** > **Niestandardowe modele** i wybierz **Nowy przepływ pracy**.

1. W polu **Nazwa** nadaj modelowi niestandardowemu rozpoznawalną nazwę.

   > [!div class="mx-imgBorder"]
   > ![Zrzut ekranu okienka Nowy przepływ pracy.](media/new-workflowv2.png "Zrzut ekranu okienka Nowy przepływ pracy")

1. Wybierz organizację zawierającą usługę sieci Web w **Dzierżawa zawierająca usługę sieci Web**.

1. Jeśli subskrypcja Uczenie maszynowe Azure znajduje się w innej dzierżawie niż usługa Customer Insights, wybierz **Zaloguj się**, używając swoich poświadczeń dla wybranej organizacji.

1. Wybierz **Obszary robocze** skojarzone z daną usługą sieci Web. 

1. Wybierz potok Azure Machine Learning z rozwijanej listy **Serwis internetowy, który zawiera twój model** rozwijany. Następnie wybierz **Dalej**.    
   Dowiedz się więcej o [publikowaniu potoku w usłudze Azure Machine Learning przy użyciu projektanta](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) lub [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). Potok musi zostać opublikowany w [punkcie końcowym potoku](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Dla **Dane wejściowe usług sieci Web**, wybierz pasującą **Encję** z analiz odbiorców i wybierz **Dalej**.
   > [!NOTE]
   > Przepływ pracy modelu niestandardowego zastosuje heurystykę do mapowania pól wejściowych usługi sieci Web do atrybutów encji na podstawie nazwy i typu danych pola. Jeśli nie można zamapować pola usługi sieci Web na jednostkę, pojawi się błąd.

   > [!div class="mx-imgBorder"]
   > ![Konfiguruj przepływ pracy.](media/intelligence-screen2-updated.png "Konfiguruj przepływ pracy")

1. W kroku **Parametry wyjściowe modelu** ustaw następujące właściwości:
      1. Wprowadź nazwę **Encji wyjściowej**, do którego ma zostać wlany wyniki strumienia.
      1. Z listy rozwijanej wybierz **Nazwę parametru magazynu danych wyjściowych** potoku wsadowego.
      1. Z listy rozwijanej wybierz **Nazwę parametru ścieżki danych wyjściowych** potoku wsadowego.

      > [!div class="mx-imgBorder"]
      > ![Panel parametrów wyjściowych modelu.](media/intelligence-screen3-outputparameters.png "Panel parametrów wyjściowych modelu")

1. Wybierz pasujący atrybut z listy rozwijanej **Identyfikator klienta w wynikach**, który identyfikuje klientów i wybierz **Zapisz**.

   > [!div class="mx-imgBorder"]
   > ![Powiązanie wyników z okienkiem Dane klient.](media/intelligence-screen4-relatetocustomer.png "Powiązanie wyników z okienkiem Dane klient")

1. Zostanie wyświetlony ekran **Zapisany przepływ pracy** ze szczegółowymi informacjami na temat przepływu pracy.    
   Jeśli skonfigurowano przepływ pracy dla potoku Azure Machine Learning, szczegółowe informacje o odbiorcach zostaną dołączone do obszaru roboczego zawierającego potok. Usługa analizy odbiorców będzie mieć rolę **Współautora** w obszarze roboczym Azure.

1. Wybierz **Gotowe**.

1. Można teraz uruchomić przepływ pracy ze strony **Modele niestandardowe**.

## <a name="edit-a-workflow"></a>Edytuj przepływ pracy

1. Na stronie **Modele niestandardowe** wybierz wielokropek pionowy w kolumnie **Akcje** obok utworzonego uprzednio przepływu pracy i wybierz **Edytuj**.

1. Można zaktualizować rozpoznawalną nazwę przepływu pracy w polu **Wyświetlana nazwa**, ale nie można zmienić skonfigurowanej usługi sieci web ani potoku. Wybierz **Dalej**.

1. Dla **Dane wejściowe usług sieci Web**, można aktualizować pasującą **Encję** z analiz odbiorców. Następnie wybierz **Dalej**.

1. W kroku **Parametry wyjściowe modelu** ustaw następujące właściwości:
      1. Wprowadź nazwę **Encji wyjściowej**, do którego ma zostać wlany wyniki strumienia.
      1. Wybierz **Nazwa parametru magazynu danych wyjściowych** dla planowanego strumienia testowego.
      1. Wybierz **Nazwa parametru ścieżki danych wyjściowych** dla planowanego strumienia testowego.

1. Wybierz pasujący atrybut z listy rozwijanej **Identyfikator klienta w wynikach**, który identyfikuje klientów i wybierz **Zapisz**.
   Wybierz atrybut z danych wyjściowych wnioskowania o wartościach podobnych do kolumny Identyfikator klienta encji Klient. Jeśli nie masz takiej kolumny w swoim zbiorze danych, wybierz atrybut, który jednoznacznie identyfikuje wiersz.

## <a name="run-a-workflow"></a>Uruchamianie przepływu pracy

1. Na stronie **Modele niestandardowe**, wybierz wielokropek pionowy w kolumnie **Akcje** obok utworzonego uprzednio przepływu pracy.

1. Wybierz **Uruchom**.

Przepływ pracy jest również uruchamiany automatycznie przy każdym planowanym odświeżeniu. Dowiedz się więcej na temat [konfigurowania zaplanowanego odświeżania](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Usuń przepływ pracy

1. Na stronie **Modele niestandardowe**, wybierz wielokropek pionowy w kolumnie **Akcje** obok utworzonego uprzednio przepływu pracy.

1. Wybierz **Usuń** i potwierdź usunięcie.

Przepływ pracy zostanie usunięty. [Encja](entities.md) utworzona w momencie utworzenia przepływu pracy pozostanie i będzie można ją wyświetlać na stronie **Encje**.

## <a name="results"></a>Wyniki

Wyniki z przepływu pracy są przechowywane w encji skonfigurowanej w fazie parametrów wyjściowych modelu. Dostęp do tych danych można uzyskać ze [strony encji](entities.md) lub za pomocą [dostępu za pośrednictwem interfejsów API](apis.md).

### <a name="api-access"></a>Dostęp za pośrednictwem interfejsu API

Aby określone zapytanie OData mogło uzyskać dane z encji modelu niestandardowego, użyj następującego formatu:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Zastąp identyfikator `<your instance id>` identyfikatorem środowiska Customer Insights, który można znaleźć na pasku adresu przeglądarki podczas uzyskiwania dostępu do aplikacji Customer Insights.

1. Zastąp encję `<custom model output entity>` nazwą encji podaną w kroku parametrów wyjściowych modelu konfiguracji modelu niestandardowego.

1. Zastąp wartość `<guid value>` identyfikatorem klienta, któremu chcesz przydzielić prawa dostępu do rekordu. Zazwyczaj identyfikator ten można znaleźć na [stronie profilów klientów](customer-profiles.md) w polu CustomerID.

## <a name="frequently-asked-questions"></a>Często zadawane pytania

- Dlaczego podczas konfigurowania przepływu pracy modelu niestandardowego nie jest widzę mojego potoku?    
  Często przyczyną tego problemu jest błąd konfiguracji, który występuje w potoku. Upewnij się, że [parametr wejściowy został skonfigurowany](azure-machine-learning-experiments.md#dataset-configuration) i [parametry i magazynu danych wyjściowych również są skonfigurowane](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights).

- Co oznacza błąd „Nie można zapisać przepływu pracy analizy”?    
  Użytkownicy zwykle widzą ten komunikat o błędzie, jeśli nie mają uprawnień administratora dostępu typu Właściciel lub Użytkownik w obszarze roboczym. Użytkownik potrzebuje wyższego poziomu uprawnień, aby umożliwić aplikacji Customer Insights przetwarzanie przepływu pracy jako usługi zamiast używania poświadczeń użytkownika do kolejnych uruchomień przepływu pracy.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
