---
title: Personalizowanie interfejsu przy użyciu danych o znanych i nieznanych użytkownikach
description: Wykorzystaj informacje o wcześniej nieznanych użytkownikach, gdy poznasz ich tożsamość.
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 8e3477750d82f965dc2d62174fb35554d9447b7b
ms.sourcegitcommit: 52eca81c36e93d553140f5a37cf6013aaa42623a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2022
ms.locfileid: "9224308"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>Personalizowanie interfejsu przy użyciu danych o znanych i nieznanych użytkownikach

Zarządzanie danymi klientów nie jest nowym wyzwaniem, ale staje się coraz trudniejsze w miarę jak użytkownicy poruszają się po różnych kanałach cyfrowych oferowanych przez marki. Użytkownik, który jest znany (uwierzytelniony) w jednym kanale, staje się nieznany (nieuwierzytelniony) w innym, jeśli nie jest zalogowany. Problemem często jest to, że nieuwierzytelnieni (nieznani) użytkownicy nie mają wspólnego identyfikatora. Można go wykorzystać do kojarzenia znaczących atrybutów profili i generowania ujednoliconych profili klientów. Customer Insights pomaga rozwiązać ten problem, pobierając dane z metod śledzenia w Twoich systemach źródłowych. Skonsolidowanie znanych i znanych profilów umożliwia organizacjom pełny obraz aktualnych profilów oraz ich transakcji historycznych, zachowań i danych demograficznych. Idzie nawet o krok dalej, zapewniając rozdzielczość tożsamości, która pozwala ujednolicić aktywność klienta w wielu kanałach, w tym na stronie internetowej, w sklepie, w programach lojalnościowych itp.

## <a name="sample-scenario"></a>Przykładowy scenariusz

Pomyślmy o sieci kawiarni, która posiada szeroką bazę klientów, która kupuje kawę i żywność w sklepach oraz zamawia produkty online. Często odwiedzający online nie są uwierzytelniani podczas przeglądania produktów, co czyni ich „nieznanymi użytkownikami”. Łańcuchowi kawy trudno jest dostarczać spersonalizowane oferty i doświadczenia, jeśli użytkownicy są nieznani. Z drugiej strony klienci mogą zalogować się na swoje konto i stać się „znanymi użytkownikami” firmy, dołączając do systemu lojalnościowego, co z kolei pozwala na bardziej spersonalizowane doświadczenia. Customer Insights może pomóc sieci kawiarni uzyskać wgląd w znanych i wcześniej nieznanych użytkowników.

Dzięki usłudze Customer Insights firma może łączyć profile klientów z danymi o aktywności z nieuwierzytelnionych (nieznanych) sesji po zalogowaniu się użytkownika i jego poznaniu. Sieć kawiarni może przenosić dane z innych źródeł danych za pomocą wbudowanych łączników do Customer Insights, aby scalać tożsamości klientów z różnych kanałów.

## <a name="prerequisites"></a>Wymagania wstępne

- Dane internetowe są gromadzone i zawierają „identyfikatory odwiedzających” dla wszystkich odwiedzających.
- Dane internetowe zawierają „uwierzytelnione identyfikatory użytkowników” dla zalogowanych odwiedzających. Identyfikatory te są łączone z systemem lojalnościowym.
- Dane o zdarzeniach o wysokiej wartości, takie jak „Widok produktu” i „Kasa”, są definiowane i uwzględniane w danych źródłowych wraz z sygnaturą czasową zdarzenia i identyfikatorem zdarzenia.

W poniższej tabeli przedstawiono uproszczony przykład przechwytywania zdarzeń internetowych o wysokiej wartości.

|EventID|EventTimeStamp|UserID|LoyaltyID|EventName|
|--|--|--|--|--|
|1|23-07-2022 10:00:00|abc123|--|Widok produktu|
|2|23-07-2022 10:05:00|abc123|707|Logowanie lojalnościowe|
|3|23-07-2022 10:10:00|abc123|707|Finalizuj|
|100|23-07-2022 10:20:00|xyz789|--|Widok produktu|

## <a name="data-ingestion"></a>Pozyskiwanie danych

Dane o klientach mogą pochodzić z Twojej witryny internetowej jako dane o wydarzeniach i mogą być przechowywane we własnych wewnętrznych lub zewnętrznych usługach analizy danych. Dane internetowe zawierają znanych i nieznanych użytkowników, jeśli witryna ma przepływ uwierzytelniania, który integruje się z usługą uwierzytelniania. Na przykład system eCommerce, który wymaga od użytkowników podania pełnych danych, aby zakończyć transakcję zakupu. Lub system lojalnościowy, który wymaga uwierzytelnienia w celu potwierdzenia ważnego odbiorcy zniżek na nagrody.

Dane zdarzenia w powyższym przykładzie zawierają różne identyfikatory profili znanych i nieznanych użytkowników. W zdarzeniu 1 i 4 użytkownicy są nieznani, natomiast w zdarzeniu 2 i 3 użytkownik o identyfikatorze abc123 zapisuje się do programu lojalnościowego.

:::image type="content" source="media/website-data-source.png" alt-text="Źródła danych, w tym witryna sieci Web firmy Contoso.":::

Aby uzyskać więcej informacji o dostępnych opcjach pozyskiwania danych, zobacz [Przegląd źródeł danych](data-sources.md).

## <a name="data-unification"></a>Ujednolicenie danych

Zbieżność nieznanych tożsamości ze znanymi tożsamościami pomaga umożliwić personalizację na podstawie zachowań użytkowników, niezależnie od stanu ich profilu (znany lub nieznany). Spersonalizowana treść dla wszystkich użytkowników pomaga klientom szybko dotrzeć do najbardziej odpowiednich produktów lub usług, którymi są w danej chwili zainteresowani.

Ponieważ niektórzy użytkownicy naszych danych są znani, możemy wykorzystać Customer Insights, aby połączyć te dane z profilem użytkownika. Więcej informacji na temat ujednolicenia profili klientów, zobacz [Omówienie ujednolicania danych](data-unification.md).

1. Wybierz pola źródłowe z encji danych sieci Web. Użyj danych profilu przechowywanych w danych internetowych i wybierz pola reprezentujące identyfikatory z danymi demograficznymi.

   :::image type="content" source="media/website-source-fields.png" alt-text="Pola źródłowe dla internetowego źródła danych.":::

1. Dodaj reguły, aby scalić zduplikowane rekordy. W przypadku danych internetowych wybierz najbardziej wypełnione dane.

1. Skonfiguruj reguły i warunki dopasowania. Dane zdarzeń profili internetowych w tym przykładzie zostaną dopasowane w identyfikatorach do profili z innych źródeł danych zawierających informacje o klientach. Skonfiguruj reguły dokładnego dopasowania dla identyfikatorów jako osobne reguły z każdą inną encją profilu, która ma odpowiedni klucz podstawowy lub dopasowanie identyfikatora. W tym przykładzie dane profilu zdarzenia WWW są używane jako ostatnia pasująca jednostka, dzięki czemu inne dane profilu są łączone jako pierwsze.
   1. Brak zaznaczenia **Uwzględnij wszystkie rekordy** tworzy ujednolicone profile dla znanych użytkowników i uwzględnia odpowiadające im nieznane identyfikatory użytkowników. Jest to przydatne w scenariuszach, w których interesuje Cię przeglądanie przeszłych działań behawioralnych znanych użytkowników, gdy byli jeszcze nieznani.
   1. Zaznaczenie **Uwzględnij wszystkie rekordy** tworzy oddzielne rekordy profilu dla nieznanych użytkowników. Nieznani użytkownicy otrzymują unikalny identyfikator klienta. W przyszłości, gdy znany profil zostanie powiązany z danymi profilu zdarzeń internetowych, podróż nowo znanego użytkownika może być przeglądana i wykorzystywana do personalizacji na podstawie nieznanych wcześniej danych behawioralnych.

:::image type="content" source="media/website-match-rule.png" alt-text="Reguła dopasowania dla encji źródła danych witryny.":::

## <a name="get-insights"></a>Pobierz wyniki analiz

Jeśli tworzone są profile klientów dla nieznanych i znanych użytkowników, dane o wysokiej wartości zdarzeń internetowych mogą być wykorzystywane jako [działania](activities.md). Te działania mogą służyć do tworzenia większej wiedzy. Na przykład klienci, którzy odwiedzili witrynę sześć miesięcy temu (kiedy byli jeszcze nieznani) lub klienci, którzy nie mają identyfikatora lojalności, nigdy nie zrealizowali transakcji.

:::image type="content" source="media/website-known-unknown.png" alt-text="Zrzut ekranu strony klienta ze znanymi i nieznanymi klientami.":::

[Wzbogać](enrichment-hub.md) dane, utwórz [miary](measures.md) i utwórz [segmenty](segments.md) w celu dalszej aktywacji.

Na przykład możesz tworzyć segmenty znanych użytkowników, którzy oglądali niektóre produkty, ale nigdy nie dokończyli transakcji.

Aby uzyskać więcej informacji, zobacz [Omówienie segmentów](segments.md).

## <a name="activate-insights"></a>Aktywuj statystyki

Istnieje kilka sposobów na wyeksportowanie danych i podjęcie działań na podstawie podstawowych informacji.

Aby uzyskać więcej informacji, zobacz [Przegląd eksportu](export-destinations.md).
