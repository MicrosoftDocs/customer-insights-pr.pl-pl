---
title: Omówienie (podgląd) połączeń
description: Połączenia z innymi usługami z aplikacji Customer Insights.
ms.date: 08/04/2022
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 8580dc7d90c75f66f73efc15f8e38f5e10fbb8a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245524"
---
# <a name="connections-preview-overview"></a>Omówienie (podgląd) połączeń

Połączenia to klucz do włączenia udostępniania danych do i z funkcji Customer Insights. Każde połączenie ustanawia udostępnianie danych w określonej usłudze. Użyj połączeń do [skonfigurowania wzbogaceń innych firm](enrichment-hub.md) i [konfigurowania eksportów](export-destinations.md). To samo połączenie może być używane wiele razy. Na przykład jedno połączenie z usługą Dynamics 365 Marketing działa dla wielu eksportów, a jedno połączenie Leadspace może zostać użyte dla kilku wzbogaceń.

## <a name="export-connections"></a>Eksportuj połączenia

Tylko administratorzy mogą konfigurować nowe połączenia, ale mogą [udzielać współautorom dostęp](#allow-contributors-to-use-a-connection-for-exports) do korzystania z istniejących połączeń. Administratorzy określają, gdzie mogą się znaleźć dane, współautorzy definiują ładunek i częstotliwość określania ich potrzeb.

## <a name="enrichment-connections"></a>Połączenia ze wzbogaceniami

Tylko administratorzy mogą konfigurować nowe połączenia, ale utworzone połączenia są zawsze dostępne zarówno dla administratorów, jak i współautorów. Administratorzy zarządzają poświadczeniami i wyrażają zgodę na przenoszenie danych. Połączenia mogą być następnie używane do wzbogacania przez administratorów i współautorów.

## <a name="add-a-new-connection"></a>Dodaj nowe połączenie

### <a name="prerequisites"></a>Wymagania wstępne

- [Uprawnienia administratora](permissions.md)
- Inne usługi Microsoft, jeśli dostępne, znajdują się w tej samej organizacji

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz typ połączenia, które chcesz utworzyć. Lub przejdź do karty **Odkryj** i wybierz **Konfiguruj** na kafelku połączenia.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Wprowadź wymagane informacje. Dokładne pola zależą od tego, z jaką usługą się łączysz. Szczegółowe informacje o określonym typie połączenia można znaleźć w artykule dotyczących usługi docelowej.

1. Jeśli do przechowywania wpisów tajnych używasz [własnej usługi Key Vault](use-azure-key-vault.md), aktywuj opcję **Użyj usługi Key Vault** i wybierz odpowiedni wpis tajny z listy.

1. Przejrzyj prywatność danych i zgodność z przepisami i wybierz opcję **Wyrażam zgodę**.

1. Aby utworzyć połączenie, wybierz **Zapisz**.

### <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Po włączeniu usługi Dynamics 365 Customer Insights w celu przesyłania danych do stron trzecich lub innych produktów firmy Microsoft, zezwalasz na przesyłanie danych poza granice zgodności dla usługi Dynamics 365 Customer Insights, w tym potencjalnie poufnych danych, takich jak dane osobowe. Microsoft przekaże takie dane na Twoje polecenie, ale Ty jesteś odpowiedzialny za zapewnienie, że osoba trzecia wywiąże się z wszelkich zobowiązań dotyczących prywatności i bezpieczeństwa, które możesz mieć. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).

Administrator Dynamics 365 Customer Insights może w dowolnym momencie usunąć połączenie, aby przerwać korzystanie z funkcji.

## <a name="allow-contributors-to-use-a-connection-for-exports"></a>Zezwalaj współautorom na używanie połączenia do eksportowania

Podczas konfigurowania lub edytowania połączenia eksportowania należy wybrać użytkowników, którzy mogą korzystać z tego konkretnego połączenia w celu zdefiniowania [eksportów](export-destinations.md). Domyślnie połączenie jest dostępne dla użytkowników, którzy mają rolę administratora. Zmień ustawienie **Określ, kto może korzystać z tego połączenia**, by zezwolić użytkownikom z rolą współautora na korzystanie z tego połączenia.

- Współautorzy nie mogą wyświetlać ani edytować połączenia. Podczas tworzenia eksportu będą widzieć tylko nazwę wyświetlaną i jej typ.
- Udostępniając połączenie, można umożliwić współautorom korzystanie z połączenia. Współautorzy będą widzieć udostępnione połączenia podczas skonfigurowania eksportu. Mogą zarządzać każdym eksportem, który korzysta z tego określonego połączenia.
- To ustawienie można zmienić, zachowując przy tym eksporty, które zostały już zdefiniowane przez współautorów.

## <a name="manage-existing-connections"></a>Zarządzanie istniejącymi połączeniami

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz kartę **Wzbogacenie** lub **Eksport**, aby wyświetlić listę połączeń wzbogacenia lub eksportu, typ połączenia, czas jego utworzenia i kto ma do niego dostęp. Listę połączeń można posortować według którejkolwiek kolumny.

1. Wybierz połączenie, aby wyświetlić dostępne akcje.

   - **Edytuj** połączenie.
   - [**Usuń**](#remove-a-connection) połączenie.

### <a name="remove-a-connection"></a>Usuwanie połączenia

Jeśli połączenie, które usuwasz, jest używane przez wzbogacenia lub eksporty, najpierw je odłącz lub usuń. Okno dialogowe usuwania przeprowadzi do odpowiedniego wzbogacenia lub eksportu.

> [!TIP]
> Wyłączone wzbogacenia i odłączone eksporty stają się nieaktywne. Można je ponownie aktywować, dodając do nich inne połączenie na stronie [Wzbogacenia](enrichment-hub.md) lub [Eksporty](export-destinations.md).

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz kartę **Wzbogacenie** lub **Eksporty**.

1. Wybierz połączenie do usunięcia.

1. Wybierz **Usuń** z menu rozwijanego. Pojawia się okno dialogowe potwierdzenia.

   1. Jeśli są dostępne wzbogacenia lub eksporty używające tego połączenia, wybierz przycisk, aby wyświetlić informacje o połączeniu.
      - **Eksporty:** wybierz opcję **Usuń** eksport lub **Odłącz połączenie**. Odłączenie połączenia spowoduje zachowanie konfiguracji eksportu, ale nie zostanie on uruchomiony, dopóki nie zostanie dodane do niego inne połączenie.
      - **Wzbogacanie:** wybierz opcję **Usuń** lub **Wyłącz** wzbogacanie.
   1. Gdy połączenie nie ma więcej zależności, wróć do opcji **Admin** > **Połączenia** i spróbuj ponownie usunąć połączenie.

1. Aby potwierdzić usunięcie, wybierz opcję **Usuń**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Konfigurowanie połączeń z wpisami tajnymi zarządzanymi przez własną usługę Key Vault

Niektóre połączenia wymagają wpisów tajnych, takich jak klucze interfejsu API lub hasła. Niektóre połączenia obsługują wpisy tajne przechowywane w własnej usłudze Key Vault. Dowiedz się więcej o obsługiwanych połączeniach i konfigurowaniu [własnej usługi Key Vault dla Customer Insights](use-azure-key-vault.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
