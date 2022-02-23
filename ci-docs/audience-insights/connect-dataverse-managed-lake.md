---
title: Tworzenie połączenia z tabelami w programie Microsoft Dataverse
description: Zaimportuj dane z zarządzanego przez Microsoft Dataverse repozytorium typu data lake.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: 436345d8932820eb4c517a9e9164b1377c1f62d3
ms.sourcegitcommit: 3807202283dd116a30f900a163d8141db621e5a8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/28/2022
ms.locfileid: "8046438"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Łączenie się z danymi w repozytorium typu data lake, którym zarządza Microsoft Dataverse



Ten artykuł dostarcza informacji o tym, jak użytkownicy Dataverse mogą szybko połączyć się z jednostkami analitycznymi w zarządzanym jeziorze Microsoft Dataverse. 

> [!NOTE]
> Musisz być administratorem organizacji Dataverse, aby przejść dalej i wyświetlić listę encji dostępnych w zarządzanym jeziorze.

## <a name="important-considerations"></a>Ważne uwagi

Dane przechowywane w usługach online, np. Azure Data Lake Storage, mogą być przechowywane w innej lokalizacji niż miejsce przetwarzania danych lub przechowywanie ich w Dynamics 365 Customer Insights. Importując lub łącząc się z danymi w usługach online, użytkownik zgadza się, że dane mogą być przenoszone do programu Dynamics 365 Customer Insights i przechowywane w nim. [Dowiedz się więcej w Centrum zaufania firmy Microsoft](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-dataverse-managed-lake"></a>Nawiązywanie połączenia z zarządzanym przez Dataverse repozytorium typu lake

1. W analizach odbiorców przejdź do **Dane** > **Źródła danych**.

2. Wybierz **Dodaj źródła danych**.

3. Wybierz **Microsoft Dataverse**, a następnie wybierz **Dalej**.

4. Wprowadź **Nazwę** źródła danych i wybierz **Dalej**. 

5. Podaj **Adres serwera** dla organizacji Dataverse i wybierz pozycję **Zaloguj się**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Ekran w kroku pozyskiwania danych, w którym użytkownik może wprowadzić adres URL środowiska Dataverse.":::

6. Wybierz tabele, które chcesz pozyskać jako encje dla szczegółowych informacji odbiorcy z dostępnej listy.    

   > [!NOTE]
   > Jeśli niektóre tabele są już zaznaczone, mogą być używane przez inne aplikacje Dynamics 365 (takie jak Dynamics 365 Sales Insights lub Customer Service Insights). Nie można tego zmienić. Te tabele będą dostępne jako jednostki po utworzeniu źródła danych.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Okno dialogowe przedstawiające listę encji w środowisku Dataverse.":::

7. Zapisz zaznaczenie, aby rozpocząć synchronizację wybranych tabel z Dataverse. Ostatnio dodane połączenie będzie można znaleźć na stronie **Źródła danych**. Zostanie ono dodane do kolejki do odświeżenia i wyświetli liczbę jednostek jako 0, dopóki wszystkie wybrane tabele nie zostaną zsynchronizowane.

Tylko jedna źródło danych środowiska może równocześnie korzystać z tego zamego Lake zarządzanego przez Dataverse.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Edytowanie źródła danych zarządzanego przez Dataverse repozytorium typu lake

Wybraną encję edytuje się tylko po utworzeniu źródła danych. Jeśli na przykład dodano dodatkowe encje do Dataverse i chcesz je również zaimportować.    
Aby połączyć się z innym data lake Dataverse, [utwórz nowe źródło danych](#connect-to-a-dataverse-managed-lake).

1. W analizach odbiorców przejdź do **Dane** > **Źródła danych**.

2. Kliknij wielokropek obok źródła danych, który chcesz zaktualizować.

3. Wybierz opcję **Edytuj** z listy.

4. Wybierz dodatkowe encje z listy dostępnych encji i wybierz **Zapisz**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
