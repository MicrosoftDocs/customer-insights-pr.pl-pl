---
title: Konfigurowanie ustawienia zabezpieczeń
description: Dowiedz się więcej o ustawieniach zabezpieczeń w Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: d20d57e9b7724e9921f9341eeaa39141b4555ff1
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387262"
---
# <a name="configure-security-settings"></a>Konfigurowanie ustawienia zabezpieczeń

Zarządzanie kluczami interfejsów API, uzyskiwanie dostępu do danych klientów i konfigurowanie łącza prywatnego Azure Private Link.

## <a name="manage-api-keys"></a>Zarządzaj kluczami interfejsu API

Wyświetlaj i zarządzaj kluczami, aby używać [interfejsów API funkcji Customer Insights](apis.md) z danymi w środowisku.

1. Przejdź do pozycji **Administracja** > **Zabezpieczenia** > i wybierz kartę **Interfejsy API**.

1. Jeśli dostęp interfejsu API do środowiska nie został ustawiony, wybierz opcję **Włącz**. Lub aby zablokować dostęp interfejsu API do środowiska, wybierz opcję **Wyłącz** i potwierdź.

1. Zarządzanie podstawowymi i pomocniczym kluczami interfejsu API:

   1. Aby wyświetlić podstawowy lub pomocniczy klucz interfejsu API, wybierz symbol **Pokaż**.

   1. Aby skopiować podstawowy lub pomocniczy klucz interfejsu API, wybierz symbol **Kopiuj**.

   1. Nowe podstawowe i dodatkowe klucze interfejsu API można utworzyć, wybierając opcję **Ponowne generowanie podstawowe** lub **Ponowne generowanie pomocnicze**.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Bezpieczne uzyskiwanie dostępu do danych klientów przy użyciu skrytki klienta (wersja zapoznawcza)

Funkcja Customer Insights używa z funkcji Skrytki klienta Power Platform. Aplikacja Skrytka klienta udostępnia interfejs do przeglądania i zatwierdzania (lub odrzucania) żądań dostępu do danych. Te żądania występują, gdy dostęp do danych klienta jest potrzebny do rozwiązania sprawy pomocy technicznej. Aby można było korzystać z tej funkcji, funkcja Customer Insights musi mieć istniejące połączenie ze środowiskiem Microsoft Dataverse w dzierżawie.

Aby uzyskać więcej informacji na temat funkcji Skrytki klienta, zobacz [podsumowanie](/power-platform/admin/about-lockbox#summary) funkcji Skrytki klienta Power Platform . W artykule opisano również [przepływ pracy](/power-platform/admin/about-lockbox#workflow) i wymaganą [konfigurację](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) w celu włączenia funkcji Skrytki klienta.

> [!IMPORTANT]
> Administratorzy globalni dla Power Platform lub administratorzy Power Platform mogą zatwierdzać żądania skrzynki klienta wydawane dla usługi Customer Insights.

## <a name="set-up-an-azure-private-link"></a>Konfigurowanie łącza prywatnego Azure Private Link

Usługa [Azure Private Link](/azure/private-link/private-link-overview) umożliwia dostęp rozwiązania Customer Insights do konta Azure Data Lake Storage za punktem końcowym w sieci wirtualnej. W przypadku danych na koncie magazynu, które nie jest widoczne w publicznym Internecie, Provate Link umożliwia połączenie z dostępem do tej sieci zastrzeżonej.

> [!IMPORTANT]
> Minimalne wymaganie roli w celu skonfigurowania połączenia Private Link:
>
> - Customer Insights: Administrator
> - Wbudowana rola Azure: [Współautor konta magazynu](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Uprawnienia dla niestandardowej roli Azure: [Microsoft.Storage/storageAccounts/read i Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. W Customer Insights przejdź do **Administrator** > **Zabezpieczenia** i wybierz kartę **Łącza prywatne**.

1. Wybierz **Dodaj prywatne łącza**.

   Okienko **Dodaj Private Link** zawiera listę kont magazynu od dzierżawcy, do których użytkownik ma uprawnienia.

1. Wybierz subskrypcja, grupa zasobów i konto magazynu.

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Wybierz pozycję **Zapisz**.

1. Należy przejść do konta Data Lake Storage i otworzyć łącze przedstawione na ekranie.

1. Zatwierdzanie łącza prywatnego Private Link.


[!INCLUDE [footer-include](includes/footer-banner.md)]
