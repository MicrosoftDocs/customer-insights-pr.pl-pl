---
title: Zarządzanie obszarami roboczymi i środowiskami
description: Tworzenie, zmienianie nazw obszarów roboczych i środowisk oraz ich usuwanie.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: ded9e98f06109b7cdc27f449455b7f58d633722f
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350650"
---
# <a name="manage-environments-and-workspaces"></a>Zarządzaj środowiskami i obszarami roboczymi

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Omówienie

W tym temacie opisano sposób zarządzania obszarami roboczymi i środowiskami po ich utworzeniu. 

- *Obszar roboczy* to miejsce do przechowywania zdarzeń i raportów oraz zarządzania nimi. W tym miejscu można wyświetlać działania użytkownika w czasie rzeczywistym. Podczas tworzenia obszaru roboczego wybierasz typ danych przesyłanych do obszaru. Obecnie są obsługiwane dane sieci Web i aplikacje mobilne. Aby uzyskać więcej informacji, zobacz temat [Tworzenie nowego obszaru roboczego i dodawanie członków](create-workspace.md).

- *Środowisko* to miejsce służące do zarządzania obszarami roboczymi i połączeniami. Aby uzyskać więcej informacji, zobacz temat [Tworzenie nowego środowiska](create-new-environment.md).

## <a name="manage-an-existing-workspace"></a>Zarządzanie istniejącym obszarem roboczym

Jednocześnie w środowisku można utrzymywać wiele obszarów roboczych. Twoja [rola](user-roles.md) określa sposób pracy w nich. 

 - Aby zarządzać obszarem, trzeba mieć uprawnienia administratora środowiska lub administratora obszaru roboczego.
 - Jako administrator obszaru roboczego możesz zmienić nazwy istniejących obszarów roboczych lub je usunąć. 

:::image type="content" source="media/workspace-edit.png" alt-text="Centrum administracyjne obszaru roboczego.":::

### <a name="edit-a-workspace-name"></a>Edytowanie nazwy obszaru roboczego

1. Przejdź do **Administrowania** > **Obszar roboczy** i wybierz **Ustawienia**.

1. Wprowadź nazwę nowego obszaru roboczego w polu **Nazwa obszaru roboczego**.

1. Wybierz pozycję **Zapisz**, aby zastosować zmiany.

### <a name="delete-a-workspace"></a>Usuwanie obszaru roboczego

Usunięcie obszaru roboczego powoduje trwałe usunięcie całej jego zawartości, danych, ustawień i uprawnień. Tej akcji nie można cofnąć.

1. Przejdź do **Administrowania** > **Obszar roboczy** i wybierz **Ustawienia**.

1. Wybierz **Usuń obszar roboczy**. 

1. W sesji dialogowej **Usuwanie obszaru roboczego** wprowadź **POTWIERDŹ USUNIĘCIE** (same wielkie litery). 

1. Wprowadź polecenie **Usuń**, aby trwale usunąć obszar roboczy.

### <a name="manage-workspace-members"></a>Zarządzanie członkami obszaru roboczego

1. Przejdź do **Administrowania** > **Obszar roboczy** i wybierz **Członkowie**.

1. Wybierz opcję **Dodaj członków**, aby nadać dostęp i [przypisać role](user-roles.md). Obecnie jedyny dostępny wybór to **Administrator obszaru roboczego**.

1. Wybierz opcję **Dodaj członków**, aby dodać ich do obszaru roboczego.

## <a name="manage-an-existing-environment"></a>Zarządzanie istniejącym środowiskiem

Administrator środowiska może uzyskać dostęp do środowiska z lewego okienka nawigacji. Możesz skonfigurować ustawienia środowiska, innych administratorów środowiska oraz obszary robocze. Wybierz karty, aby przechodzić między różnymi obszarami centrum administracyjnego.

:::image type="content" source="media/environment-edit.png" alt-text="Centrum administracyjne środowiska.":::

### <a name="edit-an-environment-name"></a>Edytowanie nazwy środowiska

1. Przejdź do **Administrowania** > **Środowisko** i wybierz **Ustawienia**.

1. Wybierz **Nazwa środowiska**, wprowadź zmiany i wybierz **Zapisz**.

### <a name="delete-an-environment"></a>Usuwanie środowiska

Administratorzy środowiska mogą usuwać środowiska. Aby można było usunąć środowisko, należy usunąć wszystkie należące do niego obszary robocze.

1. Przejdź do **Administrowania** > **Środowisko** i wybierz **Ustawienia**.

1. Wybierz **Usuń środowisko**. 

1. W sesji dialogowej **Usuwanie obszaru roboczego** wprowadź **POTWIERDŹ USUNIĘCIE** (same wielkie litery). 

1. Wybierz **Usuń**, aby trwale usunąć środowisko.

### <a name="manage-environment-members"></a>Zarządzanie członkami środowiska

1. Przejdź do **Administrowania** > **Środowisko** i wybierz **Członkowie**.

1. Wybierz opcję **Dodaj członków**, aby zaktualizować członków i [przypisać role](user-roles.md). Obecnie jedyny dostępny wybór to **Administrator środowiska**.

1. Wybierz opcję **Dodaj członków**, aby dodać ich do środowiska.

## <a name="manage-connections"></a>Zarządzaj połączeniami

Tworzenie połączeń z analizą odbiorców umożliwia wyświetlanie raportów z wglądu w zaangażowanie na podstawie ujednoliconych profili klientów. 

Aby uzyskać informacji, zobacz [Utwórz łącze między wynikami analiz odbiorców i wynikami analiz interakcji](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Zarządzanie danymi osobowymi

W celu ochrony danych osobowych klienta można usunąć lub wyeksportować dane umożliwiające identyfikację użytkownika końcowego.

Dowiedz się jak [Usuwać i eksportować dane zdarzeń zawierających dane osobowe](../dsr-rights-requests.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
