---
title: Wzbogać ujednolicone profile klientów
description: Korzystanie z funkcji w celu wzbogacenia danych klienta.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c25cfbf3808fc1534b54d2d834f1c63ff4c9fe0a
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667107"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Wzbogacenie profilów klientów (wersja zapoznawcza)

Aby wzbogacić dane klientów, należy użyć danych pochodzących ze źródeł, takich jak Microsoft i inni partnerzy.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Strona centrum wzbogacania":::

W statystykach odbiorców przejdź do **Dane** > **Wzbogacenie**, aby pracować z opcjami wzbogacania.    
Aby tworzyć lub edytować wzbogacenia, trzeba mieć uprawnienia Współautor lub Administrator. Aby uzyskać więcej informacji, zobacz [Uprawnienia](permissions.md).

Na karcie **Odkryj** znajdziesz następujące wzbogacenia:

- [Marki](enrichment-microsoft-graph.md) są dostarczane przez Microsoft Graph
- [Zainteresowania](enrichment-microsoft-graph.md) są dostarczane przez Microsoft Graph
- [Dane firmy](enrichment-leadspace.md) zapewniane przez Leadspace
- [Dane demograficzne](enrichment-experian.md) zapewniane przez Experian
- [Dane lokalizacji](enrichment-here.md) dostarczane przez HERE Technologies
- [Dane niestandardowe](enrichment-SFTP-custom-import.md) za pomocą protokołu SFTP (Secure File Transfer Protocol)

Na karcie **Moje wzbogacenia** użytkownik może zobaczyć skonfigurowane przez siebie wzbogacenia i edytować ich właściwości.

## <a name="manage-existing-enrichments"></a>Zarządzanie istniejącymi wzbogaceniami

Przejdź do **Moje wzbogacenia**, aby wyświetlić wszystkie skonfigurowane wzbogacenia. Każde wzbogacenie jest reprezentowane jako wiersz zawierający dodatkowe informacje na temat wzbogacenia.

Wybierz wzbogacenie, aby wyświetlić dostępne opcje. Można też wybrać wielokropek (...) na elemencie listy, aby wyświetlić dostępne opcje.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcje służące do zarządzania wzbogaceniami na liście wzbogaceń":::

- **Wyświetl** szczegóły wzbogacenia dzięki liczbie ulepszonych profilów klientów.
- **Edytuj** konfigurację wzbogacenia.
- **Uruchom** wzbogacenie, aby zaktualizować profile klientów za pomocą najnowszych danych.
- **Dezaktywuj** istniejące wzbogacenie, aby zapobiec jego automatycznemu odświeżaniu przy każdym planowanym odświeżeniu. Dane ostatniego pomyślnego odświeżenia będą nadal dostępne. **Uaktywnij** nieaktywne wzbogacanie, aby ponownie uruchomić odświeżanie automatyczne przy każdym planowanym odświeżeniu.
- **Usuń** wzbogacenie.

Można uruchomić lub zdezaktywować wiele operacji wzbogacania naraz, wybierając je na liście. Opcje wyświetlania i edycji nie są dostępne jako działanie zbiorcze i w danej chwili działają tylko w jednym wzbogaceniu.
