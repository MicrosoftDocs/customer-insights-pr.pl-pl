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
ms.openlocfilehash: 37696f3e82eb9b75fbf9f78363adc890891efcc3
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353970"
---
# <a name="semantic-mappings-preview"></a>Mapowania semantyczne (wersja zapoznawcza)

Mapowania semantyczne umożliwiają mapowanie danych, które nie są działaniami, na wstępnie zdefiniowane schematy. Te schematy ułatwiają funkcji szczegółowych informacji o odbiorcach lepsze zrozumienie atrybutów danych. Mapowanie semantyczne i dostarczone dane włączają nowe szczegółowe informacje i funkcje w obszarze szczegółowych informacji o odbiorcach. Aby mapować dane działań na schematy, należy zapoznać się z dokumentacją dotyczącą [działań](activities.md).

**Mapowania semantyczne są obecnie włączone w środowiskach opartych na kontach biznesowych**. *ContactProfile* jest jedynym typem mapowania semantycznego, który jest obecnie dostępny w funkcji szczegółowych informacji o odbiorcach.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definiowanie mapowania semantycznego encji ContactProfile

1. W funkcji szczegółowych informacji o odbiorcach przejdź do opcji **Dane** > **Mapowania semantyczne (wersja zapoznawcza)**.

1. Wybierz opcję **Dodaj mapowanie semantyczne**, aby uruchomić środowisko nadzorowane.

1. W kroku **Dane encji** ustaw wartości następujących pól:

   - **Nazwa mapowania semantycznego encji**: podaj nazwę mapowania semantycznego encji.
   - **Encja źródłowa**: wybierz encję zawierającą dane kontaktów.
   - **Klucz podstawowy**: wybierz pole, które jednoznacznie identyfikuje rekord kontaktu. Nie może ono zawierać żadnych powielonych wartości, pustych wartości ani brakujących wartości.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Konfigurowanie mapowania semantycznego encji z nazwą, encją źródłową i kluczem podstawowym.":::

1. Wybierz **Dalej**, aby kontynuować.

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
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Wizualizacje różnych relacji łączą encje kontaktów z encjami klientów.":::

1. Wybierz opcję **Dalej** po zakończeniu konfiguracji relacji.

1. W kroku **Ustaw typ semantyczny** wybierz opcję **Typ semantyczny**. Obecnie jest dostępny jeden **typ semantyczny** o nazwie *ContactProfile*.

1. Mapuj swoje dane na *ContactProfile* (**typ semantyczny**) dla pokazanych pól.
   - Pole wymagane: identyfikator kontaktu
   - Pola opcjonalne: imię, nazwisko, data urodzenia, płeć, podstawowy adres e-mail i podstawowy numer telefonu

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Mapowanie atrybutów danych kontaktów na podane pola wymagane i opcjonalne.":::

1. Wybierz **Dalej**, aby kontynuować.

1. W kroku **Przegląd** zapoznaj się z konfiguracją mapowania semantycznego. Wybierz opcję **Edytuj** dla odpowiadającej sekcji, aby wprowadzić zmiany.

1. Wybierz opcję **Zapisz**, aby zapisać nowe **mapowanie semantyczne**.

1. Po zapisaniu można wybrać polecenie **Uruchom** proces mapowania pochyłego lub wybrać opcję **Zamknij**, aby zapisać mapowanie semantyczne bez przetwarzania.

1. Aby uruchomić mapowanie semantyczne, wybierz mapowanie semantyczne i wybierz opcję **Odśwież**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Zarządzanie istniejącymi mapowaniami semantycznymi

W obszarze **Dane** > **Mapowania semantyczne (wersja zapoznawcza)** można wyświetlić wszystkie zapisane mapowania semantyczne i zarządzać nimi. Każde mapowanie semantyczne jest reprezentowane przez osobny wiersz. Znajdują się w nim szczegółowe informacje o encji źródłowej, typie semantycznym, typie mapowania i jego stanie.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Opcje zarządzania mapowaniami semantycznymi.":::

- **Edytuj**: otwiera konfigurację mapowania semantycznego z kroku przeglądu. Można zmienić bieżącą konfigurację. Wybierz opcję **Zapisz** i **Uruchom**, aby przetworzyć zmiany.

- **Odśwież**: odświeża wybrane mapowanie semantyczne przy użyciu najbardziej aktualnych danych z encji, które są częścią konfiguracji. Odświeżanie każdego danego mapowania semantycznego spowoduje odświeżenie wszystkich mapowań semantycznych tego samego typu.

- **Zmień nazwę**: otwiera sesję dialogową, w której można wprowadzić inną nazwę wybranego mapowania semantycznego. Wybierz pozycję **Zapisz**, aby zastosować zmiany.

- **Usuń**: otwiera sesję dialogową, aby potwierdzić usunięcie wybranego mapowania. Wybierając mapowania semantyczne i ikonę usuwania, można także usunąć kilka mapowań semantycznych jednocześnie. Aby potwierdzić usunięcie, wybierz opcję **Usuń**.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Użyj semantycznego mapowania encji ContactProfile do tworzenia aktywności na poziomie kontaktu

Po utworzeniu semantycznego mapowania encji *ContactProfile* możesz przechwytywać aktywności kontaktów. Dzięki temu możesz zobaczyć na osi czasu aktywności na koncie, który kontakt był odpowiedzialny za poszczególne aktywności. Większość kroków jest zgodna z typową konfiguracją mapowania aktywności.

   > [!NOTE]
   > Aby aktywność na poziomie kontaktu działała, musisz posiadać oba atrybuty **AccountID** i **ContactID** dla każdego rekordu w danych aktywności.

1. [Definiowanie mapowania semantycznego encji *ContactProfile*.](#define-a-contactprofile-semantic-entity-mapping) i uruchomić mapowanie semantyczne.

1. W analizach odbiorców przejdź do **Dane** > **Działania**.

1. Aby utworzyć nowe działanie, wybierz pozycję **Dodaj działanie**.

1. Nazwij aktywność, wybierz źródłową encję aktywności i wybierz klucz główny encji aktywności.

1. W kroku **Relacje** utwórz pośrednią relację między danymi źródłowymi aktywności a kontami, używając danych kontaktowych jako jednostki pośredniczącej. Aby uzyskać więcej informacji, przejdź do [ścieżek relacji bezpośredniej i pośredni](relationships.md#relationship-paths).
   - Przykładowa relacja dla działania o nazwie *Zakupy*:
      - **Dane aktywności Źródła Zakupów** > **Dane kontaktowe** na atrybucie **ContactID**
      - **Dane kontaktu** > **Dane konta** na atrybucie **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Przykładowa konfiguracja relacji.":::

1. Po ustawieniu relacji wybierz **Dalej** i zakończ konfigurację mapowania aktywności. Szczegółowe kroki dotyczące tworzenia aktywności znajdziesz w dziale [definiowanie aktywności](activities.md).

1. Uruchom swoje mapowania aktywności.

1. Twoje działania na poziomie kontaktu będą teraz widoczne na Twojej osi czasu klienta.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Wynik końcowy po skonfigurowaniu działań kontaktowych":::

### <a name="contact-level-activity-timeline-filtering"></a>Filtrowanie osi czasu aktywności na poziomie kontaktu

Po skonfigurowaniu mapowania aktywności na poziomie kontaktu i uruchomieniu go, oś czasu aktywności dla twoich klientów zostanie zaktualizowana. Zawiera ich identyfikatory lub imiona, w zależności od konfiguracji twojego *ContactProfile*, dla działań, które podjęli. Możesz filtrować aktywności według kontaktów na osi czasu, aby zobaczyć konkretne kontakty, które Cię interesują. Dodatkowo możesz zobaczyć wszystkie aktywności, które nie są przypisane do konkretnego kontaktu, wybierając **Aktywności nieprzypisane do kontaktu**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Opcje filtrowania dostępne dla aktywności na poziomie kontaktu.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]
