---
title: Zarządzaj środowiskami
description: Dowiedz się, jak zarządzać istniejącymi środowiskami usługi Customer Insights jako administrator.
ms.date: 08/15/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 8b4a88bdb75c6e638a76c39d18647681ad4556d7
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304302"
---
# <a name="manage-environments"></a>Zarządzaj środowiskami

Administratorzy [tworzą](create-environment.md) i zarządzają środowiskami. Mogą one zmienić niektóre ustawienia w istniejących środowiskach. Po utworzeniu środowiska opcje biznesowe, wpisz, region, magazyn i ustawienia Dataverse zostaną rozwiązane. Aby zmienić te ustawienia, należy [zresetować środowisko](#reset-an-existing-environment-preview) lub [utworzyć nowe środowisko](create-environment.md).

## <a name="edit-an-existing-environment"></a>Edytuj istniejące środowisko

Edytowanie szczegółów istniejącego środowiska, takich jak nazwa lub ustawienie środowiska domyślnego.

1. Wybierz selektor **Środowiska** w nagłówku aplikacji.

1. Wybierz ikonę **Edytuj**.

   :::image type="content" source="media/edit-environment.png" alt-text="Ikona do edycji ustawień środowiska.":::

1. W polu **Edytuj środowisko** można zaktualizować ustawienia środowiska.

1. Wybierz **Przeglądaj i zakończ**, a następnie **Uaktualnij**, aby zastosować zmiany.

## <a name="change-the-owner-of-an-environment"></a>Zmień właściciela środowiska

Kilku użytkowników może mieć uprawnienia administratora, ale tylko jeden użytkownik jest właścicielem środowiska. Domyślnie to administrator tworzy środowisko na początku. Jako administrator środowiska możesz przydzielić prawo własności innemu użytkownikowi z uprawnieniami administratora.

1. Wybierz selektor **Środowiska** w nagłówku aplikacji.

1. Wybierz ikonę **Edytuj**.

1. W polu **Edytowanie środowiska** przejdź do kroku **Podstawowe informacje**.

1. W polu **Zmień właściciela środowiska** wybierz nowego właściciela środowiska.  

1. Wybierz **Przeglądaj i zakończ**, a następnie **Uaktualnij**, aby zastosować zmiany.

## <a name="claim-ownership-of-an-environment"></a>Zastrzeż sobie prawo do własności środowiska

Jeśli konto użytkownika właściciela zostanie usunięte lub zawieszone, środowisko nie będzie mieć właściciela. Każdy administrator może zgłosić prawo własności i zostać nowym właścicielem. Administrator-właściciel może nadal być właścicielem środowiska lub [zmienić właściciela na innego administratora](#change-the-owner-of-an-environment).

Aby zastrzec sobie prawo własności, wybierz **Przejmij własność**, który pojawia się na górze każdej strony w Customer Insights, gdy pierwotny właściciel opuścił organizację.

## <a name="reset-an-existing-environment-preview"></a>Zresetuj istniejące środowisko (wersja zapoznawcza)

Jako właściciel środowiska możesz zresetować środowisko do stanu pustego, jeśli chcesz usunąć wszystkie konfiguracje i usunąć wprowadzone dane.

1. Wybierz selektor **Środowiska** w nagłówku aplikacji.

1. Wybierz środowisko, które chcesz zresetować i wybierz pionową wielokropek (&vellip;).

1. Wybierz opcję **Zresetuj (wersja zapoznawcza)**.

   :::image type="content" source="media/reset-environment.png" alt-text="Kontrolka resetowania środowiska.":::

1. Wybierz, czy chcesz zresetować całe środowisko, wszystko poza źródłami danych, czy wszystko, co jest skonfigurowane w unified customer profile.

1. Aby potwierdzić, wpisz nazwę środowiska i wybierz **Resetuj**.

## <a name="delete-an-existing-environment"></a>Usuń istniejące środowisko

Można je usunąć jako właściciela środowiska.

> [!IMPORTANT]
> Usunięcie środowiska nie powoduje usunięcia połączenia ze środowiskiem Dataverse. Jeśli planujesz w przyszłości połączyć to samo środowisko Dataverse z nowym środowiskiem Customer Insights, musisz usunąć to połączenie dowiedz się, jak [usunąć istniejące połączenie ze środowiskiem Dataverse](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

1. Wybierz selektor **Środowiska** w nagłówku aplikacji.

1. Wybierz środowisko, które chcesz usunąć i wybierz pionową wielokropek (&vellip;). 

1. Wybierz pozycję **Usuń**.

   :::image type="content" source="media/delete-environment.png" alt-text="Kontrolka, aby usunąć środowisko.":::

1. Aby potwierdzić usunięcie, wprowadź nazwę środowiska i wybierz **Usuń**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
