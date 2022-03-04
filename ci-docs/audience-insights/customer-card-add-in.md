---
title: Dodatek do kart klienta dla aplikacji Dynamics 365 (zawiera wideo)
description: Pokaż dane z analizy odbiorców w aplikacjach Dynamics 365 za pomocą tego dodatku.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-search-filter
- ci-customer-card
- customerInsights
ms.openlocfilehash: d67d8e2cb30cf20de204bfb293bb8ce81c7bb2f4
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353878"
---
# <a name="customer-card-add-in-preview"></a>Dodatek kart klientów (wersja zapoznawcza)



Zobacz pełen obraz klientów bezpośrednio w aplikacjach Dynamics 365. Mając zainstalowany dodatek karty klientów w obsługiwanej aplikacji Dynamics 365, możesz wyświetlać pola profilu klienta, szczegółowe informacje i oś czasu działań. Ten dodatek będzie pobierać dane z usługi Customer Insights, co nie ma wpływu na dane w połączonej aplikacji Dynamics 365.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Wymagania wstępne

- Ten dodatek działa tylko w aplikacjach opartych na modelu w Dynamics 365, takich jak Sales lub Customer Service, w wersji 9.0 lub nowszej.
- Aby dane usługi Dynamics 365 były mapowane do profilów klientów w ramach wyników analiz odbiorców, zalecamy [pozyskiwane z aplikacji Dynamics 365 przy użyciu konektora Microsoft Dataverse](connect-power-query.md). Jeśli używasz innej metody do pozyskiwania kontaktów (lub kont) Dynamics 365, musisz upewnić się, że pole `contactid` (lub `accountid`) jest ustawione jako [klucz podstawowy dla tego źródła danych w kroku mapy proces ujednolicania danych](map-entities.md#select-primary-key-and-semantic-type-for-attributes). 
- Wszystkich użytkowników usługi Dynamics 365 z dodatku karta klienta należy [dodać jako użytkowników](permissions.md) w analizie odbiorców, aby dane stały się widoczne.
- [Funkcje wyszukiwania i filtrowania skonfigurowane](search-filter-index.md) w analizie odbiorców są wymagane do wyszukiwania danych.
- Każda kontrolka dodatku zależy od określonych danych w wynikach analiz odbiorców. Niektóre dane i kontrolki są dostępne tylko w środowiskach określonych typów. W konfiguracji dodatku zostanie podana informacja o tym, czy ze względu na wybrany typ środowiska kontrolka jest niedostępna. Dowiedz się więcej o [przypadkach użycia środowisk](work-with-business-accounts.md).
  - **Kontrola miary**: wymaga [skonfigurowanych miar](measures.md) typu atrybutów klienta.
  - **Kontrola danych**: wymaga danych generowanych przy użyciu [prognoz lub niestandardowych modeli](predictions-overview.md).
  - **Kontrola szczegółów klienta**: wszystkie pola z profilu są dostępne w ujednoliconym profilu klienta.
  - **Kontrola wzbogacenia**: wymaga czynnych [wzbogaceń](enrichment-hub.md) zastosowanych dla profilów klienta. Dodatek do karty obsługuje te elementy wzbogacające: [Marki](enrichment-microsoft.md) dostarczane przez Microsoft, [Zainteresowania](enrichment-microsoft.md) dostarczane przez Microsoft oraz [Dane dot. interakcji Office](enrichment-office.md) dostarczane przez Microsoft.
  - **Kontrola kontaktów**: wymaga definicji encji semantycznej typu Kontakty.
  - **Kontrola osi czasu**: wymagane są [skonfigurowane działania](activities.md).

## <a name="install-the-customer-card-add-in"></a>Zainstaluj dodatek kart klientów

Dodatek Karta klienta to rozwiązanie dla aplikacji Customer Engagement w Dynamics 365. Aby zainstalować rozwiązanie, przejdź do AppSource i wyszukaj **Karta klienta Dynamics**. Wybierz [Dodatek kart klientów w AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) i wybierz **Pobierz teraz**.

Aby zainstalować rozwiązanie, konieczne może być zalogowanie się przy użyciu poświadczeń administracyjnych do aplikacji Dynamics 365. Może upłynąć trochę czasu zanim rozwiązanie zostanie zainstalowane w środowisku użytkownika.

## <a name="configure-the-customer-card-add-in"></a>Konfigurowanie dodatku kart klientów

1. Jako administrator, przejdź do sekcji **Ustawienia** w Dynamics 365 i wybierz **Rozwiązania**.

1. Wybierz łącze **Wyświetlana nazwa** dla rozwiązania **Dynamics 365 Customer Insights, Dodatek kart klientów (wersja zapoznawcza)**.

   > [!div class="mx-imgBorder"]
   > ![Wybierz nazwę wyświetlaną.](media/select-display-name.png "Wybierz nazwę wyświetlaną.")

1. Wybierz **Zaloguj** i wprowadź poświadczenia dla konta administracyjnego używanego do konfigurowania Customer Insights.

   > [!NOTE]
   > Sprawdź, czy w przypadku wybrania przycisku **Zaloguj** nie jest blokowane okno uwierzytelniania w wyskakujących okienkach przeglądarki.

1. Wybierz środowisko Customer Insights, z którego chcesz pobrać dane.

1. Zdefiniuj mapowanie pól na rekordy w aplikacji Dynamics 365. W zależności od danych w aplikacji Customer Insights można zmapować następujące opcje:
   - Aby zmapować z kontaktem, wybierz pole w encji Customer, które jest zgodne z identyfikatorem Twojej encji kontaktu.
   - Aby zmapować z kontem, wybierz pole w encji Customer, które jest zgodne z identyfikatorem Twojej encji konta.

   > [!div class="mx-imgBorder"]
   > ![Pole identyfikatora kontaktu.](media/contact-id-field.png "Pole identyfikatora kontaktu.")

1. Wybierz **Zapisz konfigurację**, aby zapisać ustawienia.

1. Następnie należy przypisać role zabezpieczeń w Dynamics 365, aby użytkownicy mogli dostosować i wyświetlić kartę klienta. W Dynamics 365, przejdź do **Ustawienia** > **Zabezpieczenia** > **Użytkownicy**. Wybierz użytkowników, aby edytować role użytkowników i wybierz **Zarządzaj rolami**.

1. Przypisz rolę **Konfiguratora karty Customer Insights** do klientów, którzy będą dostosowywać zawartość widoczną na karcie dla całej organizacji.

## <a name="add-customer-card-controls-to-forms"></a>Dodaj kontrolki karty klienta do formularzy

W zależności od scenariusza można dodać kontrolki do formularza **Kontakt** lub **Konto**. Jeśli środowisko wyników analiz odbiorców dotyczy klientów biznesowych, zalecamy dodanie kontrolek do formularza Konto. W takim przypadku zastąp „kontakt” w poniższych krokach przy użyciu wartości „konto”.

1. Aby dodać formanty karty klienta do formularza Kontakt, przejdź do **Ustawienia** > **Dostosowania** w Dynamics 365.

1. Wybierz **Dostosuj system**.

1. Przeglądaj do encji **Kontakt**, rozwiń ją i wybierz **Formularze**.

1. Wybierz formularz kontaktu, do którego chcesz dodać kontrolki karty klienta.

    > [!div class="mx-imgBorder"]
    > ![Wybierz formularz Kontaktu.](media/contact-active-forms.png "Wybierz formularz Kontakt.")

1. Aby dodać formant, w edytorze formularzy przeciągnij dowolne pole z **Eksplorator pól** do miejsca, gdzie ma się pojawić formant.

1. Zaznacz pole na formularzu, który został przed chwilą dodany, i wybierz pozycję **Zmień właściwości**.

1. Przejdź do karty **Formanty** i wybierz opcję **Dodaj formant**. Wybierz jeden z dostępnych formantów niestandardowych i wybierz **Dodaj**.

1. W oknie dialogowym **Właściwości pola** wyczyść pole wyboru **Wyświetl etykietę w formularzu**.

1. Wybierz opcję **Web** dla formantu. W przypadku formantu Wzbogacenie wybierz, który typ wzbogacenia chcesz wyświetlić konfigurując pole **enrichmentType**. Dodaj oddzielną kontrolkę wzbogacania dla każdego typu wzbogacania.

1. Wybierz **Zapisz** i **Opublikuj**, aby opublikować zaktualizowany formularz kontaktu.

1. Przejdź do opublikowanego formularza kontaktu. Zobaczysz ostatnio dodany formant. Może zaistnieć konieczność zalogowania się w czasie, gdy zostanie on użyty podczas pierwszego korzystania z programu.

1. Aby dostosować dane, które mają być wyświetlane w formancie, wybierz przycisk edytuj w prawym górnym rogu.

## <a name="upgrade-customer-card-add-in"></a>Zaktualizuj dodatek karty klienta

Dodatek karty klienta nie aktualizuje się automatycznie. Aby uaktualnić do najnowszej wersji, wykonaj poniższe kroki w aplikacji Dynamics 365, w której zainstalowano dodatek.

1. W aplikacji Dynamics 365 przejdź do **Ustawienia** > **Dostosowywanie** i wybierz **Rozwiązania**.

1. W tabeli dodatków zwróć uwagę na kartę **CustomerInsightsCustomerCard** i zaznacz wiersz.

1. Na pasku akcji wybierz opcję **Zastosuj uaktualnienie rozwiązania**.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Uaktualnianie rozwiązania w obszarze Dostosowywanie aplikacji Dynamics 365.":::

1. Po rozpoczęciu procesu uaktualniania będzie widzieć wskaźnik ładowania do momentu ukończenia uaktualniania. Jeśli nie ma nowszej wersji, aktualizacja wyświetli komunikat o błędzie.

## <a name="troubleshooting"></a>Rozwiązywanie problemów

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>Kontrolki z dodatku Karta klienta nie znajdują danych

**Problem:**

Nawet jeśli pola identyfikatorów zostały poprawnie skonfigurowane, klientów nie mogą znaleźć żadnych danych dotyczących klienta.  

**Rozwiązanie:**

1. Upewnij się, że dodatek Karta został skonfigurowany zgodnie z instrukcjami: [Konfigurowanie dodatku Karta klienta](#configure-the-customer-card-add-in) 

1. Przejrzyj konfigurację pozyskiwania danych. Edytuj źródło danych dla systemu Dynamics 365, który zawiera identyfikator GUID kontaktu. Jeśli w edytorze Power Query identyfikator GUID kontaktu jest wyświetlany przy użyciu wielkich liter, spróbuj wykonać następujące czynności: 
    1. Edytuj źródło danych, aby otworzyć źródło danych w edytorze Power Query.
    1. Wybierz kolumnę identyfikatora kontaktu.
    1. Wybierz pozycję **Przekształć** na pasku nagłówka, aby wyświetlić dostępne akcje.
    1. Wybierz opcję **małe litery**. Sprawdź, czy identyfikatory GUID w tabeli są teraz zapisane przy użyciu małych liter.
    1. Zapisz źródło danych.
    1. Aby propagować zmiany w identyfikatorze GUID, uruchom procesy pozyskiwania i ujednolicania danych oraz ich transmisji do klienta. 

Po zakończeniu pełnego odświeżania kontrolki dodatku Karta klienta powinny wyświetlać oczekiwane dane. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
