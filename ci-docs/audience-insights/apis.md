---
title: Praca z API
description: Korzystanie z interfejsów API i zrozumienie ograniczeń.
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a03e916676800afdd8692da865a1060952d5c4f
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689143"
---
# <a name="work-with-customer-insights-apis"></a>Pracuj z interfejsami API Customer Insights

Dynamics 365 Customer Insights udostępnia interfejsy API umożliwiające konstruowanie własnych aplikacji na podstawie danych z Customer Insights.

> [!IMPORTANT]
> Szczegółowe informacje o tych interfejsach API są wymienione w [Kompendium interfejsów API Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Zawierają one dodatkowe informacje na temat operacji i parametrów oraz odpowiedzi.

Ten artykuł zawiera instrukcje dotyczące dostępu do interfejsów API usługi Customer Insights, tworzenia rejestracji aplikacji platformy Azure i rozpoczynania pracy z dostępnymi bibliotekami klienckimi.

## <a name="get-started-trying-the-customer-insights-apis"></a>Rozpoczynanie korzystania z interfejsów API Customer Insights

1. [Zaloguj się](https://home.ci.ai.dynamics.com) do aplikacji Customer Insights. Jeśli nie dysponujesz jeszcze subskrypcją, [Załóż konto w celu rozpoczęcia wersji próbnej Customer Insights](https://aka.ms/tryci).

1. Aby włączyć interfejsy API w środowisku Customer Insights, przejdź do **Administrator** > **Uprawnienia**. Konieczne są więc uprawnienia administratora.

1. Przejdź do **karty interfejsy API** i wybierz przycisk **Włącz**.    
   Włączenie interfejsów API powoduje utworzenie podstawowego i dodatkowego klucza subskrypcji dla Twojej instancji, który jest używany w żądaniach API. Klucze można wygenerować ponownie, wybierając z listy ponowne **Wygeneruj ponownie podstawowy** lub **Wygeneruj ponownie pomocniczy** w **Administrator** > **Uprawnienia** > **Interfejsy API**.

   :::image type="content" source="media/enable-apis.gif" alt-text="Włącz interfejsy API Customer Insights":::

1. Zaznacz opcję **Poznaj nasze interfejsy API** w celu wypróbowania interfejsów API.

1. Wybierz operację interfejsu API i wybierz opcję **Wypróbuj tę funkcję**.

1. W okienku bocznym ustaw wartość w menu rozwijanym **Autoryzacja** na **domniemany**. Nagłówek `Authorization` jest dodawany wraz z dodanym tokenem okaziciela. Klucz subskrypcji zostanie wypełniony automatycznie.
  
1. Można też dodać wszystkie wymagane parametry zapytania.

1. Przewiń w dół do końca okienka bocznego i wybierz opcję **Wyślij**.

Odpowiedź HTTP będzie wkrótce widoczna poniżej.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Utwórz nową rejestrację aplikacji w witrynie Azure Portal

Te kroki ułatwiają rozpoczęcie korzystania z interfejsów API usługi Customer Insights w aplikacji platformy Azure przy użyciu uprawnień delegowanych. W pierwszej kolejności upewnij się, że [sekcją Rozpocznij pracę](#get-started-trying-the-customer-insights-apis).

1. Zaloguj się w [witrynie Azure Portal](https://portal.azure.com), korzystając z konta, które może mieć dostęp do danych Customer Insights.

1. W lewym okienku wybierz pozycję **Rejestracja aplikacji**.

1. Wybierz **Nowa rejestracja**, podaj nazwę aplikacji i wybierz typ konta.
   Opcjonalnie dodaj przekierowanie. http://localhost jest wystarczający do projektowania aplikacji na komputerze lokalnym.

1. W nowej rejestracji aplikacji przejdź do **uprawnienia interfejsu API**.

1. Zaznacz pole wyboru **Dodaj uprawnienie** i w okienku bocznym wybierz pozycję **Customer Insights**.

1. W przypadku **Typu uprawnienia** Wybierz opcję **Uprawnienia delegowane** i wybierz uprawnienie **user_impersonation**.

1. Wybierz **Przyznaj uprawnienia**. Jeśli chcesz uzyskać dostęp do interfejsu API bez logowania się użytkownika, zapoznaj się z sekcją [Uprawnienia aplikacji serwer-serwer](#server-to-server-application-permissions).

1. Wybierz opcję **Udziel administratorowi zgodę na...**, aby zakończyć rejestrację aplikacji.

Możesz użyć identyfikatora aplikacji/klienta do rejestracji tej aplikacji z biblioteką uwierzytelniania firmy Microsoft (MSAL), aby uzyskać token okaziciela do wysłania z żądaniem do interfejsu API.

Aby uzyskać więcej informacji na temat MSAL, zobacz [Omówienie biblioteki uwierzytelniania Microsoft (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).

Aby uzyskać więcej informacji na temat rejestracji aplikacji w Azure, zobacz [Nowy interfejs usługi Azure Portal App Registration](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).

Informacje o korzystaniu z interfejsów API naszych bibliotek klientów znajduje się w artykule [Biblioteki klienta usługi Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Uprawnienia dotyczące aplikacji serwera do serwera

[Sekcja rejestracji aplikacji](#create-a-new-app-registration-in-the-azure-portal) zawiera informacje na temat sposobu zarejestrowania aplikacji, która wymaga zalogowania się użytkownika w celu uwierzytelnienia. Dowiedz się, jak utworzyć rejestrację aplikacji, która nie wymaga interakcji użytkownika i może być uruchamiana na serwerze.

1. W rejestracji aplikacji w portalu Azure Portal wybierz opcję **uprawnienia interfejsu API**.

1. Zaznacz pole wyboru **Dodaj uprawnienie** i w okienku bocznym wybierz pozycję **Customer Insights**.

1. W przypadku **Typu uprawnienia** Wybierz opcję **Uprawnienia do aplikacji** i wybierz uprawnienie **CustomerInsights.Api.All**.

1. Wybierz **Przyznaj uprawnienia**.

1. Aby przyznać administratorowi uprawnienie zgody na tę aplikację, należy dodać nazwę główną usługi.

   1. Zainstaluj moduł Azure Active Directory (AD) PowerShell: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`
   1. Nawiąż połączenie ze swoim kontem AD: `Connect-AzureAD -TenantId <your tenant id>`. Identyfikator dzierżawy można znaleźć na ekranie **Omówienie** > **Azure Active Directory**.
   1. Aby dodać nazwę główną usługi, należy uruchomić następujące polecenie Azure AD: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` parametr AppID jest związany z interfejsem API aplikacji Customer Insights.

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Przykład głównej nazwy usługi":::

1. Aby zobaczyć rejestrację aplikacji wróć do **uprawnienia interfejsu API**.

1. Wybierz opcję **Udziel administratorowi zgodę na...**, aby zakończyć rejestrację aplikacji.

1. Na koniec musimy dodać nazwę rejestracji aplikacji jako użytkownika w Customer Insights.    
   Otwórz Customer Insights, przejdź do **Administrator** > **Uprawnienia** i wybierz **Dodaj użytkownika**.

1. Wyszukaj nazwę rejestracji swojej aplikacji, wybierz ją z listy wyników wyszukiwania i wybierz pozycję **Zapisz**.

## <a name="customer-insights-client-libraries"></a>Biblioteki klientów Customer Insights

Ta sekcja ułatwia rozpoczęcie korzystania z bibliotek klienta dostępnych dla interfejsów API usługi Customer Insights.

### <a name="c-nuget"></a>C# NuGet

Dowiedz się jak rozpocząć pracę za pomocą klienta C# bibliotek z NuGet.org. Aby uzyskać więcej informacji o pakiecie NuGet, zobacz [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Obecnie ten pakiet jest przeznaczony dla struktur netstandard2.0 i netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Dodawanie biblioteki klienta C# do projektu C#

1. W Visual Studio otwórz **Menedżera pakietów NuGet** dla swojego projektu.

1. Wyszukaj **Microsoft.Dynamics.CustomerInsights.Api**.

1. Wybierz **Zainstaluj**, aby dodać pakiet do projektu.
   Można też uruchomić to polecenie w **konsoli Menedżer pakietów NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Dodawanie pakietu NuGet do projektu Visual Studio":::

#### <a name="use-the-c-client-library"></a>Korzystanie z biblioteki klienta C#

1. Użyj [biblioteki uwierzytelniania firmy Microsoft (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview), aby uzyskać możliwość `AccessToken` za pomocą istniejącej [rejestracji aplikacji Azure](#create-a-new-app-registration-in-the-azure-portal).

1. Po pomyślnym uwierzytelnieniu i uzyskaniu tokena utwórz nowy lub użyj istniejącego `HttpClient` z dodatkowym **DefaultRequestHeaders "Authorization"** ustawionym na **Element nośny <access token>** i **Ocp-Apim-Subscription-Key** ustawiony na [**klucz subskrypcji** ze środowiska Customer Insights](#get-started-trying-the-customer-insights-apis).    
   Nagłówek **Autoryzacji** jest resetowany w zależności od potrzeb. Na przykład ważność tokenu wygasła.

1. Przekaż `HttpClient` do konstrukcji klienta `CustomerInsights`.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Przykład httpclient":::

1. Wywołaj z klientem „metody rozszerzające”, na przykład `GetAllInstancesAsync`. Jeśli preferowany jest dostęp do bazowego `Microsoft.Rest.HttpOperationResponse`, użyj „metod wiadomości http”, na przykład `GetAllInstancesWithHttpMessagesAsync`.

1. Odpowiedź będzie prawdopodobnie typu `object`, ponieważ metoda może zwracać wiele typów (na przykład `IList<InstanceInfo>` i `ApiErrorResult`). Aby sprawdzić zwracany typ, można bezpiecznie rzutować obiekty do typów odpowiedzi określonych na [stronie szczegółów interfejsu API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) dla tej operacji.    
   Jeśli potrzeba więcej informacji na temat żądania, użyj **metod wiadomości http**, aby uzyskać dostęp do surowego obiektu odpowiedzi.
