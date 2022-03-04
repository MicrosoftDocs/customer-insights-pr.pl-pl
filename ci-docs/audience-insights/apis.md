---
title: Praca z API
description: Korzystanie z interfejsów API i zrozumienie ograniczeń.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: b1e022f8afb8b7dbb707636009b6a25ee242a4e0
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354798"
---
# <a name="work-with-customer-insights-apis"></a>Pracuj z interfejsami API Customer Insights

Dynamics 365 Customer Insights oferuje interfejsy API do tworzenia własnych aplikacji na podstawie danych z aplikacji Customer Insights.

> [!IMPORTANT]
> Szczegółowe informacje o tych interfejsach API są wymienione w [Kompendium interfejsów API Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Zawierają one dodatkowe informacje na temat operacji i parametrów oraz odpowiedzi.

Ten artykuł opisuje, jak uzyskać dostęp do interfejsów API Customer Insights, utworzyć aplikację Azure App Registration i rozpocząć pracę z dostępnymi bibliotekami klienckimi.

## <a name="get-started-trying-the-customer-insights-apis"></a>Rozpoczynanie korzystania z interfejsów API Customer Insights

1. [Zaloguj się](https://home.ci.ai.dynamics.com) do aplikacji Customer Insights. Jeśli nie dysponujesz jeszcze subskrypcją, [Załóż konto w celu rozpoczęcia wersji próbnej Customer Insights](https://aka.ms/tryci).

1. Aby włączyć interfejsy API w środowisku Customer Insights, przejdź do **Administrator** > **Uprawnienia**. Konieczne są więc uprawnienia administratora.

1. Przejdź do **karty interfejsy API** i wybierz przycisk **Włącz**.    
 
   Włączenie interfejsów API powoduje utworzenie podstawowego i dodatkowego klucza subskrypcji dla Twojej instancji, który jest używany w żądaniach API. Klucze można wygenerować ponownie, wybierając z listy ponowne **Wygeneruj ponownie podstawowy** lub **Wygeneruj ponownie pomocniczy** w **Administrator** > **Uprawnienia** > **Interfejsy API**.

<!--  :::image type="content" source="media/enable-apis.gif" alt-text="Enable Customer Insights APIs."::: -->

1. Zaznacz opcję **Poznaj nasze interfejsy API** w celu [wypróbowania interfejsów API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Wybierz operację interfejsu API i wybierz opcję **Wypróbuj tę funkcję**.

1. W okienku bocznym ustaw wartość w menu rozwijaną **Autoryzacja** na **niejawna**. Nagłówek `Authorization` jest dodawany z tokenem elementu nośnego. Klucz subskrypcji zostanie wypełniony automatycznie.
  
1. Można też dodać wszystkie wymagane parametry zapytania.

1. Przewiń w dół do końca okienka bocznego i wybierz opcję **Wyślij**.

Odpowiedź HTTP będzie wkrótce widoczna poniżej.

<!--   :::image type="content" source="media/try-apis.gif" alt-text="How to test the APIs."::: -->

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Utwórz nową rejestrację aplikacji w witrynie Azure Portal

Te kroki pomogą Ci rozpocząć korzystanie z interfejsów API Customer Insights w aplikacji Azure przy użyciu delegowanych uprawnień. Upewnij się, że najpierw wykonasz czynności z [sekcji Wprowadzenie](#get-started-trying-the-customer-insights-apis).

1. Zaloguj się w [witrynie Azure Portal](https://portal.azure.com), korzystając z konta, które może mieć dostęp do danych Customer Insights.

1. W lewym okienku wybierz pozycję **Rejestracja aplikacji**.

1. Wybierz **Nowa rejestracja**, podaj nazwę aplikacji i wybierz typ konta.
 
   Opcjonalnie dodaj przekierowanie. http://localhost jest wystarczający do projektowania aplikacji na komputerze lokalnym.

1. W nowej rejestracji aplikacji przejdź do **uprawnienia interfejsu API**.

<!--   :::image type="content" source="media/app-registration-1.gif" alt-text="How to set API permissions in App registration."::: -->

1. Zaznacz pole wyboru **Dodaj uprawnienie** i w okienku bocznym wybierz pozycję **Customer Insights**.

1. Dla **Typu uprawnienia** wybierz **Uprawnienia delegowane**, a następnie wybierz uprawnienie **user_impersonation**.

1. Wybierz **Przyznaj uprawnienia**. Jeśli chcesz uzyskać dostęp do interfejsu API bez logowania się użytkownika, zapoznaj się z sekcją [Uprawnienia aplikacji serwer-serwer](#server-to-server-application-permissions).

1. Wybierz opcję **Udziel administratorowi zgodę na...**, aby zakończyć rejestrację aplikacji.

Możesz użyć identyfikatora aplikacji/klienta do rejestracji tej aplikacji z biblioteką uwierzytelniania firmy Microsoft (MSAL), aby uzyskać token okaziciela do wysłania z żądaniem do interfejsu API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Aby uzyskać więcej informacji na temat MSAL, zobacz [Omówienie biblioteki uwierzytelniania Microsoft (MSAL)](/azure/active-directory/develop/msal-overview).

Aby uzyskać więcej informacji na temat rejestracji aplikacji na platformie Azure, zobacz [Rejestrowanie aplikacji](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).

Aby uzyskać więcej informacji na temat korzystania z interfejsów API w naszych bibliotekach klienckich, zobacz [biblioteki klienckie aplikacji Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Uprawnienia dotyczące aplikacji serwera do serwera

[Sekcja rejestracji aplikacji](#create-a-new-app-registration-in-the-azure-portal) zawiera informacje na temat sposobu zarejestrowania aplikacji, która wymaga zalogowania się użytkownika w celu uwierzytelnienia. Dowiedz się, jak utworzyć rejestrację aplikacji, która nie wymaga interakcji użytkownika i może być uruchamiana na serwerze.

1. W rejestracji aplikacji w portalu Azure Portal wybierz opcję **uprawnienia interfejsu API**.

1. Wybierz **Dodaj uprawnienie**. 

1. Wybierz z listy **interfejsy API używane przez organizację** i wybierz pozycję **Dynamics 365 AI dla Customer Insights**. 

1. Dla **typu Uprawnienia** wybierz **Uprawnienia aplikacji**, a następnie wybierz uprawnienie **CustomerInsights.Api.All**.

1. Wybierz **Przyznaj uprawnienia**.

1. Aby zobaczyć rejestrację aplikacji wróć do **uprawnienia interfejsu API**.

1. Wybierz opcję **Udziel administratorowi zgodę na...**, aby zakończyć rejestrację aplikacji.

 <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Na koniec musimy dodać nazwę rejestracji aplikacji jako użytkownika w Customer Insights.  
   
   Otwórz Customer Insights, przejdź do **Administrator** > **Uprawnienia** i wybierz **Dodaj użytkownika**.

1. Wyszukaj nazwę rejestracji swojej aplikacji, wybierz ją z listy wyników wyszukiwania i wybierz pozycję **Zapisz**.

## <a name="customer-insights-client-libraries"></a>Biblioteki klientów Customer Insights

Ta sekcja ułatwia rozpoczęcie korzystania z bibliotek klienta dostępnych dla interfejsów API usługi Customer Insights. Cały kod źródłowy biblioteki oraz przykładowe aplikacje można znaleźć na [stronie GitHub aplikacji Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Dowiedz się jak rozpocząć pracę za pomocą klienta C# bibliotek z NuGet.org. Aby uzyskać więcej informacji o pakiecie NuGet, zobacz [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Obecnie ten pakiet jest przeznaczony dla struktur netstandard2.0 i netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Dodawanie biblioteki klienta C# do projektu C#

1. W Visual Studio otwórz **Menedżera pakietów NuGet** dla swojego projektu.

1. Wyszukaj **Microsoft.Dynamics.CustomerInsights.Api**.

1. Wybierz **Zainstaluj**, aby dodać pakiet do projektu.
 
   Można też uruchomić to polecenie w **konsoli Menedżer pakietów NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

 <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Korzystanie z biblioteki klienta C#

1. Użyj [biblioteki uwierzytelniania firmy Microsoft (MSAL)](/azure/active-directory/develop/msal-overview), aby uzyskać możliwość `AccessToken` za pomocą istniejącej [rejestracji aplikacji Azure](#create-a-new-app-registration-in-the-azure-portal).

1. Po pomyślnym uwierzytelnieniu i pobraniu tokenu można utworzyć nowy lub użyć istniejącego elementu `HttpClient` z dodatkowym elementem **„Autoryzacja” DefaultRequestHeaders** ustawionym na **„Token dostępu” elementu nośnego** i elementem **Ocp-Apim-Subscription-Key** ustawionym na [**klucz subskrypcji** ze środowiska aplikacji Customer Insights](#get-started-trying-the-customer-insights-apis).   
 
   Nagłówek **Autoryzacji** jest resetowany w zależności od potrzeb. Na przykład ważność tokenu wygasła.

1. Przekaż `HttpClient` do konstrukcji klienta `CustomerInsights`.

<!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Wywołaj z klientem „metody rozszerzające”, na przykład `GetAllInstancesAsync`. Jeśli preferowany jest dostęp do bazowego `Microsoft.Rest.HttpOperationResponse`, użyj „metod wiadomości http”, na przykład `GetAllInstancesWithHttpMessagesAsync`.

1. Odpowiedź będzie prawdopodobnie typu `object`, ponieważ metoda może zwracać wiele typów (na przykład `IList<InstanceInfo>` i `ApiErrorResult`). Aby sprawdzić zwracany typ, można bezpiecznie rzutować obiekty do typów odpowiedzi określonych na [stronie szczegółów interfejsu API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) dla tej operacji.    
   
   Jeśli potrzeba więcej informacji na temat żądania, użyj **metod wiadomości http**, aby uzyskać dostęp do surowego obiektu odpowiedzi.

### <a name="nodejs-package"></a>Pakiet NodeJS

Korzystaj z bibliotek klientów NodeJS dostępnych za pośrednictwem NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Pakiet języka Python

Korzystaj z bibliotek klientów Python dostępnych za pośrednictwem PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE[footer-include](../includes/footer-banner.md)]
