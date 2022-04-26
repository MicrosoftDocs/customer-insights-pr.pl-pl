---
title: Nowe i nadchodzące funkcje
description: Informacje o nowych funkcjach, ulepszeniach i poprawkach błędów.
ms.date: 04/05/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 2f081306271a170cf3e250fc1a193cedb70aeec6
ms.sourcegitcommit: 0363559a1af7ae16da2a96b09d6a4a8a53a8cbb8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547685"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Co nowego w możliwości wglądu odbiorców w Dynamics 365 Customer Insights

Z przyjemnością informujemy o najnowszych aktualizacjach! W tym artykule podsumowano publiczne wersje zapoznawcze, ulepszenia ogólnej dostępności oraz aktualizacje funkcji. Aby zobaczyć długofalowe plany dotyczące funkcji, zapoznaj się z [planami wydań rozwiązań Dynamics 365 i Power Platform](/dynamics365/release-plans/).

Wdrażamy aktualizacje kolejno regionami. Niektóre regiony mogą zobaczyć nowe funkcje wcześniej. O ile nie zaznaczono inaczej, nie trzeba podejmować żadnych działań, a w razie przestoju przeprowadzimy automatyczną aktualizację bez konieczności przestoju.

> [!TIP]
> Aby przesłać i głosować na żądania funkcji i sugestie dotyczące produktu, przejdź do [portalu Pomysły aplikacji Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


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

Aby uzyskać więcej informacji, zobacz [Włącz udostępnianie danych w Dataverse z własnego magazynu Azure Data Lake Storage (wersja zapoznawcza)](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

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
  
W okresie przejścia przechwytywane zdarzenia są nadal przesyłane strumieniowo do połączonych danych Data Lake. Po wyłączeniu tej funkcji udostępnianie danych między funkcjami zaangażowania odbiorcy i szczegółowych informacji o odbiorcy zostanie zatrzymane i do połączonego magazynu nie będą wysyłane żadne nowe zdarzenia.
W przypadku pytań na temat zakończenia wersji zapoznawczej możliwości należy skontaktować się bezpośrednio z zespołem obsługi konta Microsoft. Zespół zajmujący się kontem klienta będzie na bieżąco informować o nadchodzących wydaniach. 

## <a name="january-2022-updates"></a>Aktualizacje ze stycznia 2022

Aktualizacje w styczniu 2022 r. zawierają nowe funkcje, uaktualnienia wydajności i poprawki usterek.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Analiza opinii dla opinii klienta

Aplikacja Customer Insights udostępnia nową funkcję wykorzystującą technologią, która umożliwia syntetyzowanie opinii klientów i identyfikowanie określonych aspektów działalności jako szans sprzedaży na potrzeby ukierunkowanych ulepszeń. Analizując pisemne opinie klientów, można uzyskać dokładne szczegółowe informacje przy stosunkowo niewielkim koszcie. Analizy opinii obsługiwane przez modele przetwarzania języka naturalnego (NLP), które generują dwa typy pochodnych szczegółowych informacji dla każdego identyfikatora klienta. Wynik opinii (od –5 do 5) i lista odpowiednich aspektów biznesowych. 

Aby uzyskać więcej informacji, zobacz [Analizowanie opinii klienta (wersja zapoznawcza)](sentiment-analysis.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]