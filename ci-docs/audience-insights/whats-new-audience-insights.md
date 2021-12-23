---
title: Nowe i nadchodzące funkcje
description: Informacje o nowych funkcjach, ulepszeniach i poprawkach błędów.
ms.date: 12/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 346ef93e8471580b782618550ca4eb71b3f3c921
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2021
ms.locfileid: "7884275"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Co nowego w możliwości wglądu odbiorców w Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Z przyjemnością informujemy o najnowszych aktualizacjach! W tym artykule podsumowano publiczne wersje zapoznawcze, ulepszenia ogólnej dostępności oraz aktualizacje funkcji. Aby zobaczyć długofalowe plany dotyczące funkcji, zapoznaj się z [planami wydań rozwiązań Dynamics 365 i Power Platform](/dynamics365/release-plans/).

Wdrażamy aktualizacje kolejno regionami. Niektóre regiony mogą zobaczyć nowe funkcje wcześniej. O ile nie zaznaczono inaczej, nie trzeba podejmować żadnych działań, a w razie przestoju przeprowadzimy automatyczną aktualizację bez konieczności przestoju.

> [!TIP]
> Aby przesłać i głosować na żądania funkcji i sugestie dotyczące produktu, przejdź do [portalu Pomysły aplikacji Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="november-2021-updates"></a>Aktualizacje z listopada 2021

Aktualizacje w listopadzie 2021 r. zawierają nowe funkcje, uaktualnienia wydajności i poprawki usterek.

### <a name="segment-membership-now-available-in-dataverse"></a>Członkostwo segmentowe już dostępne w Dataverse

Informacje o przynależności do segmentów dla profili klientów są teraz dostępne w Dataverse wraz z profilami i spostrzeżeniami klientów. Aplikacje akcji Dynamics 365 i aplikacje sterowane modelami mogą wykorzystać te dane do wyszukania szczegółów członkostwa w segmencie dla danego klienta.

### <a name="activities-support-contact-level-details-for-business-accounts"></a>Działania wspierają szczegóły na poziomie kontaktu dla kont biznesowych

Możesz teraz konfigurować, wyświetlać i filtrować aktywności dla kontaktów na osi czasu aktywności konta biznesowego, aby lepiej zrozumieć, które kontakty z konta brały udział w konkretnych działaniach.

## <a name="october-2021-updates"></a>Aktualizacje z października 2021

Aktualizacje w październiku 2021 r. zawierają nowe funkcje, uaktualnienia wydajności i poprawki usterek.

### <a name="b-to-b"></a>B-do-B

Od października 2021 r. będzie można pracować z klientami biznesowymi i powiązanymi z nimi kontaktami w aplikacji Customer Insights. Wcześniej aplikacja była w większości dostosowana do danego klienta. Zaktualizowano kilka obszarów funkcji w celu obsługi scenariuszy typu B-do-B jako dodatek do nowego typu środowiska. Aby uzyskać omówienie obsługiwanych funkcji typu B-do-B, zobacz temat [Praca z kontami biznesowymi w funkcji Wyniki analiz odbiorców](work-with-business-accounts.md).

W poniższych sekcjach przedstawiono niektóre kluczowe obszary, które zostały dostosowane do obsługi klientów biznesowych i indywidualnych osób.

#### <a name="export-segments-based-on-business-accounts"></a>Eksportowanie segmentów na podstawie klientów biznesowych

Wszystkie operacje eksportu segmentów w funkcji Wyniki analiz odbiorców są dostępne w kontekście klientów biznesowych. Większość eksportów segmentów wymaga dodatkowej konfiguracji i [informacji kontaktowych przewidywanych](segment-builder.md#create-a-new-segment) w segmentach bazowych, aby były prawidłowe dla klientów biznesowych. Aby uzyskać więcej informacji, zobacz temat [Eksportowanie segmentów](export-destinations.md#export-segments).

#### <a name="use-the-linkedin-ads-export-with-business-accounts"></a>Używanie funkcji eksportu usługi LinkedIn Ads do klientów biznesowych

Eksportowanie ogłoszeń LinkedIn Ads jest teraz dostępne do grup docelowych kontaktów i firm w kontekście klientów biznesowych. Wybierając grupy odbiorców docelowych firm jako główny cel eksportu z usługi LinkedIn, można eksportować segmenty zbudowane na podstawie kont biznesowych bez konieczności przewidywania informacji kontaktowych. Aby uzyskać więcej informacji, przejdź do dokumentów dotyczących [eksportu z usługi LinkedIn Ads](export-linkedin-ads.md) i różnicy między [określaniem kontaktów docelowych](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) i [określaniem firm docelowych](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting). 

#### <a name="create-measures-based-on-business-accounts-and-their-hierarchy"></a>Tworzenie miar na podstawie klientów biznesowych i ich hierarchii

Kreator miar umożliwia tworzenie miar dotyczących klientów biznesowych i — opcjonalnie — korzystania z informacji o hierarchii. Informacje o hierarchii służą do zestawiania obliczeń miary dla klienta i wszystkich powiązanych z nim klientów podrzędnych. Można na przykład utworzyć miarę, taką jak łączny przychód, dla każdej grupy klientów biznesowych zidentyfikowanych według hierarchii. Aby uzyskać więcej informacji, zobacz [Definiuj miary i zarządzaj nimi](measures.md).

#### <a name="create-segments-based-on-business-accounts-and-their-hierarchy"></a>Tworzenie segmentów na podstawie klientów biznesowych i ich hierarchii

Kreator segmentów umożliwia tworzenie segmentów klientów biznesowych, które opcjonalnie zawierają informacje kontaktowe dla każdego klienta w segmencie. Jeśli jest skonfigurowana hierarchia klientów, informacje o hierarchii klientów można wykorzystać do tworzenia segmentów. Aby uzyskać więcej informacji, zobacz temat [Tworzenie nowego segmentu](segment-builder.md#create-a-new-segment).

#### <a name="retain-your-business-accounts-with-deep-insights-to-their-churn-tendency"></a>Utrzymywanie klientów biznesowych dzięki szczegółowej analizie ich tendencji do rezygnacji

Model przewidywania rezygnacji klientów obsługuje teraz także klientów biznesowych. Ryzyko rezygnacji można oceniać nie tylko dla klienta, ale także dla kombinacji klientów i kategorii produktów lub usług, które klienci kupują od Ciebie. Ten dodatek ułatwia zrozumienie, czy istnieje prawdopodobieństwo, że klient ogólnie przestanie kupować towary lub usługi od Ciebie czy tylko określoną kategorię towarów lub usług. Aby ułatwić dalsze korzystanie z tego modelu AI, wymieniono w nim również prawdopodobne powody rezygnacji klienta. Aby uzyskać więcej informacji, zobacz temat [Przewidywanie rezygnacji z transakcji (wersja zapoznawcza)](predict-transactional-churn.md).

#### <a name="see-contacts-of-a-business-account-in-customer-view"></a>Wyświetlanie kontaktów klienta biznesowego w widoku Klient

Jeśli klienci biznesowi są mapowani na powiązanych klientów, aplikacja Customer Insights pokazuje te powiązane kontakty w widoku szczegółów klienta. Aby uzyskać więcej informacji, zobacz temat [Profile klientów](customer-profiles.md).


## <a name="september-2021-updates"></a>Aktualizacje z września 2021

Aktualizacje we wrześniu 2021 r. zawierają nowe funkcje, uaktualnienia wydajności i poprawki usterek.

### <a name="activities"></a>Działania

- **Udoskonalenia osi czasu działań** Rozszerzyliśmy filtry osi czasu działań w profilach klientów. Dodatkowo można użyć nowego filtru do filtrowania według typu działania i daty. Daty można filtrować w innych warunkach. Aby uzyskać więcej informacji, zobacz temat [Wyświetlanie osi czasu działań w profilach klientów](activities.md#view-activity-timelines-on-customer-profiles).

### <a name="relationships"></a>Relacje

- **Obsługa relacji z wieloma przeskokami** Używaj relacji z wieloma przeskokami podczas konfigurowania działań i definiowania relacji między encjami. Relacje z wieloma przeskokami używają encji pośredniej w celu połączenia dwóch encji. Podczas konfigurowania działania można użyć relacji z wieloma przeskokami w celu połączenia encji działania z encją pośrednią, a następnie z encją klienta. Można łączyć relacje z wieloma przeskokami z relacjami z wieloma ścieżkami. Aby uzyskać więcej informacji, zobacz temat [Relacja z wieloma przeskokami](relationships.md#multi-hop-relationship).

- **Obsługa relacji z wieloma ścieżkami** Używaj relacji z wieloma ścieżkami podczas konfigurowania działań i definiowania relacji między encjami. Relacje z wieloma ścieżkami wiążą encję źródłową z więcej niż jedną encją. Podczas konfigurowania działania można użyć relacji z wieloma ścieżkami w celu połączenia encji działania z więcej niż jedną encją klienta. Można łączyć relacje z wieloma ścieżkami z relacjami z wieloma przeskokami. Aby uzyskać więcej informacji, zobacz temat [Relacja z wieloma ścieżkami](relationships.md#multi-path-relationship).

## <a name="august-2021-updates"></a>Aktualizacje z sierpnia 2021 r.

Aktualizacje z lipca i sierpnia 2021 r. zawierają nową funkcję, uaktualnienia wydajności i poprawki usterek.

### <a name="extensibility"></a>Rozszerzalność

- **Eksportuj segmenty do Klaviyo** Rozszerzyliśmy nasze [miejsca docelowe eksportu o Klaviyo](export-klaviyo.md). Można teraz eksportować segmenty, aby tworzyć kampanie, prowadzić marketing za pomocą poczty e-mail oraz używać wybranych grup klientów w usłudze Klaviyo. 


## <a name="june-2021-updates"></a>Aktualizacje z czerwca 2021 r.

Aktualizacje z czerwca 2021 zawierają kilka funkcji, uaktualnianie wydajności i poprawki błędów.

### <a name="data-ingestion"></a>Pozyskiwanie danych

- **Ulepszone aktualizacje postępu ujednolicenia danych** Można teraz wyświetlać bardziej szczegółowe, ulepszone dynamiczne aktualizacje stanu w krokach [procesu ujednolicania danych](data-unification.md). Ta funkcja umożliwia śledzenie szczegółowego postępu, aby zrozumieć przepływ procesu i podjąć działania, jeśli którykolwiek krok wymaga uwagi.

### <a name="extensibility"></a>Rozszerzalność

- **Eksportuj segmenty i inne dane do Salesforce Marketing Cloud** Rozszerzyliśmy nasze miejsca docelowe eksportu o [Salesforce Marketing Cloud](export-salesforce.md). Teraz możesz eksportować segmenty i inne typy danych do Salesforce Marketing Cloud za pośrednictwem markowego eksportu SFTP. Import danych może być w pełni zautomatyzowany w Salesforce i używany do tworzenia bardziej efektywnych kampanii marketingowych.  
 
- **Eksportuj segmenty do ActiveCampaign** Rozszerzyliśmy nasze miejsca docelowe eksportu o [Active Campaign](export-active-campaign.md). Można teraz eksportować segmenty, by generować kampanie, prowadzić marketing za pomocą poczty e-mail oraz pracować z wybranymi grupami klientów w usłudze ActiveCampaign.
 
- **Eksportuj segmenty do Sendinblue** Rozszerzyliśmy nasze miejsca docelowe eksportu o [Sendinblue](export-sendinblue.md). Można teraz eksportować segmenty, by generować kampanie, prowadzić marketing za pomocą poczty e-mail oraz pracować z wybranymi grupami klientów w usłudze Sendinblue.
 
### <a name="ux-updates"></a>Aktualizacje UX 

- **Nowa i ulepszona strona Klienci i strona szczegółów profilu** Przeprojektowaliśmy stronę Klienci i strony szczegółów profilu, aby poprawić wrażenia użytkownika i uzyskać lepszą wydajność. Te zmiany umożliwiają wyświetlanie, sortowanie, wyszukiwanie i filtrowanie klientów. Filtry są teraz reprezentowane w adresie URL, aby bezproblemowo udostępniać wyniki wyszukiwania innym użytkownikom. Wyniki wyszukiwania można również zapisywać jako segment.    
  Strona szczegółów profili klientów grupuje teraz dane w różnych podsekcjach, takich jak dane demograficzne, identyfikatory i inne atrybuty profilu, aby poprawić czytelność. Inne sekcje na stronie szczegółów profilu są teraz bardziej interaktywne. Na przykład sekcja działania umożliwia teraz filtrowanie i sortowanie.


## <a name="may-2021-updates"></a>Aktualizacje z maja 2021 r.

Aktualizacje z maja 2021 r. zawierają kilka funkcji, uaktualnień wydajności i poprawek usterek.

### <a name="data-ingestion"></a>Pozyskiwanie danych

- **Wyświetlanie lub modyfikowanie metadanych lub definicji encji podczas dołączania danych z magazynu Azure Data Lake Storage** Można teraz przeglądać i edytować metadane lub definicje encji w widowiskach podczas dołączania danych z folderu Common Data Model w magazynie Azure Data Lake Storage. Możliwość ta zapewnia informacje zwrotne w czasie rzeczywistym, walidację modelu i sprawdzanie błędów. Pozwala on na płynną edycję zarówno pliku model.json jak i manifest.json.

### <a name="extensibility"></a>Rozszerzalność

- **Ulepszony eksport segmentów, niestandardowy harmonogram i duplikaty** Na liście można teraz [zobaczyć wszystkie eksporty dla określonego segmentu](export-destinations.md#view-exports-and-export-details). Ten nowy widok pomaga zarządzać sposobem, w jaki dany segment jest wykorzystywany oraz dostosowywać istniejące lub tworzyć nowe eksporty.    
  Można zdefiniować [niestandardowe harmonogramy odświeżania](export-destinations.md#schedule-and-run-exports) dla pojedynczego eksportu lub kilku eksportów jednocześnie. Do tej pory wszystkie eksporty były uruchamiane przy każdym odświeżeniu systemu.    
  Zamiast tworzyć nowy eksport od podstaw, możesz zacząć od istniejącego, aby zaoszczędzić trochę czasu.

- **Eksportowanie segmentów do usługi Microsoft Advertising** Rozszerzyliśmy lokalizacje eksportu o usługę Microsoft Advertising. Za pomocą funkcji dopasowywania klientów utwórz odbiorców w usłudze Microsoft Advertising, korzystając z danych ujednoliconych profilów klientów, a następnie używaj tych odbiorców na potrzeby kampanii reklamowych. Aby uzyskać więcej informacji, zobacz temat [Eksportowanie segmentów do usługi Microsoft Advertising](export-microsoft-advertising.md).

- **Eksport segmentów do LinkedIn Ads** Rozszerzyliśmy nasze miejsca docelowe eksportu o LinkedIn Ads i umożliwiamy Ci odblokowanie Targetowania kontaktowego oraz Targetowania firmowego poprzez LinkedIn poprzez eksport Twoich ujednoliconych danych profilu klienta. Aby uzyskać więcej informacji, zobacz temat [Eksportowanie segmentów do usługi LinkedIn Ads](export-linkedin-ads.md).


- **Eksportowanie segmentów do usługi Omnisend** Rozszerzyliśmy lokalizacje eksportu o usługę Omnisend. Używając segmentów utworzonych w Wyniki analiz odbiorców, możesz generować kampanie, prowadzić marketing za pomocą poczty e-mail oraz korzystać z zalet wybranych grup klientów w usłudze Omnisend. Aby uzyskać więcej informacji, zobacz temat [Eksportowanie segmentów do usługi Omnisend](export-omnisend.md)

### <a name="predictions"></a>Przewidywania

- **Raport dotyczący użyteczności danych wejściowych** Raport użyteczności danych wejściowych zapewnia skonsolidowany widok błędów i ostrzeżeń, które mogą być generowane przez Twoje przewidywania out-of-box. Podaje również zalecenia, jak poprawić wydajność modelu.    
  Raport jest dostępny po zakończeniu procesu szkolenia modelu. Jest on tworzony dla każdego modelu osobno, niezależnie od tego czy zakończył się sukcesem czy nie.
  Obecnie ta funkcja jest dostępna tylko w modelu Rezygnacja z transakcji. Aby uzyskać więcej informacji, zobacz [Raport dotyczący użyteczności danych wejściowych](manage-predictions.md#input-data-usability-report).

### <a name="relationships"></a>Relacje

- **Widok wizualizacji relacji** Widok wizualizacji relacji umożliwia zobaczenie wszystkich istniejących relacji między obiektami i ich podobieństwa. Relacje są teraz zorganizowane w grupy: relacje utworzone przez użytkownika, systemowe oraz dziedziczone. Można także wyeksportować widok jako obraz. Aby uzyskać więcej informacji, zobacz [Zobacz relacje](relationships.md#view-relationships). 

## <a name="april-2021-updates"></a>Aktualizacja z kwietnia 2021 r.

Aktualizacje z kwietnia 2021 r. zawierają kilka funkcji, uaktualnień wydajności i poprawek usterek.

### <a name="data-unification"></a>Ujednolicenie danych
 
- **Ulepszona funkcjonalność łączenia danych w celu ich ujednolicenia**    
  
   Usprawniliśmy proces konfigurowania doświadczenie użytkownika w konfiguracji scalania procesu ujednolicania danych. Zmiany obejmują intuicyjne porządkowanie łączonych pól oraz szczegółowe statystyki pól łączonych i pojedynczych.

- **Zmiana kolejności encji i skonfigurowanie wszystkich rekordów źródłowych do encji Klient**  
      
   Można teraz zmieniać kolejność i usuwać encje z istniejącego planu łączenia w procesie ujednolicania danych. Daje to możliwość elastycznej zmiany kolejności podmiotów w procesie dopasowania zgodnie z potrzebami biznesowymi. Dodatkowo umożliwiamy włączenie wszystkich niedopasowanych rekordów do końcowej encji *Klienta*, co pozwala na zdefiniowanie zbioru danych profilu klienta.

### <a name="enrichments"></a>Wzbogacenia

 - **Nowe wzbogacenie: Rozszerzone adresy**    
  
   Cieszymy się, że możemy wprowadzić nowe wzbogacenie, aby poprawić adresy w danych klientów. Adresy w Twoich danych mogą być nieustrukturyzowane, niekompletne lub nieprawidłowe. Ta funkcja od Microsoft służy do normalizacji i wzbogacenia adresów do formatu Common Data Model w celu lepszej dokładności i głębszej analizy.
 
   Aby uzyskać więcej informacji, zobacz [wzbogacanie profilów klientów o ulepszonych adresach](enrichment-enhanced-addresses.md).

- **Konfiguracja z przewodnikiem dla wzbogacenia**    
  
   Powróciliśmy do doświadczeń związanych z konfiguracją, aby wzbogacić je o proste, kierowane doświadczenie. Masz teraz przejrzysty proces tworzenia i edycji elementów wzbogacania krok po kroku.
 
   Dodatkowo rozdzieliliśmy konfigurację połączeń dla wzbogaceń firm trzecich, aby to samo połączenie mogło być używane przez wiele wzbogaceń. Tylko administratorzy mogą konfigurować nowe połączenia, ale utworzone połączenia są zawsze dostępne zarówno dla administratorów, jak i współautorów.    

   Aby uzyskać więcej informacji, zobacz [Omówienie połączeń](connections.md).

- **Wiele wzbogaceń tego samego typu**    
  
   Umożliwiamy teraz użytkownikom tworzenie i zarządzanie wieloma wzbogaceniami tego samego typu. Na przykład, można teraz utworzyć dwa oddzielne wzbogacenia adresu, aby wzbogacić dwa różne segmenty klientów. Istnieją ograniczenia dotyczące liczby utworzonych elementów wzbogacających tego samego typu i różnią się w zależności od typu elementu wzbogacającego.
  
   Aby uzyskać więcej informacji, zobacz artykuł [Wzbogacanie profilów klienta](enrichment-hub.md).

## <a name="march-2021-updates"></a>Aktualizacje z marca 2021 r.

Aktualizacje z marca 2021 r. zawierają kilka funkcji, uaktualnień wydajności i poprawek usterek.

### <a name="activities"></a>Działania

- **Kreator działań i typy semantyczne**

   Usprawniliśmy mapowanie działań w celu ułatwienia i uproszczenia tworzenia mapowania aktywności. Dzięki tej nowej funkcji użytkownicy mogą uzyskać porady, które pomogą w ukończeniu każdego kroku procesu. W kroku mapowania aktywności, oprócz wybierania wielu typów działań, użytkownik może wybrać sposób semantycznego mapowania danych dla *Subskrypcji* i/lub funkcji *SalesOrderLine* na standardowe schematy branżowe, których można używać do przetwarzania w dół.   

   Aby uzyskać więcej informacji, zobacz [Działania klientów](activities.md).

### <a name="data-ingestion"></a>Pozyskiwanie danych

- **Połącz z lokalnymi źródłami danych przy użyciu przepływów danych i portali Power Platform** Z zadowoleniem informujemy o wersji zapoznawczej przepływów danych Power Platform i łączności lokalnej za pomocą portali Customer Insights z powiązanym środowiskiem Power Platform lub Dataverse. Wszystkie nowe źródła danych utworzone w środowisku Customer Insights z połączonym środowiskiem Dataverse staną się domyślnie przepływami danych Power Platform, dostarczając łączność danych lokalnych i bogaty zestaw łączników i możliwości przekształcenia.

### <a name="extensibility"></a>Rozszerzalność

- **Eksport zorganizowany w połączeniach i eksportach** Nazwa strony **Eksportowanie miejsc docelowych** została zmieniona na **Połączenia** i dodano osobną stronę dla **Eksportów**. W ramach tej aktualizacji istniejące eksporty danych przejdą do par połączenia i eksportu przy użyciu tego połączenia. Administratorzy mają teraz lepszą przejrzystość na temat wychodzących danych na stronie **Połączenia**. Wszystkie role użytkowników mają dostęp do strony **Eksporty**, ale tylko administratorzy mogą zezwalać współautorom na edytowanie określonych eksportów przy użyciu połączeń udostępnionych.     
  Aby uzyskać więcej informacji, zobacz [Omówienie połączeń](connections.md) i [Omówienie eksportów](export-destinations.md).

- **Eksportowanie segmentów do usługi Campaign Monitor** Rozszerzyliśmy lokalizacje eksportu o usługę Campaign Monitor. Obecnie można eksportować segmenty z funkcji Customer Insights do list Campaign Monitor i używać ich jako modelu odniesienia dla kampanii marketingowych.    
   Aby uzyskać więcej informacji, zobacz temat [Eksportowanie do programu Campaign Monitor](export-campaign-monitor.md).

- **Eksportowanie segmentów do usługi Constant Contact** Rozszerzyliśmy lokalizacje eksportu o usługę Constant Contact. Obecnie można eksportować segmenty z funkcji Customer Insights do list Constant Contact i używać ich jako modelu odniesienia dla kampanii marketingowych.   
   Aby uzyskać więcej informacji, zobacz temat [Eksportowanie do programu Constant Contact](export-constant-contact.md).

- **Eksportowanie segmentów do usługi RollWorks** Rozszerzyliśmy lokalizacje eksportu o usługę RollWorks. Obecnie można eksportować segmenty z funkcji Customer Insights do odbiorców RollWorks i używać ich jako planu bazowego dla reklam B2B.    
   Aby uzyskać więcej informacji, zobacz temat [Eksportowanie do programu RollWorks](export-rollworks.md).

- **Eksportowanie segmentów do usługi Snapchat** Rozszerzyliśmy lokalizacje eksportu o usługę Snapchat. Obecnie można eksportować segmenty z funkcji Customer Insights do odbiorców Snapchat i używać ich jako modelu odniesienia dla reklam.     
   Aby uzyskać więcej informacji, zobacz temat [Eksportowanie do programu Snapchat](export-snapchat.md).

### <a name="predictions"></a>Przewidywania

- **Użyj filtrów produktów w przewidywaniach zaleceniach produktów** Dodaliśmy możliwość używania filtrów produktów w naszym modelu polecania produktów. Teraz można utworzyć przewidywanie, która korzysta tylko z podzbioru produktów.    
   Aby uzyskać więcej informacji, zobacz [Konfigurowanie filtrów produktu](predict-product-recommendation.md#configure-product-filters).

- **Utwórz segmenty na podstawie przewidywań modelu** Dodaliśmy szybko sposób tworzenia segmentów przy użyciu wyników modelu przewidywania. Na stronie wyników modelu można łatwo utworzyć nowy segment, wybierając nową opcję **Utwórz segment**.    
  Aby uzyskać więcej informacji, zobacz temat [Tworzenie segmentu w oparciu o model przewidywania](prediction-based-segment.md).

- **Objaśnienia do rekomendacji produktów** Zostały dodane informacje na temat kluczowych czynników, na podstawie których modelu AI uczy się w celu generowania rekomendacji produktów oraz stopnia, w jakim czynniki te wpływają na zalecenia dotyczące produktów. Te informacje zostaną dodane do ekranu wyników modelu.    
   Aby uzyskać więcej informacji, zobacz temat [Przejrzyj stan i wyniki prognozy](predict-product-recommendation.md#review-a-prediction-status-and-results).

## <a name="february-2021-updates"></a>Aktualizacje z lutego 2021 r.

Aktualizacje z lutego 2021 r. zawierają kilka funkcji, uaktualnienia wydajności i poprawki błędów.

#### <a name="extensibility"></a>Rozszerzalność

- **Eksportuj segmenty do rozwiązania AdRoll**

  Rozszerzyliśmy nasze miejsca docelowe eksportu o rozwiązanie AdRoll. Obecnie można eksportować segmenty z odbiorców aplikacji Customer Insights do rozwiązania AdRoll i używać ich jako podstawy dla reklam. Aby uzyskać więcej informacji, zobacz temat [Łącznik dla rozwiązania AdRoll](export-adroll.md).

#### <a name="segments"></a>Segmenty
 
- **Duplikuj segment**
  
  Aby utworzyć nowy segment na podstawie istniejącego, można teraz zduplikować segment i edytować zduplikowany segment, aby dokładniej go sprecyzować. 

- **Dodawanie dodatkowych atrybutów do segmentu**

  Obecnie atrybuty można dołączać do pliku wyjściowego segmentu, nawet jeśli nie są one częścią profilu klienta. Na przykład można uwzględnić identyfikatory subskrypcji w segmencie, nawet jeśli należy on do encji subskrypcji, która ma relację M:1 z encją klienta. Jeśli atrybut należy do obiektu powiązanego z encją klienta, można go obecnie dołączać.  

#### <a name="predictions"></a>Przewidywania

- **Tworzenie predykcyjnych rekomendacji produktu**

  Właściwa interpretacja zainteresowania klientów produktami do kupienia jest jednym z pierwszych kroków niezbędnych do zwiększenia przychodów firmy i zwiększenia lojalności klientów dzięki personalizacji i odpowiednim interakcjom. Podawanie rekomendacji dotyczących produktów, które nie interesują klienta, może stworzyć poczucie rozdziału między klientem a firmą, a w konsekwencji ograniczyć ogólny potencjalny przychód i pogorszyć wrażenia klienta. 

  Używając własnych danych, można teraz tworzyć prognozy dotyczące produktów, które klienci będą prawdopodobnie chcieli kupić w przyszłości. Aby uzyskać więcej informacji, zobacz temat [Przewidywanie rekomendacji dotyczących produktów](predict-product-recommendation.md).

#### <a name="system-administration"></a>Administrator systemu

- **Kopiowanie środowiska obsługuje więcej typów źródeł danych**

  Administratorzy mogą kopiować konfiguracje środowiska do nowego środowiska w tej samej organizacji. Ta funkcja rozszerza funkcje środowiska kopiowania w przypadkach, w których używane są źródła danych oparte na zarządzanym data lake usługi Microsoft Dataverse lub folderze Common Data Model.

## <a name="january-2021-updates"></a>Aktualizacje ze stycznia 2021

Aktualizacje ze stycznia 2021 zawierają kilka funkcji, uaktualnianie wydajności i poprawki błędów.

#### <a name="extensibility"></a>Rozszerzalność

- **Rozszerzona funkcjonalność i zwiększona wydajność dla eksportu SFTP** Możesz teraz wyeksportować wszystkie encje wyjściowe z Customer Insights do hosta SFTP. Wcześniej eksport ograniczał się do podmiotów segmentowych. Ponadto wydajność eksportu SFTP pozwala na zwiększenie ilości danych w krótszym czasie, w zależności od wydajności hosta SFTP.    
  Aby uzyskać więcej informacji, zobacz temat [Łącznik dla SFTP (wersja zapoznawcza)](export-sftp.md).  

#### <a name="segments"></a>Segmenty

- **Sugerowane segmenty obsługiwane przez systemy uczące się w celu poprawy wskaźników** Istnieje nowy sposób odkrywania i tworzenia segmentów. System wykorzystuje model AI do sugerowania segmentów, które mogą pomóc ulepszyć KPI (miarę), które już śledzisz. Pokazujemy zakres wpływu wybranych atrybutów na miarę lub inny atrybut podstawowy. Te informacje pomagają znaleźć potencjalne segmenty, które przedstawiają możliwości.    
  Aby uzyskać więcej informacji, zobacz temat [Sugerowane segmenty (wersja zapoznawcza)](suggested-segments.md).

#### <a name="data-unification"></a>Ujednolicenie danych

- **Ulepszony sposób dopasowania** W obszarze ujednolicania danych zaktualizowano rozgrywkę. Pozwala konfigurować i wyświetlać reguły dopasowania, w tym szczegółowe statystyki, aby dokładniej wyjaśnić, jak działa dopasowywanie. Istnieją opcje wyłączenia reguły dopasowania, aby nie była już aktywna podczas zachowywania konfiguracji, przeciągania i upuszczania reguł dopasowania i nie tylko.
  Aby uzyskać więcej informacji, zobacz [Dopasuj encje](match-entities.md).

- **Dane wyjściowe deduplikacji z procesu dopasowywania są dostępne jako encja** Dane wyjściowe procesu deduplikacji z procesu dopasowywania są teraz zapisywane w oddzielnej jednostce w celu dalszej analizy. Ta encja składa się z pól używanych w procesie deduplikacji i rekordu zwycięzcy oraz odpowiednich rekordów alternatywnych, które są łączone z rekordem zwycięzcy.
  Aby uzyskać więcej informacji, zobacz [Deduplikacja wyjściowa jako encja](match-entities.md#deduplication-output-as-an-entity).

#### <a name="system-administration"></a>Administrator systemu

- **Można teraz bezproblemowo udostępniać dane wyjściowe funkcji Microsoft Dataverse** Możesz teraz udostępniać dane wyjściowe Customer Insights aplikacjom Microsoft Dataverse przy użyciu usług Microsoft Dataverse zarządzanego Data Lake. Po powiązaniu środowiska Dataverse z Customer Insights możesz włączyć udostępnianie danych.
  Aby uzyskać więcej informacji, zobacz [Zarządzanie środowiskami](manage-environments.md).




[!INCLUDE[footer-include](../includes/footer-banner.md)]