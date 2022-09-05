---
title: Żądania podmiotów danych osobowych (DSR) w kontekście rozporządzenia RODO | Microsoft Docs
description: Odpowiadanie na żądania podmiotów danych osobowych w Dynamics 365 Customer Insights.
ms.date: 08/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 49251fb46957c4d7ec205b93c9547a3cd380eb11
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387124"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Żądania osób, których dotyczą dane, w kontekście rozporządzenia RODO

Ogólne rozporządzenie o ochronie danych (RODO) w Unii Europejskiej obowiązuje od 25 maja 2018 roku. Daje istotne prawa osobom w odniesieniu do ich danych. Zasadniczo przepisy GDPR dotyczą ochrony i zapewnienia prawa do prywatności osób fizycznych. Więcej informacji na temat zaangażowania firmy Microsoft w kwestie bezpieczeństwa i zgodności można znaleźć na stronie [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Dokładamy wszelkich starań, aby pomóc klientom w spełnianiu ich wymagań dotyczących rozporządzenia RODO. Obejmuje prawo usuwania lub eksportowania danych, które zawierają dane osobowe, takie jak identyfikatory użytkowników, numery telefonów i adresy e-mail. Administratorzy mogą implementować żądania użytkowników w celu usuwania lub eksportowania danych osobowych.

## <a name="responding-to-gdpr-data-subject-delete-requests-for-customer-insights"></a>Odpowiadanie na żądania usunięcia przez osobę, której dane dotyczą, w Customer Insights

„Prawo do usunięcia danych osobowych” poprzez usunięcie prywatnych danych klienta organizacji jest kluczową ochroną w Ogólnym rozporządzeniu o ochronie danych (RODO). Usuwanie danych osobowych polega na usunięciu wszystkich danych osobowych i dzienników generowanych przez system, poza informacjami dotyczącymi dziennika inspekcji.

### <a name="manage-data-subject-delete-requests"></a>Zarządzanie żądaniami usuwania danych

Customer Insights oferuje następujące doświadczenia w produkcie, które usuwają dane osobowe dotyczące konkretnego użytkownika lub klienta:

- **Zarządzanie żądaniami usuwania danych klienta**: dane klienta w Customer Insights są pobierane z oryginalnych źródeł danych spoza Customer Insights. Najpierw wykonaj żądania usunięcia RODO w oryginalnym źródle danych.
- **Zarządzanie żądaniami usunięcia danych użytkownika Customer Insights**: Dane dla użytkowników są tworzone przez Customer Insights. Wykonaj wszystkie żądania usunięcia RODO w Customer Insights.

#### <a name="manage-requests-to-delete-customer-data"></a>Zarządzanie żądaniami usunięcia danych klienta

Jako administrator Customer Insights usuń dane klienta Customer Insights, które zostały usunięte ze źródła danych. Sprawdź, czy żądania usunięcia RODO zostały wykonane w oryginalnym źródle danych.

1. Zaloguj się w Dynamics 365 Customer Insights.

1. Przejdź do **Dane** > **Źródła danych**.

1. Dla każdego źródła danych z listy, które zawiera usunięte dane klienta:
   1. Wybierz źródło danych, a następnie wybierz **Odśwież**.
   1. Sprawdź status źródła danych w **Stan**. Znacznik wyboru oznacza, że odświeżanie zakończyło się powodzeniem. Trójkąt ostrzegawczy oznacza, że wystąpił problem. Jeśli zostanie wyświetlony trójkąt ostrzegawczy, skontaktuj się z D365CI@microsoft.com.

   :::image type="content" source="media/gdpr-data-sources.png" alt-text="Zarządzanie żądaniami usunięcia danych klienta według RODO.":::

1. Po pomyślnym odświeżeniu źródeł danych uruchom również odświeżenia podrzędne. Zwłaszcza jeśli nie masz zaplanowanego cyklicznego pełnego odświeżenia Customer Insights.

   > [!IMPORTANT]
   > Segmenty statyczne nie są uwzględniane w pełnym odświeżaniu lub uruchomionych odświeżeniach po żądaniu usunięcia. Aby upewnić się, że dane klientów zostaną usunięte również z segmentów statycznych, należy odtworzyć segmenty statyczne z odświeżonymi danymi źródłowymi.

#### <a name="manage-delete-requests-for-user-data"></a>Zarządzanie żądaniami usunięcia danych użytkownika

Jako administrator Customer Insights usuń dane użytkownika Customer Insights.

1. Zaloguj się w Dynamics 365 Customer Insights.

1. Przejdź do pozycji **Administracja** > **Zabezpieczenia** > i wybierz kartę **Użytkownicy**.

1. Zaznacz pole wyboru dla użytkownika, którego chcesz usunąć.

1. Wybierz **Usuń**.

1. Potwierdź usunięcie.

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Odpowiadanie na żądania podmiotów o eksport danych osobowych zgodnie z RODO

Prawo do przenoszenia danych osobowych pozwala podmiotowi danych składać wniosek o kopię danych osobowych w formacie elektronicznym („struktura, powszechnie stosowana, czytelna i wieloprogramowa”), który może być przekazywany innemu kontrolerowi danych.

### <a name="manage-export-and-view-requests"></a>Zarządzanie żądaniami eksportowania i wyświetlania

Zarządzaj żądaniami eksportu danych klientów lub użytkowników.

#### <a name="export-customer-data-tenant-admin"></a>Eksportowanie danych klienta (Administrator dzierżawcy)

Jako administrator dzierżawy wyeksportuj dane klientów.

1. Wysłąć wiadomość e-mail na adres D365CI@microsoft.com określając adres e-mail klienta w żądaniu. Zespół Customer Insights wyśle wiadomość e-mail na adres e-mail zarejestrowanego administratora dzierżawcy, pytając o potwierdzenie wyeksportowania danych.
2. Zatwierdź potwierdzenie wyeksportowania danych dla żądanego klienta.
3. Pobierz eksportowane dane za pomocą adresu e-mail administratora dzierżawcy.

#### <a name="export-user-data-tenant-admin"></a>Eksportuj dane użytkownika (administrator dzierżawy)

Jako administrator dzierżawy wyeksportuj dane użytkownika.

1. Wysłąć wiadomość e-mail na adres D365CI@microsoft.com określając adres e-mail użytkownika w żądaniu. Zespół Customer Insights wyśle wiadomość e-mail na adres e-mail zarejestrowanego administratora dzierżawcy, pytając o potwierdzenie wyeksportowania danych.
1. Zatwierdź potwierdzenie wyeksportowania danych dla żądanego użytkownika.
1. Pobierz eksportowane dane za pomocą adresu e-mail administratora dzierżawcy.

## <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Obsługa usuwania danych w Dynamics 365 Customer Insights

Dane są usuwane (partycje danych i migawki danych), jeśli partycje danych i migawki danych są nieaktywne przez ponad 30 dni, co oznacza, że zostały zastąpione nową partycją danych i migawką poprzez odświeżenie źródeł danych.

Nie wszystkie dane i migawki są usuwane. Najnowsze partycje danych i migawki danych są aktywne, ponieważ są używane w funkcjach Customer Insights. W przypadku najnowszych danych nie ma znaczenia, czy źródła danych nie zostały odświeżone w ciągu ostatnich 30 dni.

[!INCLUDE [footer-include](includes/footer-banner.md)]
