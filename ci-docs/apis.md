---
title: Pracuj z interfejsami API Customer Insights
description: Korzystanie z interfejsów API i zrozumienie ograniczeń.
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387353"
---
# <a name="work-with-customer-insights-apis"></a>Pracuj z interfejsami API Customer Insights

Dynamics 365 Customer Insights oferuje interfejsy API do tworzenia własnych aplikacji na podstawie danych z aplikacji Customer Insights.

> [!IMPORTANT]
> Szczegółowe informacje o tych interfejsach API są wymienione w [Kompendium interfejsów API Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Zawierają one dodatkowe informacje na temat operacji i parametrów oraz odpowiedzi.

Spróbuj skorzystać z interfejsów API Customer Insights, utworzyć rejestrację Azure App i rozpocząć pracę z bibliotekami klienckimi.

## <a name="get-started-trying-the-customer-insights-apis"></a>Rozpoczynanie korzystania z interfejsów API Customer Insights

Włącz interfejsy API Customer Insights i wypróbuj je. Administrator Customer Insights musi włączyć dostęp API do Customer Insights. Po włączeniu dostępu każdy użytkownik może używać interfejsu API z kluczem subskrypcji.

1. [Zaloguj się](https://home.ci.ai.dynamics.com) do aplikacji Customer Insights. Jeśli nie dysponujesz jeszcze subskrypcją, [Załóż konto w celu rozpoczęcia wersji próbnej Customer Insights](https://aka.ms/tryci).

1. Przejdź do pozycji **Administracja** > **Zabezpieczenia** > i wybierz kartę **Interfejsy API**.

1. Jeśli dostęp interfejsu API do środowiska nie został ustawiony, wybierz opcję **Włącz**.

   Włączenie interfejsów API powoduje utworzenie podstawowego i dodatkowego klucza subskrypcji dla Twojej instancji, który jest używany w żądaniach API. Możesz ponownie wygenerować klucze, wybierając **Regeneruj podstawową** lub **Regeneruj drugorzędną** na karcie **Interfejsy API**.

1. Zaznacz opcję [**Poznaj nasze interfejsy API**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) w celu wypróbowania interfejsów API.

1. Wyszukaj i wybierz operację interfejsu API i wybierz opcję **Wypróbuj**.

   :::image type="content" source="media/try-api.png" alt-text="Jak przetestować interfejsy API.":::

1. W okienku bocznym ustaw wartość w menu rozwijaną **Autoryzacja** na **niejawna**. Nagłówek `Authorization` jest dodawany z tokenem elementu nośnego. Klucz subskrypcji zostanie wypełniony automatycznie.
  
1. Można też dodać wszystkie wymagane parametry zapytania.

1. Przewiń w dół do końca okienka bocznego i wybierz opcję **Wyślij**.

   Odpowiedź HTTP zostanie wyświetlona u dołu okienka.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Utwórz nową rejestrację aplikacji w witrynie Azure Portal

Utwórz nową [rejestrację aplikacji](/graph/auth-register-app-v2), aby korzystać z interfejsów API Customer Insights w aplikacji platformy Azure przy użyciu delegowanych uprawnień.

1. Wykonaj czynności z [sekcji Wprowadzenie](#get-started-trying-the-customer-insights-apis).

1. Zaloguj się w [witrynie Azure Portal](https://portal.azure.com), korzystając z konta, które może mieć dostęp do danych Customer Insights.

1. Wyszukaj i wybierz **Rejestracje aplikacji**.

1. Wybierz **Nowa rejestracja**, podaj nazwę aplikacji i wybierz typ konta.

   Opcjonalnie dodaj przekierowanie. http://localhost jest wystarczający do projektowania aplikacji na komputerze lokalnym.

1. Wybierz pozycję **Zarejestruj**.

1. W nowej rejestracji aplikacji przejdź do **uprawnienia interfejsu API**.

1. Wybierz opcję **Dodaj uprawnienie** i w okienku bocznym wybierz pozycję **AI usługi Dynamics 365 for Customer Insights**.

1. Dla **Typu uprawnienia** wybierz **Uprawnienia delegowane**, a następnie wybierz uprawnienie **user_impersonation**.

1. Wybierz **Przyznaj uprawnienia**.

1. Wybierz opcję **Udziel administratorowi zgodę na...**, aby zakończyć rejestrację aplikacji.

1. Jeśli chcesz uzyskać dostęp do interfejsu API bez logowania się użytkownika, przejdź do [Uprawnienia aplikacji serwer-serwer](#server-to-server-application-permissions).

Możesz użyć identyfikatora aplikacji/klienta do rejestracji tej aplikacji z [biblioteką uwierzytelniania firmy Microsoft (MSAL)](/azure/active-directory/develop/msal-overview), aby uzyskać token okaziciela do wysłania z żądaniem do interfejsu API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Aby uzyskać więcej informacji na temat korzystania z interfejsów API w naszych bibliotekach klienckich, zobacz [biblioteki klienckie aplikacji Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Uprawnienia dotyczące aplikacji serwera do serwera

Stwórz aplikację rejestracyjną, która nie wymaga interakcji z użytkownikiem i może być uruchomiona na serwerze.

1. W rejestracji aplikacji w portalu Azure Portal wybierz opcję **uprawnienia interfejsu API**.

1. Wybierz **Dodaj uprawnienie**.

1. Wybierz z listy **interfejsy API używane przez organizację** i wybierz pozycję **Dynamics 365 AI dla Customer Insights**.

1. Dla **typu Uprawnienia** wybierz **Uprawnienia aplikacji**, a następnie wybierz uprawnienie **CustomerInsights.Api.All**.

1. Wybierz **Przyznaj uprawnienia**.

1. Aby zobaczyć rejestrację aplikacji wróć do **uprawnienia interfejsu API**.

1. Wybierz opcję **Udziel administratorowi zgodę na...**, aby zakończyć rejestrację aplikacji.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Dodaj nazwę rejestracji aplikacji jako użytkownika w Customer Insights.

   1. Otwórz usługę Customer Insights, przejdź do **Administrator** > **Zabezpieczenia** i wybierz opcję **Dodaj użytkowników**.

   1. Wyszukaj nazwę rejestracji swojej aplikacji, wybierz ją z listy wyników wyszukiwania i wybierz pozycję **Zapisz**.

## <a name="sample-queries"></a>Przykładowe zapytania

Zebraliśmy krótką listę przykładowych zapytań OData, które mogą współpracować z interfejsami API, zobacz [Przykłady zapytań OData](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>Biblioteki klientów Customer Insights

Zacznij korzystać z bibliotek klienta dostępnych dla interfejsów API Customer Insights. Cały kod źródłowy biblioteki oraz przykładowe aplikacje można znaleźć na [stronie GitHub aplikacji Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).

### <a name="c-nuget"></a>C# NuGet

Użyj bibliotek klienta C# z NuGet.org. Obecnie pakiet jest przeznaczony dla frameworków netstandard2.0 i netcoreapp2.0. Aby uzyskać więcej informacji na temat pakietu NuGet, zobacz [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).

#### <a name="add-the-c-client-library-to-a-c-project"></a>Dodawanie biblioteki klienta C# do projektu C#

1. W Visual Studio otwórz **Menedżera pakietów NuGet** dla swojego projektu.

1. Wyszukaj **Microsoft.Dynamics.CustomerInsights.Api**.

1. Wybierz **Zainstaluj**, aby dodać pakiet do projektu.

   Można też uruchomić to polecenie w **konsoli Menedżer pakietów NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Korzystanie z biblioteki klienta C#

1. Użyj [biblioteki uwierzytelniania firmy Microsoft (MSAL)](/azure/active-directory/develop/msal-overview), aby uzyskać możliwość `AccessToken` za pomocą istniejącej [rejestracji aplikacji Azure](#create-a-new-app-registration-in-the-azure-portal).

1. Po pomyślnym uwierzytelnieniu i zdobyciu tokena, utwórz nowego lub użyj istniejącego `HttpClient` z **DefaultRequestHeaders "Authorization "** ustawionym na **Bearer "access token "** i **Ocp-Apim-Subscription-Key** ustawionym na [**klucz subskrypcji** z twojego środowiska Customer Insights](#get-started-trying-the-customer-insights-apis).   

   Nagłówek **Autoryzacji** jest resetowany w zależności od potrzeb. Na przykład ważność tokenu wygasła.

1. Przekaż `HttpClient` do konstrukcji klienta `CustomerInsights`.

   <!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Wywołaj z klientem „metody rozszerzające”, na przykład `GetAllInstancesAsync`. Jeśli preferowany jest dostęp do bazowego `Microsoft.Rest.HttpOperationResponse`, użyj „metod wiadomości http”, na przykład `GetAllInstancesWithHttpMessagesAsync`.

1. Odpowiedź będzie prawdopodobnie typu `object`, ponieważ metoda może zwracać wiele typów (na przykład `IList<InstanceInfo>` i `ApiErrorResult`). Aby sprawdzić typ zwrotu, używasz obiektów w typach odpowiedzi określonych na stronie [Szczegóły API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) dla tej operacji.

   Jeśli potrzeba więcej informacji na temat żądania, użyj **metod wiadomości http**, aby uzyskać dostęp do surowego obiektu odpowiedzi.

### <a name="nodejs-package"></a>Pakiet NodeJS

Korzystaj z bibliotek klientów NodeJS dostępnych za pośrednictwem NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Pakiet języka Python

Korzystaj z bibliotek klientów Python dostępnych za pośrednictwem PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
