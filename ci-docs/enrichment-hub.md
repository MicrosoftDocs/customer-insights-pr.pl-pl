---
title: Omówienie wzbogacania danych (wersja zapoznawcza)
description: Aby wzbogacić dane klientów, należy użyć funkcji firmy Microsoft i innych usług innych firm.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 6b6daab480db5e37830ff58b71dcdd3bbdbe46da
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053893"
---
# <a name="data-enrichment-preview-overview"></a>Omówienie wzbogacania danych (wersja zapoznawcza)

Aby wzbogacić dane klientów, należy użyć danych pochodzących ze źródeł, takich jak Microsoft i inni partnerzy. Wzbogacenia innych firm konfiguruje się przy użyciu [połączeń](connections.md), które administrator konfiguruje się z poświadczeniami i wyraża zgodę na przesyłanie danych. Połączenia mogą być używane przez administratorów i współautorów do konfigurowania wzbogaceń.  

## <a name="multiple-enrichments-of-the-same-type"></a>Wiele wzbogaceń tego samego typu

Podczas konfigurowania wzbogacania jest określana encja do wzbogacenia, która umożliwia wzbogacenie tylko podzestawu profilów. Na przykład wzbogać dane tylko dla określonego segmentu. Można skonfigurować wiele wzbogaceń tego samego typu i ponownie używać tego samego połączenia. Niektóre wzbogacenia będą mieć ograniczoną liczbę wzbogaceń tego samego typu, które można utworzyć. Ograniczenia i bieżące użycie są widoczne na każdym kafelku na karcie **Poznaj** na stronie **Wzbogacanie**.

## <a name="enrich-data-sources-before-unification"></a>Wzbogać źródła danych przed unifikacją

Możesz wzbogacić dane klientów przed ujednoliceniem danych, aby zwiększyć jakość dopasowania danych. Aby uzyskać więcej informacji, zobacz [wzbogacanie źródła danych](data-sources-enrichment.md).

## <a name="create-an-enrichment"></a>Utwórz wzbogacenie

Aby tworzyć lub edytować wzbogacenia, trzeba mieć [uprawnienia](permissions.md) Współautor lub Administrator.

Przejdź do **Dane** > **Wzbogacanie**. Karta **Odnajdowanie** pokazuje wszystkie obsługiwane opcje wzbogacania.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Strona centrum wzbogacania.":::

# <a name="individual-consumers-b-to-c"></a>[Klienci indywidualni (B2C)](#tab/b2c)

- [Tożsamość AbiliTec Identity](enrichment-liveramp.md) dostarczona przez LiveRamp AbiliTec
- [Marki](enrichment-microsoft.md) dostarczone przez Microsoft
- [Dane demograficzne](enrichment-experian.md) dostarczane przez usługę Experian
- [Ulepszone adresy](enrichment-enhanced-addresses.md) od Microsoft
- [Zainteresowania](enrichment-microsoft.md) dostarczone przez Microsoft
- [Dane lokalizacji](enrichment-azure-maps.md) według map Microsoft Azure
- [Dane lokalizacji](enrichment-here.md) dostarczane przez HERE Technologies
- [Dane niestandardowe SFTP](enrichment-SFTP-custom-import.md) za pomocą protokołu SFTP (Secure File Transfer Protocol)

# <a name="business-accounts-b-to-b"></a>[Klienci biznesowi (B2B)](#tab/b2b)

- [Dane dotyczące zaangażowania konta](enrichment-office.md) dostarczone przez Microsoft
- [Dane firmy](enrichment-dnb.md) podane przez Dun & Bradstreet
- [Dane firmy](enrichment-leadspace.md) zapewniane przez Leadspace
- [Ulepszone adresy](enrichment-enhanced-addresses.md) od Microsoft
- [Rozszerzone dane firmy](enrichment-enhanced-company-data.md) dostarczane przez Microsoft
- [Dane lokalizacji](enrichment-azure-maps.md) według map Microsoft Azure
- [Dane lokalizacji](enrichment-here.md) dostarczane przez HERE Technologies
- [Dane niestandardowe SFTP](enrichment-SFTP-custom-import.md) za pomocą protokołu SFTP (Secure File Transfer Protocol)

---

## <a name="manage-existing-enrichments"></a>Zarządzanie istniejącymi wzbogaceniami

Przejdź do **Dane** > **Wzbogacanie**. Na karcie **Moje wzbogacenia** wyświetl skonfigurowane wzbogacania, ich stan, liczbę wzbogaconych klientów i czas ostatniego odświeżania danych. Listę wzbogacań można posortować według dowolnej kolumny lub użyć pola wyszukiwania, aby znaleźć wzbogacanie, którym chcesz zarządzać.

Wybierz wzbogacanie, aby wyświetlić dostępne akcje.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcje służące do zarządzania wzbogaceniami na liście wzbogaceń.":::

- **Wyświetl** szczegóły wzbogacenia dzięki liczbie ulepszonych profilów klientów.
- **Edytuj** konfigurację wzbogacenia.
- [**Uruchom**](#run-or-refresh-enrichments) wzbogacenie, aby zaktualizować profile klientów za pomocą najnowszych danych. Uruchom wiele wzbogaceń jednocześnie, wybierając je z listy.
- **Aktywowanie** lub **dezaktywowanie** wzbogacenia. Nieaktywne wzbogacenia nie będą odświeżane podczas [zaplanowanego odświeżania](system.md#schedule-tab).
- **Usuń** wzbogacenie.

Można także tworzyć [segmenty](segments.md) i [miary](measures.md) na pomocą wzbogacania.

## <a name="run-or-refresh-enrichments"></a>Uruchamianie i odświeżanie wzbogacenia

Po uruchomieniu, wzbogacenia można odświeżać automatycznie lub ręcznie na żądanie.

1. Aby ręcznie odświeżyć jedno lub więcej wzbogaceń, wybierz je i wybierz opcję **Uruchom**. Aby [zaplanować automatyczne odświeżanie](system.md#schedule-tab), przejdź do strony **Administrator** > **System** > **Harmonogram**. Czas przetwarzania zależy od rozmiaru danych klienta.

1. Opcjonalnie [sprawdź postęp procesu wzbogacania](#see-the-progress-of-the-enrichment-process).

1. Po zakończeniu procesu wzbogacania przejdź do **mojego wzbogacenia** w celu przejrzenia nowo wzbogacenia danych profilów klientów, czasu ostatniej aktualizacji i liczby profilów wzbogaconych.

1. Wybierz wzbogacanie, aby wyświetlić [wyniki wzbogacenia](#view-enrichment-results).

### <a name="see-the-progress-of-the-enrichment-process"></a>Wyświetlanie postępu procesu wzbogacania

Można tu znaleźć szczegółowe informacje o przetwarzaniu wzbogacania, w tym informacje o stanie i potencjalnych problemach podczas odświeżania lub po zakończeniu odświeżania. Zidentyfikuj procesy związane z odświeżaniem wzbogacania i dowiedz się, ile trwa ich działanie. Stan wzbogacenia jest obsługiwany w przypadku usług Experian, Leadspace, HERE Technologies, SFTP Import i Azure Maps.

1. Przejdź do **Dane** > **Wzbogacanie**.
1. Na karcie **Moje wzbogacenia** wybierz stan wzbogacania, aby otworzyć okienko boczne.
1. W okienku **szczegółów postępu** rozwiń sekcję **Wzbogacanie**.
1. W obszarze wzbogacania, dla którego chcesz wyświetlić postęp, wybierz opcję **Zobacz szczegóły**.
1. W okienku **szczegółów zadania** wybierz opcję **Pokaż szczegóły**, aby wyświetlić procesy związane z aktualizowaniem wzbogacenia i jego stanu.

## <a name="view-enrichment-results"></a>Wyświetlanie wyników wzbogacenia

Po zakończeniu procesu wzbogacenia przejrzyj wyniki wzbogacenia.

1. Przejdź do **Dane** > **Wzbogacanie**.
1. Na karcie **Moje wzbogacenia** wybierz wzbogacanie, które chcesz wyświetlić.

Wszystkie wzbogacenia pokazują podstawowe informacje, takie jak liczba wzbogaconych profili oraz liczba wzbogaconych profili w czasie. Kafelek **Podgląd wzbogaconych klientów** zawiera przykładową encję wzbogacenia. Aby uzyskać dostęp do szczegółowego widoku, wybierz opcję **Zobacz więcej** i wybierz kartę **Dane**.

:::image type="content" source="media/enrichments-results.png" alt-text="Strona wyników wzbogaceń.":::

Jeśli jest dostępna, **Liczba klientów wzbogaconych według pola** zapewnia szczegółowe informacje na temat pokrycia każdego wzbogaconego pola.

Niektóre wzbogacanie zawierają także informacje dotyczące typu wzbogacania. Aby uzyskać więcej informacji, zobacz powiązaną dokumentację.

[!INCLUDE [footer-include](includes/footer-banner.md)]
