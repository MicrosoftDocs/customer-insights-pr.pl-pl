---
title: Ustawienia zabezpieczeń w Customer Insights
description: Dowiedz się więcej o ustawieniach zabezpieczeń w Dynamics 365 Customer Insights.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947428"
---
# <a name="security-settings-in-customer-insights"></a>Ustawienia zabezpieczeń w Customer Insights

Na stronie **Zabezpieczenia** znajduje się lista opcji konfigurowania uprawnień użytkowników i funkcji, które ułatwiają lepiej zabezpieczyć usługę Dynamics 365 Customer Insights. Dostęp do tej strony mogą uzyskać tylko administratorzy.

Aby skonfigurować ustawienia, przejdź do strony **Administrator** > **Zabezpieczenia**.

Strona **Zabezpieczenia** zawiera następujące karty:

- [Użytkownicy](#users-tab)
- [Interfejsy API](#apis-tab)
- [Linki prywatne](#private-links-tab)
- [Key Vault](#key-vault-tab)
- [Bezpieczne uzyskiwanie dostępu do danych klientów przy użyciu skrytki klienta (wersja zapoznawcza)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>Karta Użytkownicy

Dostęp do danych Customer Insights jest ograniczony do użytkowników w organizacji, którzy zostali dodani do aplikacji przez administratora. Karta **Użytkownicy** umożliwia zarządzanie dostępem użytkowników i ich uprawnieniami. Aby uzyskać więcej informacji, zobacz [Uprawnienia użytkownika](permissions.md).

## <a name="apis-tab"></a>Karta Interfejsy API

Wyświetlaj i zarządzaj kluczami, aby używać [interfejsów API funkcji Customer Insights](apis.md) z danymi środowiska.

Nowe klucze podstawowe i dodatkowe można utworzyć, wybierając opcję **Ponowne generowanie podstawowe** lub **Ponowne generowanie pomocnicze**. 

Aby zablokować dostęp interfejsu API do środowiska, wybierz opcję **Wyłącz**. Jeśli interfejsy API są wyłączone, można ponownie wybrać opcję **Włącz**, aby przyznać dostęp.

## <a name="private-links-tab"></a>Karty Private Link

Usługa [Azure Private Link](/azure/private-link/private-link-overview) umożliwia dostęp rozwiązania Customer Insights do konta Azure Data Lake Storage za punktem końcowym w sieci wirtualnej. W przypadku danych na koncie magazynu, które nie jest widoczne w publicznym Internecie, Provate Link umożliwia połączenie z dostępem do tej sieci zastrzeżonej.

> [!IMPORTANT]
> Minimalne wymaganie roli w celu skonfigurowania połączenia Private Link:
>
> - Customer Insights: Administrator
> - Wbudowana rola Azure: [Współautor konta magazynu](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Uprawnienia dla niestandardowej roli Azure: [Microsoft.Storage/storageAccounts/read i Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

Konfigurowanie Private Link w Customer Insights to proces dwuetapowy. Najpierw należy rozpocząć tworzenie łącza Private Link w **Administrator** > **Zabezpieczenia** > **Private Link** w Customer Insights. Okienko **Dodaj Private Link** zawiera listę kont magazynu od dzierżawcy, do których użytkownik ma uprawnienia. Wybierz konto magazynu i wyraź zgodę na utworzenie Private Link.

Następnie należy zatwierdzić łącze Private Link po stronie konta Magazyn danych Data Lake. Otwórz łącze przedstawione na ekranie, aby zatwierdzić nowe Private Link.

## <a name="key-vault-tab"></a>Karta Key Vault

Karta **Key Vault** umożliwia łączenie i zarządzanie własnym magazynem [Azure key vault](/azure/key-vault/general/basic-concepts) w środowisku.
Dedykowanego magazynu kluczy można używać do tworzenia etapów i używania wpisów danych w granicach zgodności organizacji. Customer Insights mogą użyć wpisów tajnych w usłudze Azure Key Vault, aby [skonfigurować połączenia](connections.md) z platformami innych firm.

Aby uzyskać więcej informacji, przejrzyj temat [Użyj własnego magazynu Azure Key Vault](use-azure-key-vault.md).

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Bezpieczne uzyskiwanie dostępu do danych klientów przy użyciu skrytki klienta (wersja zapoznawcza)

Funkcja Customer Insights korzysta z funkcji Skrytki klienta Power Platform. Aplikacja Skrytka klienta udostępnia interfejs do przeglądania i zatwierdzania (lub odrzucania) żądań dostępu do danych. Te żądania występują, gdy dostęp do danych klienta jest potrzebny do rozwiązania sprawy pomocy technicznej. Aby można było korzystać z tej funkcji, funkcja Customer Insights musi mieć istniejące połączenie ze środowiskiem Microsoft Dataverse w dzierżawie.

Aby uzyskać więcej informacji na temat funkcji Skrytki klienta, zobacz [podsumowanie](/power-platform/admin/about-lockbox#summary) funkcji Skrytki klienta Power Platform . W artykule opisano również [przepływ pracy](/power-platform/admin/about-lockbox#workflow) i wymaganą [konfigurację](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) w celu włączenia funkcji Skrytki klienta.

> [!IMPORTANT]
> Administratorzy globalni dla Power Platform lub administratorzy Power Platform mogą zatwierdzać żądania skrzynki klienta wydawane dla usługi Customer Insights.

[!INCLUDE [footer-include](includes/footer-banner.md)]
