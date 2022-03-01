---
title: Wyświetlaj profile klientów
description: Umożliwia uzyskanie połączonego widoku ujednoliconych danych klienta.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 433e6ceda0ec7827bd672cff40f895d7719561df
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896340"
---
# <a name="customer-profiles"></a>Profile klientów

Na stronie **Klienci** jest wyświetlany połączony widok klientów na podstawie danych z profilu zgromadzonych na podstawie [wszystkich źródeł danych](data-sources.md). Profile klientów są dostępne po [utworzeniu ujednoliconej encji klienta](data-unification.md). Należy się upewnić, że użytkownik zakończy proces ujednolicania danych w celu uzyskania bogatszych widoków klientów. Strona umożliwia również wyszukiwanie klientów.

Klienci mogą być osobami lub organizacjami (wersja zapoznawcza). Każdy profil klienta lub organizacji jest reprezentowany przez kafelek. Wybierz kafelek, aby wyświetlić dodatkowe informacje o danym kliencie lub organizacji. Aby wyświetlić dodatkowe rekordy, należy użyć formantów podziału na strony u dołu strony.

> [!div class="mx-imgBorder"] 
> ![Profile klientów B2C](media/profiles-customers.png "Profile klientów B2C")

Organizacje (Wersja zapoznawcza)
> [!div class="mx-imgBorder"] 
> ![Profile klientów B2B](media/profile-customers-b2b.png "Profile klientów B2B")

> [!NOTE]
> Jeśli nie widzisz kafelków po wybraniu **Klienci** w nawigacji, Administrator musi [zdefiniować co najmniej jeden atrybut z możliwością wyszukiwania](search-filter-index.md) w **Wyszukiwanie i indeks filtrów**.

## <a name="search-for-customers"></a>Wyszukaj klientów

Wyszukaj klientów, wprowadzając nazwę lub inny atrybut w polu wyszukiwania. Wyszukiwanie działa tylko w encji profilu klienta utworzonej podczas procesu zjednoczenia danych.

Administrator może skonfigurować atrybuty, które można przeszukiwać, korzystając ze strony **Wyszukiwanie i indeks filtrów**. Aby uzyskać więcej informacji, zobacz [zarządzanie wyszukiwaniem i indeksem filtrów](search-filter-index.md).

## <a name="filter-customers"></a>Filtrowanie klientów

Klientów można przyfiltrować według pól encji profilu klienta. Podobnie jak w przypadku funkcji wyszukiwania administrator będzie musiał zdefiniować pola jako filtrowane przy użyciu strony **Wyszukiwanie i indeks filtrów**.

1. Wybierz **Filtruj** na stronie **Klienci**.

2. Zaznacz pola wyboru obok atrybutów, według których chcesz filtrować klientów.

   > [!div class="mx-imgBorder"] 
   > ![Profile klientów](media/profiles-customers3.png "Profile klientów")

3. Aby usunąć filtry, wybierz pozycję **Wyczyść filtry** na stronie **Klienci**.

##  <a name="customer-details-page"></a>Strona Szczegóły klienta

Wybierz dowolną tabliczkę z klientami, aby otworzyć **Stronę szczegółów klienta**. Ten widok zawiera zunifikowane informacje dotyczące wybranego klienta.

Szczegóły klienta zawierają:

-   **Kafelek profil klienta:** na tym kafelku są wyświetlane różne wartości z obiektu profilu ujdenoliconego klienta. Informacje te mogą obejmować adresy e-mail, nazwy, miasta itp. 

-   **Potencjalne zainteresowania, potencjalne marki:** Pokazuje, czy skonfigurowano wzbogacenie własne. Reprezentuje potencjalne zainteresowania i podobieństwa do marek, które może mieć klient o profilu podobnym do tego klienta. Aby uzyskać więcej informacji, zobacz [Wzbogacanie profilów klientów o koligacje marki i zainteresowania](enrichment-microsoft.md).

-   **Miary:** Pokazuje, czy skonfigurowano jedną lub więcej miar określonego typu: miary atrybutów klienta. Obejmują one obliczone KPI wokół Twoich klientów na poziomie klienta indywidualnego. Aby uzyskać więcej informacji, zobacz [Definiuj miary i zarządzaj nimi](measures.md).

-   **Oś czasu działania:** pokazuje, czy są skonfigurowane działania. Widok osi czasu zawiera chronologicznie posortowane działania tego klienta, zaczynając od ostatniej aktywności. Aby uzyskać więcej informacji, zobacz [Działania klientów](activities.md).

Wybierz **Powrót do klienta**, aby powrócić do strony wyszukiwania klienta.

## <a name="next-steps"></a>Następne kroki

[Dodawanie większej liczby źródeł danych](data-sources.md) lub [tworzenie segmentów klientów](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]