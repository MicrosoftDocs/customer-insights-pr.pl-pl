---
title: Wzbogać ujednolicone profile klientów
description: Korzystanie z funkcji w celu wzbogacenia danych klienta.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896018"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Wzbogacenie profilów klientów (wersja zapoznawcza)

Aby wzbogacić dane klientów, należy użyć danych pochodzących ze źródeł, takich jak Microsoft i inni partnerzy.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Strona centrum wzbogacania":::

W statystykach odbiorców przejdź do **Dane** > **Wzbogacenie**, aby pracować z opcjami wzbogacania.    
Aby tworzyć lub edytować wzbogacenia, trzeba mieć uprawnienia Współautor lub Administrator. Aby uzyskać więcej informacji, zobacz [Uprawnienia](permissions.md).

Na karcie **Odkryj** znajdziesz następujące wzbogacenia:

- [Marki](enrichment-microsoft.md) dostarczone przez Microsoft
- [Zainteresowania](enrichment-microsoft.md) dostarczone przez Microsoft
- [Dane firmy](enrichment-leadspace.md) zapewniane przez Leadspace
- [Dane demograficzne](enrichment-experian.md) zapewniane przez Experian
- [Dane lokalizacji](enrichment-here.md) dostarczane przez HERE Technologies
- [Dane niestandardowe](enrichment-SFTP-custom-import.md) za pomocą protokołu SFTP (Secure File Transfer Protocol)

Na karcie **Moje wzbogacenia** użytkownik może zobaczyć skonfigurowane przez siebie wzbogacenia i edytować ich właściwości.

## <a name="manage-existing-enrichments"></a>Zarządzanie istniejącymi wzbogaceniami

Przejdź do **Moje wzbogacenia**, aby wyświetlić wszystkie skonfigurowane wzbogacenia. Każde wzbogacenie jest reprezentowane jako wiersz zawierający dodatkowe informacje na temat wzbogacenia.

Wybierz wzbogacenie, aby wyświetlić dostępne opcje. Aby wyświetlić opcje, wybierz wielokropek (...) na elemencie listy.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcje służące do zarządzania wzbogaceniami na liście wzbogaceń":::

- **Wyświetl** szczegóły wzbogacenia dzięki liczbie ulepszonych profilów klientów.
- **Edytuj** konfigurację wzbogacenia.
- **Uruchom** wzbogacenie, aby zaktualizować profile klientów za pomocą najnowszych danych.
- **Dezaktywuj** istniejące wzbogacenie, aby zapobiec jego automatycznemu odświeżaniu przy każdym planowanym odświeżeniu. Dane ostatniego pomyślnego odświeżenia będą nadal dostępne. **Uaktywnij** nieaktywne wzbogacanie, aby ponownie uruchomić odświeżanie automatyczne przy każdym planowanym odświeżeniu.
- **Usuń** wzbogacenie.

Można uruchomić lub zdezaktywować wiele operacji wzbogacania naraz, wybierając je na liście. Opcje wyświetlania i edycji nie są dostępne jako działanie zbiorcze i w danej chwili działają tylko w jednym wzbogaceniu.

## <a name="enrichments-and-connections"></a>Wzbogacenia i połączenia

Wzbogacenia innych firm konfiguruje się przy użyciu [połączeń](connections.md), które administrator konfiguruje się z poświadczeniami i wyraża zgodę na przesyłanie danych. Połączenie może być następnie używane do konfiguracji wzbogaceń przez administratorów i współautorów.  

## <a name="multiple-enrichments-of-the-same-type"></a>Wiele wzbogaceń tego samego typu

Podczas konfigurowania wzbogacania jest określana encja do wzbogacenia, która umożliwia wzbogacenie tylko podzestawu profilów. Na przykład wzbogacenie danych tylko dla określonego segmentu. Można skonfigurować wiele wzbogaceń tego samego typu i ponownie używać tego samego połączenia. Niektóre wzbogacenia będą mieć ograniczoną liczbę wzbogaceń tego samego typu, które można utworzyć. Ograniczenia i bieżące użycie są widoczne na stronie **Wzbogacanie**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
