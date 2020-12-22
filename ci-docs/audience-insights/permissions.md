---
title: Zarządzanie uprawnieniami użytkowników
description: Dowiedz się o uprawnieniach i rolach użytkowników.
ms.date: 10/27/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7de78c0ef71ec5b83870d396de36a7dcabbd14e5
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689233"
---
# <a name="user-permissions"></a>Uprawnienia użytkowników

Na stronie **Uprawnienia** można skonfigurować role i uprawnienia dotyczące korzystania z analiz odbiorców.

Aby wyświetlić stronę, trzeba mieć uprawnienia administratora. Aby uzyskać dostęp do strony uprawnienia w analizach ocbiorców, należy przejść do obszaru **Administrator** > **Uprawnienia**.

Istnieją trzy typy ról:

## <a name="viewer"></a>Przeglądający

- Eksploruj informacje i segmenty na stronach **Strona główna** i **Segmenty**.
- Wyszukiwanie i filtrowanie profilów klientów przy użyciu strony **Klienci**. Pola muszą mieć możliwość przeszukiwania.
- Wyświetl stronę **Wzbogacanie** i zapoznaj się z nią.
- Przeglądaj i eksportuj encje za pomocą strony **Encje**.
- Wyświetl stan procesów systemowych przy użyciu strony **System**.
- Wyeksportuj segmenty ze strony **Segmenty**.
- Zainstaluj i skorzystaj z pulpitu nawigacyjnego **Power BI Customer Insights**.

## <a name="contributor"></a>Współautor

- Wszystkie uprawnienia dostępne dla Przeglądającego.
- Ładuj i przekształcaj dane przy użyciu strony **Źródła danych**.
- Uzupełnij sekcje *Ujednolicenie danych* (**Mapowanie**, **Dopasowywanie** i **Scalanie**), które skutkują encją ujednoliconego profilu klienta.
- Zdefiniuj **Relacje** i **Działania**.
- Utwórz segmenty, korzystając ze strony **Segmenty**.
- Utwórz miary za pomocą strony **Miary**.
- Zarządzaj konfiguracją i wzbogacaj profile klientów ze strony **Wzbogacanie** (dotyczy tylko wzbogaceń własnych).

## <a name="administrator"></a>Administrator

- Wszystkie uprawnienia dostępne dla Współautora.
- Zmień ustawienia na stronie **System**, w tym język roboczy i odśwież harmonogramy dla procesów systemowych.
- Wyświetl i dodaj uprawnienia przy użyciu strony **Uprawnienia**.
- Ustaw definicje Wyszukiwanie i Filtrowanie dla strony Klienci za pomocą strony **Wyszukiwanie i indeks filtrów** (dostępnej przez stronę **Klienci**).
- Zdefiniuj miejsca docelowe segmentu Dynamics 365 Sales przy użyciu strony **Lokalizacje docelowe eksportu**.
- Zarządzaj konfiguracją i wzbogacaj profile klientów ze strony **Wzbogacanie** (dotyczy wszystkich wzbogaceń).
- Zainstaluj i użyj **Dodatek kart klientów**.
- Dodanie **łącznika Power Apps** i korzystanie z niego.
- Włącz korzystanie z [interfejsów API Customer Insights](apis.md).

## <a name="assign-roles-and-permissions"></a>Przypisz role i uprawnienia

1. W analizach odbiorców przejdź do **Administrator** > **Uprawnienia**.

1. Wybierz pozycję **Dodaj użytkowników**, aby otworzyć okienko **Dodawanie/Edytowanie uprawnień**.

1. Użyj pola **Wyszukaj**, aby znaleźć użytkownika lub grupę Azure Active Directory, którego lub której uprawnienia chcesz dostosować. Wybierz **Rola**, aby przypisać ją do tego użytkownika lub grupy.

1. Wybierz pozycję **Zapisz**. Bieżące środowisko zostanie automatycznie udostępnione użytkownikowi lub członkom grupy, której uprawnienia zostały zmienione. Użytkownicy mogą uzyskiwać dostęp do aplikacji Customer Insights i pracować zgodnie z ich określonymi rolami.

## <a name="view-current-permissions"></a>Wyświetl bieżące uprawnienia

W analizach odbiorców przejdź do **Administrator** > **Uprawnienia**, aby zobaczyć, jakie przypisania ról są obecnie aktywne.

- Kolumna **Typ** określa pojedynczego użytkownika, grupę lub aplikację. System obsługuje poszczególnych użytkowników i grupy.
- Role są określane w kolumnie **Rola**.
- Zaznacz tytuł dowolnej kolumny, aby posortować wyniki według wartości tej kolumny.
- Użyj pola **Wyszukaj** w górnej części strony, aby zlokalizować określonych użytkowników.
