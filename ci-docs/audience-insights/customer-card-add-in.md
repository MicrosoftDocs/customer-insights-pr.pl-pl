---
title: Zainstaluj i skonfiguruj Dodatek kart klientów
description: Zainstaluj i skonfiguruj dodatek kart klientów dla Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f3c4a01f9ce7749eeee72f7901620dae7cb9b8d3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597340"
---
# <a name="customer-card-add-in-preview"></a>Dodatek kart klientów (wersja zapoznawcza)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Zobacz pełen obraz klientów bezpośrednio w aplikacjach Dynamics 365. Zobacz dane demograficzne, wyniki analiz, i osi czasu działania dzięki użyciu dodatku kart klientów.

## <a name="prerequisites"></a>Wymagania wstępne

- Aplikacja Dynamics 365 (na przykład Centrum sprzedaży lub Centrum obsługi klienta) w wersji 9.0 lub nowszej z włączoną funkcją ujednolicony interfejs.
- Profile klientów [pobierane z aplikacji Dynamics 365 z użyciem programu Common Data Service](connect-power-query.md).
- Użytkownicy dodatku karty klienta muszą być [dodawani jako użytkownicy](permissions.md) w statystykach odbiorców.
- [Skonfigurowane funkcje wyszukiwania i filtrowania](search-filter-index.md).
- Kontrola demograficzna: pola demograficzne (takie jak wiek czy płeć) są dostępne w ujednoliconym profilu klienta.
- Kontrola wzbogacenia: Wymaga czynnych [wzbogaceń](enrichment-hub.md) zastosowanych dla profilów klienta.
- Kontrola analiz: Wymaga danych wygenerowanych przy użyciu usługi Azure Machine Learning ([przewidywania](predictions.md) lub [modele niestandardowe](custom-models.md))
- Kontrola miar: wymagane są [skonfigurowane miary](measures.md).
- Kontrolka osi czasu: wymagane są [skonfigurowane działania](activities.md).

## <a name="install-the-customer-card-add-in"></a>Zainstaluj dodatek kart klientów

Dodatek Karta klienta to rozwiązanie dla aplikacji Customer Engagement w Dynamics 365. Aby zainstalować rozwiązanie, przejdź do AppSource i wyszukaj **Karta klienta Dynamics**. Wybierz [Dodatek kart klientów w AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) i wybierz **Pobierz teraz**.

Aby zainstalować rozwiązanie, konieczne może być zalogowanie się przy użyciu poświadczeń administracyjnych do aplikacji Dynamics 365.

Może upłynąć trochę czasu zanim rozwiązanie zostanie zainstalowane w środowisku użytkownika.

## <a name="configure-the-customer-card-add-in"></a>Konfigurowanie dodatku kart klientów

1. Jako administrator, przejdź do sekcji **Ustawienia** w Dynamics 365 i wybierz **Rozwiązania**.

1. Wybierz łącze **Wyświetlana nazwa** dla rozwiązania **Dynamics 365 Customer Insights, Dodatek kart klientów (wersja zapoznawcza)**.

   > [!div class="mx-imgBorder"]
   > ![Wybierz nazwę wyświetlaną](media/select-display-name.png "Wybierz nazwę wyświetlaną")

1. Wybierz **Zaloguj** i wprowadź poświadczenia dla konta administracyjnego używanego do konfigurowania Customer Insights.

   > [!NOTE]
   > Sprawdź, czy w przypadku wybrania przycisku **Zaloguj** nie jest blokowane okno uwierzytelniania w wyskakujących okienkach przeglądarki.

1. Wybierz środowisko, z którego chcesz pobrać dane.

1. Zdefiniuj, które pole jest mapowane na rekordy w aplikacji Dynamics 365.
   - Aby zmapować z kontaktem, wybierz pole w encji Customer, które jest zgodne z identyfikatorem Twojej encji kontaktu.
   - Aby zmapować z kontem, wybierz pole w encji Customer, które jest zgodne z identyfikatorem Twojej encji konta.

   > [!div class="mx-imgBorder"]
   > ![Pole identyfikatora kontaktu](media/contact-id-field.png "Pole identyfikatora kontaktu")

1. Wybierz **Zapisz konfigurację**, aby zapisać ustawienia.

1. Następnie należy przypisać role zabezpieczeń w Dynamics 365, aby użytkownicy mogli dostosować i wyświetlić kartę klienta. W Dynamics 365, przejdź do **Ustawienia** > **Zabezpieczenia** > **Użytkownicy**. Wybierz użytkowników, aby edytować role użytkowników i wybierz **Zarządzaj rolami**.

1. Przypisz rolę **Konfiguratora karty Customer Insights** do klientów, którzy będą dostosowywać zawartość widoczną na karcie dla całej organizacji.

## <a name="add-customer-card-controls-to-forms"></a>Dodaj kontrolki karty klienta do formularzy
  
1. Aby dodać formanty karty klienta do formularza Kontakt, przejdź do **Ustawienia** > **Dostosowania** w Dynamics 365.

1. Wybierz **Dostosuj system**.

1. Przeglądaj do encji **Kontakt**, rozwiń ją i wybierz **Formularze**.

1. Wybierz formularz kontaktu, do którego chcesz dodać formanty karty klienta.

    > [!div class="mx-imgBorder"]
    > ![Wybierz formularz Kontaktu](media/contact-active-forms.png "Wybierz formularz Kontaktu")

1. Aby dodać formant, w edytorze formularzy przeciągnij dowolne pole z **Eksplorator pól** do miejsca, gdzie ma się pojawić formant.

1. Zaznacz pole na formularzu, który został przed chwilą dodany, i wybierz **Zmień właściwości**.

1. Przejdź do karty **Formanty** i wybierz opcję **Dodaj formant**. Wybierz jeden z dostępnych formantów niestandardowych i wybierz **Dodaj**.

1. W oknie dialogowym **Właściwości pola** wyczyść pole wyboru **Wyświetl etykietę w formularzu**.

1. Wybierz opcję **Web** dla formantu. W przypadku formantu Wzbogacenie wybierz, który typ wzbogacenia chcesz wyświetlić konfigurując pole **enrichmentType**. Dodaj oddzielną kontrolkę wzbogacania dla każdego typu wzbogacania.

1. Wybierz **Zapisz** i **Opublikuj**, aby opublikować zaktualizowany formularz kontaktu.

1. Przejdź do opublikowanego formularza kontaktu. Zobaczysz ostatnio dodany formant. Może zaistnieć konieczność zalogowania się w czasie, gdy zostanie on użyty podczas pierwszego korzystania z programu.

1. Aby dostosować dane, które mają być wyświetlane w formancie, wybierz przycisk edytuj w prawym górnym rogu.

## <a name="upgrade-customer-card-add-in"></a>Zaktualizuj dodatek karty klienta
Dodatek karty klienta nie aktualizuje się automatycznie. Aby uaktualnić do najnowszej wersji, wykonaj tę procedurę w aplikacji Dynamics 365, która ma zainstalowany dodatek.

1. W aplikacji Dynamics 365 przejdź do **Ustawienia** > **Dostosowywanie** i wybierz **Rozwiązania**.

1. W tabeli dodatków zwróć uwagę na kartę **CustomerInsightsCustomerCard** i zaznacz wiersz.

1. Na pasku akcji wybierz opcję **Zastosuj uaktualnienie rozwiązania**.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Uaktualnianie rozwiązania w obszarze Dostosowywanie aplikacji Dynamics 365":::

1. Po rozpoczęciu procesu uaktualniania będzie widzieć wskaźnik ładowania do momentu ukończenia uaktualniania. Jeśli nie ma nowszej wersji, aktualizacja wyświetli komunikat o błędzie.


[!INCLUDE[footer-include](../includes/footer-banner.md)]