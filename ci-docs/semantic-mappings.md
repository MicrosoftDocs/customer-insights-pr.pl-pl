---
title: Mapowania semantyczne (wersja zapoznawcza)
description: Omówienie mapowań semantycznych i sposobu ich używania.
ms.date: 12/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 7c9588ac7a132ca6f43cf26ea3a744109a0dd2b8
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183644"
---
# <a name="semantic-mappings-preview"></a>Mapowania semantyczne (wersja zapoznawcza)

Mapowania semantyczne umożliwiają mapowanie danych, które nie są działaniami, na wstępnie zdefiniowane schematy. Te schematy ułatwiają funkcji Customer Insights lepsze zrozumienie atrybutów danych. Mapowanie semantyczne i dostarczone dane włączają nowe szczegółowe informacje i funkcje w obszarze Customer Insights. Aby mapować dane działań na schematy, należy zapoznać się z dokumentacją dotyczącą [działań](activities.md).

**Mapowania semantyczne są obecnie włączone w środowiskach opartych na kontach biznesowych**. *ContactProfile* jest jedynym typem mapowania semantycznego, który jest obecnie dostępny w funkcji Customer Insights.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definiowanie mapowania semantycznego encji ContactProfile

1. Przejdź do **Dane** > **Mapowania semantyczne (wersja zapoznawcza)**.

1. Wybierz opcję **Dodaj mapowanie semantyczne**, aby uruchomić środowisko nadzorowane.

1. W kroku **Dane encji** ustaw wartości następujących pól:

   - **Nazwa mapowania semantycznego encji**: nazwa mapowania semantycznego encji.
   - **Encja źródłowa**: encja zawierającą dane kontaktów.
   - **Klucz podstawowy**: pole, które jednoznacznie identyfikuje rekord kontaktu. Nie może ono zawierać żadnych powielonych wartości, pustych wartości ani brakujących wartości.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Konfigurowanie mapowania semantycznego encji z nazwą, encją źródłową i kluczem podstawowym.":::

1. Wybierz **Dalej**.

1. W kroku **Relacje** skonfiguruj szczegóły, aby łączyć dane kontaktów z odpowiadającymi im danymi klienta. Ten krok obrazuje połączenie między encjami.  

   Istnieją dwa typy ścieżek relacji, które można wdrożyć: **Relacje bezpośrednie** i **Relacje pośrednie**. Aby uzyskać więcej informacji, przejdź do [ścieżek relacji bezpośredniej i pośredni](relationships.md#relationship-paths).

   1. Wybierz opcję **Dodaj relację**, aby skonfigurować relację.
   1. Wybierz atrybut z encji źródłowej, który łączy encję kontaktu z inną encją.
   1. Wybierz encję, z którą chcesz połączyć encję kontaktu. Encję można wybrać w sekcji **Encje klientów** lub **Encja pośrednia**. W przypadku wybrania encji pośredniej należy zdefiniować drugą relację w celu połączenia z docelową encją klienta.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Wybieranie opcji Encja klientów lub Encja pośrednia.":::

   1. Podaj **nazwę relacji**. Jeśli relacja między encjami już istnieje, nazwa relacji jest tylko do odczytu. Jeśli nie istnieje relacja, zostanie utworzona nowa relacja z podaną nazwą.
   1. Wybierz opcję **Zastosuj**, aby zakończyć konfigurację relacji.

   > [!NOTE]
   > Można skonfigurować więcej relacji między encją kontaktu a innymi encjami klienta za pomocą encji pośrednich.
   
     :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Wizualizacje różnych relacji łączą encje kontaktów z encjami klientów.":::

1. Wybierz **Dalej**.

1. W kroku **Ustaw typ semantyczny** wybierz opcję **Typ semantyczny**. Obecnie jest dostępny jeden **typ semantyczny** o nazwie *ContactProfile*.

1. Zamapuj swój identyfikator kontaktu na typ semantyczny *ContactProfile* **Contact ID**. Opcjonalnie zmapuj inne pola, takie jak imię, nazwisko, płeć lub adres e-mail.

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Mapowanie atrybutów danych kontaktów na podane pola wymagane i opcjonalne.":::

1. Wybierz **Dalej**.

1. W kroku **Przegląd** zapoznaj się z konfiguracją mapowania semantycznego. Aby wprowadzić zmiany, wybierz opcję **Edytuj** dla odpowiadającej sekcji.

1. Wybierz pozycję **Zapisz**.

1. Aby przetworzyć mapowanie semantyczne, wybierz **Uruchom**. Można też wybrać opcję **Zamknij**, by zapisać mapowanie semantyczne bez jego przetwarzania. Aby uruchomić go później, wybierz mapowanie semantyczne i wybierz **Odśwież**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Zarządzanie istniejącymi mapowaniami semantycznymi

Przejdź do **Dane** > **Mapowania semantyczne (wersja zapoznawcza)**, aby wyświetlić zapisane mapowania semantyczne, ich encję źródłową, typ semantyczny, typ mapowania i stan.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Opcje zarządzania mapowaniami semantycznymi.":::

Wybierz mapowanie semantyczne, aby wyświetlić dostępne akcje.
- **Edytuj** bieżącą konfigurację. Wybierz opcję **Zapisz** i **Uruchom**, aby przetworzyć zmiany.
- **Odśwież** mapowanie semantyczne, by uwzględnić najnowsze dane. Odświeżanie każdego danego mapowania semantycznego spowoduje odświeżenie wszystkich mapowań semantycznych tego samego typu.
- **Zmień nazwę** mapowania semantycznego. Wybierz pozycję **Zapisz**.
- **Usuń** mapowanie semantyczne. Aby usunąć więcej niż jedno mapowanie semantyczne naraz, wybierz mapowania semantyczne i ikonę usuwania. Aby potwierdzić usunięcie, wybierz opcję **Usuń**.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Użyj semantycznego mapowania encji ContactProfile do tworzenia aktywności na poziomie kontaktu

Po utworzeniu semantycznego mapowania encji *ContactProfile* możesz przechwytywać aktywności kontaktów. Dzięki temu możesz zobaczyć na osi czasu aktywności na koncie, który kontakt był odpowiedzialny za poszczególne aktywności. Większość kroków jest zgodna z typową konfiguracją mapowania aktywności.

   > [!NOTE]
   > Aby aktywność na poziomie kontaktu działała, musisz posiadać oba atrybuty **AccountID** i **ContactID** dla każdego rekordu w danych aktywności.

1. [Zdefiniuj mapowanie encji semantycznych *ContactProfile*](#define-a-contactprofile-semantic-entity-mapping) i uruchom mapowanie semantyczne.

1. Wybierz pozycję **Dane** > **Działania**.

1. Aby utworzyć nowe działanie, wybierz pozycję **Dodaj działanie**.

1. Nazwij aktywność, wybierz źródłową encję aktywności i wybierz klucz główny encji aktywności.

1. W kroku **Relacje** utwórz pośrednią relację między danymi źródłowymi aktywności a kontami, używając danych kontaktowych jako jednostki pośredniczącej. Aby uzyskać więcej informacji, przejdź do [ścieżek relacji bezpośredniej i pośredni](relationships.md#relationship-paths).
   - Przykładowa relacja dla działania o nazwie *Zakupy*:
      - **Dane aktywności Źródła Zakupów** > **Dane kontaktowe** na atrybucie **ContactID**
      - **Dane kontaktu** > **Dane konta** na atrybucie **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Przykładowa konfiguracja relacji.":::

1. Po ustawieniu relacji wybierz **Dalej** i zakończ konfigurację mapowania aktywności. Szczegółowe kroki dotyczące tworzenia aktywności znajdziesz w dziale [definiowanie aktywności](activities.md).

1. Uruchom swoje mapowania aktywności.

1. Po zakończeniu mapowania działań na poziomie kontaktu wybierz opcję **Klienci**. Działania na poziomie kontaktu są wyświetlane na osi czasu klienta.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Wynik końcowy po skonfigurowaniu działań kontaktowych":::

### <a name="contact-level-activity-timeline-filtering"></a>Filtrowanie osi czasu aktywności na poziomie kontaktu

Oś czasu działań dla Twoich klientów zawiera ich identyfikatory lub imiona i nazwiska, w zależności od konfiguracji twojego *ContactProfile*, dla działań, które podjęli. Filtruj działania według kontaktów na osi czasu, aby zobaczyć konkretne kontakty, które Cię interesują. Aby wyświetlić wszystkie aktywności, które nie są przypisane do konkretnego kontaktu, wybierz **Aktywności nieprzypisane do kontaktu**.

:::image type="content" source="media/Contact_Activities3.png" alt-text="Opcje filtrowania dostępne dla aktywności na poziomie kontaktu.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
