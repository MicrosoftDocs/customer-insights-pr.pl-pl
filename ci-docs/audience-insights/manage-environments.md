---
title: Utwórz środowisko i zarządzaj nim.
description: 'Dowiedz się, jak zapisać się w usłudze i zarządzać środowiskami.'
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
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

Aby używać [gotowych modeli przewidywania](predictions-overview.md#out-of-box-models), skonfiguruj udostępnianie danych w funkcji Dataverse. Można też włączyć pozyskiwanie danych z lokalnych źródeł danych, udostępniając adres URL środowiska funkcji Microsoft Dataverse, którym administruje Twoja organizacja. Wybierz opcję **Włącz udostępnianie danych**, aby udostępnić dane wyjściowe usługi Customer Insights danym data lake zarządzanym przez usługę Dataverse.

> [!IMPORTANT]
> Customer Insights i Dataverse muszą znajdować się w tym samym regionie, aby umożliwić wymianę danych.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Opcje konfiguracji umożliwiające udostępnianie danych funkcji Microsoft Dataverse.":::

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

## <a name="reset-an-existing-environment"></a>Zresetuj istniejące środowisko

Jako administrator jeśli chcesz usunąć wszystkie konfiguracje i przetworzone dane, możesz zresetować środowisko do stanu pustego.

1.  Wybierz selektor **Środowiska** w nagłówku aplikacji. 

2.  Wybierz środowisko, które chcesz zresetować, i wybierz wielokropek (**...**). 

3. Wybierz opcję **Reset**. 

4.  Aby potwierdzić usunięcie, wprowadź nazwę środowiska i wybierz pozycję **Zresetuj**.

## <a name="delete-an-existing-environment"></a>Usuń istniejące środowisko

Jako Administrator użytkownik możesz usunąć administrowane środowisko.

1.  Wybierz selektor **Środowiska** w nagłówku aplikacji.

2.  Wybierz środowisko, które chcesz zresetować, i wybierz wielokropek (**...**). 

3. Wybierz opcję **Usuń**. 

4.  Aby potwierdzić usunięcie, wprowadź nazwę środowiska i wybierz **Usuń**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
