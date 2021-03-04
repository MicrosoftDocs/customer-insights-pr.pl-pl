---
title: Mapowanie encji do ujednolicenia danych
description: Mapowanie danych w celu utworzenia ujednoliconych profili klientów.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 0088daae0be0cb3e71f87387648430d2353081c9
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267048"
---
# <a name="map-entities-and-attributes"></a>Mapowanie encji i atrybutów

**Mapowanie** jest pierwszym etapem procesu ujednolicenia danych w analizach odbiorców. Mapowanie składa się z trzech faz:

- *Wybór encji*: należy zidentyfikować encje, które prowadzą do zestawu danych z pełniejszymi informacjami o klientach.
- *Wybór atrybutu*: dla każdej encji należy określić kolumny, które mają zostać połączone i uzgodnić w fazach *dopasowywania* i *scalania*. Te kolumny są nazywane *Atrybutami*.
- *Wybór klucza podstawowego i typu semantycznego*: Dla każdej encji zidentyfikuj atrybut, który chcesz zdefiniować jako klucz podstawowy dla tej encji, a dla każdego atrybutu zidentyfikuj typ semantyczny, który najlepiej opisuje ten atrybut.

Aby uzyskać więcej informacji na temat ogólnego przebiegu zjednoczenia danych, zobacz [Ujednolicanie](data-unification.md).

## <a name="select-the-first-entities"></a>Zaznacz pierwsze encje

1. W analizach odbiorców przejdź do **Dane** > **Ujednolicanie** > **Mapowanie**.

2. Rozpocznij fazę mapowania, zaznaczając **Wybierz encje**.

3. W fazach *dopasuj* i *scal* wybierz encje i atrybuty, które mają być używane. Wymagane atrybuty można wybrać z encji oddzielnie lub dodać wszystkie atrybuty z encji, zaznaczając pole wyboru **Dołącz wszystkie pola** na poziomie encji. Zalecamy wybranie co najmniej dwóch encji, które mają być korzystne w procesie zjednoczenia danych.

   > [!div class="mx-imgBorder"]
   > ![Dodaj encje przykład](media/data-manager-configure-map-add-entities-example.png "Dodaj encje przykład")

   W tym przykładzie dodajemy encje **eCommerceContacts** i **loyCustomers**. Wybierając te encje, można uzyskać wgląd w informacje o tym, których użytkownicy biznesowi w trybie online są członkami programu lojalnościowego.
   
   Korzystając z słów kluczowych można przeszukiwać atrybuty i encje, aby wybrać wymagane, które mają zostać zamapowane.
   
     > [!div class="mx-imgBorder"]
   > ![Przykład przeszukiwanych pól](media/data-manager-configure-map-search-fields-example.png "Przykład przeszukiwanych pól")

4. Wybierz **Zastosuj**, aby potwierdzić wybrane opcje.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Wybierz klucz podstawowy i typ semantyczny dla atrybutów

Po wybraniu encji strona **Mapa** wymienia wybrane encje do przejrzenia. Zdefiniuj klucz podstawowy encji i zidentyfikuj typ semantyczny atrybutu w encji.

- **Klucz podstawowy**: Wybierz jeden atrybut jako klucz podstawowy dla każdej encji. Aby atrybut był prawidłowym kluczem podstawowym, nie może zawierać zduplikowanych wartości, brakujących wartości ani wartości null. Atrybuty typu danych ciąg, liczba całkowita i GUID są obsługiwane jako klucze podstawowe i będą wyświetlane w polu, w którym będzie można dokonać wyboru.

- **Typ semantyczny atrybutu**: Kategorie atrybutów, takie jak adres e-mail lub nazwa. Aby używać modeli AI do inteligentnego przewidywania semantyki, zaoszczędzić czas i poprawić dokładność, ustaw **Inteligentne mapowanie** na **Włączone**. Inteligentne mapowanie podświetla rekomendacje semantyki w oparciu o AI w polu **Typ**. Po ustawieniu na **Wyłączone**, zobaczysz nasze zwykłe rekomendacje dotyczące mapowania. Dowolny typ semantyczny można wybrać z listy dostępnych opcji i zastąpić sugerowany wybór.

> [!div class="mx-imgBorder"]
> ![Typ atrybutu i przewidywanie semantyczne](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Typ atrybutu i przewidywanie semantyczne")

Możliwe jest również dodanie niestandardowego typu semantycznego. Zaznacz pole typu dla atrybutu i wpisz nazwę niestandardowego typu semantycznego. Użytkownik może w ten sposób również zmieniać typy atrybutów, które były identyfikowane przez system.

Wszystkie atrybuty, w przypadku których typ semantyczny jest identyfikowany automatycznie, są zgrupowane w sekcji **Przegląd zamapowanych pól**. Przejrzyj te atrybuty i ich typy semantyczne, ponieważ zostaną użyte do połączenia encji w kroku scalania ujednolicania danych.

Atrybuty, które nie są automatycznie mapowane na typ semantyczny, są zgrupowane w sekcji **Definiuj dane w niezamapowanych polach**. Zaznacz pole typu semantycznego dla niezamapowanych atrybutów, lub wprowadź niestandardową nazwę typu atrybutu.

> [!div class="mx-imgBorder"]
> ![Klucz podstawowy i typ atrybutu](media/data-manager-configure-map-add-attributes.png "Klucz podstawowy i typ atrybutu")

> [!NOTE]
> Jedno pole powinno być zamapowane na typ semantyczny Person.FullName, aby wypełnić nazwę klienta na karcie klienta. W przeciwnym razie karty klientów nie będą posiadały nazw. 

## <a name="add-and-remove-attributes-and-entities"></a>Dodawanie i usuwanie atrybutów i encji

1. Na **Ujednolicanie** > **Mapa** wybierz **Edytuj pola**.

2. W okienku **Edytuj pola** dodaj lub usuń atrybuty i encje. Aby znaleźć i wybrać swoje atrybuty i encje, należy użyć narzędzia Wyszukaj lub przewinąć. Nie można usunąć atrybutu lub encji, jeśli zostały już dopasowane.

   > [!div class="mx-imgBorder"]
   > ![Dodawanie lub usuwanie atrybutów](media/configure-data-map-edit.png "Dodawanie lub usuwanie atrybutów")

3. Wybierz **Zastosuj**.

## <a name="add-images-to-profiles"></a>Dodawanie obrazów do profilów

Jeśli encja zawiera adresy URL publicznie dostępnych obrazów profilów lub logo, można dodać je do profilu ujednoliconego klienta.

Wybierz encję i znajdź pole zawierające adres URL do obrazu profilu. W polu wejściowym **Wpisz** ręcznie wprowadź poniższą wartość: 
- Dla osoby: Person.ProfileImage
- Dla organizacji: Organization.LogoImage

Wykonaj kroki procedury ujednolicania i upewnij się, że atrybut zawierający adres URL obrazu jest dodany również w kroku [Scal](merge-entities.md).

## <a name="set-attributes-for-organizations"></a>Ustawianie atrybutów dla organizacji

Dla organizacji (wersja zapoznawcza) typ atrybutu powinien zostać zamapowany na „Organization.Name”
> [!div class="mx-imgBorder"]
> ![Klucz podstawowy i typ atrybutu B2B](media/configure-data-map-edit-b2b.png "Klucz podstawowy i typ atrybutu B2B")

## <a name="next-step"></a>Następny krok

W ramach procesu ujednolicenia danych przejdź na stronę **Dopasowywanie**. Więcej informacji na temat tej fazy można przeczytać na stronie [**Dopasowywanie**](match-entities.md).

> [!TIP]
> Zapoznaj się z następującym filmem: [Wprowadzenie: Tworzenie ujednoliconego profilu klienta](https://youtu.be/oBfGEhucAxs).


[!INCLUDE[footer-include](../includes/footer-banner.md)]