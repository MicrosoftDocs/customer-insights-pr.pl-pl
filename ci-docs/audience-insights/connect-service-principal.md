---
title: Połącz się z kontem Azure Data Lake Storage Gen2 przy użyciu nazwy głównej usługi
description: Użyj głównej usługi Azure, aby uzyskać szczegółowe informacje o odbiorcach, aby połączyć się z własnym data lake podczas dołączania go do szczegółowych informacji o odbiorcach.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eebbac1370a847869d98beaf70db49b809d762e7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267735"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>Połącz analizy odbiorców z kontem Azure Data Lake Storage Gen2 za pomocą głównej usługi platformy Azure

Zautomatyzowane narzędzia korzystające z usług platformy Azure powinny zawsze mieć ograniczone uprawnienia. Zamiast logowania się do aplikacji jako w pełni uprzywilejowany użytkownik, platforma Azure oferuje nazwy głównej usługi. Czytaj dalej, aby dowiedzieć się, jak połączyć szczegółowe informacje o odbiorcach z kontem Azure Data Lake Storage Gen2 przy użyciu nazwy głównej usługi usługi platformy Azure zamiast kluczy konta magazynu. 

Możesz użyć nazwy głównej usługi, aby bezpiecznie [dodać lub edytować folder Common Data Model](connect-common-data-model.md) jako źródło danych lub [utworzyć nowe lub zaktualizować istniejące środowisko](manage-environments.md#create-an-environment-in-an-existing-organization).

> [!IMPORTANT]
> - Konto magazynu Azure Data Lake Gen2, które ma używać jednostki usługi, musi mieć [włączoną funkcję Hierarchiczna przestrzeń nazw (HNS)](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).
> - Aby utworzyć nazwę główną usługi, trzeba mieć uprawnienia administratora w ramach Twojej subskrypcji platformy Azure.

## <a name="create-azure-service-principal-for-audience-insights"></a>Utwórz nazwę głównej usługi Azure do analiz odbiorców

Przed utworzeniem nowej nazwy głównej usługi na potrzeby statystyk odbiorców sprawdź, czy już istnieje w Twojej organizacji.

### <a name="look-for-an-existing-service-principal"></a>Poszukaj istniejącej nazwy głownej usługi

1. W tym celu należy przejść do [portalu administracyjnego Azure](https://portal.azure.com) i zalogować się do organizacji.

2. Wybierz **Azure Active Directory** z usług Azure.

3. W obszarze **Zarządzanie** wybierz pozycję **Aplikacje korporacyjne**.

4. Wyszukaj własny identyfikator aplikacji analizy odbiorców `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` lub nazwę `Dynamics 365 AI for Customer Insights`.

5. Jeśli znajdziesz pasujący rekord, oznacza to, że istnieje jednostka usługi dla szczegółowych informacji o odbiorcach. Nie musisz go ponownie tworzyć.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Zrzut ekranu pokazujący istniejącą nazwę główną usługi.":::
   
6. Jeśli nie są zwracane żadne wyniki, utwórz nową nazwę główną.

### <a name="create-a-new-service-principal"></a>Utwórz nową nazwę główną usługi

1. Zainstaluj najnowszą wersję **Azure Active Directory PowerShell for Graph**. Aby uzyskać więcej informacji, zobacz temat [Instalowanie Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).
   - Na komputerze wybierz klawisz Windows na klawiaturze i wyszukaj **Windows PowerShell** i **Uruchom jako administrator**.
   
   - W wyświetlonym oknie PowerShell wprowadź polecenie `Install-Module AzureAD`.

2. Utwórz nazwę główną usługi dla analizy odbiorców z modułem Azure AD PowerShell.
   - W oknie PowerShell wprowadź polecenie `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Zastąp „identyfikator dzierżawy” rzeczywisty identyfikator dzierżawy, w której chcesz utworzyć jednostkę usługi. Parametr nazwy środowiska `AzureEnvironmentName` jest opcjonalny.
  
   - Wprowadź `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. To polecenie tworzy nazwę główną usługi dla analiz odbiorcy w wybranej dzierżawie.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Udziel uprawnień do nazwy głównej usługi, aby uzyskać dostęp do konta magazynu

Przejdź do obszaru Azure portal, aby przyznać uprawnienia do nazwy głównej usługi dla konta magazynu, którego chcesz użyć w analizach odbiorców.

1. W tym celu należy przejść do [portalu administracyjnego Azure](https://portal.azure.com) i zalogować się do organizacji.

1. Otwórz konto magazynu, do którego chcesz, aby nazwa główna usługi miała dostęp do szczegółowych informacji o odbiorcach.

1. Wybierz pozycję **Kontrola dostępu (IAM)** z okienka nawigacji i wybierz pozycję **Dodaj** > **Dodaj przypisanie roli**.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Zrzut ekranu pokazujący Portal Azure podczas dodawania przypisania roli.":::
   
1. W okienku **Dodawanie przypisania roli** ustaw następujące właściwości:
   - Rola: *Współautor danych w usłudze Blob Storage*
   - Przypisz dostęp do: *Użytkownik, grupa lub nazwa główna usługi*
   - Zaznacz: *Dynamics 365 AI for Customer Insights* ([utworzona nazwa główna usługi](#create-a-new-service-principal))

1.  Wybierz pozycję **Zapisz**.

Rozpowszechnienie zmian może zająć do 15 minut.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Wprowadź identyfikator zasobu platformy Azure lub szczegóły subskrypcji platformy Azure w załączniku konta magazynu do usługi analiz odbiorców.

Dołącz konto magazynowe Azure Data Lake w analizach odbiorców do [przechowywania danych wyjściowych](manage-environments.md) lub [używania jako źródła danych](connect-common-data-service-lake.md). Wybranie opcji Azure Data Lake umożliwia wybranie podejścia opartego na zasobach lub subskrypcji.

Wykonaj poniższe czynności, aby podać wymagane informacje na temat wybranego podejścia.

### <a name="resource-based-storage-account-connection"></a>Połączenie z kontem magazynu oparte na zasobach

1. Przejdź do [portalu administrowania Azure](https://portal.azure.com), zaloguj się do subskrypcji i otwórz konto magazynu.

1. Wybierz **Ustawienia** > **Właściwości** w okienku nawigacji.

1. Skopiuj wartość identyfikatora zasobu konta magazynu.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Skopiuj identyfikator zasobu konta magazynu.":::

1. W szczegółach dotyczących odbiorców wstaw identyfikator zasobu w polu zasobu wyświetlanym na ekranie połączenia konta magazynu.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Wprowadź informacje o identyfikatorze zasobu konta magazynu.":::   
   
1. Kontynuuj pozostałe kroki w szczegółach dotyczących odbiorców, aby dołączyć konto magazynu.

### <a name="subscription-based-storage-account-connection"></a>Połączenie z kontem magazynu oparte na subskrypcji

1. Przejdź do [portalu administrowania Azure](https://portal.azure.com), zaloguj się do subskrypcji i otwórz konto magazynu.

1. Wybierz **Ustawienia** > **Właściwości** w okienku nawigacji.

1. Przejrzyj **Subskrypcje**, **Grupa zasobów** i **Nazwa** konta magazynu, aby się upewnić, że wybierasz odpowiednie wartości w analizach odbiorcy.

1. W szczegółach dotyczących odbiorców wybierz wartości lub odpowiednie pola podczas dołączania konta magazynu.
   
1. Kontynuuj pozostałe kroki w szczegółach dotyczących odbiorców, aby dołączyć konto magazynu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]