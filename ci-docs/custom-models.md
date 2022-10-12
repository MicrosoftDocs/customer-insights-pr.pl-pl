---
title: Niestandardowe modele Uczenie maszynowe | Microsoft Docs
description: Praca z modelami niestandardowymi z Uczenie maszynowe Azure w Dynamics 365 Customer Insights.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 89553b511d249fd586e36a1c4944a977513b0643
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609759"
---
# <a name="custom-machine-learning-models"></a>Niestandardowe modele Uczenie maszynowe

> [!NOTE]
> Wsparcie dla Machine Learning Studio (classic) zakończy się 31 sierpnia 2024 roku. Zalecamy przejście na [Azure Machine Learning](/azure/machine-learning/overview-what-is-azure-machine-learning) do tej daty.
>
> Od 1 grudnia 2021 roku nie będzie można tworzyć nowych zasobów Machine Learning Studio (klasycznego). Do 31 sierpnia 2024 roku możecie nadal korzystać z istniejących zasobów Machine Learning Studio (classic). Aby uzyskać więcej informacji, zobacz [Migracja do Azure Machine Learning](/azure/machine-learning/migrate-overview).

Niestandardowe modele umożliwiają zarządzanie przepływami pracy opartymi na modelach Azure Machine Learning. Przepływy pracy pomagają wybrać dane, z których chcesz generować szczegółowe informacje, i odwzorować wyniki na ujednolicone dane klientów. Aby uzyskać więcej informacji na temat budowania niestandardowych modeli ML, zobacz [Korzystanie z modeli opartych na Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Wymagania wstępne

- Usługi webowe publikowane przez [partie w potoku Azure Machine Learning](/azure/machine-learning/concept-ml-pipelines).
- Potok musi zostać opublikowany w [punkcie końcowym potoku](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).
- Aby korzystać z tej funkcji, potrzebujesz [konta magazynu Azure Data Lake Gen2](/azure/storage/blobs/data-lake-storage-quickstart-create-account) skojarzonego z wystąpieniem usługi Azure Studio.
- W przypadku obszarów roboczych usługi Azure Machine Learning z potokami musisz mieć uprawnienia dostępu administratora typu Właściciel lub Użytkownik do obszaru roboczego usługi Azure Machine Learning.

  > [!NOTE]
  > Dane są przesyłane między wystąpieniami rozwiązania Customer Insights a wybranymi usługami internetowymi lub potokami platformy Azure w przepływie pracy. Podczas przesyłania danych do usługi platformy Azure upewnij się, że usługa jest skonfigurowana do przetwarzania danych w sposób (oraz w lokalizacji) umożliwiający zachowanie zgodności z wymaganiami prawnymi lub regulacyjnymi dotyczącymi danych Twojej organizacji.

## <a name="add-a-new-workflow"></a>Dodaj nowy przepływ pracy

1. Przejdź do **Analizy** > **Niestandardowe modele** i wybierz **Nowy przepływ pracy**.

1. Podaj rozróżnianą **Nazwę**.

   :::image type="content" source="media/new-workflowv2.png" alt-text="Zrzut ekranu okienka Nowy przepływ pracy.":::

1. Wybierz organizację zawierającą usługę sieci Web w **Dzierżawa zawierająca usługę sieci Web**.

1. Jeśli subskrypcja Uczenie maszynowe Azure znajduje się w innej dzierżawie niż usługa Customer Insights, wybierz **Zaloguj się**, używając swoich poświadczeń dla wybranej organizacji.

1. Wybierz **Obszary robocze** skojarzone z daną usługą sieci Web.

1. Wybierz potok Azure Machine Learning z rozwijanej listy **Serwis internetowy, który zawiera twój model** rozwijany. Następnie wybierz **Dalej**.
   Dowiedz się więcej o [publikowaniu potoku w usłudze Azure Machine Learning przy użyciu projektanta](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) lub [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).

1. Dla **Dane wejściowe usług sieci Web**, wybierz pasującą **Encję** z Customer Insights. Następnie wybierz **Dalej**.
   > [!NOTE]
   > Przepływ pracy modelu niestandardowego zastosuje heurystykę do mapowania pól wejściowych usługi sieci Web do atrybutów encji na podstawie nazwy i typu danych pola. Jeśli nie można zamapować pola usługi sieci Web na jednostkę, pojawi się błąd.

   :::image type="content" source="media/intelligence-screen2-updated.png" alt-text="Konfiguruj przepływ pracy.":::

1. W **Parametry wyjściowe modelu** ustaw następujące właściwości:
   - **Nazwa encji** dla wyników wyjściowych potoku
   - Wybierz **Nazwa parametru magazynu danych wyjściowych** dla planowanego strumienia partii
   - Wybierz **Nazwa parametru ścieżki danych wyjściowych** dla planowanego strumienia partii

   :::image type="content" source="media/intelligence-screen3-outputparameters.png" alt-text="Panel parametrów wyjściowych modelu.":::

1. Wybierz pasujący atrybut **Identyfikator klienta w wynikach**, który identyfikuje klientów i wybierz **Zapisz**.

   :::image type="content" source="media/intelligence-screen4-relatetocustomer.png" alt-text="Powiązanie wyników z okienkiem Dane klient.":::

   Zostanie wyświetlony ekran **Zapisany przepływ pracy** ze szczegółowymi informacjami na temat przepływu pracy. Jeśli skonfigurowano przepływ pracy dla potoku uczenia maszynowego Azure, usługa Customer Insights dołącza do obszaru roboczego zawierającego potok. Usługa Customer Insights otrzyma rolę **Współautor** w obszarze roboczym platformy Azure.

1. Wybierz pozycję **Gotowe**. Zostanie wyświetlona strona **Modele niestandardowe**.

1. Wybierz wielokropek pionowy (&vellip;) dla prepływu pracy i wybierz opcję **Uruchom**. Przepływ pracy jest również uruchamiany automatycznie przy każdym [planowanym odświeżeniu](schedule-refresh.md).

## <a name="manage-an-existing-workflow"></a>Zarządzanie istniejącym przepływem pracy

Przejdź **Analiza** > **Modele niestandardowe**, aby wyświetlić utworzone przepływy pracy.

Wybierz przepływ pracy, aby wyświetlić dostępne akcje.

- **Edytuj** przepływ pracy
- **Uruchamianie** przepływu pracy
- [**Usuń**](#delete-a-workflow) przepływ pracy

### <a name="edit-a-workflow"></a>Edytuj przepływ pracy

1. Przejdź do opcji **Analiza** > **Modele niestandardowe**.

1. Wraz z przepływem pracy, który chcesz zaktualizować, wybierz z wielokropek pionowy (&vellip;) i wybierz **Edytuj**.

1. W razie potrzeby zmień **Nazwę wyświetlaną** i wybierz przycisk **Dalej**.

1. Dla **Dane wejściowe usług sieci Web**, w razie potrzeby możesz aktualizować pasującą **Encję** z Customer Insights. Następnie wybierz **Dalej**.

1. W **Parametry wyjściowe modelu** zmień którekolwiek z poniższych opcji:
   - **Nazwa encji** dla wyników wyjściowych potoku
   - Wybierz **Nazwa parametru magazynu danych wyjściowych** dla planowanego strumienia partii
   - Wybierz **Nazwa parametru ścieżki danych wyjściowych** dla planowanego strumienia partii

1. Zmień pasujący atrybut z **Identyfikator klienta w wynikach**, by zidentyfikować klientów. Wybierz atrybut z danych wyjściowych wnioskowania o wartościach podobnych do kolumny Identyfikator klienta encji Klient. Jeśli brak takiej kolumny w swoim zbiorze danych, wybierz atrybut, który jednoznacznie identyfikuje wiersz.

1. Wybierz pozycję **Zapisz**

### <a name="delete-a-workflow"></a>Usuń przepływ pracy

1. Przejdź do opcji **Analiza** > **Modele niestandardowe**.

1. Wraz z przepływem pracy, który chcesz usunąć, wybierz z wielokropek pionowy (&vellip;) i wybierz **Usuń**.

1. Potwierdź usunięcie.

Przepływ pracy zostanie usunięty. [Encja](entities.md) utworzona w momencie utworzenia przepływu pracy pozostanie i będzie można ją wyświetlać na stronie **Dane** > **Encje**.

## <a name="view-the-results"></a>Wyświetlanie wyników

Wyniki z przepływu pracy są przechowywane w nazwie encji skonfigurowanej dla **Parametrów danych wyjściowych modelu**. Dostęp do tych danych ze [strony **Dane** > **Encje**](entities.md) lub za pomocą [dostępu do interfejsu API](apis.md).

### <a name="api-access"></a>Dostęp za pośrednictwem interfejsu API

Aby określone zapytanie OData mogło uzyskać dane z encji modelu niestandardowego, użyj następującego formatu:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Zastąp identyfikator `<your instance id>` identyfikatorem środowiska Customer Insights, który jest wyświetlany na pasku adresu przeglądarki podczas uzyskiwania dostępu do aplikacji Customer Insights.

1. Zastąp `<custom model output entity>`nazwę encji podaną dla **parametrów wyjściowych modelu**.

1. Zastąp wartość `<guid value>` identyfikatorem klienta, któremu chcesz przydzielić prawa dostępu. Ten identyfikator ten można znaleźć na [stronie profilów klientów](customer-profiles.md) w polu CustomerID.

## <a name="frequently-asked-questions"></a>Często zadawane pytania

- Dlaczego podczas konfigurowania przepływu pracy modelu niestandardowego nie jest widzę mojego potoku?
  Często przyczyną tego problemu jest błąd konfiguracji, który występuje w potoku. Upewnij się, że [parametr wejściowy został skonfigurowany](azure-machine-learning-experiments.md#dataset-configuration) i [parametry i magazynu danych wyjściowych również są skonfigurowane](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights).

- Co oznacza błąd „Nie można zapisać przepływu pracy analizy”? 
  Użytkownicy zwykle widzą ten komunikat o błędzie, jeśli nie mają uprawnień administratora dostępu typu Właściciel lub Użytkownik w obszarze roboczym. Użytkownik potrzebuje wyższego poziomu uprawnień, aby umożliwić aplikacji Customer Insights przetwarzanie przepływu pracy jako usługi zamiast używania poświadczeń użytkownika do kolejnych uruchomień przepływu pracy.

- Czy jest obsługiwany prywatny punkt końcowy/łącze prywatne dla przepływu pracy modelu niestandardowego?
  Rozwiązanie Customer Insights nie obsługuje obecnie prywatnych punktów końcowych standardowych modeli, ale jest dostępne obejście ręczne. Skontaktuj się z działem pomocy technicznej, aby uzyskać szczegółowe informacje.

## <a name="responsible-ai"></a>Odopowiedzialne AI

Przewidywania umożliwiają zwiększanie komfortu obsługi klienta, poprawianie funkcji biznesowych i strumienia przychodów. Stanowczo zaleca się, aby zrównoważyć wartość przewidywanie w stosunku do oddziaływania i skutków, które można wprowadzić w sposób etyczny. Dowiedz się więcej o tym, jak firma Microsoft [zajmuje się odpowiedzialną sztuczną inteligencją](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Użytkownik może również zapoznać się [z technikami i procesami dotyczącymi odpowiedzialności za uczenie maszynowe](/azure/machine-learning/concept-responsible-ml) dotyczące usługi Azure Machine Learning.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

[!INCLUDE [footer-include](includes/footer-banner.md)]
