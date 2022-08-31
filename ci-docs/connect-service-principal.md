---
title: Połącz się z kontem Azure Data Lake Storage przy użyciu nazwy głównej usługi Azure
description: Do łączenia się z własnym repozytorium data lake użyj nazwy głównej usługi Azure.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: eba10068c48db5c147100c25a397bcc13b014784
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304210"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Połącz się z kontem Azure Data Lake Storage przy użyciu nazwy głównej usługi Azure

Dynamics 365 Customer Insights ma opcję połączenia z kontem Azure Data Lake Storage za pomocą nazwy głównej usługi Azure zamiast kluczy konta magazynu.

Zautomatyzowane narzędzia korzystające z usług platformy Azure powinny zawsze mieć ograniczone uprawnienia. Zamiast logowania się do aplikacji jako w pełni uprzywilejowany użytkownik, platforma Azure oferuje nazwy głównej usługi. Możesz użyć nazwy głównej usługi do bezpiecznego [dodania lub edycji folderu Common Data Model jako źródła danych](connect-common-data-model.md) lub [utworzenia lub aktualizacji środowiska](create-environment.md).

## <a name="prerequisites"></a>Wymagania wstępne

- Konto usługi Data Lake Storage, które będzie korzystać z głównej usługi, musi mieć Gen2. Konta magazynu usługi Azure Data Lake Gen1 nie są obsługiwane.
- Konto magazynu Azure Data Lake Storage musi mieć [włączoną hierarchiczną przestrzeń nazw](/azure/storage/blobs/data-lake-storage-namespace).
- Uprawnienia administratora dla dzierżawy platformy Azure, jeśli musisz utworzyć nową jednostkę usługi.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Utwórz nazwę główną usługi Azure dla rozwiązania Customer Insights

Przed utworzeniem nowej nazwy głównej usługi dla Customer Insights sprawdź, czy istnieje on już w twojej organizacji. W większości przypadków już istnieje.

### <a name="look-for-an-existing-service-principal"></a>Poszukaj istniejącej nazwy głownej usługi

1. W tym celu należy przejść do [portalu administracyjnego Azure](https://portal.azure.com) i zalogować się do organizacji.

2. W opcji **Usługi Azure** wybierz **Azure Active Directory**.

3. W obszarze **Zarządzaj** wybierz opcję **Microsoft Application**.

4. Dodaj filtr dla **Identyfikatora aplikacji zaczynającego się od** `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` lub wyszukiwanie jej nazwy `Dynamics 365 AI for Customer Insights`.

5. Jeśli znaleziono pasujący rekord, oznacza to, że nazwa główna usługi już istnieje. [Udziel uprawnień](#grant-permissions-to-the-service-principal-to-access-the-storage-account) do nazwy głównej usługi, aby uzyskać dostęp do konta magazynu.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Zrzut ekranu przedstawiający istniejący nazwę główną usługi.":::

6. Jeśli nie są zwracane żadne wyniki, [utwórz nową nazwę główną](#create-a-new-service-principal).

### <a name="create-a-new-service-principal"></a>Utwórz nową nazwę główną usługi

1. Zainstaluj najnowszą wersję programu Azure Active Directory PowerShell dla programu Graph. Aby uzyskać więcej informacji, przejdź do [instalacji programu Azure Active Directory PowerShell dla programu Graph](/powershell/azure/active-directory/install-adv2).

   1. Na komputerze naciśnij klawisz Windows na klawiaturze i wyszukaj program **Windows PowerShell** i wybierz opcję **Uruchom jako Administrator**.

   1. W wyświetlonym oknie PowerShell wprowadź polecenie `Install-Module AzureAD`.

2. Utwórz nazwę główną usługi dla usługi Customer Insights przy użyciu modułu Azure AD PowerShell.

   1. W oknie PowerShell wprowadź polecenie `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Zastąp *[identyfikator swojego katalogu]* rzeczywistym identyfikatorem katalogu subskrypcji Azure, w której chcesz utworzyć główną usługę. Parametr nazwy środowiska, `AzureEnvironmentName`, jest opcjonalny.
  
   1. Wprowadź `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. To polecenie tworzy podmiot główny usługi dla rozwiązania Customer Insights w wybranej subskrypcji platformy Azure.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Udziel uprawnień do nazwy głównej usługi, aby uzyskać dostęp do konta magazynu

Aby przyznać uprawnienia do podmiotu usługi dla konta magazynu, które ma być potrzebne w funkcji Customer Insights, należy przypisać jedną z następujących ról do konta magazynu lub konteneru:

|Poświadczenia|Wymagania|
|----------|------------|
|Obecnie zalogowany użytkownik|**Rola**: czytnik danych obiektu blob magazynu, współautor obiektu blob magazynu lub właściciel obiektu blob magazynu.<br>**Poziom**: można przyznać uprawnienia dla konta magazynu lub kontenera.</br>|
|Jednostka usługi Customer Insights<br>Używanie usługi Azure Data Lake Storage jako źródła danych</br>|Opcja 1<ul><li>**Rola**: czytnik danych obiektu blob magazynu, współautor obiektu blob magazynu lub właściciel obiektu blob magazynu.</li><li>**Poziom**: można przyznać uprawnienia dla konta magazynu.</li></ul>Opcja 2 *(bez udostępniania głównego dostępu usługi do konta magazynu)*<ul><li>**Rola 1**: czytnik danych obiektu blob magazynu, współautor obiektu blob magazynu lub właściciel obiektu blob magazynu.</li><li>**Poziom**: można przyznać uprawnienia dla kontenera.</li><li>**Rola 2**: Delegat danych obiektów blob magazynu.</li><li>**Poziom**: można przyznać uprawnienia dla konta magazynu.</li></ul>|
|Jednostka usługi Customer Insights <br>Używanie Azure Data Lake Storage jako lokalizacji wyjściowej lub docelowej</br>|Opcja 1<ul><li>**Rola**: współautor obiektu blob magazynu lub właściciel obiektu blob magazynu.</li><li>**Poziom**: można przyznać uprawnienia dla konta magazynu.</li></ul>Opcja 2 *(bez udostępniania głównego dostępu usługi do konta magazynu)*<ul><li>**Rola**: współautor obiektu blob magazynu lub właściciel obiektu blob magazynu.</li><li>**Poziom**: można przyznać uprawnienia dla kontenera.</li><li>**Rola 2**: Delegat obiektów blob magazynu.</li><li>**Poziom**: można przyznać uprawnienia dla konta magazynu.</li></ul>|

1. W tym celu należy przejść do [portalu administracyjnego Azure](https://portal.azure.com) i zalogować się do organizacji.

1. Otwórz konto magazynu, do którego ma mieć dostęp podmiot usługi Customer Insights.

1. W lewym okienku wybierz opcję **Kontrola dostępu (IAM)**, a następnie wybierz opcję **Dodaj** > **Dodaj przypisanie roli**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Zrzut ekranu przedstawiający portal Azure Portal podczas dodawania przypisania roli.":::

1. W okienku **Dodaj przypisane roli** ustaw następujące właściwości:
   - **Rola**: czytnik danych obiektu blob magazynu, współautor obiektu blob magazynu lub właściciel obiektu blob magazynu na podstawie wymienionych wyżej uprawnień.
   - **Przypisz dostęp do**: **Użytkownik, grupa lub nazwa główna usługi**
   - **Wybierz** członków: **Dynamics 365 AI dla Customer Insights** (podmiot [usługi wyszukiwany](#create-a-new-service-principal) wcześniej w tej procedurze)

1. Wybierz **Przejrzyj + przypisz**.

Rozpowszechnienie zmian może zająć do 15 minut.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Wprowadź identyfikator zasobu Azure lub szczegóły subskrypcji Azure w załączniku do konta magazynu i rozwiązania Customer Insights

Dołączyć konto Data Lake Storage do Customer Insights w celu [przechowywania danych wyjściowych](manage-environments.md) lub [użycia ich jako źródła danych](connect-dataverse-managed-lake.md). Wybierz metodę [opartą na zasobach](#resource-based-storage-account-connection) lub [oparta na subskrypcjach](#subscription-based-storage-account-connection) i wykonaj te czynności.

### <a name="resource-based-storage-account-connection"></a>Połączenie z kontem magazynu oparte na zasobach

1. Przejdź do [portalu administrowania Azure](https://portal.azure.com), zaloguj się do subskrypcji i otwórz konto magazynu.

1. W lewym okienku przejdź do **Ustawienia** > **Punkty końcowe**.

1. Skopiuj wartość identyfikatora zasobu konta magazynu.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Skopiuj identyfikator zasobu konta magazynu.":::

1. W oknie Customer Insights wstaw identyfikator zasobu w polu zasobów wyświetlanym na ekranie połączenia z kontem magazynu.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Wprowadź informacje o identyfikatorze zasobu konta magazynu.":::

1. Kontynuuj pozostałe kroki w aplikacji Customer Insights, aby dołączyć konto magazynu.

### <a name="subscription-based-storage-account-connection"></a>Połączenie z kontem magazynu oparte na subskrypcji

1. Przejdź do [portalu administrowania Azure](https://portal.azure.com), zaloguj się do subskrypcji i otwórz konto magazynu.

1. W lewym okienku wybierz pozycję **Właściwości** > **Ustawienia**.

1. Przejrzyj grupy **Subskrypcja**, **Grupa zasobów** i **Nazwa** konta magazynu, aby upewnić się, że w aplikacji Customer Insights wybierzesz odpowiednie wartości.

1. W Customer Insights podczas dołączania konta magazynu wybierz wartości odpowiadające im pól.

1. Kontynuuj pozostałe kroki w aplikacji Customer Insights, aby dołączyć konto magazynu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
