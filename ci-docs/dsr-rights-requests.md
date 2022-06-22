---
title: Żądania podmiotów danych osobowych (DSR) w kontekście rozporządzenia RODO | Microsoft Docs
description: Odpowiadanie na żądania podmiotów danych osobowych w Dynamics 365 Customer Insights.
ms.date: 05/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: c71305ab835b0f4f75adcce716e795959f898e47
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947381"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Żądania osób, których dotyczą dane, w kontekście rozporządzenia RODO

Ogólne rozporządzenie o ochronie danych (RODO) w Unii Europejskiej obowiązuje od 25 maja 2018 roku. Daje istotne prawa osobom w odniesieniu do ich danych. Zasadniczo przepisy GDPR dotyczą ochrony i zapewnienia prawa do prywatności osób fizycznych. Więcej informacji na temat zaangażowania firmy Microsoft w kwestie bezpieczeństwa i zgodności można znaleźć na stronie [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Dokładamy wszelkich starań, aby pomóc klientom w spełnianiu ich wymagań dotyczących rozporządzenia RODO. Obejmuje prawo usuwania i eksportowania danych, które zawierają dane osobowe, takie jak identyfikatory użytkowników, numery telefonów i adresy e-mail. Administratorzy mogą implementować żądania użytkowników w celu usuwania lub eksportowania danych osobowych.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Odpowiadanie na żądania podmiotów o usunięcie danych osobowych zgodnie z RODO w Dynamics 365 Customer Insights

„Prawo do usunięcia danych osobowych” poprzez usunięcie prywatnych danych klienta organizacji jest kluczową ochroną w Ogólnym rozporządzeniu o ochronie danych (RODO). Usuwanie danych osobowych polega na usunięciu wszystkich danych osobowych i dzienników generowanych przez system, poza informacjami dotyczącymi dziennika inspekcji.

#### <a name="manage-data-subject-delete-requests"></a>Zarządzanie żądaniami usuwania danych

Customer Insights oferuje następujące doświadczenia w produkcie, które usuwają dane osobowe dotyczące konkretnego użytkownika lub klienta:

- **Zarządzanie żądaniami usuwania danych klienta**: dane klienta w Customer Insights są pobierane z oryginalnych źródeł danych spoza Customer Insights. Wszystkie żądania dotyczące usuwania danych według RODO muszą zostać wykonane w oryginalnym źródle danych.
- **Zarządzanie żądaniami usunięcia danych użytkownika Customer Insights**: Dane dla użytkowników są tworzone przez Customer Insights. Wszystkie żądania dotyczące usuwania danych według RODO muszą zostać wykonane w Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Zarządzanie żądaniami usunięcia danych klienta

Administrator Customer Insights może wykonać poniższe kroki w celu usunięcia danych klienta, które zostały usunięte ze źródła danych:

1. Zaloguj się w Dynamics 365 Customer Insights.
2. Przejdź do **Dane** > **Źródła danych**
3. Dla każdego źródła danych z listy, które zawiera usunięte dane klienta:
   1. Wybierz wielokropek pionowy (&vellip;) i wybierz opcję **Odśwież**.
   2. Sprawdź status źródła danych w **Stan**. Znacznik wyboru oznacza, że odświeżanie zakończyło się powodzeniem. Trójkąt ostrzegawczy oznacza, że wystąpił problem. Jeśli zostanie wyświetlony trójkąt ostrzegawczy, skontaktuj się z D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Zarządzanie żądaniami usunięcia danych klienta według RODO.](media/gdpr-data-sources.png "Zarządzanie żądaniami usunięcia danych klienta według RODO")

##### <a name="manage-delete-requests-for-user-data"></a>Zarządzanie żądaniami usunięcia danych użytkownika

Administrator Customer Insights może wykonać poniższe kroki w celu usunięcia danych użytkownika Customer Insights:

1. Zaloguj się w Dynamics 365 Customer Insights.
2. Przejdź do **Administrator** > **Zabezpieczenia** > **Uprawnienia**.
3. Zaznacz pole wyboru dla użytkownika, którego chcesz usunąć.
4. Wybierz **Usuń**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Odpowiadanie na żądania podmiotów o eksport danych osobowych zgodnie z RODO

W ramach naszych starań, aby wspierać użytkowników w trakcie wdrażania Ogólnego rozporządzenia o ochronie danych (RODO), opracowano dokumentację ułatwiającą odpowiadanie na zapytania od podmiotów danych.

#### <a name="manage-export-and-view-requests"></a>Zarządzanie żądaniami eksportowania i wyświetlania

Prawo do przenoszenia danych osobowych pozwala podmiotowi danych składać wniosek o kopię danych osobowych w formacie elektronicznym („struktura, powszechnie stosowana, czytelna i wieloprogramowa”), który może być przekazywany innemu kontrolerowi danych.

##### <a name="export-customer-data-tenant-admin"></a>Eksportowanie danych klienta (Administrator dzierżawcy)

W celu wyeksportowania danych administrator dzierżawy może wykonać następujące kroki:

1. Wysłąć wiadomość e-mail na adres D365CI@microsoft.com określając adres e-mail klienta w żądaniu. Zespół Customer Insights wyśle wiadomość e-mail na adres e-mail zarejestrowanego administratora dzierżawcy, pytając o potwierdzenie wyeksportowania danych.
2. Zatwierdź potwierdzenie wyeksportowania danych dla żądanego klienta.
3. Pobierz eksportowane dane za pomocą adresu e-mail administratora dzierżawcy.

##### <a name="export-user-data-tenant-admin"></a>Eksportuj dane użytkownika (administrator dzierżawy)

1. Wysłąć wiadomość e-mail na adres D365CI@microsoft.com określając adres e-mail użytkownika w żądaniu. Zespół Customer Insights wyśle wiadomość e-mail na adres e-mail zarejestrowanego administratora dzierżawcy, pytając o potwierdzenie wyeksportowania danych.
2. Zatwierdź potwierdzenie wyeksportowania danych dla żądanego użytkownika.
3. Pobierz eksportowane dane za pomocą adresu e-mail administratora dzierżawcy.

[!INCLUDE [footer-include](includes/footer-banner.md)]