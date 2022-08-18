---
title: Przypisywanie uprawnień użytkowników
description: Dowiedz się o uprawnieniach i rolach użytkowników.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245432"
---
# <a name="assign-user-permissions"></a>Przypisywanie uprawnień użytkowników

Dostęp do danych Customer Insights jest ograniczony do użytkowników w organizacji, którzy są dodani do aplikacji przez administratora. Administrator może dodawać, edytować lub usuwać użytkowników. Użytkownik może być jednym użytkownikiem, grupą lub aplikacją. Istnieją trzy typy ról, które może mieć użytkownik:

## <a name="viewer"></a>Przeglądający

- Eksploruj informacje i segmenty na stronach **Strona główna** i **Segmenty**.
- Wyszukiwanie i filtrowanie profilów klientów przy użyciu strony **Klienci**. Pola muszą mieć możliwość przeszukiwania.
- Wyświetl stronę **Wzbogacanie** i zapoznaj się z nią.
- Przeglądaj i eksportuj encje za pomocą strony **Encje**.
- Wyświetl stan procesów systemowych przy użyciu strony **System**.
- Wyświetl eksporty na stronie **Eksporty**.
- Zainstaluj i skorzystaj z pulpitu nawigacyjnego **Power BI Customer Insights**.

## <a name="contributor"></a>Współautor

- Wszystkie uprawnienia dostępne dla Przeglądającego.
- Ładuj i przekształcaj dane przy użyciu strony **Źródła danych**.
- Zakończ **Ujednolicanie danych**, którego efektem jest ujednolicony profil klienta.
- Zdefiniuj **Relacje** i **Działania**.
- Utwórz segmenty, korzystając ze strony **Segmenty**.
- Utwórz miary za pomocą strony **Miary**.
- Zarządzaj konfiguracją i wzbogacaj profile klientów ze strony **Wzbogacanie** (dotyczy tylko wzbogaceń własnych).
- Zarządzanie i tworzenie eksportów na podstawie [połączeń udostępnionych współautorom](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Administrator

- Wszystkie uprawnienia dostępne dla Współautora.
- Zmień ustawienia na stronie **System**, w tym język roboczy, odśwież harmonogramy dla procesów systemowych i eksportowania dzienników diagnostycznych.
- Na stronie **Zabezpieczenia** zmień ustawienia, w tym użytkowników, klucze interfejsów API, łącza prywatne i magazyn kluczy key vault.
- Ustaw definicje Wyszukiwanie i Filtrowanie dla strony Klienci za pomocą strony **Wyszukiwanie i indeks filtrów** (dostępnej przez stronę **Klienci**).
- Zarządzaj połączeniami i zezwalaj innym rolom użytkownika na dostęp do nich na stronie **Połączenia**.
- Zarządzaj konfiguracją i wzbogacaj profile klientów ze strony **Wzbogacanie** (dotyczy wszystkich wzbogaceń).
- Zarządzanie i tworzenie eksportów ich na stronie **Eksporty**.
- Zainstaluj i użyj **Dodatek kart klientów**.
- Dodanie **łącznika Power Apps** i korzystanie z niego.
- Włącz korzystanie z [interfejsów API Customer Insights](apis.md).
- [Przypisz własność środowiska](manage-environments.md#change-the-owner-of-an-environment) innemu administratorowi.

## <a name="admin-owner"></a>Administrator (właściciel)

- Wszystkie uprawnienia administratora.
- [Zresetuj i usuń](manage-environments.md#reset-an-existing-environment-preview) środowisko.

## <a name="add-users"></a>Dodaj użytkowników

1. Przejdź do pozycji **Administracja** > **Zabezpieczenia** i wybierz kartę **Użytkownicy**.

1. Wybierz pozycję **Dodaj użytkowników**, aby otworzyć okienko **Dodawanie/Edytowanie uprawnień**.

1. Użyj pola **Wyszukaj**, aby znaleźć użytkownika lub grupę Azure Active Directory, które chcesz dodać. Wybierz **Rola**, aby przypisać ją do tego użytkownika lub grupy.

1. Wybierz pozycję **Zapisz**. Bieżące środowisko jest automatycznie udostępnione użytkownikowi lub członkom grupy. Użytkownicy mogą uzyskiwać dostęp do aplikacji Customer Insights i pracować zgodnie z ich określonymi rolami.

## <a name="view-current-permissions"></a>Wyświetl bieżące uprawnienia

Przejdź do opcji **Administrator** > **Zabezpieczenia** i wybierz kartę **Użytkownicy**, aby wyświetlić listę aktywnych użytkowników i ich przypisania ról. Listę użytkowników można posortować według dowolnej kolumny lub użyć pola wyszukiwania, aby znaleźć konkretnego użytkownika.

## <a name="manage-current-users"></a>Zarządzanie bieżącymi użytkownikami

Przejdź do **Administrator** > **Zabezpieczenia** i wybierz kartę **Użytkownicy**. Listę użytkowników można posortować według dowolnej kolumny lub użyć pola wyszukiwania, aby znaleźć użytkownika, którym chcesz zarządzać.

Wybierz użytkownika, aby wyświetlić dostępne akcje.

- **Edytuj**, aby edytować rolę użytkownika w funkcji Customer Insights. Wybierz **Zapisz**, aby potwierdzić zmianę.
- **Usuń**, aby usunąć użytkownika z dostępu do danych Customer Insights. Aby potwierdzić usunięcie, wybierz opcję **Usuń**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
