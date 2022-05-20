---
title: Wybierz pola źródłowe do ujednolicenia danych
description: Pierwszym krokiem w procesie ujednolicenia jest wybranie encji, atrybutów, kluczy głównych i typów semantycznych, aby zmapować dane do ujednoliconego profilu klienta.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: a962f1353b6e25b40c60b39a81ac936873f34d92
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741008"
---
# <a name="select-source-fields-for-data-unification"></a>Wybierz pola źródłowe do ujednolicenia danych

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Pierwszym krokiem w ujednolicenia jest wybranie encji i pól w twoich zbiorach danych, które chcesz ujednolicić. Wybierz encje, które zawierają szczegóły dotyczące klientów, takie jak imię, adres, numer telefonu i e-mail. Możesz wybrać jedną lub więcej encji.

## <a name="select-entities-and-fields"></a>Wybierz encje i pola

1. Przejdź do sekcji **Dane** > **Ujednolicanie**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Zrzut ekranu strony docelowej ujednolicania dla doświadczenia pierwszego uruchomienia z wyróżnieniem Zacznij..":::

1. Wybierz **Rozpocznij**.

1. Na stronie **Pola źródłowe** wybierz **Wybierz encje i pola**. Zostanie wyświetlony panel **Wybierz encje i pola**.

1. Wybierz co najmniej jedną encję.

1. Dla każdej wybranej encji określ pola, których chcesz użyć do dopasowania rekordów klientów oraz pola, które mają być zawarte w profilu ujednoliconym. Te pola są nazywane *atrybutami*. Możesz wybrać wymagane atrybuty pojedynczo z encji lub uwzględnić wszystkie atrybuty z encji, zaznaczając pole wyboru na poziomie encji. Korzystając z słów kluczowych można przeszukiwać atrybuty i encje, aby wybrać wymagane, które mają zostać zamapowane.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Zrzut ekranu z zaznaczonymi encjami i atrybutami.":::

   W tym przykładzie dodajemy encje **Kontakty** i **KlienciLojalność**. Wybierając te encje, można uzyskać wgląd w informacje o tym, których użytkownicy biznesowi w trybie online są członkami programu lojalnościowego.

1. Wybierz **Zastosuj**, aby potwierdzić wybrane opcje. Zostaną wyświetlone wybrane encje i atrybuty.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Wybierz klucz podstawowy i typ semantyczny dla atrybutów

   :::image type="content" source="media/m3_select_primary.png" alt-text="Zrzut ekranu z zaznaczonymi encjami z nie zaznaczonym kluczem głównym." lightbox="media/m3_select_primary.png":::

Dla każdej encji wykonaj następujące kroki.

1. Wybierz **Klucz podstawowy**. Klucz podstawowy jest atrybutem unikalnym dla danej encji. Aby atrybut był prawidłowym kluczem podstawowym, nie może zawierać zduplikowanych wartości, brakujących wartości ani wartości null. Atrybuty typu ciąg, liczba całkowita i GUID są obsługiwane jako klucze podstawowe.

1. Aby używać modeli AI do inteligentnego przewidywania semantyki, oszczędzać czas i poprawiać dokładność, upewnij się, że **Inteligentne mapowanie** jest włączone. Inteligentne mapowanie podświetla rekomendacje semantyki w oparciu o AI w polu **Typ**. Możesz zastąpić sugerowany wybór, wybierając dowolny typ semantyczny z dostępnej listy opcji.

1. Dla każdego atrybutu wybierz semantyczny **Typ**, który najlepiej opisuje ten atrybut, np. imię, miasto czy adres e-mail.

   > [!NOTE]
   > Jedno pole powinno mapować się na typ semantyczny *Person.FullName*, aby wypełnić nazwę klienta w karcie klienta. W przeciwnym razie karty klientów nie będą posiadały nazw.

   1. Aby zmienić typ atrybutu zidentyfikowany przez system, wybierz inny typ. Jeśli ten typ nie istnieje, utwórz własny typ semantyczny, wybierając pole **Typ** atrybutu i wpisując nazwę własnego typu semantycznego.

   1. Aby dodać atrybut zawierający adres URL do publicznie dostępnych zdjęć profilowych lub logo, wybierz encję i pole, które zawiera adres URL. W polu **Typ** wprowadź następujące:
      - Dla osoby: Person.ProfileImage
      - Dla organizacji: Organization.LogoImage

   1. Dla atrybutu nazwy konta wpisz "Organization.Name" w polu **Typ**.

1. Przejrzyj atrybuty, w których typ semantyczny jest identyfikowany automatycznie. Atrybuty te są wymienione w **Przegląd zmapowanych pól**. Tylko atrybuty tego samego typu mogą być łączone w kroku **Ujednolicone pola klienta**. Typy semantyczne są wykorzystywane do automatycznego sugerowania spostrzeżeń. Upewnij się, że wybrane przez ciebie typy są spójne dla wszystkich wybranych jednostek.

1. W przypadku atrybutów, które nie są automatycznie mapowane do typu semantycznego, wybierz pole typu semantycznego, wpisz własną nazwę typu atrybutu lub pozostaw je niezmapowane. Atrybuty te są wymienione w punkcie **Definiowanie danych w polach niemapowanych**.

1. Po wykonaniu kroków dla każdej jednostki wybierz **Zapisz pola źródłowe**.

1. Wybierz **Dalej**.

> [!div class="nextstepaction"]
> [Następny krok: Usuń duplikaty](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
