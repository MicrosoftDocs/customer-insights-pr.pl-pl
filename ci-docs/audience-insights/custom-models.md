---
title: Niestandardowe modele Uczenie maszynowe | Microsoft Docs
description: Praca z modelami niestandardowymi z Uczenie maszynowe Azure w Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34489faaecc5da1ce3dd68d799b3e0e0d9672ab7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267247"
---
# <a name="custom-machine-learning-models"></a>Niestandardowe modele Uczenie maszynowe

**Analizy** > **Modele niestandardowe** umożliwia zarządzanie przepływami pracy na podstawie modeli Uczenie maszynowe platformy Azure. Przepływy pracy pomagają wybrać dane, z których chcesz generować szczegółowe informacje, i odwzorować wyniki na ujednolicone dane klientów. Aby uzyskać więcej informacji na temat budowania niestandardowych modeli ML, zobacz [Korzystanie z modeli opartych na Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Odopowiedzialne AI

Przewidywania umożliwiają zwiększanie komfortu obsługi klienta, poprawianie funkcji biznesowych i strumienia przychodów. Stanowczo zaleca się, aby zrównoważyć wartość przewidywanie w stosunku do oddziaływania i skutków, które można wprowadzić w sposób etyczny. Dowiedz się więcej o tym, jak firma Microsoft [zajmuje się odpowiedzialną sztuczną inteligencją](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Użytkownik może również zapoznać się [z technikami i procesami dotyczącymi odpowiedzialności za uczenie maszynowe](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) dotyczące usługi Azure Machine Learning.

## <a name="prerequisites"></a>Wymagania wstępne

- Obecnie ta funkcja obsługuje usługi sieci Web opublikowane za pośrednictwem potoków wsadowych usługi [Machine Learning Studio (klasyczna)](https://studio.azureml.net) i [Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).

- Aby korzystać z tej funkcji, potrzebujesz konta magazynu Azure Data Lake Gen2 skojarzonego z wystąpieniem usługi Azure Studio. Aby uzyskać więcej informacji, zobacz [Tworzenie konta magazynu Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)

## <a name="add-a-new-workflow"></a>Dodaj nowy przepływ pracy

1. Przejdź do **Analizy** > **Niestandardowe modele** i wybierz **Nowy przepływ pracy**.

1. W polu **Nazwa** nadaj modelowi niestandardowemu rozpoznawalną nazwę.

   > [!div class="mx-imgBorder"]
   > ![Zrzut ekranu okienka Nowy przepływ pracy](media/new-workflowv2.png "Zrzut ekranu okienka Nowy przepływ pracy")

1. Wybierz organizację zawierającą usługę sieci Web w **Dzierżawa zawierająca usługę sieci Web**.

1. Jeśli subskrypcja Uczenie maszynowe Azure znajduje się w innej dzierżawie niż usługa Customer Insights, wybierz **Zaloguj się**, używając swoich poświadczeń dla wybranej organizacji.

1. Wybierz **Obszary robocze** skojarzone z daną usługą sieci Web. Na liście znajdują się dwie sekcje, jedna dla Azure Machine Learning w wersji 1 (Machine Learning Studio (klasyczna)) i Azure Machine Learning w wersji 2 (Azure Machine Learning). Jeśli nie masz pewności, który obszar roboczy jest odpowiedni dla Twojej usługi internetowej Machine Learning Studio (klasycznej), wybierz opcję **Dowolny**.

1. Wybierz usługę sieciową Machine Learning Studio (klasyczną) lub potok Azure Machine Learning na liście rozwijanej **Uslugi sieci Web, która zawiera model**. Następnie wybierz **Dalej**.
   - Więcej informacji o [publikowaniu usługi sieci Web w Machine Learning Studio (klasyczny)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Dowiedz się więcej o [publikowaniu potoku w usłudze Azure Machine Learning przy użyciu projektanta](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) lub [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). Potok musi zostać opublikowany w [punkcie końcowym potoku](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Dla **Dane wejściowe usług sieci Web**, wybierz pasującą **Encję** z analiz odbiorców i wybierz **Dalej**.
   > [!NOTE]
   > Przepływ pracy modelu niestandardowego zastosuje heurystykę do mapowania pól wejściowych usługi sieci Web do atrybutów encji na podstawie nazwy i typu danych pola. Jeśli nie można zamapować pola usługi sieci Web na jednostkę, pojawi się błąd.

   > [!div class="mx-imgBorder"]
   > ![Konfiguruj przepływ pracy](media/intelligence-screen2-updated.png "Konfiguruj przepływ pracy")
   
1. W kroku **Parametry wyjściowe modelu** ustaw następujące właściwości:
   - Machine Learning Studio (klasyczna)
      1. Wprowadź nazwę **Encji wyjściowej**, do którego ma zostać wlany wyniki usługi sieci Web.
   - Uczenie maszynowe Azure
      1. Wprowadź nazwę **Encji wyjściowej**, do którego ma zostać wlany wyniki strumienia.
      1. Z listy rozwijanej wybierz **Nazwę parametru magazynu danych wyjściowych** potoku wsadowego.
      1. Z listy rozwijanej wybierz **Nazwę parametru ścieżki danych wyjściowych** potoku wsadowego.
      
      > [!div class="mx-imgBorder"]
      > ![Panel parametrów wyjściowych modelu](media/intelligence-screen3-outputparameters.png "Panel parametrów wyjściowych modelu")

1. Wybierz pasujący atrybut z listy rozwijanej **Identyfikator klienta w wynikach**, która identyfikuje klientów, i wybierz **Zapisz**.
   
   > [!div class="mx-imgBorder"]
   > ![Powiązanie wyników z okienkiem Dane klient](media/intelligence-screen4-relatetocustomer.png "Powiązanie wyników z okienkiem Dane klient")

1. Zostanie wyświetlony ekran **Zapisany przepływ pracy** ze szczegółowymi informacjami na temat przepływu pracy.    
   Jeśli skonfigurowano przepływ pracy dla potoku Azure Machine Learning, szczegółowe informacje o odbiorcach zostaną dołączone do obszaru roboczego zawierającego potok. Usługa analizy odbiorców będzie mieć rolę **Współautora** w obszarze roboczym Azure.

1. Wybierz **Gotowe**.

1. Można teraz uruchomić przepływ pracy ze strony **Modele niestandardowe**.

## <a name="edit-a-workflow"></a>Edytuj przepływ pracy

1. Na stronie **Modele niestandardowe** wybierz wielokropek pionowy w kolumnie **Akcje** obok utworzonego uprzednio przepływu pracy i wybierz **Edytuj**.

1. Można zaktualizować rozpoznawalną nazwę przepływu pracy w polu **Wyświetlana nazwa**, ale nie można zmienić skonfigurowanej usługi sieci web ani potoku. Wybierz **Dalej**.

1. Dla **Dane wejściowe usług sieci Web**, można aktualizować pasującą **Encję** z analiz odbiorców. Następnie wybierz **Dalej**.

1. W kroku **Parametry wyjściowe modelu** ustaw następujące właściwości:
   - Machine Learning Studio (klasyczna)
      1. Wprowadź nazwę **Encji wyjściowej**, do którego ma zostać wlany wyniki usługi sieci Web.
   - Uczenie maszynowe Azure
      1. Wprowadź nazwę **Encji wyjściowej**, do którego ma zostać wlany wyniki strumienia.
      1. Wybierz **Nazwa parametru magazynu danych wyjściowych** dla planowanego strumienia testowego.
      1. Wybierz **Nazwa parametru ścieżki danych wyjściowych** dla planowanego strumienia testowego.

1. Wybierz pasujący atrybut z listy rozwijanej **Identyfikator klienta w wynikach**, która identyfikuje klientów, i wybierz **Zapisz**.
   Musisz wybrać atrybut z danych wyjściowych wnioskowania o wartościach podobnych do kolumny Identyfikator klienta encji Klient. Jeśli nie masz takiej kolumny w swoim zbiorze danych, wybierz atrybut, który jednoznacznie identyfikuje wiersz.

## <a name="run-a-workflow"></a>Uruchamianie przepływu pracy

1. Na stronie **Modele niestandardowe**, wybierz wielokropek pionowy w kolumnie **Akcje** obok utworzonego uprzednio przepływu pracy.

1. Wybierz **Uruchom**.

Przepływ pracy jest również uruchamiany automatycznie przy każdym planowanym odświeżeniu. Dowiedz się więcej na temat [konfigurowania zaplanowanego odświeżania](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Usuń przepływ pracy

1. Na stronie **Modele niestandardowe**, wybierz wielokropek pionowy w kolumnie **Akcje** obok utworzonego uprzednio przepływu pracy.

1. Wybierz **Usuń** i potwierdź usunięcie.

Przepływ pracy zostanie usunięty. [Encja](entities.md) utworzona w momencie utworzenia przepływu pracy pozostanie i będzie można ją wyświetlać na stronie **Encje**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]