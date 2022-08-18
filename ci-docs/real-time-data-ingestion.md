---
title: Pozyskiwanie danych w czasie rzeczywistym (wersja zapoznawcza)
description: Ogólne informacje na temat funkcji w czasie rzeczywistym w Customer Insights.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 2652e0868f5cc514ab6df9c150a9183cf95ae589
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246121"
---
# <a name="real-time-data-ingestion-preview"></a>Pozyskiwanie danych w czasie rzeczywistym (wersja zapoznawcza)

Działająca niemal w czasie rzeczywistym funkcja umożliwia wyświetlenie, w ciągu zaledwie sekund, najnowszych interakcji między klientami a produktami lub usługami.

[W zaplanowanym odświeżaniu](schedule-refresh.md) znajduje się wiele rekordów i przedstawiono wiele operacji złożonych. Po pierwsze, dane są pobierane ze źródła danych. Następnie dane są ujednolicane i wzbogacane o dodatkowe informacje. Każdy przebieg tego procesu może potrwać od kilku minut do kilku godzin.

Funkcjonalność czasu rzeczywistego zapewnia natychmiastowe wykorzystanie danych do momentu, gdy kolejne zaplanowane odświeżanie pobierze te dane ze źródła danych.

Aktualizacje w czasie rzeczywistym mają czas wygaśnięcia, po którym nie będą już zastępować wartości ze źródła danych:

- Aktualizacje profilu będą przechowywane przez cztery godziny
- Działania będą przechowywane przez 30 dni

Te wartości są parametrami wywołania interfejsu API, które można zmienić. Mają one na celu zagwarantowanie, że dane źródłowe pozostaną źródłem prawdy. Jeśli chcesz, aby aktualizacje w czasie rzeczywistym były uwzględniane dłużej, musisz dodać je do źródła danych, aby były pobierane podczas następnego zaplanowanego odświeżania.

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>Aktualizacja w czasie rzeczywistym ujednoliconych pól profilu klienta

Zaktualizowane profile będą wyświetlane w widoku karty klientów lub innej wizualizacji w ciągu kilku sekund.

Ponieważ operacje w czasie rzeczywistym mają miejsce po zakończeniu ujednolicania danych, mają one zastosowanie wyłącznie w przypadku ujednoliconych profili klientów. W rezultacie zmiany profilu w czasie rzeczywistym nie będą aktualizować miar, członkostwa w segmencie ani wzbogaceń.

### <a name="limitations"></a>Ograniczenia

- Profile klientów mogą być aktualizowane, ale nie można ich tworzyć ani usuwać.
- Obecnie nie jest możliwe eksportowanie aktualizacji w czasie rzeczywistym do systemów zewnętrznych, takich jak Power BI.

## <a name="real-time-creation-of-activities"></a>Tworzenie działań w czasie rzeczywistym

Interfejs API czasu rzeczywistego umożliwia publikowanie nowej aktywności z systemu źródłowego (indywidualny rekord źródłowy) w ujednoliconym profilu klienta. Nowe działanie będzie dostępne jako ujednolicone działanie w tej osi czasu ujednoliconego profilu klienta w ciągu sekund. Możesz zobaczyć oś czasu w widoku karty klienta lub dowolnej innej skonfigurowanej integracji osi czasu.

> [!NOTE]
>
> - Działania są niezmienne. Nie zmienią się po utworzeniu.
> - Obecnie segmenty i miary nie są aktualizowane w oparciu o nowe działanie.
> - Działania dodane wyłącznie za pośrednictwem interfejsu API w czasie rzeczywistym nie są częścią eksportów i nie będą widoczne w usłudze PowerBI.

Istnieją dwa sposoby łączenia się z interfejsem API w czasie rzeczywistym:

- [pośrednio](#connect-via-the-dynamics-365-customer-insights-connector), za pomocą [łącznika Dynamics 365 Customer Insights](/connectors/customerinsights/)
- [bezpośrednio](#connect-directly-to-the-real-time-api), przy użyciu kodu

Oba sposoby wiążą się z poniższymi wymaganiami wstępnymi:

- Środowisko Customer Insights
- Ujednolicone profile klientów
- Działania skonfigurowane i wykonane
- Uprawnienia współautora lub administratora do uwierzytelniania konta

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Połącz za pośrednictwem łącznika Dynamics 365 Customer Insights

Interfejs API w czasie rzeczywistym może pobierać dane z dedykowanego łącznika Power Platform, [łącznik Dynamics 365 Customer Insights](/connectors/customerinsights/), bez konieczności pisania i wdrażania kodu.    
Łącznik może wykonywać te same akcje w czasie rzeczywistym, co interfejs API. Użytkownik musi mieć ważną licencję na łączniki Premium. Aby uzyskać więcej informacji, zobacz [Licencje na Power Apps i Power Automate, często zadawane pytania](/power-platform/admin/powerapps-flow-licensing-faq).

- Power Platform [Power Apps i/lub Power Automate](/connectors/)
- Azure [Logic Apps](/azure/connectors/apis-list)

Szczegółowe informacje o tworzeniu przepływów można znaleźć w artykule [Dokumentacja Power Automate](/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>Połącz bezpośrednio z interfejsem API w czasie rzeczywistym

Możesz korzystać z funkcji czasu rzeczywistego, tworząc własny potok i łącząc się bezpośrednio z interfejsem API czasu rzeczywistego.    
Działanie można ogłosić w formacie systemu źródłowego lub w formacie UnifiedActivity. Pobierz format, tworząc wywołanie interfejsu API do /api/instances/{instanceId}/manage/entities/UnifiedActivity.

Szczegółowe informacje o tym interfejsie API, w tym parametry i odpowiedzi, można znaleźć w sekcji **EntityData** w [skorowidzu interfejsów API Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Aby uzyskać więcej informacji, zobacz temat [Praca z interfejsami API Customer Insights](apis.md).

## <a name="understand-your-real-time-usage-with-telemetry"></a>Informacje o sposobie korzystania z telemetrii w czasie rzeczywistym

Uzyskaj przegląd liczby żądań do interfejsu API czasu rzeczywistego i informacje o problemach, które może napotkać system. Można uzyskać dostęp do [telemetryki w czasie rzeczywistym](system.md#view-api-usage). 


[!INCLUDE [footer-include](includes/footer-banner.md)]
