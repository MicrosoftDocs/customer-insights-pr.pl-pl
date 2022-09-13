---
title: Nowości w rozwiązaniu Dynamics 365 Customer Insights
description: Informacje o nowych funkcjach, ulepszeniach i poprawkach błędów.
ms.date: 08/31/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: acba06cba5fb5cbf0bca5aeb30b603003555fc32
ms.sourcegitcommit: 3ab8f1c0ba5874095a19f0b6367b9a4432f72ed1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/06/2022
ms.locfileid: "9409370"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Nowości w rozwiązaniu Dynamics 365 Customer Insights

Z przyjemnością informujemy o najnowszych aktualizacjach! W tym artykule podsumowano publiczne wersje zapoznawcze, ulepszenia ogólnej dostępności oraz aktualizacje funkcji. Aby zobaczyć długofalowe plany dotyczące funkcji, zapoznaj się z [planami wydań rozwiązań Dynamics 365 i Power Platform](/dynamics365/release-plans/).

Wdrażamy aktualizacje kolejno regionami. Niektóre regiony mogą zobaczyć nowe funkcje wcześniej. O ile nie zaznaczono inaczej, nie trzeba podejmować żadnych działań, a w razie przestoju przeprowadzimy automatyczną aktualizację bez konieczności przestoju.

> [!TIP]
> Aby przesłać i głosować na żądania funkcji i sugestie dotyczące produktu, przejdź do [portalu Pomysły aplikacji Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="august-2022-updates"></a>Aktualizacje z sierpnia 2022 r.

Aktualizacje w sierpniu 2022 r. zawierają nowe funkcje, uaktualnienia wydajności i poprawki usterek.

### <a name="contact-unification-in-b-to-b-environments"></a>Rozsyłanie kontaktów w środowiskach B-to-B

Środowiska B-to-B w Customer Insights obsługują obecnie ulepszane funkcje unification danych.

Możesz teraz ujednolicić kontakty oprócz kont, aby uzyskać pełny widok kontaktów biznesowych. Ujednolicone kontakty są powiązane z ujednoliconymi kontami i są teraz wymienione na kartach klientów. 

Aby uzyskać więcej informacji, zobacz [Utwórz ujednolicony profil kontaktu](data-unification-contacts.md).

### <a name="create-and-export-of-segments-based-on-unified-contacts"></a>Tworzenie i eksportowanie segmentów na podstawie ujednoliconych kontaktów

Dzięki nowej unifikacji kontaktów możesz tworzyć segmenty kontaktów, korzystając z kryteriów z kontaktów, kont lub obu. Te segmenty można wyeksportować w celu aktywowania w innych usługach.

Aby uzyskać więcej informacji, zobacz [Przegląd eksportu](export-destinations.md).

### <a name="deployment-regions-aligned-with-microsoft-dataverse"></a>Regiony wdrożenia dopasowane do usługi Microsoft Dataverse

Podczas tworzenia nowego środowiska Customer Insights można wybrać region, w którym usługa ma być wdrażana i hostowana. Zaktualizowaliśmy wybór regionu, aby pasował do usługi Microsoft Dataverse i platformy Power Platform.

Teraz można łatwo wybrać ten sam region co istniejące środowisko usługi Microsoft Dataverse lub konto usługi Azure Data Lake Storage (w przypadku wybrania tej opcji), w zależności od dostępności usługi Customer Insights w tym regionie.

Aby uzyskać więcej informacji, zobacz tematy [Tworzenie nowego środowiska](create-environment.md) i [Dostępność produktu według lokalizacji geograficznych](https://dynamics.microsoft.com/availability-reports/).

## <a name="july-2022-updates"></a>Aktualizacje z lipca 2022 r.

Aktualizacje w lipcu 2022 r. zawierają nowe funkcje, uaktualnienia wydajności i poprawki usterek.

### <a name="export-to-moengage"></a>Eksportuj do programu MoEngage

Eksportuj segmenty ujednoliconych profili klientów do MoEngage i używaj ich do marketingu e-mailowego w MoEngage.

Aby uzyskać więcej informacji, zobacz temat [Eksportowanie segmentów do usługi MoEngage](export-moengage.md).

### <a name="ssh-support-for-sftp-based-exports"></a>Obsługa protokołu SSH dla eksportów opartych na platformie SFTP

Wybierz, czy chcesz uwierzytelniać za pośrednictwem usługi SSH, czy nazwa użytkownika/hasło w przypadku połączeń z miejscami eksportu SFTP.

Aby uzyskać więcej informacji, zobacz temat [Eksportowanie danych do hostów SFTP](export-sftp.md).

### <a name="personalize-experiences-with-data-about-known-and-unknown-users"></a>Personalizowanie środowiska przy użyciu danych o znanych i nieznanych użytkownikach

Zarządzanie danymi klientów nie jest nowym wyzwaniem, ale staje się coraz trudniejsze w miarę jak użytkownicy poruszają się po różnych kanałach cyfrowych oferowanych przez marki. Użytkownik, który jest znany (uwierzytelniony) w jednym kanale, staje się nieznany (nieuwierzytelniony) w innym, jeśli nie jest zalogowany. Problemem często jest to, że nieuwierzytelnieni (nieznani) użytkownicy nie mają wspólnego identyfikatora. Można go wykorzystać do kojarzenia znaczących atrybutów profili i generowania ujednoliconych profili klientów. Customer Insights pomaga rozwiązać ten problem, pobierając dane z metod śledzenia w Twoich systemach źródłowych.

Aby uzyskać więcej informacji, zobacz temat [Personalizowanie środowiska przy użyciu danych o znanych i nieznanych użytkownikach](unknown-to-known.md).

## <a name="june-2022-updates"></a>Aktualizacje z czerwca 2022 r.

Aktualizacje w czerwcu 2022 r. zawierają nowe funkcje, uaktualnienia wydajności i poprawki usterek.

### <a name="updated-user-experience-for-data-sources-and-data-ingestion"></a>Zaktualizowane środowisko użytkownika dotyczące źródeł danych i pozyskiwania danych

Importowanie danych z szerokiego zakresu źródeł danych jest podstawą do zaimportowania danych klientów w programie Dynamics 365 Customer Insights. Zrewidowaliśmy środowisko użytkownika dotyczące importowania i łączenia źródeł danych. Ta aktualizacja ma ułatwić użytkownikom wgląd w dane programu Customer Insights.

Aby uzyskać więcej informacji, zobacz [Omówienie źródeł danych](data-sources.md).

### <a name="export-to-inmobi"></a>Eksportuj do programu InMobi

Program InMobi pomaga zrozumieć, zidentyfikować i pozyskiwać odbiorców. Segmenty i inne dane można eksportować do usługi InMobi za pośrednictwem kont Azure Blob Storage.

Aby uzyskać więcej informacji, zobacz [Eksportowanie do InMobi (wersja zapoznawcza)](export-inmobi.md)

### <a name="lockbox-support-in-customer-insights"></a>Obsługa skrzynki odbiorczej w aplikacji Customer Insights

Aplikacja Skrytka klienta udostępnia interfejs do przeglądania i zatwierdzania (lub odrzucania) żądań dostępu do danych. Te żądania występują, gdy dostęp do danych klienta jest potrzebny do rozwiązania sprawy pomocy technicznej.

Aby uzyskać więcej informacji, zobacz [Bezpieczne uzyskiwanie dostępu do danych klientów przy użyciu skrytki klienta (wersja zapoznawcza)](security-overview.md#securely-access-customer-data-with-customer-lockbox-preview).

### <a name="connect-to-your-data-using-azure-private-link"></a>Łączenie się z danymi przy użyciu łącza Azure Private Link

Usługa Azure Private Link umożliwia dostęp rozwiązania Customer Insights do konta Azure Data Lake Storage za punktem końcowym w sieci wirtualnej. W przypadku danych na koncie magazynu, które nie jest widoczne w publicznym Internecie, Provate Link umożliwia połączenie z dostępem do tej sieci zastrzeżonej.

Aby uzyskać więcej informacji, zobacz [Użyj linku prywatnego w Customer Insights](security-overview.md#set-up-an-azure-private-link).

## <a name="may-2022-updates"></a>Aktualizacje z maja 2022 r.

Aktualizacje w maju 2022 r. zawierają nowe funkcje, uaktualnienia wydajności i poprawki usterek.

### <a name="updated-data-unification-experience"></a>Zaktualizowane środowisko ujednolicania danych

 Ujednolicenie danych pozwala na połączenie niegdyś odrębnych źródeł danych w jeden główny zbiór danych, który zapewnia ujednolicony widok tych danych. Dane mogą być ujednolicone dla pojedynczej lub wielu encji. Najpierw należy [wybrać encje i pola źródłowe](map-entities.md), [usunąć zduplikowane rekordy](remove-duplicates.md), określić reguły [dopasowania warunków](match-entities.md) i zdefiniować [pola, które mają być uwzględnić w unified customer profile](merge-entities.md).

Aby uzyskać więcej informacji, zobacz [Omówienie ujednolicania danych](data-unification.md).

### <a name="refreshed-home-page-in-customer-insights"></a>Odświeżona strona główna w aplikacji Customer Insights

**Strona główna** prowadzi użytkownika przez proces konfiguracji kluczowych funkcji i zawiera przegląd segmentów, miar i danych wzbogacających. Odświeżyliśmy środowisko, aby dostarczyć bardziej odpowiednich informacji w skrócie.

Aby uzyskać więcej informacji, zobacz temat [Poznaj Customer Insights](home.md).

### <a name="track-usage-of-a-segment"></a>Śledzenie użycia segmentu

Możesz teraz [śledzić użycie segmentów](segments.md#track-usage-of-a-segment) w aplikacjach, które są oparte na tej samej organizacji Dataverse, która jest połączona z Customer Insights. W [przypadku segmentów usługi Customer Insights używanych w Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile) system informuje o poszczególnych segmentach.

### <a name="export-to-criteo"></a>Eksportowanie do usługi Criteo

Criteo platforma online, która pomaga użytkownikom w zarządzaniu reklamami cyfrowymi. Możesz teraz eksportować segmenty unified customer profile w celu generowania kampanii, dostarczania e-mail marketingu i korzystania z określonych grup klientów za pomocą Criteo.

Aby uzyskać więcej informacji, zobacz [Eksportowanie segmentów w Criteo (wersja zapoznawcza)](export-criteo.md).

### <a name="refined-documentation-structure-for-environment-creation"></a>Uściślona struktura dokumentacji dotyczącej tworzenia środowiska

Poprawiliśmy dokumenty pomocy dotyczące tworzenia środowisk i zarządzania nimi w aplikacji Customer Insights. Artykuły są teraz zgrupowane w węźle Środowiska w spisie treści. Te artykuły zawierają więcej wskazówek na różne sposoby tworzenia środowisk i mają bardziej czytelną strukturę. Jeśli masz opinię, którą chcesz się podzielić, daj nam znać za pośrednictwem formantów pod koniec artykułów pomocy.

Aby uzyskać więcej informacji, zobacz temat [Jak to zrobić: tworzenie nowego środowiska](create-environment.md).

## <a name="april-2022-updates"></a>Aktualizacja z kwietnia 2022 r.

Aktualizacje w kwietniu 2022 r. zawierają nowe funkcje, uaktualnienia wydajności i poprawki usterek.

### <a name="dun--bradstreet-enrichment-preview"></a>Utwórz wzbogacenie Dun&Bradstreet (wersja zapoznawcza)

Firma Dun & Bradstreet dostarcza dane komercyjne, analizy i szczegółowe informacje dla firm. Dzięki niej klienci z ujednoliconymi profilami klientów dla firm mogą wzbogacać swoje dane. Wzbogacenie zawiera atrybuty, takie jak numer DUNS, wielkość firmy, lokalizacja, branża i inne.

Aby uzyskać więcej informacji, zobacz [Wzbogacanie profili firm z Dun & Bradstreet (wersja zapoznawcza)](enrichment-dnb.md).

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>Określ typ miary podczas tworzenia nowej miary

Możesz teraz rozróżnić pomiędzy miarami dla poszczególnych profili a miarami dla całego biznesu. Podczas gdy miary biznesowe są widoczne na stronie głównej Customer Insights, miary dotyczące klientów są eksponowane na szczegółowych widokach klientów.

Aby uzyskać więcej informacji, zobacz temat [Korzystanie z konstruktora miar do tworzenia miar od podstaw](measure-builder.md).

### <a name="consolidation-of-customer-insights-documentation"></a>Konsolidacja dokumentacji Customer Insights

Przejrzeliśmy nasze artykuły w dokumentacji i usunęliśmy wzmianki o możliwościach wglądu w zaangażowanie i w widownię. W przyszłości, pisząc o podstawowych funkcjach aplikacji, będziemy konsekwentnie odwoływać się do nazwy produktu Customer Insights. Ta zmiana prowadzi także do znacznej przebudowy spisu treści, struktury adresów URL i ścieżek dostępu do plików w repozytorium dokumentacji. Wszystkie twoje zakładki i istniejące linki nadal działają i przekierowują na zaktualizowane adresy URL.

Jeśli chcesz dać nam znać, jak postrzegasz tę zmianę lub zauważyłeś, że coś nie działa tak, jak powinno, powiedz nam o tym, [przesyłając opinię dla tej strony](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**).

## <a name="march-2022-updates"></a>Aktualizacje z marca 2022 r.

Aktualizacje w marcu 2022 r. zawierają nowe funkcje, uaktualnienia wydajności i poprawki usterek.

### <a name="liveramp-abilitec-enrichment-preview"></a>Wzbogacenie LiveRamp AbiliTec (wersja zapoznawcza)

LiveRamp zapewnia rozwiązywanie problemów z tożsamością i konsolidację danych klientów. Możesz mapować osobiste identyfikatory w swoich danych klientów do grafu tożsamości AbiliTec i otrzymywać identyfikatory AbiliTec. Możesz wtedy wykorzystać te identyfikatory do lepszego ujednolicenia danych klientów.

Aby uzyskać więcej informacji, zobacz [Wzbogacanie profilów klientów przy użyciu danych tożsamości z LiveRamp (wersja zapoznawcza)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Organizuj segmenty i miary za pomocą znaczników i filtrów

Jeśli twoja organizacja utrzymuje wiele segmentów lub miar, znalezienie właściwego może czasem wydawać się trudne. Ta nowa funkcja pozwala na organizowanie list za pomocą etykiet i kolumn. Pomaga szybko i łatwo wyszukiwać dane oraz dostosowywać widoki.

Aby uzyskać więcej informacji, zobacz [Praca z etykietami i kolumnami](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Włącz udostępnianie danych z Dataverse, gdy korzystasz z własnego konta przechowywania danych

Jeśli Twoje środowisko używa własnej usługi Azure Data Lake Storage do przechowywania danych Customer Insights, udostępnianie danych za pomocą Microsoft Dataverse wymaga dodatkowej konfiguracji.
Wcześniej mogłeś włączyć udostępnianie danych w Dataverse tylko wtedy, gdy Twoje dane były przechowywane w naszym zarządzanym data lake.

Aby uzyskać więcej informacji, zobacz [Włącz udostępnianie danych w Dataverse z własnego magazynu Azure Data Lake Storage (wersja zapoznawcza)](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Nowe miejsca eksportu: Iterable i Braze

Wciąż poszerzamy nasz ekosystem kierunków eksportowych o nowe połączenia. Możesz teraz eksportować segmenty do Iterable i Braze, aby korzystać z ich usług aktywacyjnych.

Aby uzyskać więcej informacji, zobacz [Eksport segmentów do Iterable (wersja zapoznawcza)](export-iterable.md) i [Eksport segmentów do Braze (wersja zapoznawcza)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>Usprawnienia eksportu do Marketo i Google Ads

Zmieniające się interfejsy API w połączonych usługach wymagają aktualizacji, aby łączniki działały niezawodnie i bezproblemowo. Udostępniliśmy kilka aktualizacji dotyczących eksportu do usług Marketo i Google Ads:

- Google Ads: Nowa wersja łącznika eksportu Google Ads upraszcza proces uwierzytelniania i pozwala teraz na automatyczne tworzenie nowych odbiorców Google Ads. 
- Marketo: nowa wersja łącznika eksportu Marketo zapewnia obsługę identyfikatora Marketo ID, co pozwala uniknąć duplikatów danych, zaktualizować istniejące rekordy i utworzyć nowe rekordy w Marketo. 

## <a name="february-2022-updates"></a>Aktualizacje z lutego 2022 r.

Aktualizacje w lutym 2022 r. zawierają nowe funkcje, uaktualnienia wydajności i poprawki usterek.

### <a name="general-availability-for-prediction-models"></a>Ogólna dostępność dla modeli predykcyjnych

Niestandardowe modele predykcji, w tym **rezygnacja subskrypcji**, **rezygnacja transakcyjny** i **wartość życiowa klienta (CLV)** stają się ogólnie dostępne jako część Customer Insights. 

Aby uzyskać więcej informacji, zobacz [Przegląd przewidywań](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Nowe źródło danych: Integracja z Azure Synapse Analytics (wersja zapoznawcza)

Azure Synapse Analytics to usługa analizy dla przedsiębiorstw, która przyspiesza wgląd w szczegółowe dane w magazynach danych i w systemach danych big data.

Organizacje, które już korzystają z Azure Synapse Analytics, mogą wprowadzać te dane do Customer Insights. 

Więcej informacji: [Nawiązywanie połączeń ze źródłami danych Azure Synapse (wersja zapoznawcza)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>Wzbogacenie LiveRamp (wersja zapoznawcza)

LiveRamp zapewnia rozwiązywanie problemów z tożsamością i konsolidację danych klientów. Możesz mapować osobiste identyfikatory w swoich danych klientów do grafu tożsamości AbiliTec i otrzymywać identyfikatory AbiliTec. Możesz wtedy wykorzystać te identyfikatory do lepszego ujednolicenia danych klientów.

Aby uzyskać więcej informacji, zobacz [Wzbogacanie profilów klientów przy użyciu danych tożsamości z LiveRamp (wersja zapoznawcza)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Wzbogacanie źródeł danych (wersja zapoznawcza)

Wykorzystaj dane ze źródeł takich jak Microsoft i inni partnerzy, aby wzbogacić dane o klientach przed ich ujednoliceniem. Wzbogacenie źródeł danych pomaga w uzyskaniu większej kompletności i jakości danych, co może pomóc w osiągnięciu lepszych wyników po ujednoliceniu danych.

Aby uzyskać więcej informacji, zobacz [Wzbogacanie dla źródeł danych (wersja zapoznawcza)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Zmień właściciela środowiska

Podczas gdy kilku użytkowników może mieć uprawnienia administratora w Customer Insights, tylko jeden użytkownik jest właścicielem środowiska. Ulepszone doświadczenie pozwala na zmianę właściciela środowiska i przejęcie własności, jeśli poprzedni właściciel opuścił organizację. 

Aby uzyskać więcej informacji, zobacz [Zmiana właściciela środowiska](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Proces przygotowania danych wymienia przyczyny uszkodzenia uszkodzonych rekordów

Przygotowanie danych pokazuje teraz powód uszkodzenia dla wszystkich pól z uszkodzonymi danymi. Informacje są podawane na poziomie poszczególnych rekordów, co ułatwia ich identyfikację. 

Więcej informacji: [Uszkodzone źródła danych](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Koniec podglądu dla funkcji raportowania w Wynikach analiz interakcji

Wersja zapoznawcza możliwości szczegółowych informacji zaangażowania usługi Dynamics 365 Customer Insights zakończyła się 15 lutego 2022 r.  
Ta zmiana oznacza, że wersja próbna usługi Customer Insights nie obejmuje już możliwości tworzenia lejków ani innych funkcji raportowania.

Zapraszamy do zapoznania się z wieloma innymi funkcjami aplikacji [Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/), platformy danych klientów firmy Microsoft (CDP).    
 
W okresie przejścia istniejący uczestnicy wersji zapoznawczej nadal mają dostęp do pewnych funkcji i możliwości wersji zapoznawczej:

- Uzyskiwanie kodu do instrumentacji witryny internetowej lub aplikacji mobilnej 
- Wyświetlanie zdarzeń i właściwości zdarzeń 
- Ulepszanie ujednoliconych profili z pozyskanymi i uściślonymi zdarzeniami w celu odniesienia korzyści z pełnej wartości danych klienta
  
W okresie przejścia przechwytywane zdarzenia są nadal przesyłane strumieniowo do połączonych danych Data Lake. Po wyłączeniu tej funkcji udostępnianie danych zostanie zatrzymane i do połączonego magazynu nie będą wysyłane żadne nowe zdarzenia.
W przypadku pytań na temat zakończenia wersji zapoznawczej możliwości należy skontaktować się bezpośrednio z zespołem obsługi konta Microsoft. Zespół zajmujący się kontem klienta będzie na bieżąco informować o nadchodzących wydaniach. 

## <a name="january-2022-updates"></a>Aktualizacje ze stycznia 2022

Aktualizacje w styczniu 2022 r. zawierają nowe funkcje, uaktualnienia wydajności i poprawki usterek.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Analiza opinii dla opinii klienta

Aplikacja Customer Insights udostępnia nową funkcję wykorzystującą technologią, która umożliwia syntetyzowanie opinii klientów i identyfikowanie określonych aspektów działalności jako szans sprzedaży na potrzeby ukierunkowanych ulepszeń. Analizując pisemne opinie klientów, można uzyskać dokładne szczegółowe informacje przy stosunkowo niewielkim koszcie. Analizy opinii obsługiwane przez modele przetwarzania języka naturalnego (NLP), które generują dwa typy pochodnych szczegółowych informacji dla każdego identyfikatora klienta. Wynik opinii (od –5 do 5) i lista odpowiednich aspektów biznesowych. 

Aby uzyskać więcej informacji, zobacz [Analizowanie opinii klienta (wersja zapoznawcza)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]