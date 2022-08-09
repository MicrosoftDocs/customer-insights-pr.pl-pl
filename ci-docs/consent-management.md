---
title: Użycie zgody klienta
description: Szanuj preferencje dotyczące zgody klientów w Customer Insights, importując dane zgody.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 99fe24cb47a8c20f629182d9a1c6adfd36a1eaf7
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188061"
---
# <a name="use-customer-consent"></a>Użycie zgody klienta

Przepisy dotyczące ochrony danych i ochrony prywatności dają osobom prawo do zarządzania sposobem, w jaki organizacja korzysta z danych osobowych. Przykładami takich przepisów jest Ogólne rozporządzenie o ochronie danych w Unii Europejskiej lub Ustawa o ochronie prywatności konsumenta w Kalifornii w Stanach Zjednoczonych. Przepisy te umożliwiają użytkownikom nie wyrażenie zgody na zbieranie, przetwarzanie swoich danych osobowych przez inne firmy lub udostępnianych ich osobom trzecim.  

Klienci mogą cofnąć lub wycofać zgodę na określone formy kontaktu. Użytkownik może również zażądać od nich rezygnacji z gromadzenia, przechowywania, używania lub sprzedaży swoich danych osobowych. Ważne jest, aby organizacja honorowała zgodę wszystkich klientów i preferencje dotyczące prywatności.  

Program Dynamics 365 Customer Insights umożliwia honorowanie żądań klientów przez importowanie i przechowywanie ich preferencji w ramach unified customer profile.

Jeśli dane zgody są przechowywane niezależnie od profilów klientów, [dodaj dane zgody jako nowe źródło danych](#import-and-unify-consent-data). Źródło danych zawierające dane zgody jest dodawane do procesu ujednolicania danych. Pomyślne ujednolicenie danych zgody i profilów klientów prowadzi następnie do unified customer profile zawierających informacje o zgodzie. W przypadku profilów klientów, które już zawierają informacje dotyczące zgody, przejdź bezpośrednio do sekcji [Użycie zgody klienta](#use-consent-data).

## <a name="prerequisites"></a>Wymagania wstępne

W danych źródłowych muszą być dostępne następujące informacje, aby ujednolicić dane zgody w innych profilach klientów:

- Klucz alternatywny, aby zamapować informacje dotyczące zgody na profile użytkowników w aplikacji Customer Insights. Na przykład numer telefonu lub adres e-mail.
- Wartość zgody w celu określenia stanu zgody klienta.

Rozważ dodanie następujących *opcjonalnych* informacji:

- Klucz podstawowy do zaktualizowania stanu zgody, jeśli klient żąda zmiany.
- Typ zgody, jeśli istnieje więcej niż jeden sposób przetwarzania informacji o kliencie.
- Data zgody lub dowolny inny typ danych istotnych dla scenariuszy wyrażania zgody.

Przykładowa tabela prostej bazy danych zgody z wieloma opcjami wyrażania zgody:

|Identyfikator zgody (klucz podstawowy)   |Adres e-mail (klucz alternatywny)  |Opcja zgody  |Wartość zgody  |
|---------|---------|---------|---------|
|1    |  holly@contoso.com       |  Biuletyn       |  Fałsz       |
|2    |  holly@contoso.com       |  Aktualizacje produktu       |  Prawda       |
|3    |  frank@contoso.com       |  Biuletyn       | Prawda        |
|100    |  frank@contoso.com       |  Aktualizacje produktu       |  Fałsz       |

## <a name="import-and-unify-consent-data"></a>Importowanie i ujednolicenie danych zgody

Importuj dane dotyczące zgody w taki sam sposób, w jaki pozyskujesz inne źródła danych do Customer Insights. Aby uzyskać więcej informacji na temat obsługiwanych źródeł danych i sposobu ich importowania, zobacz [Omówienie źródeł danych](data-sources.md).

Aby uzyskać więcej informacji na temat ujednolicania źródeł danych, zobacz [Omówienie ujednolicania danych](data-unification.md).

## <a name="use-consent-data"></a>Używanie danych dotyczących zgody

Gdy dane zgody są częścią unified customer profile, możesz ich używać w funkcji Customer Insights. Na przykład utwórz segment z regułą, aby zagwarantować, że będziesz honorować preferencje dotyczące prywatności i ochrony danych klientów. Reguły wspierające preferencje dotyczące zgody są używane, aby wykluczać użytkowników z segmentu na podstawie atrybutów profilu. Dodanie reguły do segmentu, który nie obejmuje profilów klientów, które nie zawierają zgody na kontakt.

Odwołując się do powyższej tabeli przykładowej, segment może zawierać tę regułę: `Consent option=Newsletter & Consent value=True`. Ta konfiguracja powoduje segment, który honoruje preferencje dotyczące kontaktu w celu wysłania biuletynu.

Aby uzyskać więcej informacji na temat segmentów tworzenia, zobacz temat [Tworzenie segmentów](segment-builder.md).

Po utworzeniu segmentu można użyć jednej z wielu [opcji eksportowania](export-destinations.md), aby korzystać z tego segmentu w innych aplikacjach.

## <a name="ensure-updated-consent-status"></a>Upewnij się, że zgoda została zaktualizowana

Ważne jest, aby stan zgody klienta był aktualizowany. Zaplanowane odświeżenie w aplikacji Customer Insights zawsze importuje najnowszy stan źródeł danych. Te informacje są następnie przetwarzane w ramach ujednolicania danych i powodują zaktualizowanie profilów klientów. Te zaktualizowane profile są następnie używane do odświeżania segmentów, aby zapewnić pracę z najbardziej aktualnymi informacjami.

Innymi słowy, dane źródłowe importowane do rozwiązania Customer Insights zawsze mają najnowsze informacje.

Aby uzyskać więcej informacji, zobacz [Ręczne odświeżanie segmentów](segments.md#refresh-segments) lub [konfigurowanie zaplanowanego odświeżania](system.md#schedule-tab).

[!INCLUDE [footer-include](includes/footer-banner.md)]
