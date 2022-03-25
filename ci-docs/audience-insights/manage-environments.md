---
title: Utwórz środowisko i zarządzaj nim.
description: Dowiedz się, jak zapisać się w usłudze i zarządzać środowiskami.
ms.date: 02/09/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 4f4e5a8415f6c2128b0480edf67f317124eeeba9
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376889"
---
# <a name="manage-environments"></a>Zarządzaj środowiskami

## <a name="switch-environments"></a>Przełącz środowiska

Wybierz kontrolkę **Środowiska** w prawym górnym rogu strony, aby zmienić środowiska.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Zrzut ekranu przedstawiający formant do przełączania środowisk.":::

Administratorzy mogą [tworzyć](create-environment.md) i zarządzać środowiskami.

## <a name="edit-an-existing-environment"></a>Edytuj istniejące środowisko

Użytkownik może edytować niektóre szczegóły istniejących środowisk.

1.  Wybierz selektor **Środowiska** w nagłówku aplikacji.

2.  Wybierz ikonę **Edytuj**.

3. W polu **Edytuj środowisko** można zaktualizować ustawienia środowiska.

Aby uzyskać więcej informacji o ustawieniach środowiska, zobacz temat [Tworzenie nowego środowiska](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Nawiązywanie połączenia z usługą Microsoft Dataverse
   
Krok **Microsoft Dataverse** umożliwia połączenie aplikacji Customer Insights ze środowiskiem Dataverse.

Aby używać [gotowych modeli przewidywania](predictions-overview.md#out-of-box-models), skonfiguruj udostępnianie danych w funkcji Dataverse. Można też włączyć pozyskiwanie danych z lokalnych źródeł danych, udostępniając adres URL środowiska funkcji Microsoft Dataverse, którym administruje Twoja organizacja.

> [!IMPORTANT]
> Customer Insights i Dataverse muszą znajdować się w tym samym regionie, aby umożliwić wymianę danych.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="Opcje konfiguracji umożliwiające udostępnianie danych funkcji Microsoft Dataverse.":::

> [!NOTE]
> Aplikacja Customer Insights nie obsługuje następujących scenariuszy udostępniania danych:
> - Po zapisaniu wszystkich danych we własnej usłudze Azure Data Lake Storage nie będzie można włączyć udostępniania danych danym data lake zarządzanym przez funkcję Dataverse.
> - W przypadku włączenia udostępniania usłudze Dataverse, nie będzie można [tworzyć przewidywanych lub brakujących wartości w encji](predictions.md).

## <a name="copy-the-environment-configuration"></a>Kopiowanie konfiguracji środowiska

Podczas tworzenia nowego środowiska można skopiować konfigurację z istniejącego środowiska. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Zrzut ekranu przedstawiający opcje ustawień w ustawieniach środowiska.":::

Zobaczysz listę wszystkich dostępnych środowisk w organizacji, z których można kopiować dane.

Kopiowane są następujące ustawienia konfiguracji:

- Importowanie/importowanie źródeł danych
- Konfiguracja ujednolicania danych (mapowanie, dopasowywanie, scalanie)
- Segmenty
- Miary
- Relacje
- Działania
- Wyszukiwanie i indeks filtrów
- Lokalizacje docelowe eksportu
- Zaplanowane odświeżanie
- Wzbogacenia
- Zarządzanie modelem
- Przypisania ról

Następujące dane *nie* są kopiowane:

- Profile klientów.
- Poświadczenia źródła danych. Konieczne będzie podanie poświadczeń dla każdego źródła danych i ręczne odświeżenie źródeł danych.

- Źródła danych z folderu Common Data Model i danych data lake zarządzanych przez Dataverse. Konieczne będzie ręczne utworzenie tych źródeł danych pod tą samą nazwą jak w środowisku źródłowym.

Podczas kopiowania środowiska zostanie wyświetlony komunikat z potwierdzeniem, że utworzono nowe środowisko. Wybierz **Przejdź do źródeł danych**, aby wyświetlić listę źródeł danych.

Wszystkie źródła danych ukażą stan **Wymagane poświadczenia**. Dokonaj edycji źródeł danych i wprowadź poświadczenia, aby je odświeżyć.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lista źródeł danych, które zostały skopiowane i wymagają uwierzytelniania.":::

Po odświeżeniu źródeł danych przejdź do **Dane** > **Ujednolicanie**. W tym miejscu można znaleźć ustawienia z poziomu środowiska źródłowego. Edytuj je zgodnie z wymaganiami lub wybierz **Uruchom**, aby rozpocząć proces ujednolicania danych i utworzyć zunifikowaną encję klienta.

Po zakończeniu ujednolicania danych należy przejść do **Miary** i **Segmenty**, aby je również odświeżyć.

## <a name="change-the-owner-of-an-environment"></a>Zmień właściciela środowiska

Podczas gdy kilku użytkowników może mieć uprawnienia administratora w Customer Insights, tylko jeden użytkownik jest właścicielem środowiska. Domyślnie to administrator tworzy środowisko na początku. Jako administrator środowiska możesz przydzielić prawo własności innemu użytkownikowi z uprawnieniami administratora.

1. Wybierz selektor **Środowiska** w nagłówku aplikacji.

1. Wybierz ikonę **Edytuj**.

1. W polu **Edytowanie środowiska** przejdź do kroku **Podstawowe informacje**.

1. W polu **Zmień właściciela środowiska** wybierz nowego właściciela środowiska.  

1. Wybierz **Przeglądaj i zakończ**, a następnie **Uaktualnij**, aby zastosować zmiany. 

## <a name="claim-ownership-of-an-environment"></a>Zastrzeż sobie prawo do własności środowiska

Jeśli właściciel środowiska opuści organizację lub jego konto użytkownika zostanie usunięte, środowisko nie będzie miało właściciela. Użytkownik z uprawnieniami administratora może odebrać prawo własności i stać się nowym właścicielem. Mogą oni nadal być właścicielami środowiska lub [zmienić właściciela na innego administratora](#change-the-owner-of-an-environment). 

Aby zastrzec sobie prawo własności, wybierz **Przejmij własność**, który pojawia się na górze każdej strony w Customer Insights, gdy pierwotny właściciel opuścił organizację.

## <a name="reset-an-existing-environment"></a>Zresetuj istniejące środowisko

Jako właściciel środowiska możesz zresetować środowisko do stanu pustego, jeśli chcesz usunąć wszystkie konfiguracje i usunąć wprowadzone dane.

1.  Wybierz selektor **Środowiska** w nagłówku aplikacji. 

2.  Wybierz środowisko, które chcesz zresetować, i wybierz wielokropek (**...**). 

3. Wybierz opcję **Reset**. 

4.  Aby potwierdzić usunięcie, wprowadź nazwę środowiska i wybierz pozycję **Zresetuj**.

## <a name="delete-an-existing-environment"></a>Usuń istniejące środowisko

Jako właściciel środowiska możesz usunąć środowisko, którym administrujesz.

1.  Wybierz selektor **Środowiska** w nagłówku aplikacji.

2.  Wybierz środowisko, które chcesz zresetować, i wybierz wielokropek (**...**). 

3. Wybierz opcję **Usuń**. 

4.  Aby potwierdzić usunięcie, wprowadź nazwę środowiska i wybierz **Usuń**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
