---
title: Mapowania semantyczne (wersja zapoznawcza)
description: Omówienie mapowań semantycznych i sposobu ich używania.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 8780c11c8b091717349f0fd75a36b99c3a63ab49
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303889"
---
# <a name="semantic-mappings-preview"></a>Mapowania semantyczne (wersja zapoznawcza)

> [!NOTE]
> Strona **Mapowania mapowania danych** jest dostępna tylko dla środowisk biznesowych (B-to-B), w których przy użyciu tej strony utworzono już profile kontaktów. Możesz nadal tworzyć profile poszczególnych kontaktów i zarządzać nimi, korzystając ze strony **Odwzorowania semantyczne**. Możesz też [ujednoliceć dane kontaktów w](data-unification-contacts.md) celu usunięcia duplikatów, zidentyfikować dopasowania w poszczególnych encji i utworzyć jeden ujednolicony profil kontaktu. Następnie możesz użyć ujednoliconego profilu kontaktu do tworzenia działań na poziomie kontaktu.

Mapowania semantyczne umożliwiają mapowanie danych, które nie są działaniami, na wstępnie zdefiniowane schematy. Te schematy ułatwiają funkcji Customer Insights lepsze zrozumienie atrybutów danych. Mapowanie semantyczne i dostarczone dane włączają nowe szczegółowe informacje i funkcje w obszarze Customer Insights. Aby mapować dane działań na schematy, należy zapoznać się z dokumentacją dotyczącą [działań](activities.md).

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

[!INCLUDE [footer-include](includes/footer-banner.md)]
