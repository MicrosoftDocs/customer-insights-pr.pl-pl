---
title: Wzbogać profile klientów o dane z Microsoft Office 365
description: Użyj zastrzeżonych danych z Microsoft Office, aby wzbogacić swoje profile klientów o dane dotyczące zaangażowania.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 7192b7680e73a581dd603de174c57b20bec996dd
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954146"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Wzbogać profile klientów o dane dotyczące zaangażowania (podgląd)

Wykorzystaj dane z usługi Microsoft Office 365, aby wzbogacić profile kont klientów o spostrzeżenia dotyczące zaangażowania za pośrednictwem aplikacji Office 365. Dane dotyczące zaangażowania składają się z aktywności e-mailowej i aktywności na spotkaniach, które są agregowane na poziomie konta. Na przykład liczba maili z konta biznesowego lub liczba spotkań z tego konta. Nie są udostępniane żadne dane dotyczące poszczególnych użytkowników.

## <a name="supported-countries-or-regions"></a>Obsługiwane kraje lub regiony

Obecnie obsługujemy następujące regiony: Zjednoczone Królestwo, Europa, Ameryka Północna.

## <a name="prerequisites"></a>Wymagania wstępne

- Ma aktywną licencję Office 365.
- [Profile jednolicone klientów](customer-profiles.md) na podstawie [kont biznesowych](work-with-business-accounts.md).
- [Dołączona organizacja Microsoft Dataverse](create-environment.md#step-3-connect-to-microsoft-dataverse) w środowisku Customer Insights.
- Uprawnienia [administratora](permissions.md#admin).
- Zgoda od administratora dzierżawy Office 365 na wykorzystanie danych Office 365 w celu zapewnienia **Insights for the Organization** w aplikacjach Dynamics 365.

## <a name="configure-the-enrichment"></a>Konfiguracja wzbogacania

1. Przejdź do **Dane** > **Wzbogacenie** i wybierz kartę **Odkrywanie**.

1. Wybierz opcję **Wzbogać moje dane** na kafelku **Zaangażowanie konta**.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="kafelek interakcja z klientami":::

1. Przejrzyj omówienie, a następnie wybierz **Dalej**.

1. Wprowadź adresy e-mail z organizacji, dla których mają być agregowane dane Office. Tylko dane z podanych adresów mailowych są przetwarzane w celu odpowiedniej komunikacji. Najlepszą praktyką jest używanie grup e-mailowych, na przykład *Amerykański zespół sprzedaży*, które są łatwo zarządzane w Office 365. Liczba adresów mailowych w grupach jest rozwiązywana i pokazywana. Całkowita liczba adresów mailowych musi wynosić co najmniej 2 i nie może przekroczyć 2500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Adresy e-mailowe osób odpowiedzialnych za prowadzenie konta.":::

1. Przejrzyj i wyraź zgodę na [Zgodę administratora dzierżawcy Office 365](#office-365-tenant-administrator-consent), wybierając **Wyrażam zgodę**.

1. Wybierz **Dalej**.

1. Wybierz **zestaw danych kontaktów** i wybierz profil, który chcesz wzbogacić. Wybierz **Dalej**.

1. Zamapuj pole adresu e-mail kontaktu i wybierz opcję **Dalej**.

1. Podaj **Nazwę** dla wzbogacenia oraz **Obiekt wyjściowy**.

1. Wybierz opcję **Zapisz wzbogacenie** po przejrzeniu wybranych opcji.

1. Wybierz opcję **Zamknij**, aby powrócić do strony **Wzbogacania**.

### <a name="office-365-tenant-administrator-consent"></a>Zgoda administratora dzierżawy Office 365

Do aktywacji wzbogacenia wymagana jest zgoda administratora dzierżawy Office 365. Po zapisaniu wzbogacenia do administratorów dzierżawców Office 365 wysyłana jest wiadomość e-mail z prośbą o zapoznanie się i wyrażenie zgody na wykorzystanie przez aplikacje Dynamics 365 danych Office 365 przedsiębiorstwa w celu zapewnienia **Analiza dla organizacji**. Administrator dzierżawy Office 365 może również wyrazić zgodę bezpośrednio w swojej konsoli administracyjnej Office 365, wybierając **Analiza dla Organizacji**.

## <a name="running-the-enrichment-for-the-first-time"></a>Uruchomienie wzbogacenia po raz pierwszy

Gdy wzbogacanie jest uruchamiane po raz pierwszy, po wyrażeniu zgody przez administratora dzierżawy Office 365, rozpoczyna się pobieranie danych z Office 365. Ten proces może trochę potrwać. Pierwszy kurs wzbogacania będzie miał miejsce z sześciogodzinnym opóźnieniem. Po zakończeniu wzbogacania możesz zobaczyć liczbę dni, które obejmują dane, na stronie przeglądu zaangażowania konta. Przy dużej ilości danych uruchom ponownie wzbogacanie po kilku dniach. Zapewnia to, że dane są kompletne dla całego przedziału czasowego, czyli jednego roku.

W zależności od rozmiaru twoich danych w Office, może upłynąć kilka godzin, zanim proces wzbogacania zostanie zakończony.

Gdy uruchomisz wzbogacanie, Microsoft przetworzy dane w granicach zgodności z Office 365, aby utworzyć zagregowane spostrzeżenia, które następnie zostaną dodane do Twojego środowiska Customer Insights. Żadne dane na poziomie indywidualnym (na przykład treść wiadomości e-mail lub zaproszenia do kalendarza) nie są dostępne dla użytkowników Customer Insights.

Wybierz **Uruchom**, aby rozpocząć proces wzbogacenia.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Wyniki wzbogacenia

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]Jest to encja pakietu *Office*. *Office_UserEntity* zawiera identyfikatory Active Directory dla adresów e-mail, które zostały wybrane podczas konfiguracji wzbogacania.

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Podgląd wyników po uruchomieniu procesu wzbogacania.":::

Wszystkie dane są agregowane aż do poziomu konta. System oblicza dla każdego konta wynik zaangażowania, który waha się od 0 do 100. Wynik zaangażowania stanowi zbiorczą miarę zaangażowania konta w maile i spotkania w stosunku do innych kont. Poniższa lista zawiera zagregowane dane, które dostarcza wzbogacenie zaangażowania konta:

| Dane                                                                              | Nazwa kolumny                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Ocena interakcji                                                                  |  EngagementScore                         |
| Liczba maili na koncie                                                       |  NoOfEmails_ToAccount                    |
| Liczba maili z konta                                                     |  NoOfEmails_FromAccount                  |
| Liczba spotkań zainicjowanych przez konto                                           |  NoOfMeetings_FromAccount                |
| Liczba spotkań zainicjowanych przez twoją organizację                                 |  NoOfMeetings_ToAccount                  |
| Liczba osób z Twojej organizacji biorących udział w spotkaniach z kontem                  |  NoOfContactsInvolved_Meetings           |
| Liczba osób z Twojej organizacji w konwersacjach mailowych z kontem       |  NoOfContactsInvolved_Emails             |
| Liczba osób z konta uczestniczących w spotkaniach z waszą organizacją                  |  NoOfAccountContactsInvolved_Meetings    |
| Liczba osób z konta w konwersacjach mailowych z Twoją organizacją       |  NoOfAccountContactsInvolved_Emails      |
| Data rozpoczęcia zaangażowania (pierwszy e-mail lub spotkanie w danych)                        |  EngagementStartDate                     |
| Dni od ostatniego emaila                                                             |  DaysSinceLastEmail                      |
| Dni od ostatniego spotkania                                                           |  DaysSinceLastMeeting                    |
| Średni czas trwania spotkań                                                      |  AverageDuration_Of_Meetings             |
| Średni czas trwania odpowiedzi na e-mail z konta                                    |  AverageDuration_Of_AccountEmailReplies  |
| Data rozpoczęcia agregacji                                                            |  AggregationStartDate                    |
| Poziom agregacji (rok, miesiąc, lub tydzień)                                          |  AggregationLevel                        |

## <a name="see-enrichment-data-on-the-customer-card"></a>Zobacz dane dotyczące wzbogacenia na karcie klienta

Interakcje z kontem mogą być również widoczne na kartach poszczególnych klientów. Przejdź do **Klienci** i wybierz profil klienta. W karcie klienta znajdziesz wynik zaangażowania konta, całkowitą liczbę maili oraz całkowitą liczbę spotkań z ostatniego roku. Znajdziesz też wykresy, które pokazują historię maili i spotkań.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Karta klienta ze wzbogaconymi danymi.":::

## <a name="next-steps"></a>Następne kroki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]
Na przykład, segment zawierający wszystkich klientów, którzy mają wartość powyżej 60 dla *dni od ostatniego e-maila* i *dni od ostatniego spotkania*. Ten segment zawiera nieaktywne konta, które możesz spróbować reaktywować.

[!INCLUDE [footer-include](includes/footer-banner.md)]
