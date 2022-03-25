---
title: Korzystanie z własnej usługi Azure Key Vault w celu zarządzania wpisani tajnymi
description: Dowiedz się, jak skonfigurować usługę Customer Insights do używania własnego magazynu kluczy Azure Key Vault.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 418575f724090628da8bd01e2569a4cb9e646337
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376521"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Korzystanie z własnej usługi Azure Key Vault (wersja zapoznawcza)

Połączenie dedykowanego [magazynu kluczy Azure](/azure/key-vault/general/basic-concepts) ze środowiskiem szczegółowych informacji o odbiorcach ułatwia organizacjom spełnienie wymagań dotyczących zgodności.
Dedykowanego magazynu kluczy można używać do tworzenia etapów i używania wpisów danych w granicach zgodności organizacji. Odbiorcy mogą użyć wpisów tajnych w usłudze Azure Key Vault, aby [skonfigurować połączenia](connections.md) z platformami innych firm.

## <a name="link-the-key-vault-to-the-audience-insights-environment"></a>Łączenie magazynu kluczy ze środowiskiem szczegółowych informacji o odbiorcach

### <a name="prerequisites"></a>Wymagania wstępne

Aby skonfigurować magazyn kluczy w obszarze szczegółowych informacji o odbiorcach, należy spełnić następujące wymagania wstępne:

- Masz aktywną subskrypcję platformy Azure.

- Masz rolę użytkownika [Administrator](permissions.md#admin) w rozwiązaniu analiza odbiorców. Dowiedz się więcej o [uprawnieniach użytkowników w środowisku szczegółowych informacji o odbiorcach](permissions.md#assign-roles-and-permissions).

- Masz role [Współautor](/azure/role-based-access-control/built-in-roles#contributor) i [Administrator dostępu użytkowników](/azure/role-based-access-control/built-in-roles#user-access-administrator) w magazynie kluczy lub grupie zasobów, do której należy magazyn kluczy. Aby uzyskać więcej informacji, przejdź do tematu [Dodawanie i usuwanie przypisań ról platformy Azure za pomocą witryny Azure Portal](/azure/role-based-access-control/role-assignments-portal). Jeśli nie masz roli Administrator dostępu użytkowników w magazynie kluczy, musisz oddzielnie skonfigurować uprawnienia kontroli dostępu na podstawie ról dla jednostki usługi platformy Azure dla aplikacji Dynamics 365 Customer Insights. Wykonaj kroki, aby [użyć jednostki usługi platformy Azure](connect-service-principal.md) dla magazynu kluczy, który ma zostać połączony.

- Zapora usługi Key Vault w magazynie kluczy musi być **wyłączona**.

- Magazyn kluczy znajduje się w tej samej [lokalizacji platformy Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview), co środowisko szczegółowych informacji o odbiorcach. Obszar środowiska w obszarze szczegółowych informacji o odbiorcach w obszarze **Administracja** > **System** > **Informacje** > **Region**.

### <a name="link-a-key-vault-to-the-environment"></a>Łączenie magazynu kluczy ze środowiskiem

1. Przejdź do pozycji **Administracja** > **System**, a następnie wybierz kartę **Zabezpieczenia**.
1. Na kafelku **Magazyn kluczy** wybierz opcję **Konfiguracja**.
1. Wybierz **subskrypcję**.
1. Wybierz magazyn kluczy z listy rozwijanej **Key Vault**. Jeśli wyświetlono zbyt wiele magazynów kluczy, wybierz grupę zasobów w celu ograniczenia wyników wyszukiwania.
1. Zaakceptuj oświadczenie dotyczące **zasad ochrony poufności informacji i zgodności**.
1. Wybierz pozycję **Zapisz**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Kroki procesu konfigurowania połączonego magazynu kluczy w obszarze szczegółowych informacji o odbiorcach.":::

Kafelek **Key Vault** będzie teraz zawierał nazwę połączonego magazynu kluczy, grupę zasobów i subskrypcję. Jest on gotowy do użycia w konfiguracji połączenia.
Aby uzyskać szczegółowe informacje na temat uprawnień do magazynu kluczy, które są przyznawane w obszarze szczegółowych informacji o odbiorcach, przejdź do sekcji [Uprawnienia przyznawane w magazynie kluczy do szczegółowych informacji o odbiorcach](#permissions-granted-on-the-key-vault-to-audience-insights) w dalszej części tego artykułu.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Korzystanie z magazynu kluczy w konfiguracji połączenia

Podczas [konfigurowania połączeń](connections.md) z platformami innych firm do konfigurowania połączeń można użyć wpisów tajnych z połączonego magazynu kluczy.

1. Przejdź do **Admin** > **Połączenia**.
1. Wybierz opcję **Dodaj połączenie**.
1. W przypadku obsługiwanych typów połączenia dostępny jest przełącznik **Użyj usługi Key Vault** po połączeniu z magazynem kluczy.
1. Zamiast ręcznie wprowadzać dane do magazynu kluczy, można wybrać nazwę wpisu tajnego, która wskazuje na wartość w magazynie kluczy.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Okienko połączenia z połączeniem SFTP, które korzysta z wpisu tajnego usługi Key Vault.":::

## <a name="supported-connection-types"></a>Obsługiwane typy połączeń

Obsługiwane są następujące połączenia [eksportu](export-destinations.md):

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Usługa Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault-to-audience-insights"></a>Uprawnienia przyznawane w magazynie kluczy do szczegółowych informacji o odbiorcach

Poniższe uprawnienia są przyznawane szczegółowym informacjom o odbiorcach w połączonym magazynie kluczy, jeśli włączono [zasady dostępu do usługi Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) lub [kontrolę dostępu na podstawie ról na platformie Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

### <a name="key-vault-access-policy"></a>Zasady dostępu usługi Key Vault

| Pisz        | Uprawnienia          |
| ----------- | -------------------- |
| Klawisz         | [Pobieranie kluczy](/rest/api/keyvault/get-keys), [Pobieranie klucza](/rest/api/keyvault/get-key)                                 |
| Klucz tajny      | [Pobieranie wpisów tajnych](/rest/api/keyvault/get-secrets), [Pobieranie wpisu tajnego](/rest/api/keyvault/get-secret)                     |
| Certyfikat | [Pobieranie certyfikatów](/rest/api/keyvault/get-certificates), [Pobieranie certyfikatu](/rest/api/keyvault/get-certificate) |

Powyższe wartości to minimum do wymienienia na liście i odczytu podczas wykonywania.

### <a name="azure-role-based-access-control"></a>Kontrola dostępu na podstawie ról na platformie Azure

Role Key Vault — czytelnik i Key Vault — użytkownik wpisów tajnych zostaną dodane do szczegółowych informacji o odbiorcach. Aby uzyskać szczegółowe informacje na temat tych ról, przejdź do tematu [Wbudowane role platformy Azure dla operacji płaszczyzny danych usługi Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Rekomendacje

- Należy użyć oddzielnego lub dedykowanego magazynu kluczy zawierającego tylko wpisy tajne wymagane dla szczegółowych informacji o odbiorcach. Dowiedz się więcej o tym, dlaczego [zalecane jest używanie oddzielnych magazynów kluczy](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Postępuj zgodnie z [najlepszymi rozwiązaniami do użycia w usłudze Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) w przypadku opcji kontroli dostępu, tworzenia kopii zapasowych, inspekcji i odzyskiwania.

## <a name="frequently-asked-questions"></a>Często zadawane pytania

### <a name="can-audience-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Czy funkcja szczegółowych informacji o odbiorcach może zapisywać wpisy tajne lub nadpisywać wpisy tajne w magazynie kluczy?

Nr Tylko uprawnienia do odczytu i tworzenie listy określone w sekcji [przyznawanych uprawnień](#permissions-granted-on-the-key-vault-to-audience-insights) we wcześniejszej części tego artykułu są przyznawane funkcji szczegółowych informacji o odbiorcach. W systemie nie można dodawać, usuwać ani nadpisywać wpisów tajnych w magazynie kluczy. Również z tego powodu nie można wprowadzać poświadczeń w przypadku, gdy połączenie używa usługi Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Czy można zmienić połączenie z używania wpisów tajnych usługi Key Vault na uwierzytelnianie domyślne?

Nr Po skonfigurowaniu połączenia przy użyciu wpisu tajnego z połączonego magazynu kluczy nie można zmienić go z powrotem na połączenie domyślne. Utwórz oddzielne połączenie, a jeśli stare połączenie nie będzie już potrzebne, usuń je.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-audience-insights"></a>Jak cofnąć dostęp do magazynu kluczy dla funkcji szczegółowych informacji o odbiorcach?

W zależności od tego, czy włączono [zasady dostępu usługi Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) lub [kontrolę dostępu na podstawie ról platformy Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli), należy usunąć uprawnienia jednostki usługi `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` o nazwie `Dynamics 365 AI for Customer Insights`. Wszystkie połączenia z magazynem kluczy zostaną zatrzymane.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Wpis tajny używany w połączeniu został usunięty z magazynu kluczy. Co mogę zrobić?

W funkcji szczegółowych informacji o odbiorcach jest wyświetlane powiadomienie, gdy skonfigurowany wpis tajny z magazynu kluczy nie jest już dostępny. Włącz [usuwanie nietrwałe](/azure/key-vault/general/soft-delete-overview) w magazynie kluczy, aby przywrócić wpisy tajne, jeśli zostaną przypadkowo usunięte.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Połączenie nie działa, ale mój wpis tajny znajduje się w magazynie kluczy. Co może być przyczyną?

Powiadomienie jest wyświetlane w funkcji szczegółowych informacji o odbiorcach, gdy nie może ona uzyskać dostępu do magazynu kluczy. Możliwe przyczyny:

- Uprawnienia do jednostki usługi funkcji szczegółowych informacji o odbiorcach zostały usunięte. Należy je przywrócić ręcznie.

- Zapora w magazynie kluczy została włączona. Zaporę należy wyłączyć, aby magazyn kluczy był ponownie dostępny dla funkcji szczegółowych informacji o odbiorcach.
