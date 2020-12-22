---
title: Połącz się z encjami w Lake zarządzanym przez Common Data Service
description: Zaimportuj dane z zarządzanego przez Common Data Service repozytorium typu data lake.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643411"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Łączenie się z danymi w repozytorium typu data lake, którym zarządza Common Data Service

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

W tym artykule zamieszczono informacje dotyczące tego, w jaki sposób istniejący klienci Dynamics 365 mogą szybko połączyć się z encjami analitycznymi w zarządzanym przez Common Data Service repozytorium typu lake. Aby kontynuować pracę i zobaczyć listę encji dostępnych w zarządzany repozytorium typu lake należy mieć uprawnienia administratora w organizacji Common Data Service.

## <a name="important-considerations"></a>Ważne uwagi

Dane przechowywane w usługach online, np. Azure Data Lake Storage, mogą być przechowywane w innej lokalizacji niż miejsce przetwarzania danych lub przechowywanie ich w Dynamics 365 Customer Insights. Importując lub łącząc się z danymi w usługach online, użytkownik zgadza się, że dane mogą być przenoszone do programu Dynamics 365 Customer Insights i przechowywane w nim. [Dowiedz się więcej w Centrum zaufania firmy Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Nawiązywanie połączenia z zarządzanym przez Common Data Service repozytorium typu lake

1. W analizach odbiorców przejdź do **Dane** > **Źródła danych**.

2. Wybierz **Dodaj źródła danych**.

3. Wybierz **Połącz z Common Data Service** i wybierz **Dalej**.

4. Wprowadź **Nazwę** źródła danych i wybierz **Dalej**.

5. Wprowadź **Adres serwera** dla organizacji Common Data Service i wybierz **Zaloguj się**.

   > [!div class="mx-imgBorder"]
   > ![Okno dialogowe umożliwiające wprowadzanie adresu serwera Common Data Service](media/enter-CDS-org-details.png)

6. Wybierz encje, które chcesz pozyskać z dostępnej listy.    

   > [!NOTE]
   > Jeśli niektóre encje są już wybrane, mogą być używane przez inne aplikacje Dynamics 365 (na przykład Dynamics 365 Sales Insights lub Customer Service Insights). Nie można tego zmienić. Te encje będą dostępne po utworzeniu źródła danych.

   > [!div class="mx-imgBorder"]
   > ![Okno dialogowe pokazujące listę encji w organizacji Common Data Service](media/select-analytical-entities.png)

7. Aby rozpocząć synchronizowanie zaznaczonych encji z zarządzanym przez Common Data Service repozytorium typu lake zapisz wybrane opcje. Ostatnio dodane połączenie będzie można znaleźć na stronie **Źródła danych**. Element zostanie umieszczony w kolejce do odświeżenia i będzie pokazywał liczbę encji jako 0, aż do chwili zsynchronizowania wszystkich encji.

Tylko jedna źródło danych środowiska może równocześnie korzystać z tego zamego Lake zarządzanego przez Common Data Service.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Edytowanie źródła danych zarządzanego przez Common Data Service repozytorium typu lake

Wybraną encję edytuje się tylko po utworzeniu źródła danych. Jeśli na przykład dodano dodatkowe encje do Common Data Service i chcesz je również zaimportować.    
Aby połączyć z innym Common Data Service, [utwórz nowe źródło danych](#connect-to-a-common-data-service-managed-lake).

1. W analizach odbiorców przejdź do **Dane** > **Źródła danych**.

2. Kliknij wielokropek obok źródła danych, który chcesz zaktualizować.

3. Wybierz opcję **Edytuj** z listy.

4. Wybierz dodatkowe encje z listy dostępnych encji i wybierz **Zapisz**.
