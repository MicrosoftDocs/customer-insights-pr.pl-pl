---
title: Omówienie przewidywania
description: Scenariusze i opcje przewidywania, które obejmuje aplikacja Dynamics 365 Customer Insights.
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610203"
---
# <a name="predictions-overview"></a>Omówienie przewidywania

Dynamics 365 Customer Insights posiada wiele opcji, które wykorzystują sztuczną inteligencję i uczenie maszynowe do przewidywania danych.

## <a name="out-of-box-models"></a>Modele out-of-box

Najłatwiejszym sposobem na rozpoczęcie przewidywania danych są predefiniowane modele, często określane jako modele out-of-box. Wymagają one jedynie określonych danych i struktury, aby szybko generować spostrzeżenia. Są dostępne następujące modele:

# <a name="individual-consumers-b-to-c"></a>[Klienci indywidualni (B2C)](#tab/b2c)

- [Wartość okresu istnienia klienta](predict-customer-lifetime-value.md): informacje o potencjalnych przychodach klienta w czasie całej interakcji z firmą.
- [Rekomendacje produktu](predict-product-recommendation.md): sugeruje zestawy rekomendacji produktu w oparciu o zachowanie klientów o podobnych wzorcach zakupu.
- [Rezygnacja z subskrypcji](predict-subscription-churn.md): Przewidywanie, czy klient jest zagrożony zaprzestaniem korzystania z produktów lub usług subskrypcyjnych Twojej firmy.
- [Rezygnacja z transakcji](predict-transactional-churn.md): przewiduje brak możliwości zakupu produktów lub usług przez indywidualnego klienta w określonym horyzoncie czasowym.
- [Analiza nastrojów](sentiment-analysis.md): analizuje nastroje opinii klientów i identyfikuje często wymieniane aspekty biznesowe.

# <a name="business-accounts-b-to-b"></a>[Klienci biznesowi (B2B)](#tab/b2b)

- [Rezygnacja z transakcji](predict-transactional-churn.md): przewiduje brak możliwości zakupu produktów lub usług przez konto klienta w określonym horyzoncie czasowym.

---

> [!TIP]
> Zaleca się regularne odświeżanie wraz z zaktualizowanymi danymi modeli, aby upewnić się, że są one dokładne w celu poinformowania o tym sprawy dotyczącej użytkowania firmy. Dane są odświeżane ad hoc, gdy systemowe źródła danych zostaną korzystające z nowych lub zaktualizowanych źródeł danych. Jednak w takim przypadku modele będą używać tylko rescore i nadal będą korzystać z istniejących danych szkoleniowych.
>
> Konfiguruj **Harmonogram aktualizacji**, ustawiając harmonogram ponownego uczenia modelu podczas konfiguracji. Model przeszkoli się i ponownie oceni zgodnie z tym harmonogramem, który możesz zmienić w dowolnym momencie.

## <a name="azure-machine-learning-integration"></a>Integracja uczenia maszynowego Azure

Jeśli organizacja korzysta już ze scenariuszy uczenia maszynowego opartych na eksperymentach uczenia maszynowego Azure, funkcja niestandardowych modeli w Customer Insights pomaga połączyć kropki. Twórz przepływy pracy, które pomogą Ci wybrać dane, z których chcesz wygenerować spostrzeżenia i zmapować wyniki do Twoich ujednoliconych profili klientów. Aby uzyskać więcej informacji, zobacz [Niestandardowe modele uczenia maszynowego](custom-models.md).

## <a name="manage-existing-predictions"></a>Zarządzanie istniejącymi przewidywaniami

Przejdź do strony **Analizy** > **Przewidywania**. Na karcie **Moje prognozy** można wyświetlać utworzone prognozy przewidywanie, ich typ, nazwę encji wyjściowej, stan, czas ostatniej edycji przewidywania i ostatnie odświeżenie danych. Listę przewidywań można posortować według którejkolwiek kolumny.

Wybierz przewidywanie, aby wyświetlić dostępne akcje.

:::image type="content" source="media/predictions.png" alt-text="Strona Moje przewidywania.":::

- **Edytuj** przewidywanie, aby zmienić jego właściwości.
- [**Odśwież**](#refresh-a-prediction) przewidywanie, aby uwzględnić najnowsze dane.
- **Wyświetl** szczegóły przewidywania.
- [**Raport o przydatności danych wejściowych**](#view-the-input-data-usability-report) w celu wyświetlenia błędów, ostrzeżeń i zaleceń.
- **Usuń** przewidywanie.

### <a name="refresh-a-prediction"></a>Odświeżanie przewidywania

Przewidywania mogą być odświeżane w harmonogramie automatycznym lub ręcznie odświeżane na żądanie. Aby ręcznie odświeżyć wszystkie prognozy, wybierz opcję **Odśwież wszystkie**. Aby ręcznie odświeżyć prognozę, wybierz ją i wybierz opcję **Odśwież**. Aby [zaplanować automatyczne odświeżanie](schedule-refresh.md), przejdź do strony **Administrator** > **System** > **Harmonogram**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>Wyświetl raport użyteczności danych wejściowych

Raport użyteczności danych wejściowych zapewnia skonsolidowany widok błędów i ostrzeżeń, które mogą być generowane przez Twoje przewidywania out-of-box. Podaje również zalecenia, jak poprawić wydajność modelu.

Raport jest dostępny po zakończeniu procesu szkolenia modelu. Jest on tworzony dla każdego modelu osobno, niezależnie od tego czy szkolenie zakończyło się sukcesem czy nie.

Na karcie **Moje prognozy** wybierz pozycję przewidywanie i wybierz **Wprowadź raport użyteczności danych**. Z widoku szczegółów przewidywania wybierz opcję **Wprowadź raport użyteczności danych**.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Przykład raportu użyteczności danych wejściowych zawierającego tabelę z błędami, ostrzeżeniami i zaleceniami.":::

Raport zawiera:

- **Nazwa**: opisowa nazwa błędu, ostrzeżenia lub rekomendacji.
- **Krok**: faza modelowania, trenowania lub oceny, której dotyczą informacje.
- **Stan**: poziom istotności informacji (błąd, ostrzeżenie, rekomendacja).
- **Nazwa kolumny**: kolumna w encji, którą należy zmodyfikować, aby poprawić wydajność modelu.
- **Nazwa encji**: nazwa encji, którą należy zmodyfikować, aby poprawić wydajność modelu.
- **Szczegóły**: szczegółowe informacje o błędzie, ostrzeżeniu lub rekomendacji.

[!INCLUDE [footer-include](includes/footer-banner.md)]
