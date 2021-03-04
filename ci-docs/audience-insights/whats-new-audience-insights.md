---
title: Nowe i nadchodzące funkcje
description: Informacje o nowych funkcjach, ulepszeniach i poprawkach błędów.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 9183c8af4fb9f9f08ac63d8d0cd37c6868bba310
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270445"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Co nowego w możliwości wglądu odbiorców w Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Z przyjemnością informujemy o najnowszych aktualizacjach! W tym artykule podsumowano publiczne wersje zapoznawcze, ulepszenia ogólnej dostępności oraz aktualizacje funkcji. Aby zobaczyć długofalowe plany dotyczące funkcji, zapoznaj się z [planami wydań rozwiązań Dynamics 365 i Power Platform](https://docs.microsoft.com/dynamics365/release-plans/).

Możesz również obejrzeć poniższy film, aby dowiedzieć się więcej o możliwościach planowanych na ostatnie sześć miesięcy.

> [!VIDEO https://www.youtube.com/embed/jQh-7pscH30]

Wdrażamy aktualizacje kolejno regionami. Niektóre regiony mogą zobaczyć nowe funkcje wcześniej. O ile nie zaznaczono inaczej, nie trzeba podejmować żadnych działań, a w razie przestoju przeprowadzimy automatyczną aktualizację bez konieczności przestoju.

> [!TIP]
> Aby przesłać i głosować na żądania funkcji i sugestie dotyczące produktu, przejdź do [portalu Pomysły aplikacji Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

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


## <a name="december-2020-updates"></a>Aktualizacje z grudnia 2020

Aktualizacje w grudniu 2020 zawierają kilka funkcji, uaktualnianie wydajności i poprawki błędów.

### <a name="new-and-updated-features-in-december-2020"></a>Nowe i zaktualizowane funkcje w grudniu 2020

#### <a name="data-enrichment"></a>Wzbogacanie danych

- **Udoskonalone wzbogacenie marki i zainteresowania**
  
  Uprościliśmy nasze wskaźniki podobieństwa, aby były łatwiejsze do zrozumienia i użycia. Możesz teraz szybko identyfikować klientów na podstawie ich powinowactwa do danej marki lub zainteresowania.

  Dodatkowo dodaliśmy nowe opcje konfiguracji, aby lepiej kontrolować sposób wzbogacania profili klientów. 

  Aby uzyskać więcej informacji, zobacz [Wzbogacanie profilów klientów o koligacje marki i zainteresowania](enrichment-microsoft-graph.md).

- **Kontrola profilów do wzbogacenia**

  Możesz teraz wzbogacić tylko podzbiór profili klientów o opcję wyboru encji segmentu zamiast domyślnej encji klienta. Utwórz segment z profilami klientów, które chcesz wzbogacić, i wybierz go w konfiguracji wzbogacania dla zestawu danych klienta.
  Ta funkcja jest obecnie dostępna tylko dla wzbogacań dostarczanych przez firmę Experian i HERE Technologies. Wkrótce udostępnimy tę możliwość większej liczbie wzbogaceń.

  Aby uzyskać więcej informacji, zobacz temat [Wzbogać profile klientów o dane demograficzne z Experian](enrichment-experian.md) lub [Wzbogacenie profili klientów o HERE Technologies](enrichment-here.md).

#### <a name="extensibility"></a>Rozszerzalność

- **Aktywowanie segmentów za pośrednictwem usługi Autopilot**

  Eksportuj segmenty do Autopilot i wykorzystuj je w celach marketingowych. Aby uzyskać więcej informacji, zobacz temat [Łącznik dla Autopilot (wersja zapoznawcza)](export-autopilot.md).

- **Aktywowanie segmentów za pośrednictwem usługi SendGrid**

  Eksportuj segmenty do SendGrid i wykorzystuj je w celach marketingowych. Aby uzyskać więcej informacji, zobacz temat [Łącznik dla SendGrid](export-sendgrid.md).

#### <a name="system-administration"></a>Administrator systemu

- **Zaktualizowane środowisko zarządzania**
  
  Możesz teraz tworzyć, edytować, usuwać i resetować środowiska bezpośrednio z selektora środowiska w nagłówku aplikacji. 
  
  Ponadto środowisko, którego używasz, zostanie przypięte u góry panelu środowiska, więc nie musisz już go szukać.

  Aby uzyskać więcej informacji, zobacz [Zarządzanie środowiskami](manage-environments.md).

## <a name="november-2020-updates"></a>Aktualizacje z listopada 2020

Aktualizacje w listopadzie 2020 zawierają kilka funkcji, uaktualnianie wydajności i poprawki błędów.

### <a name="new-and-updated-features-in-november-2020"></a>Nowe i zaktualizowane funkcje w listopadzie 2020

#### <a name="data-enrichment"></a>Wzbogacanie danych

- **Wprowadź własne wzbogacone dane za pomocą niestandardowego importu Secure File Transfer Protocol (SFTP)**
  
  Niestandardowy import SFTP umożliwia importowanie wzbogaconych danych, które nie muszą przechodzić przez proces ujednolicania danych. Zapoznaj się z informacjami o imporcie niestandardowym SFTP.

  Aby uzyskać więcej informacji, zobacz temat [Wzbogać profile klientów o niestandardowe dane (wersja zapoznawcza)](enrichment-SFTP-custom-import.md).
 
- **Wzbogać dane swoich klientów o dane lokalizacyjne z HERE Technologies**

  Dzięki usługom wzbogacania danych HERE Technologies możesz dokładniej zrozumieć lokalizację swoich klientów dzięki normalizacji adresu, ekstrakcji szerokości i długości geograficznej i nie tylko. Dowiedz się więcej o wzbogacaniu z HERE Technologies.

  Aby uzyskać więcej informacji, zobacz temat [Wzbogacenie profili klientów o HERE Technologies](enrichment-here.md).

#### <a name="data-unification"></a>Ujednolicenie danych

- **Elastyczność w zakresie włączania profilowania danych na wybranych encjach i polach z konta magazynu**

  Możesz wskazać, które jednostki danych i pola z folderu Common Data Model na koncie magazynowym usługi Azure Data Lake, które chcesz włączyć profilowanie danych w ramach procesu pozyskiwania danych.

  Aby uzyskać więcej informacji, zobacz [Połącz się z folderem Common Data Model](connect-common-data-model.md#connect-to-a-common-data-model-folder).

#### <a name="extensibility"></a>Rozszerzalność

- **Aktywowanie segmentów za pośrednictwem usługi Google Ads**

  Eksportuj segmenty z do list odbiorców Google Ads i używaj tych list do reklamowania się w wyszukiwarce Google, sieci reklamowej Google, YouTube i Gmailu. Dowiedz się więcej o aktywowaniu segmentów przez Google Ads.

  Aby uzyskać więcej informacji, zobacz temat [Łącznik dla Google Ads](export-google-ads.md).

- **Aktywowanie segmentów za pośrednictwem usługi Marketo**

  Eksportuj segmenty do odbiorców Marketo i używaj tych odbiorców do automatyzacji marketingu. Dowiedz się więcej o aktywowaniu segmentów przez Marketo. 

  Aby uzyskać więcej informacji, zobacz temat [Łącznik dla Marketo](export-marketo.md).

- **Aktywowanie segmentów za pośrednictwem usługi DotDigital**

  Eksportuj segmenty do DotDigital i wykorzystuj je w celach marketingowych. Dowiedz się więcej o aktywowaniu segmentów przez DotDigital. 

  Aby uzyskać więcej informacji, zobacz temat [Łącznik dla DotDigital](export-dotdigital.md).

#### <a name="predictions"></a>Przewidywania

- **Przewidywanie rezygnacji z transakcji**

  Funkcja przewidywania rezygnacji z transakcji umożliwia, bez pomocy analityka danych, przewidywanie prawdopodobieństwa, że klient przestanie kupować produkty lub usługi.  Korzystając z wyniku prognozy, możesz łączyć inne informacje o klientach, takie jak wartość klienta, w celu tworzenia segmentów klientów o wysokim ryzyku rezygnacji lub klientów o dużej wartości. Użyj tego segmentu, aby bezpośrednio kierować reklamy do klientów poprzez działania marketingowe, obsługę klienta i inne scenariusze, aby zmniejszyć ryzyko odejścia.
 
  Skonfiguruj definicję rezygnacji jako okno czasowe specyficzne dla Twojej firmy i określ, kiedy klienci są uznawani za odchodzących. Na przykład sklep spożywczy może chcieć uznać klienta za klienta, który zrezygnował z usługi, jeśli nie kupił niczego w ciągu ostatnich 30 dni.
 
  W miarę kontynuowania tworzenia prognozy wskażemy Ci, jakie dane są potrzebne, i umożliwimy mapowanie danych o Twojej firmie na pola wymagane do przewidywania rezygnacji klientów. Możesz również ustawić harmonogram ponownego szkolenia modelu na podstawie nowych informacji w systemie, aby dostosować się do zmieniających się okoliczności biznesowych.
 
  Więcej informacji można znaleźć w temacie [Przewidywanie rezygnacji z transakcji (wersja zapoznawcza)](predict-transactional-churn.md).

#### <a name="system-administration"></a>Administrator systemu

- **Resetuj środowisko**

  Zresetuj wszystko w środowisku wybranego wystąpienia, aby rozpocząć od nowa.

  Aby uzyskać więcej informacji, zobacz [Zresetuj istniejące środowisko](manage-environments.md#reset-an-existing-environment).


- **Łączenie się z kontem magazynowym Azure Data Lake przy użyciu głównej usługi**

  Zapisuj dane wyjściowe i odczytuj dane z konta magazynu przy użyciu głównej usługi platformy Azure. Istniejące połączenia z kontem magazynu mogą nadal korzystać z klucza konta. Oferują też opcję uaktualnienia, która umożliwia korzystanie z usługi, która jest przenoszona na następny okres. Nowe połączenia będą oparte na metodzie uwierzytelniania z usługą główną dla konta magazynu.

  Aby uzyskać więcej informacji, zobacz temat [Połącz się z kontem Azure Data Lake Storage Gen2 za pomocą jednostki usługi platformy Azure, aby uzyskać szczegółowe informacje o odbiorcach](connect-service-principal.md).

## <a name="october-2020-updates"></a>Aktualizacje z października 2020

Aktualizacje w październiku 2020 zawierają kilka funkcji, uaktualnianie wydajności i poprawki błędów.

### <a name="new-and-updated-features-in-october-2020"></a>Nowe i zaktualizowane funkcje w październiku 2020

#### <a name="extensibility"></a>Rozszerzalność

- **Eksport do Mailchimp**

Eksportuj segmenty do istniejących list odbiorców w Mailchimp, aby zapewnić spersonalizowaną obsługę poczty e-mail dla swoich klientów.

Aby uzyskać więcej informacji, zobacz temat [Łącznik dla Mailchimp](export-mailchimp.md).

#### <a name="data-enrichment"></a>Wzbogacanie danych

- **UsuN zduplikowane rekordy źródłowe w encji Dopasuj**

Określ reguły deduplikacji dotyczące jednostek używanych w procesie dopasowywania do identyfikacji zduplikowanych rekordów. Scal je w jeden rekord i połącz ze sobą wszystkie rekordy źródłowe z tym scalanym rekordem. Ten zdeduplikowany rekord zostanie następnie użyty w procesie dopasowywania między encjami.

Aby uzyskać więcej informacji, zobacz [Definiowanie deduplikacji dla encji dopasowania](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="system-administration"></a>Administrator systemu

- **Aranżacja: Nowa opcja odświeżania w scalaniu**

Do dzisiaj, kiedy uruchamiasz proces scalania, system obsługiwał wszystkie dalsze procesy, które zależą od scalania i kolejnych procesów. Można teraz sprawdzić wyniki procesu scalania (ujednoliconej encji klienta) przed użyciem go podczas przetwarzania podrzędnego, takiego jak segmenty lub miary.
Na stronie scalania możesz teraz wybrać uruchomienie tylko kroku scalania i uruchomić tylko ten proces. Aby odświeżyć również wszystkie dalsze procesy, możesz wybrać uruchom scalanie i dalsze procesy. 

## <a name="september-2020-updates"></a>Aktualizacje z września 2020

Aktualizacje we wrześniu 2020 zawierają kilka funkcji, uaktualnianie wydajności i poprawki błędów.

### <a name="new-and-updated-features-in-september-2020"></a>Nowe i zaktualizowane funkcje we wrześniu 2020

#### <a name="activities"></a>Działania

- **Inteligentne przewidywanie semantyki atrybutów**

Ta nowa funkcja przewiduje typy semantyczne atrybutów wejściowych, które są przekazywane do procesu ujednolicania danych. Używa modeli uczenia maszynowego, co poprawia dokładność i pozwala zaoszczędzić czas.

#### <a name="enrichments"></a>Wzbogacenia

- **Wzbogacenie danych demograficznych od Experian**

Wzbogacenie danych demograficznych z Experian jest obecnie dostępne w wersji zapoznawczej. Experian jest globalnym liderem w zakresie sprawozdawczości kredytowej dla konsumentów i firm oraz usług marketingowych. Dzięki [usługom wzbogacania danych Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage), możesz lepiej zrozumieć klientów zbogacając profile klientów danymi demograficznymi, takimi jak rozmiar gospodarstwa domowego, przychód itp.

Aby użyć tej funkcji, należy mieć aktywną subskrypcję programu Experian.

Aby uzyskać więcej informacji, zobacz [Wzbogacanie profilów klientów za pomocą danych demograficznych z Experian](enrichment-experian.md)


#### <a name="system-administration"></a>Administrator systemu

- **Okienko Szczegóły zadania**

Okienko Szczegóły zadania umożliwia wyświetlenie szczegółowych informacji o zadaniach wykonywanych przez system. Jest to wygodny sposób na identyfikowanie problemów z konfiguracją oraz znajdowanie rozwiązań.
Przejrzyj komunikaty o błędach i zobacz, jak rozwiązać potencjalne problemy.
 
- **Przetwarzanie informacji dodanych do kolejnych stron**

To ulepszenie dodaje informacje o stanie encji na stronie **Encje** i **Klienci**.
 
Oprócz tego można znaleźć szczegółowe informacje na temat postępu procesów, wraz ze szczegółami zadania na obu tych stronach.

- **Udoskonalenia strony Stan systemu**

Udoskonaliliśmy strukturę tabeli Szczegóły stanu w **System** > **Stan** podczas przeglądania eksportu danych.
 
Oprócz tego błędy w kolumnie **Szczegóły** są bardziej szczegółowe i bardziej funkcjonalne. 
 
- **Anuluj cofa zadanie z powrotem do poprzedniego stanu**

Jeśli zadanie zostanie anulowane, na przykład w procesie dopasowania, powróci do ostatniego stanu. Jeśli na przykład proces Dopasuj został ukończony wczoraj a Ty anulujesz go dzisiaj, powróci on do stanu Zakończony powodzeniem z wczoraj.


## <a name="august-2020-updates"></a>Aktualizacje z sierpnia 2020 r.

Aktualizacje w sierpniu 2020 zawierają kilka funkcji, uaktualnianie wydajności i poprawki błędów.

### <a name="new-and-updated-features-in-august-2020"></a>Nowe i zaktualizowane funkcje w sierpniu 2020

#### <a name="data-unification"></a>Ujednolicenie danych

- **Udoskonalony sposób obsługi etapu mapy podczas zjednoczenia danych**

  Sposób działania etapu mapowania w procesie ujednolicania danych pozwala na bardziej płynne wybieranie encji, atrybutów i definiowanie semantyki.

  Zmiany obejmują:
  
  - Mniejsza liczba interakcji wymaganych do dodania encji i pól
  - Ulepszone funkcje wyszukiwania na stronie Mapa
  - Wizualna i łatwa identyfikacja sugerowanego typu pola

#### <a name="enrichment"></a>Wzbogacenie

- **Wzbogacanie zainteresowania dostępne na kolejnych rynkach**

  Rozszerzamy możliwość wzbogacenia zainteresowania poza Stany Zjednoczone na pięć innych rynków: Kanadę, Australię, Wielką Brytanię, Francję i Niemcy. Dzięki temu rozszerzeniu możesz wzbogacić swoje dane klientów o zainteresowania bardziej odpowiednie na tych rynkach. Twoje profile klientów znajdujących się na tych rynkach będą również wzbogacone o lokalne dane zastrzeżone w programie Microsoft Graph.
  Aby uzyskać więcej informacji, zobacz [Wzbogacanie profilów klientów o koligacje marki i zainteresowania](enrichment-microsoft-graph.md)


## <a name="july-2020-updates"></a>Aktualizacje z lipca 2020 r.

Aktualizacje z lipca 2020 zawierają kilka funkcji, uaktualnianie wydajności i poprawki błędów.

### <a name="new-and-updated-features-in-july-2020"></a>Nowe i zaktualizowane funkcje wprowadzone w lipcu 2020

#### <a name="extensibility"></a>Możliwości rozszerzania

- **Wyzwalacz Power Automate dla kompletnego procesu ujednolicenia**

  Rozszerzyliśmy wyzwalacze dla Power Automate, i użytkownik może utworzyć powiadomienie lub akcję po wykonaniu odświeżenia procesu ujednolicania (mapowanie, dopasowanie, scalanie).    
  Aby uzyskać więcej informacji, zobacz [Łącznik Power Automate](export-power-automate.md)

#### <a name="enrichment"></a>Wzbogacenie

- **Wzbogacanie zainteresowania marką dostępne na kolejnych rynkach**

  Rozszerzamy możliwość wzbogacenia sympatii do marki poza Stany Zjednoczone na pięć innych rynków: Kanadę, Australię, Wielką Brytanię, Francję i Niemcy. Dzięki temu rozszerzeniu możesz wzbogacić dane klientów o lokalne marki na tych rynkach. Twoje profile klientów znajdujących się na tych rynkach będą również wzbogacone o lokalne dane zastrzeżone w programie Microsoft Graph.
  Aby uzyskać więcej informacji, zobacz [Wzbogacanie profilów klientów o koligacje marki i zainteresowania](enrichment-microsoft-graph.md)

## <a name="june-2020-updates"></a>Aktualizacje z czerwca 2020 r.

Aktualizacje z czerwca 2020 zawierają kilka funkcji, uaktualnianie wydajności i poprawki błędów.

### <a name="new-and-updated-features-in-june-2020"></a>Nowe i zaktualizowane funkcje wprowadzone w czerwcu 2020

#### <a name="enrichment"></a>Wzbogacenie

- **Wzbogacenie danymi firmowymi z Leadspace**
  
  Umożliwia zdefiniowanie pól w ujednoliconych profilach klientów służących do wyszukiwania pokrewnych danych firmowych w programie Leadspace. Po uruchomieniu procesu wzbogacania profile B2B są wzbogacane o więcej atrybutów, w tym wielkość firmy, lokalizację, branżę i inne.    
  Ta współpraca umożliwia poprawienie jakości danych dzięki danym pochodzącym od innych firm. Aby można było użyć tego wzbogacenia, konieczne jest posiadanie licencji Leadspace na dostęp do danych firmowych typu B2B. System użyje tej licencji, aby zapewnić ciągłe wzbogacanie danych.    
  Aby uzyskać więcej informacji, zobacz [Wzbogacanie profili firmowych za pomocą Leadspace](enrichment-leadspace.md).

- **Strona centrum wzbogacania**

  Wszystkie dostępne Wzbogacanie danych od pierwszych i innych dostawców wzbogaceń są konfigurowane w tym samym miejscu. Konfigurowanie wzbogacania danych jest sprawnym doświadczeniem, które jest zarządzane z typowego miejsca.    
  Aby uzyskać więcej informacji, zobacz artykuł [Wzbogacanie profilów klienta](enrichment-hub.md).

- **Oddzielanie wzbogacania koligacji marek i zainteresowań**

  Koligacje marek i zainteresowania są teraz dostępne jako dwa niezależne wzbogacenia. Wyodrębnione wzbogacenia zapewniają elastyczność konfigurowania i zarządzania nimi osobno w zależności od wymagań biznesowych lub potrzeb.    
  Aby uzyskać więcej informacji, zobacz [Wzbogacanie profilów klientów o koligacje marki i zainteresowania](enrichment-microsoft-graph.md).

#### <a name="extensibility"></a>Możliwości rozszerzania

- **Klikalne adresy URL dla działań ujednoliconych w dodatku Karta klienta Dynamics 365**

  Ujednolicone działania w dodatku karty klienta pokazują teraz klikalne adresy URL, jeśli takie adresy URL zostały zdefiniowane podczas konfigurowania działań.    
  Aby uzyskać więcej informacji, zobacz [Dodatek Karta klienta](customer-card-add-in.md).

- **Koligacje marki i zainteresowania dostępne w dodatku Karta klienta Dynamics 365**

  Nowy formant w dodatku Karta klienta Dynamics 365 umożliwia pokazywanie wzbogaceń koligacji marki i zainteresowań w kontaktach w aplikacjach Customer Engagement w Dynamics 365.    
  Aby uzyskać więcej informacji, zobacz [Dodatek Karta klienta](customer-card-add-in.md).

- **Więcej wyzwoleń Power Automate**

  Rozszerzyliśmy nasze wyzwalacze dla Power Automate i dodaliśmy następujące wyzwalacze:
  - Pobierz powiadomienie lub wykonaj akcję, kiedy zakończy się zautomatyzowane pełne odświeżanie (źródła danych, zjednoczanie, pomiary, eksport)
  - Zdefiniuj próg dla miary biznesowej. Można na przykład utworzyć powiadomienie wysyłane po przekroczeniu określonego progu. Oprócz tego wyzwalacz dostarcza informacji, które pozwalają na zbudowanie bardziej złożonych przepływów pracy w Power Automate.    
  Aby uzyskać więcej informacji, zobacz [Łącznik Power Automate](export-power-automate.md)

- **Eksportowanie do Menedżera Facebook Ads**
  
  Dzięki tej funkcji można eksportować segmenty do Facebook Ads Manager. Segmenty są eksportowane jako odbiorcy niestandardowi w celu korzystania z ujednoliconych profilów klientów w kampaniach marketingowych i reklamach Facebook. Odbiorcy niestandardowi są również przydatni do tworzenia kampanii w programie Instagram za pośrednictwem Menedżera Facebook Ads.    
  Aby uzyskać więcej informacji, zobacz temat [Łącznik dla Menedżera Facebook Ads](export-facebook.md).

#### <a name="predictions"></a>Przewidywania

- **Przewidywanie zmian subskrypcji**

  Zastosuj środowisko nadzorowane w celu utworzenia przewidywania zmian w obszarach subskrypcji, takich jak usługi w chmurze, członkostwo klienta i inne sektory. 

  Funkcja Przewidywanie zmian subskrypcji umożliwia prognozowanie prawdopodobieństwa, że klient wstrzyma korzystanie z produktów lub usług opartych na subskrypcji bez angażowania specjalisty od danych. Przy użyciu wyniku przewidywania można połączyć inne informacje o klientach, aby stworzyć segmenty o wysokim ryzyku rezygnacji. Za pomocą tego segmentu możesz bezpośrednio kierować reklamy do klientów w ramach marketingu, obsługi klienta i innych scenariuszy, aby zmniejszyć ryzyko rezygnacji określonych klientów, aby zwiększyć przychody i obniżyć koszty.

  W ramach tego procesu użytkownik może skonfigurować definicję rezygnacji jako okno oparte na czasie związane z daną działalnością. Na przykład firma zajmująca się strumieniowym przesyłaniem wideo, która ma proces comiesięcznej subskrypcji, może chcieć rozważyć, że klient zrezygnuje po 15 dniach od daty wygaśnięcia subskrypcji.

  Podczas pracy nad przewidywaniem podpowiemy, jakie dane są potrzebne, i umożliwimy mapowanie danych o firmie na pola wymagane do przewidywania rezygnacji klientów. Informacje służbowe zmieniają się, możesz również ustawić harmonogram ponownych szkoleń na nowych informacjach w systemie, aby dostosować się do zmieniających się warunków biznesowych.    
  Aby uzyskać więcej informacji, zobacz [Przewidywanie zmian subskrypcji (wersja zapoznawcza)](predict-subscription-churn.md).

#### <a name="segments"></a>Segmenty

- **Znajdź podobnych klientów**
  
  Znajdź podobnych klientów na bazie klientów przy użyciu sztucznej analizy. Model klasyfikacji binarnej uczenia maszynowego przypisuje wynik podobieństwa do klientów w rozwiniętym segmencie. Wynik jest uzależniony od podobieństwa do klientów w segmencie źródłowym. W zależności od wyniku podobieństwa do nowo tworzonego segmentu są dodawane profile klientów.

  Czasami nazywane modelowaniem podobnym w marketingu cyfrowym, wykorzystuje model AI, aby pomóc znaleźć klientów, którzy są podobni do innego segmentu Twoich klientów, biorąc pod uwagę więcej atrybutów. Nie tylko zezwala na wybieranie atrybutów, ale również umożliwia określenie maksymalnej liczby klientów, którzy powinni należeć do nowego segmentu. Następnie model AI obliczy wyniki podobieństwa dla każdego klienta na podstawie wybranych atrybutów i znajdzie klientów o wyższym średnim poziomie podobieństwa. Powstały segment będzie obejmował klientów, którzy wyglądają podobnie do klienta w oryginalnym segmencie.    
  Aby uzyskać więcej informacji, zobacz [Podobni klienci](find-similar-customer-segments.md).

- **Nakładanie się segmentów i różnice**

  Nakładanie się segmentów umożliwia wyświetlenie ilu klientów i którzy z nich są częścią wspólną dwóch lub więcej segmentów. Na przykład, jak segment obejmujący klientów wydających dużo pokrywa się z segmentem bardzo zadowolonych klientów lub jak segment klientów rezygnujących pokrywa się z segmentem klientów z niskim zadowoleniem. Dodatkowo możesz analizować, jak zmienia się nakładanie się na podstawie wybranego dodatkowego atrybutu.

  Elementy odróżniające segmenty ukazują co odróżnia jeden segment od reszty klientów lub innego segmentu. Wystarczy tylko określić segment, a system zidentyfikuje atrybuty profilu i miary, które odróżniają segment w postaci uporządkowanej listy różnic - od najsilniejszego elementu odróżniającego do najsłabszego.    
  Aby uzyskać więcej informacji zobacz [Informacje o segmentach (wersja zapoznawcza)](segment-insights.md).

- **Okres istnienia segmentu**
  
  Zdefiniuj harmonogram, aby aktywować lub dezaktywować segment.    
  Aby uzyskać więcej informacji, zobacz [Zarządzanie istniejącymi segmentami](segments.md#manage-existing-segments).

## <a name="may-2020-updates"></a>Aktualizacje z maja 2020 r.

Aktualizacje z maja 2020 roku zawierają kilka funkcji, uaktualnień wydajności oraz poprawki błędów.

### <a name="new-and-updated-features-in-may-2020"></a>Nowe i zaktualizowane funkcje w maju 2020

#### <a name="data-ingestion"></a>Pozyskiwanie danych

- **Pozyskiwanie danych w czasie rzeczywistym: widoki historii**

  Podczas korzystania z naszego interfejsu API do pozyskiwania aktualizacji w czasie rzeczywistym, można wyświetlić zagregowaną historię do 30 dni, dotyczącą tych aktualizacji. Użytkownik ma dostęp do zagregowanych rekordów wszystkich zakończonych pomyślnie lub zakończonych niepowodzeniem wywołań interfejsów API, w tym wyników, systemu źródłowego i innych przydatnych metadanych.    
  Aby uzyskać więcej informacji, zobacz [Pozyskiwanie danych w czasie rzeczywistym](real-time-data-ingestion.md).

- **Pozyskiwanie danych w czasie rzeczywistym: aktualizacje profilu**

  To rozszerzenie pozyskiwania danych w czasie rzeczywistym umożliwia wyświetlenie w ciągu sekund zmian w poszczególnych polach profilu użytkownika.    
  Oprócz funkcji działań w czasie rzeczywistym system obsługuje aktualizacje o niskim poziomie opóźnienia w polach profilu. Aktualizacje w czasie rzeczywistym dla pól profilów mają czas wygaśnięcia i dlatego nie są zamiennikami zaplanowanych odświeżeń.    
  Aby uzyskać więcej informacji, zobacz [Pozyskiwanie danych w czasie rzeczywistym](real-time-data-ingestion.md).

#### <a name="extensibility"></a>Możliwości rozszerzania

- **Zaktualizowana oś czasu i podział na strony w dodatku Karta klienta**

  Oś czasu rozwiązania dodatku karty klienta jest zgodna z osią czasu działania. Udoskonalona zostałą paginacja osi czasu, która ukazuje do 50 działań naraz. Umożliwia także ładowanie większej liczby działań na osi czasu.    
  Aby uzyskać więcej informacji, zobacz [Dodatek Karta klienta](customer-card-add-in.md).

- **Wyzwalanie Power Automate dla zmian segmentu**

  Wyzwalacze dla Power Automate służą do definiowania, co można utworzyć z przepływu. Nowo dodany wyzwalacz umożliwia zdefiniowanie progu dla segmentu. Można na przykład utworzyć powiadomienie wysyłane po przekroczeniu określonego progu.    
  Aby uzyskać więcej informacji, zobacz [Łącznik Power Automate](export-power-automate.md).

- **Obsługa wielodostępna dla modeli niestandardowych**

  Konfigurowanie przepływów pracy dla modeli niestandardowych za pomocą usługi sieci Web innej dzierżawy Uczenie maszynowe Azure. Podczas tworzenia nowego przepływu pracy dla modeli niestandardowych możesz zalogować się do dzierżawy Azure Machine Learning. Ta funkcja stanowi dodatek do istniejących funkcji integracji z własną niestandardową usługą sieci Web Uczenie maszynowe Azure.    
  Aby uzyskać więcej informacji, zobacz [Niestandardowe modele uczenia maszynowego](custom-models.md).

#### <a name="segments"></a>Segmenty

- **Automatyzacja ścieżki encji**

  Podczas tworzenia segmentu użytkownicy muszą zdefiniować ścieżkę encji. Dzięki tej funkcji można w zautomatyzować definicję ścieżki encji, aby skupić się na kryteriach segmentacji, które mają być brane pod uwagę.    
  Jeśli encja, dla której chcesz segmentować klientów, jest bezpośrednio powiązana z jednolitą encją klienta, nie trzeba już definiować ścieżki encji. Jeśli jednak istnieje wiele możliwych ścieżek encji, należy zdefiniować je ręcznie.

- **Akcje na wielu segmentach**
  
  Użytkownicy mogą wybierać wiele segmentów i wykonywać na nich działania, takie jak odświeżanie segmentów jednym kliknięciem.    

- **Odśwież segmenty**

  Użytkownicy mogą odświeżać jeden segment lub wybierać tylko te segmenty, które chcą odświeżyć.    

  
- **Udoskonalenia w segmentach złożonych**

  Użytkownicy mogą tworzyć, edytować i usuwać segmenty oparte na innych segmentach. Na przykład segment skonstruowany na innym segmencie, który został utworzony w trzecim segmencie.    

- **Strona Lista segmentów**

  Nowy projekt strony segmentów korzysta z formatu listy umożliwiając wyświetlenie większej liczby segmentów jednocześnie. Dodanie pola wyszukiwania umożliwia szybkie znalezienie segmentów. Użytkownicy mogą obecnie stosować akcje, takie jak pobieranie lub usuwanie wielu segmentów naraz. Zostanie wprowadzony nowy sposób tendencji, który umożliwia szybką identyfikację znaczących zmian w segmentach.    
  Aby uzyskać więcej informacji, zobacz [Tworzenie segmentów i zarządzanie nimi](segments.md).

#### <a name="system-administration"></a>Administrator systemu

- **Aplikacja Customer Insights dostępna w Microsoft Dynamics 365 Online Government**

  Dzięki rosnącej liczbie kanałów służących do interakcji, dane dotyczące obywateli są rozproszone w licznych systemach, pofragmentowane na dane o charakterze silosowym, dając fragmentaryczny widok informacji o interakcjach z obywatelami. Bez pełnego widoku interakcji obywateli w różnych kanałach rządy nie są w stanie dokonać modernizacji na skalę. Firma Microsoft pragnie wspierać potrzeby technologiczne administracji rządowej, aby sprostać oczekiwaniom obywateli dotyczącym spójnych i responsywnych środowisk.    
  Wersja 1 z 2020 roku, Dynamics 365 Customer Insights, będzie dostępna dla Government Community Cloud (GCC), środowiska opracowanego w celu sprostania wyższym wymaganiom zgodności z agendami rządowymi Stanów Zjednoczonych. Agencje realizują zunifikowany widok obywateli i używają wstępnie utworzonego AI, aby wyciągnąć wnioski, które ulepszają interakcje, zapewniają funkcje pracownikom i przekształcają społeczności jednocześnie zmniejszając złożoność IT i zachowując zgodność ze standardem Stanów Zjednoczonych i normami bezpieczeństwa. Dynamics 365 Government jest zgodne z wymaganiami Federal Risk and Authorization Management Program (FedRAMP) Stanów Zjednoczonych, dzięki czemu federalne agencje amerykańskie korzystają z oszczędności kosztów i rygorystycznych zabezpieczeń w chmurze firmy Microsoft.

## <a name="april-2020-updates"></a>Aktualizacja z kwietnia 2020 r.

Aktualizacje z kwietnia 2020 roku zawierają kilka funkcji, uaktualnień wydajności oraz poprawki błędów.

### <a name="new-and-updated-features-in-april-2020"></a>Nowe i zaktualizowane funkcje w kwietniu 2020

#### <a name="activities"></a>Działania

- **Mapowanie encji działanie do standardowego typu działania**
  
  Konfigurowanie i przechowywanie działań opiera się obecnie na projektowaniu statycznym w celu ich wyświetlania na osi czasu. Semantyczne znaczenie działań, które ma potencjalne możliwości wielokrotnego użytku w modelach AI, nie jest obecnie w pełni używane. Planuje się, że na oś czasu działania będzie bardziej dynamiczna, w oparciu o typ działania i lepszą analizę semantyczną tych działań. Ta funkcja ma za zadanie identyfikować typ działania, co zdefiniowano w Common Data Model dla każdego pozyskanego działania.
  Aby uzyskać więcej informacji, zobacz [Działania klientów](activities.md).

#### <a name="data-ingestion"></a>Pozyskiwanie danych

- **Pozyskiwanie danych w czasie rzeczywistym: działania**
  
  Pozyskiwanie danych w czasie rzeczywistym zapewnia natychmiastowe wykorzystanie danych do momentu, gdy kolejne zaplanowane odświeżanie pobierze te dane ze źródła danych.    
  Aby uzyskać więcej informacji, zobacz [Pozyskiwanie danych w czasie rzeczywistym](real-time-data-ingestion.md).

- **Udoskonalenia przygotowywania danych**
  
  Dowiedz się więcej na temat danych pozyskanych w encji. Korzystając z podsumowania danych, można zapoznać się z charakterystyką jakościową danych, co może pomóc w podejmowaniu odpowiednich działań.    
  Aby uzyskać więcej informacji, patrz [Badanie danych encji](entities.md#exploring-a-specific-entitys-data).

- **Pozyskiwania danych analitycznych z Dynamics 365 z Common Data Service**
  
  Common Data Service jest dostępna jako metoda tworzenia źródeł danych. Istniejący klienci Dynamics 365 mogą pozyskiwać encje analityczne z  Common Data Service do Customer Insights. Jeden źródło danych może równocześnie korzystać z tego samego jeziora zarządzanego przez Common Data Service w środowisku Customer Insights.    
  Aby uzyskać więcej informacji, zobacz [Łączenie z danymi w repozytuorium data lake zarządzanym przez Common Data Service](connect-common-data-service-lake.md).

#### <a name="extensibility"></a>Możliwości rozszerzania

- **Eksportuj do LiveRamp**

  Aktywuj swoje dane w LiveRamp®, aby łączyć się z ponad 500 platformami obejmującymi ekosystemy cyfrowe, społecznościowe i telewizyjne. Wykorzystaj swoje dane w LiveRamp do kierowania, tłumienia i personalizowania kampanii reklamowych.    
  Aby uzyskać więcej informacji, zobacz [Łącznik LiveRamp&reg;](export-liveramp.md).

- **Dodatek Customer Insights Teams**
  
  Bot zawiera funkcje wyszukiwania ujednoliconych profilów klientów. Zostanie wyświetlona karta zawierająca maksymalnie 15 pól z wynikowego profilu klienta. Wiele pasujących elementów zwraca listę wyników, w których można wybrać profil.    
  Aby uzyskać więcej informacji, zobacz [Bot Teams dla Customer Insights](export-teams-bot.md).

#### <a name="measures"></a>Miary

- **Strona Lista miar**
  
  Poprawa na stronie miar obejmuje pomoc techniczną dotyczącą działań w ramach jednej miary oraz na wielu miarach jednocześnie. Ponadto znajdziesz pole wyszukiwania umożliwiające szybkie znajdowanie i śledzenie miar.    
  Aby uzyskać więcej informacji, zobacz [Tworzenie segmentów i zarządzanie nimi](segments.md).

- **Udoskonalenia w miarach złożonych**
  
  Użytkownicy mogą tworzyć, edytować i usuwać miary oparte na innych miarach. Na przykład miara skonstruowana na innej mierze, która została utworzona w trzeciej mierze.

#### <a name="segments"></a>Segmenty

- **Inny operator**
  
  Operator In-set zezwala na segmentację dla klientów według kilku możliwych wartości ciągów. Przed dodaniem tego operatora należało skonstruować takie segmenty z wieloma warunkami LUB. Operator In-set pozwala wykonać tę czynność przy jednym warunku.    
  Aby uzyskać więcej informacji, zobacz [Tworzenie segmentów i zarządzanie nimi](segments.md).

#### <a name="system-administration"></a>Administrator systemu

- **Kopiowanie ustawień konfiguracji do nowego środowiska**
  
  Skopiowanie konfiguracji z jednego środowiska do innego. Podczas tworzenia nowego środowiska można wybrać istniejące środowisko, z którego ma zostać skopiowana konfiguracja. Obecnie są obsługiwane źródła danych, ujednolicanie danych, relacje, miary i segmenty do skopiowania. Poświadczenia źródła danych i same dane nie są kopiowane.    
  Aby uzyskać więcej informacji, zobacz [Zarządzanie środowiskami](manage-environments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]