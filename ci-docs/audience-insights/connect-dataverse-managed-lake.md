---
title: Tworzenie połączenia z tabelami w programie Microsoft Dataverse
description: Zaimportuj dane z zarządzanego przez Microsoft Dataverse repozytorium typu data lake.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: ffeccffd0e353cb5490b537552d585c184ad672f9c806e673bd04743214ad068
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033093"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Łączenie się z danymi w repozytorium typu data lake, którym zarządza Microsoft Dataverse

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Ten artykuł zawiera informacje o tym, jak użytkownicy Dataverse mogą szybko łączyć się ze swoimi jednostkami analitycznymi w zarządzanym lake Dataverse. Aby kontynuować pracę i zobaczyć listę encji dostępnych w zarządzany repozytorium typu lake należy mieć uprawnienia administratora w organizacji Dataverse.

## <a name="important-considerations"></a>Ważne uwagi

Dane przechowywane w usługach online, np. Azure Data Lake Storage, mogą być przechowywane w innej lokalizacji niż miejsce przetwarzania danych lub przechowywanie ich w Dynamics 365 Customer Insights. Importując lub łącząc się z danymi w usługach online, użytkownik zgadza się, że dane mogą być przenoszone do programu Dynamics 365 Customer Insights i przechowywane w nim. [Dowiedz się więcej w Centrum zaufania firmy Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-dataverse-managed-lake"></a>Nawiązywanie połączenia z zarządzanym przez Dataverse repozytorium typu lake

1. W analizach odbiorców przejdź do **Dane** > **Źródła danych**.

2. Wybierz **Dodaj źródła danych**.

3. Wybierz pozycję **Połącz z zarządzanym lake Microsoft Dataverse** i wybierz pozycję **Dalej**.

4. Wprowadź **Nazwę** źródła danych i wybierz **Dalej**. Wytyczne dotyczące nazw: 
   - Rozpocznij od litery.
   - Używaj tylko liter i liczb. Spacje i znaki specjalne są niedozwolone.
   - Użyj między 3 do 64 znaków.

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