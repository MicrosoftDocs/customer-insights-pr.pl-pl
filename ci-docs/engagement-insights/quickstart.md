---
title: Szybki start — wprowadzenie do produktu
description: Pierwsze kroki w celu skonfigurowania funkcji obsługi analizy interakcji.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 11/05/2020
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6690b016be4ad26faa797e5f87aba60caa48ddff
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232983"
---
# <a name="first-run-experience"></a>Pierwsze uruchomienie

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Obsługa analizy interakcji w Dynamics 365 Customer Insights umożliwia zbieranie i analizę zachowań klientów w witrynie sieci Web. W tym artykule wyjaśniono sposób rozpoczęcia pracy z analizą interakcji, konfigurowanie obszaru roboczego, dodawanie do niego członków i wprowadzanie zmian.

## <a name="sign-up-for-a-demo-of-engagement-insights"></a>Rejestracja w celu skorzystania z wersji zapoznawczej analizy interakcji

Najpierw należy mieć aktywne konto użytkownika Microsoft Azure Active Directory. 

1. Otwórz [witrynę sieci Web analizy interakcji](https://home.ci.ai.dynamics.com/app/engagement-insights). 

1. Zaloguj się za pomocą konta służbowego lub szkolnego.

1. Wybierz region i za pomocą pola wyboru wybierz, czy chcesz otrzymywać aktualizacje i oferty pocztą e-mail.

1. Przejrzyj **warunki użytkowania funkcji analizy interakcji (wersja zapoznawcza)** i **zasady ochrony prywatności** i wybierz **Zapoznaj się z wersją demonstracyjną**, aby je zaakceptować.

1. Poznaj produkt przy użyciu zestawu danych przykładowych. 

## <a name="set-up-your-first-workspace-in-engagement-insights"></a>Konfigurowanie pierwszego obszaru roboczego w aplikacji do analizy interakcji

Obszar roboczy to miejsce do przechowywania zdarzeń i raportów oraz zarządzania nimi.

Aby utworzyć pierwszy obszar roboczy

1. W funkcji analizy interakcji wybierz pozycję **Połącz dane**, aby uruchomić kreatora. 

:::image type="content" source="media/banner.png" alt-text="Strona Customer Insights z przyciskiem połącz dane.":::

2. Wybierz rodzaj aktywności, którą chcesz zmierzyć w nowym obszarze roboczym. Obecnie jest dostępne tylko **działanie w witrynie sieci Web**. **Działania w aplikacji** i **działania na urządzeniach** staną się dostępne w przyszłych wersjach.

1. Wybierz opcję **Dalej**, aby potwierdzić i utworzyć obszar roboczy.

1. Dodaj fragment kodu do witryny sieci Web, aby rozpocząć otrzymywanie danych z funkcji analizy interakcji Kod można wdrożyć od razu lub udostępnić kod oraz instrukcje administratorowi witryny. Aby znaleźć później fragment kodu, przejdź do **Administrowanie** > **Obszar roboczy** > **Przewodnik instalacji**.

   > [!IMPORTANT]
   > Dane nie będą wyświetlane w obszarze roboczym, dopóki kod nie zostanie zaimplementowany w witrynie sieci Web.

1. Wybierz opcję **Gotowe**, aby otworzyć nowy obszar roboczy. 

## <a name="add-members-to-an-existing-workspace"></a>Dodawanie członków do istniejącego obszaru roboczego

Domyślnie dostęp do niego ma tylko osoba, która utworzyła obszar roboczy. W każdej chwili możesz dodać innych użytkowników z organizacji do istniejącego obszaru roboczego.

:::image type="content" source="media/add-members.png" alt-text="Strona Członkowie z wyróżnieniem na przycisku Dodaj członków.":::

1. Przejdź do **Administrowanie** > **Obszar roboczy** > **Członkowie**.

2. Wybierz opcję **Dodaj członków**. W polu **Członkowie** można dodać inne osoby w organizacji. Można dodać wielu członków jednocześnie.

3. Wybierz **Rolę**, która ma zostać przypisana do nowych członków. Obecnie jedyny dostępny wybór to **Administrator obszaru roboczego**. W kolejnych wersjach zostaną dodane inne role.

4. Wybierz opcję **Dodaj członków**, aby potwierdzić.

Aby usunąć członków z obszaru roboczego, wybierz opcję **...** obok imion na stronie **Członkowie**, a następnie z menu rozwijanego wybierz polecenie **Usuń**.

## <a name="edit-a-workspace"></a>Edytowanie obszaru roboczego

W dowolnym momencie można edytować szczegóły istniejących obszarów roboczych.

:::image type="content" source="media/change-workspace-settings.png" alt-text="Strona Ustawienia obszaru roboczego z objaśnieniami nazwy i opisu obszaru roboczego.":::

1. Wybierz kolejno pozycje **Administracja** > **Obszar roboczy** > **Ustawienia**.

1. Zmienianie **Nazwy** obszaru roboczego.

1. Wybierz pozycję **Zapisz**, aby zastosować zmiany.

## <a name="add-another-new-workspace"></a>Dodawanie kolejnego obszaru roboczego

:::image type="content" source="media/workspace-switcher.png" alt-text="Strona Customer Insights z objaśnieniami w okienku nawigacji i opisem.":::

W celu sklasyfikowania danych można utworzyć dodatkowe obszary robocze.

1. W selektorze obszaru roboczego wybierz opcję **Nowy obszar roboczy**.

1. Wprowadź **nazwę** i opcjonalny **opis**.

1. Wybierz pozycję **Utwórz**.

## <a name="switch-between-workspaces"></a>Przełączanie między obszarami roboczymi

Aby przełączać się między obszarami roboczymi, wybierz przełącznik obszaru roboczego. Można również utworzyć nowy obszar roboczy lub wybrać **próbkę sieci Web** w celu zobaczenia raportów i wypróbowania funkcji przy użyciu przykładowych danych. 



[!INCLUDE[footer-include](../includes/footer-banner.md)]