---
title: Tworzenie połączenia z tabelami w programie Microsoft Dataverse
description: Zaimportuj dane z zarządzanego przez Microsoft Dataverse repozytorium typu data lake.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: c470956b0453ac2558ed85acdeebba120a0ca55d
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011716"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Łączenie się z danymi w repozytorium typu data lake, którym zarządza Microsoft Dataverse

Użytkownicy Microsoft Dataverse mogą szybko łączyć się z obiektami analitycznymi w zarządzanej platformie Microsoft Dataverse.

> [!NOTE]
> Musisz być administratorem organizacji Dataverse, aby przejść dalej i wyświetlić listę encji dostępnych w zarządzanym jeziorze.

## <a name="important-considerations"></a>Ważne uwagi

1. Dane przechowywane w usługach online, np. Azure Data Lake Storage, mogą być przechowywane w innej lokalizacji niż miejsce przetwarzania danych lub przechowywanie ich w Dynamics 365 Customer Insights. Importując lub łącząc się z danymi w usługach online, użytkownik zgadza się, że dane mogą być przenoszone do programu Dynamics 365 Customer Insights i przechowywane w nim. [Dowiedz się więcej w Centrum zaufania firmy Microsoft](https://www.microsoft.com/trust-center).
2. Widoczne są tylko encje Dataverse, [których śledzenie](/power-platform/admin/enable-change-tracking-control-data-synchronization) jest włączone. Te encje można wyeksportować do data lake zarządzanego Dataverse i używać ich w aplikacji Customer Insights. W tabelach Dataverse domyślnych włączono śledzenie zmian. W przypadku tabel niestandardowych musisz włączyć śledzenie zmian. Aby sprawdzić, czy w tabeli Dataverse włączono śledzenie zmian, przejdź do [Power Apps](https://make.powerapps.com) > **Dane** > **Tabele**. Znajdź interesującą Cię tabelę i wybierz ją. Przejdź do **Ustawienia** > **Opcje zaawansowane** i przejrzyj ustawienia **Śledź zmiany**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Nawiązywanie połączenia z zarządzanym przez Dataverse repozytorium typu lake

1. Przejdź do **Dane** > **Źródła danych**.

1. Wybierz **Dodaj źródła danych**.

1. Wybierz opcję **Microsoft Dataverse**.

1. Wprowadź **Nazwa** dla źródła danych i opcjonalnie **Opis**.

1. Podaj **Adres serwera** dla organizacji Dataverse i wybierz pozycję **Zaloguj się**.

1. Z dostępnej listy wybierz tabele, które mają być pozyskane jako encje do wglądu w Customer Insights.

   > [!NOTE]
   > Jeśli niektóre tabele są już zaznaczone, mogą być używane przez inne aplikacje Dynamics 365 (takie jak Dynamics 365 Sales Insights lub Customer Service Insights). Nie można tego zmienić. Te tabele będą dostępne jako jednostki po utworzeniu źródła danych.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Okno dialogowe przedstawiające listę encji w środowisku Dataverse.":::

1. Zapisz zaznaczenie, aby rozpocząć synchronizację wybranych tabel z Dataverse. Ostatnio dodane połączenie będzie można znaleźć na stronie **Źródła danych**. Zostanie ono dodane do kolejki do odświeżenia i wyświetli liczbę jednostek jako 0, dopóki wszystkie wybrane tabele nie zostaną zsynchronizowane.

Tylko jedna źródło danych środowiska może równocześnie korzystać z tego zamego Lake zarządzanego przez Dataverse.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Edytowanie źródła danych zarządzanego przez Dataverse repozytorium typu lake

Wybraną encję edytuje się tylko po utworzeniu źródła danych. Jeśli na przykład dodano dodatkowe encje do Dataverse i chcesz je również zaimportować.
Aby połączyć się z innym data lake Dataverse, [utwórz nowe źródło danych](#connect-to-a-dataverse-managed-lake).

1. Przejdź do **Dane** > **Źródła danych**.

1. Obok źródła danych, które chcesz zaktualizować, wybierz **Edytuj**.

1. Wybierz dodatkowe encje z listy dostępnych encji i wybierz **Zapisz**.
