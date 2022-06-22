---
title: Wzbogacanie profilów klientów na podstawie danych lokalizacji z usługi Azure Maps
description: Ogólne informacje o wzbogaceniach od naszej firmy w usłudze Azure Maps.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a806b2d0c791972c967c90694527608b4def9f3f
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953641"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Wzbogacanie profilów klientów za pomocą usługi Azure Maps (wersja zapoznawcza)

Mapowania Azure zapewniają dane i usługi oparte na lokalizacjach, co zapewnia dostęp do danych geograficznych przy użyciu wbudowanej analizy lokalizacji. Usługi wzbogacenia danych za pomocą usługi Azure Maps poprawiają dokładność informacji o lokalizacjach klientów. Dodają one funkcje, takie jak normalizacja adresu i wyodrębnianie szerokości i długości geograficznej, do aplikacji Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Wymagania wstępne

- Aktywna subskrypcja platformy Azure. Aby uzyskać subskrypcję, [utwórz konto lub uzyskaj bezpłatną wersję próbną](https://azure.microsoft.com/services/azure-maps/).

- [Połączenie](connections.md) Azure Maps jest [konfigurowane](#configure-the-connection-for-azure-maps) przez administratora.

## <a name="configure-the-connection-for-azure-maps"></a>Konfigurowanie połączenia dla usługi Azure Maps

Musisz mieć rolę [administratora](permissions.md#admin) funkcji Customer Insights i mieć aktywny klucz interfejsu API Map Azure Maps.

1. Wybierz opcję **Dodaj połączenie** podczas konfigurowania wzbogacenia lub wybierz pozycję **Administracja** > **Połączenia** i wybierz opcję **Skonfiguruj** na kafelku usługi Azure Maps.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Strona konfiguracji połączenia w usłudze Azure Maps.":::

1. Wprowadź nazwę połączenia i prawidłowy klucz interfejsu API Map Azure Maps.

1. Przejrzyj i wyraź zgodę na [Zasady ochrony prywatności danych](#data-privacy-and-compliance), wybierając przycisk **I agree (Wyrażam zgodę)**.

1. Wybierz **Weryfikuj**, aby sprawdzić poprawność konfiguracji, a następnie wybierz opcję **Zapisz**.

### <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Włączenie funkcji przekazywania danych do usługi Azure Maps w aplikacji Dynamics 365 Customer Insights umożliwia przesyłanie danych poza granice obszaru zgodności dla aplikacji Dynamics 365 Customer Insights, w tym potencjalnie poufnych danych, takich jak dane osobiste. Microsoft przekaże takie dane na twoje polecenie, ale to ty jesteś odpowiedzialny za zapewnienie, że spotkanie Azure Maps spełnia wszelkie zobowiązania dotyczące prywatności i bezpieczeństwa, jakie możesz mieć. Więcej informacji można znaleźć w [Oświadczeniu o ochronie prywatności Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć wzbogacanie, aby przestać używać tej funkcji.

## <a name="configure-the-enrichment"></a>Konfiguracja wzbogacania

1. Przejdź do **Dane** > **Wzbogacenie** i wybierz kartę **Odkrywanie**.

1. Wybierz opcję **Wzbogać moje dane** na kafelku Microsoft Azure Maps z **Lokalizacji**.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Kafelek usługi Azure Maps.":::

1. Przejrzyj omówienie, a następnie wybierz **Dalej**.

1. Wybierz połączenie. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Wybierz **Dalej**.

1. Wybierz **Zestaw danych klienta** i wybierz profil i segment, który chcesz wzbogacić o dane dotyczące tożsamości z Microsoft. Można wybrać encję *Klient*, aby wzbogacić wszystkie profile klientów, lub wybierz jednostkę segmentu, aby wzbogacić tylko profile klientów zawarte w tym segmencie.

1. Zdefiniuj typy pól z ujednoliconych profilów, które mają być dopasowane: adres podstawowy i/lub dodatkowy. Można oddzielnie określić mapowanie pól dla obu adresów i wzbogacić profile dla obu adresów. Na przykład: adres domowy i adres służbowy. Wybierz **Dalej**.

1. Zamapuj pola na dane lokalizacji z witryny Azure Maps. Pola **Ulica 1** i **Kod pocztowy** są wymagane dla wybranego adresu głównego i / lub dodatkowego. Aby uzyskać większą dokładność dopasowania, należy dodać więcej pól.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Mapowanie atrybutów Azure Maps.":::

1. Wybierz **Dalej**, by zakończyć mapowanie pól.

1. Przeglądanie **Ustawień zaawansowanych**, które oferują maksymalną elastyczność w przypadku obsługi zaawansowanych spraw. Zazwyczaj nie trzeba zmieniać następujących wartości domyślnych.

   - **Typ adresów**: najlepsze dopasowanie adresu zwracane jest nawet wtedy, gdy jest niekompletny. Aby otrzymać tylko pełne adresy &mdash; na przykład adresy z numerem telefonu &mdash; wyczyść wszystkie pola wyboru poza polem **Adresy punktów**.
   - **Język**: adresy są zwracane w języku według regionu adresu. Aby zastosować ustandaryzowany język adresu, wybierz język z menu rozwijanego. Na przykład wybranie opcji **angielskiej** zwraca **Copenhagen, Denmark** zamiast **København, Danmark**.
   - **Maksymalna liczba wyników**: liczba wyników dla każdego adresu.

1. Wybierz **Dalej**.

1. Podaj **Nazwę** dla wzbogacenia oraz **Nazwa encji wyjściowej**.

1. Wybierz opcję **Zapisz wzbogacenie** po przejrzeniu wybranych opcji.

1. Wybierz przycisk **Uruchom**, aby rozpocząć proces wzbogacenia lub zamknąć, aby powrócić do strony **Wzbogacanie**.

## <a name="enrichment-results"></a>Wyniki wzbogacenia

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Liczba klientów wzbogaconych według pola** zapewnia szczegółowe informacje na temat pokrycia każdego wzbogaconego pola.

## <a name="next-steps"></a>Następne kroki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
