---
title: Zarządzanie obszarami roboczymi i środowiskami
description: Tworzenie, zmienianie nazw obszarów roboczych i środowisk oraz ich usuwanie.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 09/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: a5b48db5ae23ea65bf608d67348d493bfdc7678f
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486048"
---
# <a name="manage-environments-and-workspaces"></a>Zarządzaj środowiskami i obszarami roboczymi

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Omówienie

Obszar roboczy to miejsce do przechowywania zdarzeń i raportów oraz zarządzania nimi. W tym miejscu można wyświetlać działania użytkownika w czasie rzeczywistym. Podczas tworzenia obszaru roboczego wybierasz typ danych przesyłanych do obszaru. Obecnie są obsługiwane dane sieci Web i aplikacje mobilne.

Środowisko to miejsce służące do zarządzania obszarami roboczymi i połączeniami. Sposób korzystania z środowisk zależy od organizacji i danej sprawy użycia. Można na przykład utworzyć:

-   Jedno środowisko.
-   Oddzielne środowiska testowe i produkcyjne.
-   Oddzielne środowiska dla określonych zespołów lub działów w organizacji, które zawierają odpowiednie zdarzenia dla poszczególnych odbiorców.
-   Oddzielne środowiska dla różnych oddziałów firmy na świecie.
-   Połączenia z usługą Customer Insights — analiza odbiorców.

## <a name="choose-an-environment-and-create-a-workspace"></a>Wybieranie środowiska i tworzenie obszaru roboczego 

Każdy obszar roboczy musi być w środowisku. Podczas tworzenia obszaru roboczego można wybrać wstępnie istniejące środowisko lub utworzyć nowe. Następnie można dodać członków obszaru roboczego i rozpocząć zbieranie danych.

**Aby utworzyć pierwszy obszar roboczy**

1. W analizie interakcji wybierz pozycję **Nowy** z przełącznika obszaru roboczego. 

   :::image type="content" source="media/New-workspace.png" alt-text="Wybieranie strony w Customer Insights.":::

1. Wybierz środowisko z listy lub wybierz opcję **Utwórz nowe środowisko**.

1. Wprowadź **Nazwę obszaru roboczego**. 

1. Wybierz rodzaj środowiska, które chcesz stworzyć, w zależności od tego, czy chcesz mierzyć to, co dzieje się na stronie internetowej czy w aplikacji mobilnej. 

1. Członków i ich poziom uprawnień można dodać na liście **Rola**. Następnie wybierz opcję **Zakończ**, aby utworzyć obszar roboczy lub **Dalej**, aby zainstalować kod. 

1. Zainstaluj fragment kodu, aby rozpocząć odbieranie danych, a następnie wybierz opcję **Gotowe**. 

## <a name="manage-a-workspace"></a>Zarządzanie obszarem roboczym

Jednocześnie w środowisku można utrzymywać wiele obszarów roboczych. Twoja [rola](user-roles.md) określa sposób pracy w nich. 

 - Aby zarządzać obszarem, trzeba mieć uprawnienia administratora środowiska lub administratora obszaru roboczego.
 - Jako administrator obszaru roboczego możesz zmienić nazwy istniejących obszarów roboczych lub je usunąć. 

### <a name="edit-a-workspace-name"></a>Edytowanie nazwy obszaru roboczego

1. Przejdź do **Administrowania** > **Obszar roboczy** i wybierz **Ustawienia**.

1. Wprowadź nazwę nowego obszaru roboczego w polu **Nazwa obszaru roboczego**.

1. Wybierz pozycję **Zapisz**, aby zastosować zmiany.

### <a name="delete-a-workspace"></a>Usuwanie obszaru roboczego

Usunięcie obszaru roboczego spowoduje trwałe usunięcie całej jego zawartości, danych, ustawień i uprawnień. Tej akcji nie można cofnąć.

1. Przejdź do **Administrowania** > **Obszar roboczy** i wybierz **Ustawienia**.

1. Wybierz **Usuń obszar roboczy**. 

1. Wprowadź polecenie **POTWIERDŹ USUNIĘCIE**, w polu **Usuń obszar roboczy**. 

1. Wprowadź polecenie **Usuń**, aby trwale usunąć obszar roboczy.

### <a name="manage-workspace-members"></a>Zarządzanie członkami obszaru roboczego

1. Przejdź do **Administrowania** > **Obszar roboczy** i wybierz **Członkowie**.

1. Wybierz opcję **Dodaj członków**, aby nadać dostęp i [przypisać role](user-roles.md). Obecnie jedyny dostępny wybór to **Administrator obszaru roboczego**.

1. Wybierz opcję **Dodaj członków**, aby dodać ich do obszaru roboczego.

## <a name="manage-an-environment"></a>Zarządzaj środowiskiem

Administrator środowiska może uzyskać dostęp do środowiska z lewego okienka nawigacji. Możesz skonfigurować ustawienia środowiska, innych administratorów środowiska oraz obszary robocze. Wybierz karty, aby przechodzić między różnymi obszarami centrum administracyjnego.

:::image type="content" source="media/New-environment.png" alt-text="Centrum administracyjne środowiska.":::

### <a name="create-an-environment"></a>Utwórz środowisko

1. W wyborze obszaru roboczego wybierz **_Nowy**.

1. W środowisku z przewodnikiem otwórz menu rozwijane **Środowisko**, a następnie wybierz **Utwórz nowe środowisko**. 

1. Podaj **Nazwę środowiska**.

   :::image type="content" source="media/create-environment.png" alt-text="W środowisku z przewodnikiem określ szczegóły środowiska.":::

1. Wybierz **Region** i wybierz **Dalej**. 

1. Podaj nazwę obszaru roboczego i wybierz, który typ obszaru roboczego chcesz utworzyć. 

1.  Opcjonalnie dodaj członków i skopiuj wstawkę kodu, by zakończyć proces tworzenia.

### <a name="rename-an-environment"></a>Zmiana nazwy środowiska

1. Przejdź do **Administrowania** > **Środowisko** i wybierz **Ustawienia**.

1. Wybierz **Nazwa środowiska**, wprowadź zmiany i wybierz **Zapisz**.

### <a name="manage-environment-members"></a>Zarządzanie członkami środowiska

1. Przejdź do **Administrowania** > **Środowisko** i wybierz **Członkowie**.

1. Wybierz opcję **Dodaj członków**, aby zaktualizować członków i [przypisać role](user-roles.md). Obecnie jedyny dostępny wybór to **Administrator środowiska**.

1. Wybierz opcję **Dodaj członków**, aby dodać ich do środowiska.

### <a name="delete-an-environment"></a>Usuwanie środowiska

Administratorzy środowiska mogą usuwać środowiska. Aby można było usunąć środowisko, należy usunąć wszystkie należące do niego obszary robocze.

1. Przejdź do **Administrowania** > **Środowisko** i wybierz **Ustawienia**.

1. Wybierz **Usuń środowisko**. 

1. Wprowadź polecenie **POTWIERDŹ USUNIĘCIE**, w polu **Usuń obszar roboczy**. 

1. Wybierz **Usuń**, aby trwale usunąć środowisko.

## <a name="manage-connections"></a>Zarządzaj połączeniami

Tworzenie połączeń z analizą odbiorców umożliwia wyświetlanie raportów z wglądu w zaangażowanie na podstawie ujednoliconych profili klientów. 

Aby uzyskać informacji, zobacz [Utwórz łącze między wynikami analiz odbiorców i wynikami analiz interakcji](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Zarządzanie danymi osobowymi

W celu ochrony danych osobowych klienta można usunąć lub wyeksportować dane umożliwiające identyfikację użytkownika końcowego.

Dowiedz się jak [Usuwać i eksportować dane zdarzeń zawierających dane osobowe](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
