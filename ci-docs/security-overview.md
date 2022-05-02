---
title: Ustawienia zabezpieczeń w Dynamics 365 Customer Insights
description: Dowiedz się więcej o ustawieniach zabezpieczeń w Dynamics 365 Customer Insights.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653736"
---
# <a name="security-overview-page"></a>Strona przeglądu zabezpieczeń

Na stronie **Zabezpieczenia** znajduje się lista opcji konfigurowania uprawnień użytkowników i funkcji, które ułatwiają lepiej zabezpieczyć usługę Dynamics 365 Customer Insights. Dostęp do tej strony mogą uzyskać tylko administratorzy. 

Aby skonfigurować ustawienia, przejdź do strony **Administrator** > **Zabezpieczenia**.

Strona **Zabezpieczenia** zawiera następujące karty:
- [Użytkownicy](#users-tab)
- [Interfejsy API](#apis-tab)
- [Key Vault](#key-vault-tab)

## <a name="users-tab"></a>Karta Użytkownicy

Dostęp do danych Customer Insights jest ograniczony do użytkowników w organizacji, którzy zostali dodani do aplikacji przez administratora. Karta **Użytkownicy** umożliwia zarządzanie dostępem użytkowników i ich uprawnieniami. Aby uzyskać więcej informacji, zobacz [Uprawnienia użytkownika](permissions.md).

## <a name="apis-tab"></a>Karta Interfejsy API

Wyświetlaj i zarządzaj kluczami, aby używać [interfejsów API funkcji Customer Insights](apis.md) z danymi środowiska.

Nowe klucze podstawowe i dodatkowe można utworzyć, wybierając opcję **Ponowne generowanie podstawowe** lub **Ponowne generowanie pomocnicze**. 

Aby zablokować dostęp interfejsu API do środowiska, wybierz opcję **Wyłącz**. Jeśli interfejsy API są wyłączone, można ponownie wybrać opcję **Włącz**, aby przyznać dostęp.

## <a name="key-vault-tab"></a>Karta Key Vault

Karta **Key Vault** umożliwia łączenie i zarządzanie własnym magazynem [Azure key vault](/azure/key-vault/general/basic-concepts) w środowisku.
Dedykowanego magazynu kluczy można używać do tworzenia etapów i używania wpisów danych w granicach zgodności organizacji. Customer Insights mogą użyć wpisów tajnych w usłudze Azure Key Vault, aby [skonfigurować połączenia](connections.md) z platformami innych firm.

Aby uzyskać więcej informacji, przejrzyj temat [Użyj własnego magazynu Azure Key Vault](use-azure-key-vault.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
