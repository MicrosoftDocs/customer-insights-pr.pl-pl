---
title: Mapowania semantyczne (wersja zapoznawcza)
description: Omówienie mapowań semantycznych i sposobu ich używania.
ms.date: 09/28/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: b0884b8b6a2c5abe4b3967d1b57d11a3a6d65c5b
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/11/2021
ms.locfileid: "7622948"
---
# <a name="semantic-mappings"></a>Mapowania semantyczne

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

> [!TIP]
> Istnieje [sześć typów stanu](system.md#status-types) zadań/procesów. Ponadto większość procesów [zależy od innych procesów podrzędnych](system.md#refresh-policies). Istnieje możliwość wybrania stanu procesu w celu wyświetlenia szczegółowych informacji o postępie w całym zadaniu. Po wybraniu opcji **Zobacz szczegółowe informacje** dla jednego z zadań zadania, można znaleźć więcej informacji: czas przetwarzania, Data ostatniego przetwarzania oraz wszystkie błędy i ostrzeżenia skojarzone z zadaniem.

## <a name="manage-existing-semantic-mappings"></a>Zarządzanie istniejącymi mapowaniami semantycznymi

W obszarze **Dane** > **Mapowania semantyczne (wersja zapoznawcza)** można wyświetlić wszystkie zapisane mapowania semantyczne i zarządzać nimi. Każde mapowanie semantyczne jest reprezentowane przez osobny wiersz. Znajdują się w nim szczegółowe informacje o encji źródłowej, typie semantycznym, typie mapowania i jego stanie.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Opcje zarządzania mapowaniami semantycznymi.":::

- **Edytuj**: otwiera konfigurację mapowania semantycznego z kroku przeglądu. Można zmienić bieżącą konfigurację. Wybierz opcję **Zapisz** i **Uruchom**, aby przetworzyć zmiany.

- **Odśwież**: odświeża wybrane mapowanie semantyczne przy użyciu najbardziej aktualnych danych z encji, które są częścią konfiguracji. Odświeżanie każdego danego mapowania semantycznego spowoduje odświeżenie wszystkich mapowań semantycznych tego samego typu.

- **Zmień nazwę**: otwiera sesję dialogową, w której można wprowadzić inną nazwę wybranego mapowania semantycznego. Wybierz pozycję **Zapisz**, aby zastosować zmiany.

- **Usuń**: otwiera sesję dialogową, aby potwierdzić usunięcie wybranego mapowania. Wybierając mapowania semantyczne i ikonę usuwania, można także usunąć kilka mapowań semantycznych jednocześnie. Aby potwierdzić usunięcie, wybierz opcję **Usuń**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
