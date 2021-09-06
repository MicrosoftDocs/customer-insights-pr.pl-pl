---
title: Połącz się z kontem Azure Data Lake Storage przy użyciu nazwy głównej usługi
description: Do łączenia się z własnym repozytorium data lake użyj nazwy głównej usługi Azure.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 845d1f55eb99f2adf9b437124addec4f6d016fec
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461161"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Połącz się z kontem Azure Data Lake Storage przy użyciu nazwy głównej usługi Azure
<!--note from editor: The Cloud Style Guide would have us just use "Azure Data Lake Storage" to mean the current version, unless the old version (Gen1) is mentioned. I've followed this guidance, even though it seems that our docs and Azure docs are all over the map on this.-->
Zautomatyzowane narzędzia korzystające z usług platformy Azure powinny zawsze mieć ograniczone uprawnienia. Zamiast logowania się do aplikacji jako w pełni uprzywilejowany użytkownik, platforma Azure oferuje nazwy głównej usługi. Przeczytaj, jak połączyć konto Dynamics 365 Customer Insights z kontem Azure Data Lake Storage za pomocą nazwy głównej usługi Azure zamiast kluczy konta magazynu. 

Można użyć nazwy głównej usługi, by bezpiecznie [dodać lub edytować folder Common Data Model jako źródło danych](connect-common-data-model.md) lub [utworzyć lub zaktualizować środowisko](get-started-paid.md).<!--note from editor: Suggested. Or it could be ", or create a new environment or update an existing one". I think "new" is implied with "create". The comma is necessary.-->

> [!IMPORTANT]
> - Konto usługi Stora Data Lake, które będzie korzystać z<!--note from editor: Suggested. Or perhaps it could be "The Data Lake Storage account to which you want to give access to the service principal..."--> nazwy głównej usługi musi mieć [włączony hierarchiczny obszar nazw](/azure/storage/blobs/data-lake-storage-namespace).
> - Aby utworzyć nazwę główną usługi, trzeba mieć uprawnienia administratora w ramach Twojej subskrypcji platformy Azure.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Utwórz nazwę główną usługi Azure dla rozwiązania Customer Insights

Przed utworzeniem nowej nazwy głównej usługi dla wyników analiz odbiorców lub interakcji sprawdź, czy istnieje ona już w organizacji.

### <a name="look-for-an-existing-service-principal"></a>Poszukaj istniejącej nazwy głownej usługi

1. W tym celu należy przejść do [portalu administracyjnego Azure](https://portal.azure.com) i zalogować się do organizacji.

2. W opcji **Usługi Azure** wybierz **Azure Active Directory**.

3. W obszarze **Zarządzanie** wybierz pozycję **Aplikacje korporacyjne**.

4. Wyszukaj identyfikator<!--note from editor: Via Microsoft Writing Style Guide.--> aplikacji Microsoft:
   - Wyniki analiz odbiorców: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` o nazwie `Dynamics 365 AI for Customer Insights`
   - Wyniki analiz interakcji: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` o nazwie `Dynamics 365 AI for Customer Insights engagement insights`

5. Jeśli znaleziono pasujący rekord, oznacza to, że nazwa główna usługi już istnieje. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Zrzut ekranu przedstawiający istniejący nazwę główną usługi.":::
   
6. Jeśli nie są zwracane żadne wyniki, utwórz nową nazwę główną.

>[!NOTE]
>Aby korzystać z pełnej możliwości usługi Dynamics 365 Customer Insights, zalecamy dodanie obu aplikacji do nazwy głównej usługi.<!--note from editor: Using the note format is suggested, just so this doesn't get lost by being tucked up in the step.-->

### <a name="create-a-new-service-principal"></a>Utwórz nową nazwę główną usługi
<!--note from editor: Some general formatting notes: The MWSG wants bold for text the user enters (in addition to UI strings and the settings users select), but there's plenty of precedent for using code format for entering text in PowerShell so I didn't change that. Note that italic should be used for placeholders, but not much else.-->
1. Zainstaluj najnowszą wersję programu Azure Active Directory PowerShell dla programu Graph. Aby uzyskać więcej informacji, przejdź do [instalacji programu Azure Active Directory PowerShell dla programu Graph](/powershell/azure/active-directory/install-adv2).

   1. Na komputerze wybierz klawisz Windows i wyszukaj program **Windows PowerShell** i wybierz opcję **Uruchom jako Administrator**.<!--note from editor: Or should this be something like "search for **Windows PowerShell** and, if asked, select **Run as administrator**."?-->
   
   1. W wyświetlonym oknie PowerShell wprowadź polecenie `Install-Module AzureAD`.

2. Utwórz nazwę główną usługi dla usługi Customer Insights przy użyciu modułu Azure AD PowerShell.

   1. W oknie PowerShell wprowadź polecenie `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Zamień *„[swój identyfikator dzierżawcy]”*<!--note from editor: Edit okay? Or should the quotation marks stay in the command line, in which case it would be "Replace *[your tenant ID]* --> na rzeczywisty identyfikator dzierżawcy, w którym ma zostać utworzyć główna nazwa usługi. Parametr nazwy środowiska, `AzureEnvironmentName`, jest opcjonalny.
  
   1. Wprowadź `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. To polecenie tworzy nazwę główną usługi dla analiz odbiorcy w wybranej dzierżawie. 

   1. Wprowadź `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. To polecenie tworzy nazwę główną usługi dla wyników analiz interakcji<!--note from editor: Edit okay?--> w wybranym dzierżawcy.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Udziel uprawnień do nazwy głównej usługi, aby uzyskać dostęp do konta magazynu

Przejdź do obszaru Azure portal, aby przyznać uprawnienia do nazwy głównej usługi dla konta magazynu, którego chcesz użyć w analizach odbiorców.

1. W tym celu należy przejść do [portalu administracyjnego Azure](https://portal.azure.com) i zalogować się do organizacji.

1. Otwórz konto magazynu, do którego chcesz, aby nazwa główna usługi miała dostęp do szczegółowych informacji o odbiorcach.

1. W lewym okienku wybierz opcję **Kontrola dostępu (IAM)**, a następnie wybierz opcję **Dodaj** > **Dodaj przypisanie roli**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Zrzut ekranu przedstawiający portal Azure Portal podczas dodawania przypisania roli.":::

1. W okienku **Dodaj przypisane roli** ustaw następujące właściwości:
   - Rola: **Współautor danych w usłudze Blob Storage**
   - Przypisz dostęp do: **Użytkownik, grupa lub nazwa główna usługi**
   - Wybierz: **Dynamics 365 AI dla Customer Insights** i **Dynamics 365 AI dla wyników analiz interakcji usługi Customer Insights** (dwie [nazwy główne usługi](#create-a-new-service-principal) wcześniej utworzone w tej procedurze)

1.  Wybierz pozycję **Zapisz**.

Rozpowszechnienie zmian może zająć do 15 minut.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Wprowadź identyfikator zasobu platformy Azure lub szczegóły subskrypcji platformy Azure w załączniku konta magazynu do wyników analiz odbiorców

Możesz<!--note from editor: Edit suggested only if this section is optional.--> dołączyć konto Data Lake Storage do wyników analiz odbiorców w celu [przechowywania danych wyjściowych](manage-environments.md) lub [użycia ich jako źródła danych](connect-common-data-service-lake.md). Ta opcja umożliwia wybór podejścia opartego na zasobach lub subskrypcji. W zależności od wybranego podejścia postępuj zgodnie z procedurą podaną w jednej z poniższych sekcji.<!--note from editor: Suggested.-->

### <a name="resource-based-storage-account-connection"></a>Połączenie z kontem magazynu oparte na zasobach

1. Przejdź do [portalu administrowania Azure](https://portal.azure.com), zaloguj się do subskrypcji i otwórz konto magazynu.

1. W lewym okienku wybierz pozycję **Właściwości** > **Ustawienia**.

1. Skopiuj wartość identyfikatora zasobu konta magazynu.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Skopiuj identyfikator zasobu konta magazynu.":::

1. W wynikach analiz odbiorców wstaw identyfikator zasobów w polu zasobów wyświetlanym na ekranie połączenia z kontem magazynu.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Wprowadź informacje o identyfikatorze zasobu konta magazynu.":::   

1. Kontynuuj pozostałe kroki w szczegółach dotyczących odbiorców, aby dołączyć konto magazynu.

### <a name="subscription-based-storage-account-connection"></a>Połączenie z kontem magazynu oparte na subskrypcji

1. Przejdź do [portalu administrowania Azure](https://portal.azure.com), zaloguj się do subskrypcji i otwórz konto magazynu.

1. W lewym okienku wybierz pozycję **Właściwości** > **Ustawienia**.

1. Przejrzyj **Subskrypcje**, **Grupa zasobów** i **Nazwa** konta magazynu, aby się upewnić, że wybierasz odpowiednie wartości w analizach odbiorcy.

1. W wynikach analiz odbiorców wybierz wartości dla odpowiednich pól podczas dołączania konta magazynu.

1. Kontynuuj pozostałe kroki w szczegółach dotyczących odbiorców, aby dołączyć konto magazynu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]