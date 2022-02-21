---
title: Połącz się z kontem Azure Data Lake Storage przy użyciu nazwy głównej usługi
description: Do łączenia się z własnym repozytorium data lake użyj nazwy głównej usługi Azure.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 1af01e5579f85d7c8bc8976a003f53ef2dd280d1
ms.sourcegitcommit: b7189b8621e66ee738e4164d4b3ce2af0def3f51
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2022
ms.locfileid: "8088160"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Połącz się z kontem Azure Data Lake Storage przy użyciu nazwy głównej usługi Azure

Ten artykuł omawia, jak połączyć Dynamics 365 Customer Insights z kontem Azure Data Lake Storage, używając nazwy głównej usługi Azure zamiast kluczy konta przechowywania. 

Zautomatyzowane narzędzia korzystające z usług platformy Azure powinny zawsze mieć ograniczone uprawnienia. Zamiast logowania się do aplikacji jako w pełni uprzywilejowany użytkownik, platforma Azure oferuje nazwy głównej usługi. Możesz użyć nazwy głównej usługi do bezpiecznego [dodania lub edycji folderu Common Data Model jako źródła danych](connect-common-data-model.md) lub [utworzenia lub aktualizacji środowiska](create-environment.md).

> [!IMPORTANT]
> - Konto usługi Data Lake Storage, które będzie korzystać z jednostki usługi, musi być typu Gen2 i mieć [włączoną hierarchiczną przestrzeń nazw](/azure/storage/blobs/data-lake-storage-namespace). Konta magazynu usługi Azure Data Lake Gen1 nie są obsługiwane.
> - Aby utworzyć nazwę główną usługi, potrzebujesz uprawnień administratora dla swojej subskrypcji Azure.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Utwórz nazwę główną usługi Azure dla rozwiązania Customer Insights

Przed utworzeniem nowej nazwy głównej usługi dla Customer Insights sprawdź, czy istnieje on już w twojej organizacji.

### <a name="look-for-an-existing-service-principal"></a>Poszukaj istniejącej nazwy głownej usługi

1. W tym celu należy przejść do [portalu administracyjnego Azure](https://portal.azure.com) i zalogować się do organizacji.

2. W opcji **Usługi Azure** wybierz **Azure Active Directory**.

3. W obszarze **Zarządzanie** wybierz pozycję **Aplikacje korporacyjne**.

4. Wyszukaj identyfikator aplikacji Microsoft:
   - Wyniki analiz odbiorców: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` o nazwie `Dynamics 365 AI for Customer Insights`
   - Wyniki analiz interakcji: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` o nazwie `Dynamics 365 AI for Customer Insights engagement insights`

5. Jeśli znaleziono pasujący rekord, oznacza to, że nazwa główna usługi już istnieje. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Zrzut ekranu przedstawiający istniejący nazwę główną usługi.":::
   
6. Jeśli nie są zwracane żadne wyniki, utwórz nową nazwę główną.

>[!NOTE]
>Aby korzystać z pełnej możliwości usługi Dynamics 365 Customer Insights, zalecamy dodanie obu aplikacji do nazwy głównej usługi.

### <a name="create-a-new-service-principal"></a>Utwórz nową nazwę główną usługi

1. Zainstaluj najnowszą wersję programu Azure Active Directory PowerShell dla programu Graph. Aby uzyskać więcej informacji, przejdź do [instalacji programu Azure Active Directory PowerShell dla programu Graph](/powershell/azure/active-directory/install-adv2).

   1. Na komputerze wybierz klawisz Windows i wyszukaj program **Windows PowerShell** i wybierz opcję **Uruchom jako Administrator**.
   
   1. W wyświetlonym oknie PowerShell wprowadź polecenie `Install-Module AzureAD`.

2. Utwórz nazwę główną usługi dla usługi Customer Insights przy użyciu modułu Azure AD PowerShell.

   1. W oknie PowerShell wprowadź polecenie `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Zastąp *[identyfikator dzierżawcy]* rzeczywistym identyfikatorem dzierżawcy, w którym chcesz utworzyć jednostkę usługi. Parametr nazwy środowiska, `AzureEnvironmentName`, jest opcjonalny.
  
   1. Wprowadź `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. To polecenie tworzy nazwę główną usługi dla analiz odbiorcy w wybranej dzierżawie. 

   1. Wprowadź `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. To polecenie tworzy nazwę główną usługi dla szczegółowych informacji o odbiorcach w ramach wybranego dzierżawcy.

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

Możesz dołączyć konto Data Lake Storage do szczegółowych informacji o odbiorcach w celu [przechowywania danych wyjściowych](manage-environments.md) lub [użycia ich jako źródła danych](connect-common-data-service-lake.md). Ta opcja umożliwia wybór podejścia opartego na zasobach lub subskrypcji. W zależności od wybranego podejścia postępuj zgodnie z procedurą podaną w jednej z poniższych sekcji.

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
