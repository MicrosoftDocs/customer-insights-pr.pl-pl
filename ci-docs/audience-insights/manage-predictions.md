---
title: Wspólne zadania dla scenariuszy przewidywania
description: Dowiedz się, jak zarządzać, rozwiązywać problemy i udoskonalać prognozy.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: dccb8dcca8f65f64973e46fed9d83034d58282e2
ms.sourcegitcommit: bcc47d15d4f0eacf008e4dbc09baac7f062b3ca8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2021
ms.locfileid: "6315891"
---
# <a name="manage-predictions"></a><span data-ttu-id="cd4fa-103">Zarządzaj przewidywaniami</span><span class="sxs-lookup"><span data-stu-id="cd4fa-103">Manage predictions</span></span>

<span data-ttu-id="cd4fa-104">W tym artykule omówiono kilka zadań, które są wspólne dla większości scenariuszy predykcji.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="cd4fa-105">Rozwiązywanie problemów dotyczących nieudanych przewidywań</span><span class="sxs-lookup"><span data-stu-id="cd4fa-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="cd4fa-106">Wybierz **Analizy** > **Przewidywania** i wybierz kartę **Moje przewidywania**.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="cd4fa-107">Zaznacz wielokropek pionowy obok etykiety przewidywań, dla których chcesz wyświetlić dzienniki błędów.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="cd4fa-108">Wybierz **Dzienniki**.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-108">Select **Logs**.</span></span>

1. <span data-ttu-id="cd4fa-109">Przejrzyj wszystkie błędy.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-109">Review all the errors.</span></span> <span data-ttu-id="cd4fa-110">Istnieje kilka typów błędów, które mogą wystąpić, i opisują one jaki warunek spowodował błąd.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="cd4fa-111">Na przykład błąd polegający na tym, że jest zbyt mało danych, aby dokładnie przeprowadzić przewidywanie, jest zwykle rozwiązywany dzięki załadowaniu dodatkowych danych do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="cd4fa-112">Raport dotyczący użyteczności danych wejściowych</span><span class="sxs-lookup"><span data-stu-id="cd4fa-112">Input data usability report</span></span>

<span data-ttu-id="cd4fa-113">Raport użyteczności danych wejściowych zapewnia skonsolidowany widok błędów i ostrzeżeń, które mogą być generowane przez Twoje przewidywania out-of-box.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="cd4fa-114">Podaje również zalecenia, jak poprawić wydajność modelu.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="cd4fa-115">Raport jest dostępny po zakończeniu procesu szkolenia modelu.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="cd4fa-116">Jest on tworzony dla każdego modelu osobno, niezależnie od tego czy zakończył się sukcesem czy nie.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="cd4fa-117">Wyświetl raport użyteczności danych wejściowych</span><span class="sxs-lookup"><span data-stu-id="cd4fa-117">View the input data usability report</span></span>

<span data-ttu-id="cd4fa-118">Po zakończeniu etapu szkolenia modelu out-of-box wyświetl raport:</span><span class="sxs-lookup"><span data-stu-id="cd4fa-118">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="cd4fa-119">Wybierz grupy obok nazwy modelu i wybierz **Raport dotyczący użyteczności danych wejściowych**.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-119">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="cd4fa-120">Wybierz stan modelu, wybierz pozycję **Zobacz Raport o przydatności danych wejściowych** w okienku bocznym.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-120">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="cd4fa-121">Wybierz jeden z modeli z listy i wybierz **Raport dotyczący użyteczności danych wejściowych** na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-121">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="cd4fa-122">Otwórz stronę z wynikami modelu i wybierz **Raport dotyczący użyteczności danych wejściowych** na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-122">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="cd4fa-123">Informacje zawarte w raporcie o użyteczności danych wejściowych</span><span class="sxs-lookup"><span data-stu-id="cd4fa-123">Information in the input data usability report</span></span>

<span data-ttu-id="cd4fa-124">Poniższe kolumny w raporcie zawierają informacje pomocne do poprawy danych dla modelu.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-124">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Przykład raportu użyteczności danych wejściowych zawierającego tabelę z błędami, ostrzeżeniami i zaleceniami.":::

- <span data-ttu-id="cd4fa-126">Nazwa: Opisowa nazwa błędu, ostrzeżenia lub zalecenia.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-126">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="cd4fa-127">Krok: Faza modelu, trenuj lub punktuj, informacje dotyczą.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-127">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="cd4fa-128">Stan: Poziom istotności informacji (błąd, ostrzeżenie, zalecenie).</span><span class="sxs-lookup"><span data-stu-id="cd4fa-128">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="cd4fa-129">Nazwa kolumny: Kolumna w encji, która musi zostać zmodyfikowana, aby poprawić wydajność modelu.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-129">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="cd4fa-130">Nazwa encji: Nazwa encji, którą należy zmodyfikować, aby poprawić wydajność modelu.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-130">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="cd4fa-131">Szczegóły: szczegółowe informacje o błędzie, ostrzeżenie lub zalecenia.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-131">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="cd4fa-132">Odświeżanie przewidywania</span><span class="sxs-lookup"><span data-stu-id="cd4fa-132">Refresh a prediction</span></span>

<span data-ttu-id="cd4fa-133">Przewidywania będą odświeżane automatycznie w oparciu o ten sam [harmonogram odświeżania danych](system.md#schedule-tab) skonfigurowany w ustawieniach.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-133">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="cd4fa-134">Można je również ręcznie odświeżyć.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-134">You can refresh them manually too.</span></span>

1. <span data-ttu-id="cd4fa-135">Wybierz **Analizy** > **Przewidywania** i wybierz kartę **Moje przewidywania**.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-135">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="cd4fa-136">Wybierz pionowy wielokropek obok przewidywania, które chcesz odświeżyć.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-136">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="cd4fa-137">Wybierz **Odśwież**.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-137">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="cd4fa-138">Usuń przewidywanie</span><span class="sxs-lookup"><span data-stu-id="cd4fa-138">Delete a prediction</span></span>

<span data-ttu-id="cd4fa-139">Usunięcie przewidywanie usuwa również jej encję wyjściową.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-139">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="cd4fa-140">Wybierz **Analizy** > **Przewidywania** i wybierz kartę **Moje przewidywania**.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-140">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="cd4fa-141">Wybierz pionowy wielokropek obok przewidywania, które chcesz usunąć.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-141">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="cd4fa-142">Wybierz **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-142">Select **Delete**.</span></span>
