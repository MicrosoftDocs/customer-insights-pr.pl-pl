---
title: Wzbogać ujednolicone profile klientów
description: Korzystanie z funkcji w celu wzbogacenia danych klienta.
ms.date: 07/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: a64bbd754d4013d0a6243074ac9f55991547be82b269047a9937b583baf98697
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032541"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Wzbogacenie profilów klientów (wersja zapoznawcza)

Aby wzbogacić dane klientów, należy użyć danych pochodzących ze źródeł, takich jak Microsoft i inni partnerzy.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Strona centrum wzbogacania.":::

W statystykach odbiorców przejdź do **Dane** > **Wzbogacenie**, aby pracować z opcjami wzbogacania.  

Aby tworzyć lub edytować wzbogacenia, trzeba mieć uprawnienia Współautor lub Administrator. Aby uzyskać więcej informacji, zobacz [Uprawnienia](permissions.md).

Na karcie **Odkryj** znajdziesz następujące wzbogacenia:

- [Marki](enrichment-microsoft.md) dostarczone przez Microsoft
- [Zainteresowania](enrichment-microsoft.md) dostarczone przez Microsoft
- [Ulepszone adresy](enrichment-enhanced-addresses.md) od Microsoft
- [Dane firmy](enrichment-leadspace.md) zapewniane przez Leadspace
- [Dane demograficzne](enrichment-experian.md) dostarczane przez usługę Experian
- [Dane lokalizacji](enrichment-here.md) dostarczane przez HERE Technologies
- [Dane niestandardowe](enrichment-SFTP-custom-import.md) za pomocą protokołu SFTP (Secure File Transfer Protocol)

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

Wzbogacenia innych firm konfiguruje się przy użyciu [połączeń](connections.md), które administrator konfiguruje się z poświadczeniami i wyraża zgodę na przesyłanie danych. Połączenie może być następnie używane do konfiguracji wzbogaceń przez administratorów i współautorów.  

## <a name="multiple-enrichments-of-the-same-type"></a>Wiele wzbogaceń tego samego typu

Podczas konfigurowania wzbogacania jest określana encja do wzbogacenia, która umożliwia wzbogacenie tylko podzestawu profilów. Na przykład wzbogać dane tylko dla określonego segmentu. Można skonfigurować wiele wzbogaceń tego samego typu i ponownie używać tego samego połączenia. Niektóre wzbogacenia będą mieć ograniczoną liczbę wzbogaceń tego samego typu, które można utworzyć. Ograniczenia i bieżące użycie są widoczne na stronie **Wzbogacanie**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
