---
title: Wzbogać ujednolicone profile klientów
description: Korzystanie z funkcji w celu wzbogacenia danych klienta.
ms.date: 02/07/2022
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
ms.openlocfilehash: e8cac35ccf7012524dc22cb4a499dc605dd66346
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355396"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Wzbogacenie profilów klientów (wersja zapoznawcza)

Aby wzbogacić dane klientów, należy użyć danych pochodzących ze źródeł, takich jak Microsoft i inni partnerzy.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Strona centrum wzbogacania.":::

W statystykach odbiorców przejdź do **Dane** > **Wzbogacenie**, aby pracować z opcjami wzbogacania.  

Aby tworzyć lub edytować wzbogacenia, trzeba mieć uprawnienia Współautor lub Administrator. Aby uzyskać więcej informacji, zobacz [Uprawnienia](permissions.md).

Na karcie **Odnajdowanie** znajdziesz wszystkie obsługiwane opcje wzbogacania.

# <a name="individual-consumers-b-to-c"></a>[Klienci indywidualni (B2C)](#tab/b2c)

- [Marki](enrichment-microsoft.md) dostarczone przez Microsoft
- [Zainteresowania](enrichment-microsoft.md) dostarczone przez Microsoft
- [Ulepszone adresy](enrichment-enhanced-addresses.md) od Microsoft 
- [Dane demograficzne](enrichment-experian.md) dostarczane przez usługę Experian
- [Dane niestandardowe](enrichment-SFTP-custom-import.md) za pomocą protokołu SFTP (Secure File Transfer Protocol) 
- [Azure Maps](enrichment-azure-maps.md) oferowane przez Microsoft
- [Dane lokalizacji](enrichment-here.md) dostarczane przez HERE Technologies 

# <a name="business-accounts-b-to-b"></a>[Klienci biznesowi (B2B)](#tab/b2b)

- [Dane firmy](enrichment-leadspace.md) zapewniane przez Leadspace
- [Ulepszone adresy](enrichment-enhanced-addresses.md) od Microsoft 
- [Rozszerzone dane firmy](enrichment-enhanced-company-data.md) dostarczane przez Microsoft
- [Dane lokalizacji](enrichment-here.md) dostarczane przez HERE Technologies 
- [Dane niestandardowe](enrichment-SFTP-custom-import.md) za pomocą protokołu SFTP (Secure File Transfer Protocol) 
- [Azure Maps](enrichment-azure-maps.md) oferowane przez Microsoft
- [Dane dotyczące zaangażowania konta](enrichment-office.md) dostarczone przez Microsoft

---

Na karcie **Moje wzbogacenia** użytkownik może zobaczyć skonfigurowane przez siebie wzbogacenia i edytować ich właściwości.

## <a name="manage-existing-enrichments"></a>Zarządzanie istniejącymi wzbogaceniami

Przejdź do karty **Moje wzbogacenia**, aby zobaczyć wszystkie skonfigurowane wzbogacania. Każde wzbogacenie jest reprezentowane jako wiersz zawierający dodatkowe informacje na temat wzbogacenia.

Wybierz wzbogacenie, aby wyświetlić dostępne opcje. Aby wyświetlić opcje, wybierz wielokropek (...) na elemencie listy. Jeśli skonfigurowano kilka wzbogaceń, można użyć pola wyszukiwania, aby szybko je znaleźć.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcje służące do zarządzania wzbogaceniami na liście wzbogaceń.":::

- **Wyświetl** szczegóły wzbogacenia dzięki liczbie ulepszonych profilów klientów.
- **Edytuj** konfigurację wzbogacenia.
- **Uruchom** wzbogacenie, aby zaktualizować profile klientów za pomocą najnowszych danych.
- **Dezaktywuj** istniejące wzbogacenie, aby zapobiec jego automatycznemu odświeżaniu przy każdym planowanym odświeżeniu. Dane ostatniego pomyślnego odświeżenia będą nadal dostępne. **Uaktywnij** nieaktywne wzbogacanie, aby ponownie uruchomić odświeżanie automatyczne przy każdym planowanym odświeżeniu.
- **Usuń** wzbogacenie.

Uruchom lub dezaktywuj wiele wzbogaceń jednocześnie, zaznaczając je na liście. Opcje wyświetlania i edycji nie są dostępne jako akcja zbiorcza. Działają tylko dla jednego wzbogacenia naraz.

## <a name="enrichments-and-connections"></a>Wzbogacenia i połączenia

Wzbogacenia innych firm konfiguruje się przy użyciu [połączeń](connections.md), które administrator konfiguruje się z poświadczeniami i wyraża zgodę na przesyłanie danych. Połączenia mogą być używane przez administratorów i współautorów do konfigurowania wzbogaceń.  

## <a name="multiple-enrichments-of-the-same-type"></a>Wiele wzbogaceń tego samego typu

Podczas konfigurowania wzbogacania jest określana encja do wzbogacenia, która umożliwia wzbogacenie tylko podzestawu profilów. Na przykład wzbogać dane tylko dla określonego segmentu. Można skonfigurować wiele wzbogaceń tego samego typu i ponownie używać tego samego połączenia. Niektóre wzbogacenia będą mieć ograniczoną liczbę wzbogaceń tego samego typu, które można utworzyć. Ograniczenia i bieżące użycie są widoczne na stronie **Wzbogacanie**.

## <a name="see-the-progress-of-the-enrichment-process"></a>Wyświetlanie postępu procesu wzbogacania

Można tu znaleźć szczegółowe informacje o przetwarzaniu wzbogacania, w tym informacje o stanie i potencjalnych problemach podczas odświeżania lub po zakończeniu odświeżania. Zidentyfikuj procesy związane z odświeżaniem wzbogacania i dowiedz się, ile trwa ich działanie. Stan wzbogacenia jest obsługiwany w przypadku usług Experian, Leadspace, HERE Technologies, SFTP Import i Azure Maps.

Aby wyświetlić stan wzbogacania

1. Przejdź do **Dane** > **Wzbogacanie**. 
1. Na karcie **Moje wzbogacenia** wybierz stan wzbogacania, aby otworzyć okienko boczne. 
1. W okienku **szczegółów postępu** rozwiń sekcję **Wzbogacanie**. 
1. W obszarze wzbogacania, dla którego chcesz wyświetlić postęp, wybierz opcję **Zobacz szczegóły**. 
1. W okienku **szczegółów zadania** wybierz opcję **Pokaż szczegóły**, aby wyświetlić procesy związane z aktualizowaniem wzbogacenia i jego stanu. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
