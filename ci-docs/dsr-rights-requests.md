---
title: Żądania podmiotów danych osobowych (DSR) w kontekście rozporządzenia RODO | Microsoft Docs
description: Odpowiadaj na żądania osób, których dotyczą dane, dotyczące możliwości wglądu odbiorców w Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6faaeb6a1ee34c3e5c8e7d465b37cee589bc920c
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483694"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Żądania osób, których dotyczą dane, w kontekście rozporządzenia RODO

Ogólne rozporządzenie o ochronie danych (RODO) w Unii Europejskiej obowiązuje od 25 maja 2018 roku. Daje istotne prawa osobom w odniesieniu do ich danych. Zasadniczo przepisy GDPR dotyczą ochrony i zapewnienia prawa do prywatności osób fizycznych. Więcej informacji na temat zaangażowania firmy Microsoft w kwestie bezpieczeństwa i zgodności można znaleźć na stronie [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Dokładamy wszelkich starań, aby pomóc klientom w spełnianiu ich wymagań dotyczących rozporządzenia RODO. Obejmuje prawo usuwania i eksportowania danych, które zawierają dane osobowe, takie jak identyfikatory użytkowników, numery telefonów i adresy e-mail. Administratorzy mogą implementować żądania użytkowników w celu usuwania lub eksportowania danych osobowych.

## <a name="audience-insights"></a>Wyniki analiz odbiorców

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Odpowiadanie na żądania usunięcia przez osobę, której dane dotyczą, dotyczące RODO dotyczące możliwości wglądu odbiorców w Dynamics 365 Customer Insights

„Prawo do usunięcia danych osobowych” poprzez usunięcie prywatnych danych klienta organizacji jest kluczową ochroną w Ogólnym rozporządzeniu o ochronie danych (RODO). Usuwanie danych osobowych polega na usunięciu wszystkich danych osobowych i dzienników generowanych przez system, poza informacjami dotyczącymi dziennika inspekcji.

#### <a name="manage-data-subject-delete-requests"></a>Zarządzanie żądaniami usuwania danych

Analiza odbiorców oferuje następujące doświadczenia w produkcie, które usuwają dane osobowe dotyczące konkretnego użytkownika lub klienta:

- **Zarządzanie żądaniami usuwania danych klienta**: dane klienta w Customer Insights są pobierane z oryginalnych źródeł danych spoza Customer Insights. Wszystkie żądania dotyczące usuwania danych według RODO muszą zostać wykonane w oryginalnym źródle danych.
- **Zarządzanie żądaniami usunięcia danych użytkownika Customer Insights**: Dane dla użytkowników są tworzone przez Customer Insights. Wszystkie żądania dotyczące usuwania danych według RODO muszą zostać wykonane w Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Zarządzanie żądaniami usunięcia danych klienta

Administrator Customer Insights może wykonać poniższe kroki w celu usunięcia danych klienta, które zostały usunięte ze źródła danych:

1. Zaloguj się w Dynamics 365 Customer Insights.
2. W analizach odbiorców przejdź do **Dane** > **Źródła danych**
3. Dla każdego źródła danych z listy, które zawiera usunięte dane klienta:
   1. Wybierz (...) i wybierz **Odśwież**.
   2. Sprawdź status źródła danych w **Stan**. Znacznik wyboru oznacza, że odświeżanie zakończyło się powodzeniem. Trójkąt ostrzegawczy oznacza, że wystąpił problem. Jeśli zostanie wyświetlony trójkąt ostrzegawczy, skontaktuj się z D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Zarządzanie żądaniami usunięcia danych klienta według RODO.](audience-insights/media/gdpr-data-sources.png "Zarządzanie żądaniami usunięcia danych klienta według RODO")

##### <a name="manage-delete-requests-for-user-data"></a>Zarządzanie żądaniami usunięcia danych użytkownika

Administrator Customer Insights może wykonać poniższe kroki w celu usunięcia danych użytkownika Customer Insights:

1. Zaloguj się w Dynamics 365 Customer Insights.
2. W analizach odbiorców przejdź do **Administrator** > **Uprawnienia**.
3. Zaznacz pole wyboru dla użytkownika, którego chcesz usunąć.
4. Wybierz **Usuń**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Odpowiadanie na żądania podmiotów o eksport danych osobowych zgodnie z RODO

W ramach naszych starań, aby wspierać użytkowników w trakcie wdrażania Ogólnego rozporządzenia o ochronie danych (RODO), opracowano dokumentację ułatwiającą przygotowanie. W tej dokumentacji opisano kroki, które możesz podjąć dzisiaj, aby zapewnić zgodność z RODO podczas korzystania ze statystyk odbiorców.

#### <a name="manage-export-and-view-requests"></a>Zarządzanie żądaniami eksportowania i wyświetlania

Prawo do przenoszenia danych osobowych pozwala podmiotowi danych składać wniosek o kopię danych osobowych w formacie elektronicznym („struktura, powszechnie stosowana, czytelna i wieloprogramowa”), który może być przekazywany innemu kontrolerowi danych.

##### <a name="export-customer-data-tenant-admin"></a>Eksportowanie danych klienta (Administrator dzierżawcy)

W celu wyeksportowania danych administrator dzierżawy może wykonać następujące kroki:

1. Wysłąć wiadomość e-mail na adres D365CI@microsoft.com określając adres e-mail klienta w żądaniu. Zespół Customer Insights wyśle wiadomość e-mail na adres e-mail zarejestrowanego administratora dzierżawcy, pytając o potwierdzenie wyeksportowania danych.
2. Zatwierdź potwierdzenie wyeksportowania danych dla żądanego klienta.
3. Pobierz eksportowane dane za pomocą adresu e-mail administratora dzierżawcy.

##### <a name="export-user-data-tenant-admin"></a>Eksportuj dane użytkownika (administrator dzierżawy)

1. Wysłąć wiadomość e-mail na adres D365CI@microsoft.com określając adres e-mail użytkownika w żądaniu. Zespół Customer Insights wyśle wiadomość e-mail na adres e-mail zarejestrowanego administratora dzierżawcy, pytając o potwierdzenie wyeksportowania danych.
2. Zatwierdź potwierdzenie wyeksportowania danych dla żądanego użytkownika.
3. Pobierz eksportowane dane za pomocą adresu e-mail administratora dzierżawcy.

## <a name="engagement-insights"></a>Szczegółowe informacje o zaangażowaniu

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>Usuwanie i eksportowanie danych zdarzeń zawierających informacje umożliwiające identyfikację użytkownika końcowego

W poniższych sekcjach opisano sposób usuwania i eksportowania danych zdarzeń, które mogą zawierać dane osobowe.

Usuwanie lub eksportowanie danych:

1. Oznaczenie właściwości zdarzenia zawierającego dane z informacjami osobistymi.
2. Usuwanie lub eksportowanie danych skojarzonych z określonymi wartościami (na przykład: określonym identyfikatorem użytkownika).

#### <a name="tag-and-update-event-properties"></a>Oznaczanie i aktualizowanie właściwości zdarzenia

Dane osobowe są oznaczone na poziomie właściwości zdarzenia. Najpierw należy oznaczać właściwości, które mają być usunięte lub wyeksportowane.

Aby oznaczyć właściwość zdarzenia jako zawierającą informacje osobowe, wykonaj następujące kroki:

1. Otwórz obszar roboczy zawierający zdarzenie.

1. Przejdź do **Dane** > **Zdarzenia**, aby wyświetlić listę zdarzeń w wybranym obszarze roboczym.
  
1. Wybierz zdarzenie, które chcesz oznaczyć.

1. Wybierz opcję **Edytuj właściwości**, aby otworzyć okienko z listą wszystkich właściwości wybranego zdarzenia.
     
1. Wybierz opcję **...** a następnie wybierz opcję **Edytuj**, aby dotrzeć do okna dialogowego **Aktualizacja właściwości**.

   ![Edytuj zdarzenie.](engagement-insights/media/edit-event.png "Edytuj zdarzenie")

1. W oknie **Aktualizacja właściwości** wybierz pozycję **...** w prawym górnym rogu, a następnie wybierz pole **Zawiera EUII**. Kliknij przycisk **Aktualizuj**, aby zapisać zmiany.

   ![Zapisz zmiany.](engagement-insights/media/update-property.png "Zapisz swoje zmiany")

   > [!NOTE]
   > Za każdym razem, gdy schemat zdarzenia zmienia się lub tworzy nowe zdarzenie, zaleca się, aby w razie potrzeby ocenić właściwości skojarzonego zdarzenia i oznaczyć je jako zawierający dane osobowe.

#### <a name="delete-or-export-tagged-event-data"></a>Usuwanie lub eksportowanie oznaczonych zdarzeń

Jeśli wszystkie właściwości zdarzenia zostały oznaczone odpowiednio zgodnie z opisem w poprzednim kroku, administrator środowiska może utworzyć żądanie usunięcia dla oznaczonego zdarzenia.

Aby zarządzać żądaniami usunięcia lub eksportu EUII

1. Wybierz kolejno pozycje **Administracja** > **Środowisko** > **Ustawienia**.

1. W sekcji **Zarządzanie informacjami umożliwiającymi identyfikację użytkownika końcowego (EUII)** wybierz opcję **Zarządzanie interfejsem EUII**.

##### <a name="deletion"></a>Usuwanie

W celu usunięcia można wprowadzić listę identyfikatorów użytkowników rozdzielanych przecinkami w sekcji **Usuwanie informacji umożliwiających identyfikację użytkownika końcowego (EUII)**. Te identyfikatory zostaną porównywane ze wszystkimi oznaczonymi właściwościami zdarzeń wszystkich projektów w bieżącym środowisku za pomocą dokładnego dopasowania ciągów. 

Jeśli wartość właściwości odpowiada jednemu z podanych identyfikatorów, skojarzone zdarzenie zostanie trwale usunięte. Ze względu na nieodwracalność tej akcji należy potwierdzić usunięcie po wybraniu opcji **Usuń**.

##### <a name="export"></a>Export

Proces eksportu jest identyczny z procesem usuwania, jeśli chodzi o definiowanie wartości właściwości zdarzenia w sekcji **Eksportowanie informacji umożliwiających identyfikację użytkownika końcowego (EUII)**. Ponadto musisz podać adres URL **magazynu obiektów blob Azure** w celu określenia miejsca docelowego eksportu. Adres URL obiektu blob Azure musi zawierać [sygnaturę dostępu współdzielonego](/azure/storage/common/storage-sas-overview) (SAS).

Po wybraniu opcji **Eksportu** wszystkie zdarzenia bieżącego zespołu zawierające pasujące oznaczone właściwości zostaną wyeksportowane w formacie CSV do miejsca docelowego eksportu.

### <a name="good-practices"></a>Najlepsze rozwiązania

* Należy unikać wysyłania zdarzeń zawierających dane osobowe.
* Jeśli konieczne jest wysłanie zdarzeń zawierających dane EUII, ogranicz liczbę zdarzeń i właściwości zdarzeń zawierających dane z zestawu EUII. Najlepiej jest ograniczyć się do jednego z takich zdarzeń.
* Należy upewnić się, że jak najmniejsza liczba osób ma dostęp do wysłanych danych osobowych.
* W przypadku zdarzeń zawierających dane osobowe należy upewnić się, że ustawiono dla jednej właściwości unikatowy identyfikator, który można łatwo połączyć z określonym użytkownikiem (np. identyfikator użytkownika). Ułatwia to przetwarzanie danych oraz eksportowanie lub usuwanie odpowiednich danych.
* Jako zawierające dane osobiste należy oznaczać tylko jedną właściwość dla każdego zdarzenia. Najlepiej jest wybrać taką, która zawiera tylko unikatowy identyfikator.
* Nie należy oznaczać właściwości zawierających pełne wartości (na przykład całe treści żądania). Funkcja wykorzystuje dokładne dopasowanie łańcuchów podczas decydowania, które zdarzenia mają zostać usunięte lub wyeksportowane.

[!INCLUDE[footer-include](includes/footer-banner.md)]