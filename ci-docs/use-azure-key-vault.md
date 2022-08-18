---
title: Korzystanie z własnej usługi Azure Key Vault (wersja zapoznawcza)
description: Dowiedz się, jak skonfigurować usługę Customer Insights do używania własnego magazynu kluczy Azure Key Vault w celu zarządzania wpisami tajnymi.
ms.date: 08/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 229fb5698a02d1d73c30442f61c7b1b5fce918bf
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246168"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Korzystanie z własnej usługi Azure Key Vault (wersja zapoznawcza)

Połączenie dedykowanego [magazynu kluczy Azure key vault](/azure/key-vault/general/basic-concepts) ze środowiskiem Customer Insights o odbiorcach ułatwia organizacjom spełnienie wymagań dotyczących zgodności.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Łączenie magazynu kluczy ze środowiskiem Customer Insights

Ustawianie dedykowanego magazynu kluczy do tworzenia etapów i używania wpisów danych w granicach zgodności organizacji.

### <a name="prerequisites"></a>Wymagania wstępne

- Aktywna subskrypcja platformy Azure.

- Rola [Administrator](permissions.md#admin) [przypisana](permissions.md#add-users) w rozwiązaniu Customer Insights.

- Role [Współautor](/azure/role-based-access-control/built-in-roles#contributor) i [Administrator dostępu użytkowników](/azure/role-based-access-control/built-in-roles#user-access-administrator) w magazynie kluczy key vault lub grupie zasobów, do której należy magazyn kluczy key vault. Aby uzyskać więcej informacji, przejdź do tematu [Dodawanie i usuwanie przypisań ról platformy Azure za pomocą witryny Azure Portal](/azure/role-based-access-control/role-assignments-portal). Jeśli nie masz roli Administrator dostępu użytkowników w magazynie kluczy, skonfiguruj uprawnienia kontroli dostępu na podstawie ról dla jednostki usługi platformy Azure dla aplikacji Dynamics 365 Customer Insights. Wykonaj kroki, aby [użyć jednostki usługi platformy Azure](connect-service-principal.md) dla magazynu kluczy, który ma zostać połączony.

- Magazyn Key Vault musi być **wyłączoną** zaporę Key Vault.

- Magazyn kluczy key vault znajduje się w tej samej [lokalizacji platformy Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview), co środowisko Customer Insights. Aby poznać region środowiska, przejdź do karty **Administrator** > **System** i **Informacje** w Customer Insights.

### <a name="recommendations"></a>Rekomendacje

- [Należy użyć oddzielnego lub dedykowanego magazynu kluczy](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults) zawierającego tylko wpisy tajne wymagane dla Customer Insights.

- Postępuj zgodnie z [najlepszymi rozwiązaniami do użycia w usłudze Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) w przypadku opcji kontroli dostępu, tworzenia kopii zapasowych, inspekcji i odzyskiwania.

### <a name="link-a-key-vault-to-the-environment"></a>Łączenie magazynu kluczy ze środowiskiem

1. Przejdź do pozycji **Administracja** > **Bezpieczeństwo**, a następnie wybierz kartę **Key Vault**.
1. Na kafelku **Magazyn kluczy** wybierz opcję **Konfiguracja**.
1. Wybierz **subskrypcję**.
1. Wybierz magazyn kluczy z listy rozwijanej **Key Vault**. Jeśli dostępnych jest zbyt wiele magazynów kluczy, wybierz grupę zasobów w celu ograniczenia wyników wyszukiwania.
1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.
1. Wybierz pozycję **Zapisz**.

Kafelek **Key Vault** będzie teraz zawierał nazwę połączonego magazynu kluczy, subskrypcję i grupę zasobów. Jest on gotowy do użycia w konfiguracji połączenia.
Aby uzyskać szczegółowe informacje na temat uprawnień do magazynu kluczy, które są przyznawane w Customer Insights, przejdź do sekcji [Uprawnienia przyznawane w magazynie kluczy do Customer Insights](#permissions-granted-on-the-key-vault).

## <a name="use-the-key-vault-in-the-connection-setup"></a>Korzystanie z magazynu kluczy w konfiguracji połączenia

Podczas [konfigurowania połączeń](connections.md) z [obsługiwanymi platformami innych firm](#supported-connection-types) do konfigurowania połączeń użyj wpisów tajnych z połączonego magazynu kluczy.

1. Przejdź do **Admin** > **Połączenia**.
1. Wybierz opcję **Dodaj połączenie**.
1. W przypadku obsługiwanych typów połączenia dostępny jest przełącznik **Użyj usługi Key Vault** po połączeniu z magazynem kluczy.
1. Zamiast ręcznie wprowadzać dane do magazynu kluczy, wybierz nazwę wpisu tajnego, która wskazuje na wartość w magazynie kluczy.

   :::image type="content" source="media/use-key-vault-secret.png" alt-text="Okienko połączenia z połączeniem SFTP, które korzysta z wpisu tajnego usługi Key Vault.":::

1. Aby utworzyć połączenie, wybierz **Zapisz**.

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

## <a name="permissions-granted-on-the-key-vault"></a>Uprawnienia przyznane w magazynie key vault

Poniższe uprawnienia są przyznawane Customer Insights w połączonym magazynie kluczy, jeśli włączono [zasady dostępu do usługi Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) lub [kontrolę dostępu na podstawie ról na platformie Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

### <a name="key-vault-access-policy"></a>Zasady dostępu usługi Key Vault

| Pisz        | Uprawnienia          |
| ----------- | -------------------- |
| Klawisz         | [Pobieranie kluczy](/rest/api/keyvault/keys/get-keys/get-keys), [Pobieranie klucza](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Klucz tajny      | [Pobieranie wpisów tajnych](/rest/api/keyvault/secrets/get-secrets/get-secrets), [Pobieranie wpisu tajnego](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Certyfikat | [Pobieranie certyfikatów](/rest/api/keyvault/certificates/get-certificates/get-certificates), [Pobieranie certyfikatu](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

Powyższe wartości to minimum do wymienienia na liście i odczytu podczas wykonywania.

### <a name="azure-role-based-access-control"></a>Kontrola dostępu na podstawie ról na platformie Azure

[Role Key Vault — czytelnik i Key Vault — użytkownik wpisów tajnych](/azure/key-vault/general/rbac-guide?tabs=azure-cli) zostaną dodane do Customer Insights.

## <a name="frequently-asked-questions"></a>Często zadawane pytania

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Czy funkcja Customer Insights może zapisywać wpisy tajne lub nadpisywać wpisy tajne w magazynie kluczy?

Nie Tylko uprawnienia do odczytu i tworzenie listy określone w sekcji [przyznawanych uprawnień](#permissions-granted-on-the-key-vault) są przyznawane funkcji Customer Insights. W systemie nie można dodawać, usuwać ani nadpisywać wpisów tajnych w magazynie kluczy. Również z tego powodu nie można wprowadzać poświadczeń w przypadku, gdy połączenie używa usługi Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Czy można zmienić połączenie z używania wpisów tajnych usługi Key Vault na uwierzytelnianie domyślne?

Nr Po skonfigurowaniu połączenia przy użyciu wpisu tajnego z połączonego magazynu kluczy nie można zmienić go z powrotem na połączenie domyślne. Utwórz oddzielne połączenie, a jeśli stare połączenie nie będzie już potrzebne, usuń je.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Jak cofnąć dostęp do magazynu kluczy dla funkcji Customer Insights?

Jeśli włączono [zasady dostępu usługi Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) lub [kontrolę dostępu na podstawie ról platformy Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli), usuń uprawnienia jednostki usługi `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` o nazwie `Dynamics 365 AI for Customer Insights`. Wszystkie połączenia z magazynem kluczy zostaną zatrzymane.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Wpis tajny używany w połączeniu został usunięty z magazynu kluczy. Co mogę zrobić?

W funkcji Customer Insights jest wyświetlane powiadomienie, gdy skonfigurowany wpis tajny z magazynu kluczy nie jest już dostępny. Włącz [usuwanie nietrwałe](/azure/key-vault/general/soft-delete-overview) w magazynie kluczy, aby przywrócić wpisy tajne, jeśli zostaną przypadkowo usunięte.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Połączenie nie działa, ale mój wpis tajny znajduje się w magazynie kluczy. Co może być przyczyną?

Powiadomienie jest wyświetlane w funkcji Customer Insights, gdy nie może ona uzyskać dostępu do magazynu kluczy. Możliwe przyczyny:

- Uprawnienia do jednostki usługi Customer Insights zostały usunięte. Należy je przywrócić ręcznie.

- Zapora w magazynie kluczy została włączona. Zaporę należy wyłączyć, aby magazyn kluczy był ponownie dostępny dla Customer Insights.
