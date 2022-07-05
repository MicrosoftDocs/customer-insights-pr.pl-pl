---
title: 'Instrukcje: zarządzanie środowiskami'
description: Dowiedz się, jak zarządzać istniejącymi środowiskami usługi Customer Insights jako administrator.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: fc3b3f404cf0ac84c782778414494289c803babe
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081672"
---
# <a name="how-to-manage-environments"></a>Instrukcje: zarządzanie środowiskami

Administratorzy [tworzą](create-environment.md) i zarządzają środowiskami. Mogą one zmienić niektóre ustawienia w istniejących środowiskach. Po utworzeniu środowiska opcje biznesowe, wpisz, region, magazyn i ustawienia Dataverse zostaną rozwiązane. Aby zmienić te ustawienia, należy zresetować środowisko lub utworzyć nowe środowisko.

## <a name="edit-an-existing-environment"></a>Edytuj istniejące środowisko

Użytkownik może edytować niektóre szczegóły istniejących środowisk.

1. Wybierz selektor **Środowiska** w nagłówku aplikacji.

1. Wybierz ikonę **Edytuj**.

   :::image type="content" source="media/edit-environment.png" alt-text="Ikona do edycji ustawień środowiska.":::

1. W polu **Edytuj środowisko** można zaktualizować ustawienia środowiska.

Aby zacząć od świeżego środowiska, zobacz [Tworzenie nowego środowiska](create-environment.md).

## <a name="change-the-owner-of-an-environment"></a>Zmień właściciela środowiska

Kilku użytkowników może mieć uprawnienia administratora, ale tylko jeden użytkownik jest właścicielem środowiska. Domyślnie to administrator tworzy środowisko na początku. Jako administrator środowiska możesz przydzielić prawo własności innemu użytkownikowi z uprawnieniami administratora.

1. Wybierz selektor **Środowiska** w nagłówku aplikacji.

1. Wybierz ikonę **Edytuj**.

1. W polu **Edytowanie środowiska** przejdź do kroku **Podstawowe informacje**.

1. W polu **Zmień właściciela środowiska** wybierz nowego właściciela środowiska.  

1. Wybierz **Przeglądaj i zakończ**, a następnie **Uaktualnij**, aby zastosować zmiany.

## <a name="claim-ownership-of-an-environment"></a>Zastrzeż sobie prawo do własności środowiska

Jeśli konto użytkownika właściciela zostanie usunięte lub zawieszone, środowisko nie będzie mieć właściciela. Każdy administrator może zgłosić prawo własności i zostać nowym właścicielem. Mogą oni nadal być właścicielami środowiska lub [zmienić właściciela na innego administratora](#change-the-owner-of-an-environment).

Aby zastrzec sobie prawo własności, wybierz **Przejmij własność**, który pojawia się na górze każdej strony w Customer Insights, gdy pierwotny właściciel opuścił organizację.

## <a name="reset-an-existing-environment-preview"></a>Zresetuj istniejące środowisko (wersja zapoznawcza)

Jako właściciel środowiska możesz zresetować środowisko do stanu pustego, jeśli chcesz usunąć wszystkie konfiguracje i usunąć wprowadzone dane.

1. Wybierz selektor **Środowiska** w nagłówku aplikacji.

1. Wybierz środowisko, które chcesz zresetować i wybierz pionową wielokropek (&vellip;).

1. Wybierz opcję **Reset**.

   :::image type="content" source="media/reset-environment.png" alt-text="Kontrolka resetowania środowiska.":::

1. Wybierz, czy chcesz zresetować całe środowisko, wszystko poza źródłami danych, czy wszystko, co jest skonfigurowane w unified customer profile.

1. Aby potwierdzić, wpisz nazwę środowiska i wybierz **Resetuj**.

## <a name="delete-an-existing-environment"></a>Usuń istniejące środowisko

Jako właściciel środowiska możesz usunąć środowisko, którym administrujesz.

1. Wybierz selektor **Środowiska** w nagłówku aplikacji.

1. Wybierz środowisko, które chcesz zresetować i wybierz pionową wielokropek (&vellip;). 

1. Wybierz opcję **Usuń**.

   :::image type="content" source="media/delete-environment.png" alt-text="Kontrolka, aby usunąć środowisko.":::

1. Aby potwierdzić usunięcie, wprowadź nazwę środowiska i wybierz **Usuń**.

> [!IMPORTANT]
> Usunięcie środowiska nie powoduje usunięcia połączenia ze środowiskiem Dataverse. Jeśli planujesz w przyszłości połączyć to samo środowisko Dataverse z nowym środowiskiem Customer Insights, musisz usunąć to połączenie Dowiedz się, jak [usunąć istniejące połączenie ze środowiskiem Dataverse](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

[!INCLUDE [footer-include](includes/footer-banner.md)]
