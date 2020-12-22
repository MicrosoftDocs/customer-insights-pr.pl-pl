---
title: Uzupełnij częściowe dane za pomocą przewidywania
description: Aby wypełnić niekompletne dane klientów, należy użyć przewidywania.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 66f0b16b5d05741ab98ca5ce2157da8c46b6d9e0
ms.sourcegitcommit: 5379c2b77d613d071a177f509e6417ebf3c47516
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "4648724"
---
# <a name="complete-your-partial-data-with-predictions"></a>Uzupełnij częściowe dane przy użyciu przewidywań

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Przewidywania umożliwiają łatwe tworzenie prognozowanych wartości, które mogą poprawić zrozumienie klienta. Na stronie **Analizy** > **Przewidywania** można wybrać pozycję **Moje przewidywania**, aby wyświetlić obszary, które zostały skonfigurowane w innych częściach analiz odbiorców, oraz umożliwić dalsze dostosowanie ich.

> [!NOTE]
> Nie można korzystać z tej funkcji, jeśli w środowisku jest używany Magazyn Azure Data Lake Gen 2.
>
> Funkcja przewidywania używa zautomatyzowanych środków służących do oceny danych i tworzy przewidywania ich na podstawie tych danych i dlatego może służyć jako metoda profilowania, ponieważ ten termin jest określony przez Ogólne rozporządzenie o ochronie danych („RODO”). Korzystanie z tej funkcji przez klienta do przetwarzania danych może podlegać RODO lub innym prawom lub rozporządzeniom. Użytkownik ma obowiązek zagwarantować, że użytkowanie Dynamics 365 Customer Insights wraz z przewidywaniami jest zgodne ze wszystkimi obowiązującymi przepisami prawnymi i wykonawczymi, w tym prawa związane z ochroną prywatności, danymi osobowymi, danymi biometrycznymi, ochroną danych i poufność informacji.

## <a name="prerequisites"></a>Wymagania wstępne

Aby organizacja mogła korzystać z funkcji przewidywania, należy się upewnić, że są spełnione następujące wymagania wstępne:

1. W organizacji jest używane wystąpienie [skonfigurowane w Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) i znajduje się on w tej samej organizacji, w której znajduje się klient Customer Insights.

2. Środowisko użytkownika jest dołączone do wystąpienia Common Data Service.

W przypadku [tworzenia nowego środowiska](manage-environments.md) należy je skonfigurować w oknie dialogowym **Tworzenie środowiska** i wybrać opcję **Zaawansowane**. Jeśli środowisko zostało już utworzone, przejdź do jego ustawień i wybierz **Zaawansowane**. W obszarze w sekcji **Korzystanie z przewidywania** wprowadź adres URL wystąpienia Common Data Service, do którego chcesz dodać środowisko.

## <a name="create-a-prediction-in-the-customer-entity"></a>Tworzenie przewidywania w encji Klienta

1. W analizach odbiorców przejdź do **Dane** > **Encje**.

2. Wybierz encję **Klient**.

3. W encji **Klient: CustomerInsights** wybierz na karcie **Pola**.

4. Znajdź nazwę atrybutu, dla którego chcesz prognozować wartości, a następnie wybierz ikonę **przegląd** w kolumnie **podsumowanie**.
   > [!div class="mx-imgBorder"]
   > ![Ikona przegląd](media/intelligence-overviewicon.png "Ikona przegląd")

5. Jeśli istnieje duża liczba brakujących wartości atrybutu, wybierz **Przewiduj brakujące wartości**, aby kontynuować przewidywanie.
   > [!div class="mx-imgBorder"]
   > ![Status przeglądu z pokazanym przyciskiem przewidywania brakujących wartości](media/intelligence-overviewpredictmissingvalues.png "Status przeglądu z pokazanym przyciskiem przewidywania brakujących wartości")

6. Uzupełnij pola **Wyświetlana nazwa** i **Nazwa encji wyjściowej** dla wyników przewidywania.

7. Wstępnie wypełniona lista opcji będzie wskazywać miejsce, w którym można zamapować wartości na kategorię przewidywaną. W tym przypadku tylko te opcje kategorii będą miały wartość 0 lub 1, ponieważ są one mapowane na wartość prawda/fałsz lub na dwójkową naturę przewidywania. W kolumnie Kategoria zamapuj wartości pól, które mają być klasyfikowane jako „0”, w końcowym przewidywaniu na „0”, a pozycje, które mają być klasyfikowane jako „1”, w końcowym przewidywaniu na „1”.
   > [!div class="mx-imgBorder"]
   > ![Przykład przedstawiający mapowane wartości pól w kategoriach](media/intelligence-categorymapping.png "Przykład przedstawiający mapowane wartości pól w kategoriach")

8. Wybierz **Gotowe**, a prognoza zostanie przetworzona. Przetwarzanie zajmie trochę czasu w zależności od rozmiaru i stopnia złożoności danych. Wyniki będą dostępne w nowej encji na podstawie **Nazwa encji wyjściowej** utworzonego przewidywania.

## <a name="create-a-prediction-while-creating-a-segment"></a>Tworzenie przewidywania podczas tworzenia segmentu

Podczas tworzenia segmentu możliwe jest również przewidywanie brakujących wartości konkretnego wybranego atrybutu. Szczególnie wtedy, gdy użytkownik szybko tworzy segment na podstawie zunifikowanej encji klienta lub encji Customer_Measure.

W ramach tego przepływu użytkownik powinien wybrać konkretny atrybut, który będzie podstawą segmentu, na przykład Zadowolenie klienta lub Kwota zakupu. Po utworzeniu segmentu system zasugeruje metodę przewidywania brakujących wartości atrybutu.

1. W analizach odbiorców wybierz kolejno kafelki **Segmenty** i **Profile**.

2. Wybierz **Pole**, na którym ma być utworzony segment, i wybierz **operatora**, a następnie wybierz pozycję **Przejrzyj**.

3. Wprowadź **nazwę** i **wyświetlaną nazwę** segmentu.

4. Wybierz pozycję **Zapisz**.

5. Jeśli utworzony segment zawiera niekompletne dane w polu źródłowym, można wybrać opcję przewidywania brakujących wartości.
   > [!div class="mx-imgBorder"]
   > ![Przycisk przewidywania](media/segments-predictoption.png "Przycisk przewidywania")

6. Uzupełnij pola **Wyświetlana nazwa** i **Nazwa encji wyjściowej** dla wyników przewidywania.

7. Wybierz **Gotowe**. Przewidywanie zostanie wygenerowana wkrótce w nowej encji i będzie dostępne pod nazwą podaną dla **Nazwa encji wyjściowej**.

## <a name="view-a-prediction"></a>Zobacz przewidywanie

1. W analizach odbiorców przejdź do **Analizy** > **Przewidywania** > **Moje przewidywania**.

2. Wybierz przewidywania do przeglądu.

3. W kolumnie **akcje** wybierz wielokropek i wybierz opcję **widok**.

4. W widoku przewidywania będzie widoczna liczba punktów danych.
   > [!div class="mx-imgBorder"]
   > ![Strona przewidywań](media/intelligence-predictionsviewpage.png "Strona przewidywań")

   - **Wartości przewidywane** pokazują mapowanie utworzone podczas fazy mapowania według wartości pola do kategorii. Są to wartości w zestawie danych, które zostały zamapowane na określoną kategorię.
   -**Pola mające największy wpływ** są to czynniki w zestawie danych, które mogą mieć wpływ na wiarygodność prognozowanej wartości pola, które jest mapowane na określoną kategorię.
   - **Wydajność** wskazuje, jak są wykonywane przewidywania. Aby dowiedzieć się więcej, prosimy kliknąć link.
   - **Podgląd** pokazuje przykłady zestawu danychów wyjściowych z przewidywania i prawdopodobieństwa lub pewność przewidywanej wartości, gdzie 0 jest niepewna, a wartość 1 jest określona jako pewna.

## <a name="update-a-prediction"></a>Aktualizuj przewidywanie

1. W analizach odbiorców przejdź do **Analizy** > **Przewidywania** > **Moje przewidywania**.

2. Wybierz sposób przewidywania, który chcesz zaktualizować, i wybierz ikonę **Aktualizuj**.

3. Przewidywanie będzie zaplanowane do przetworzenia. Czas ostatniej aktualizacji jest wyświetlany w kolumnie **Zaktualizowano** na stronie **Przewidywania**.

## <a name="edit-a-prediction"></a>Edytuj przewidywanie

Po utworzeniu przewidywania można dostosować model w AI Builder w celu zwiększenia efektywności modelu.  

1. W analizach odbiorców przejdź do **Analizy** > **Przewidywania** > **Moje przewidywania**.

2. Zaznacz przewidywanie, które chcesz edytować.

3. W kolumnie **akcje** wybierz wielokropek i wybierz opcję **widok**.

4. Wybierz **Dostosuj w aplikacji AI Builder**.

5. Zaktualizuj model w konstruktorze AI Builder. [Więcej informacji o zarządzaniu modelami w AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).

Następne uruchomienie funkcji przewidywania będzie mieć zaktualizowany utworzony model.

> [!NOTE]
> Nowe modele utworzone w narzędziu AI Builder nie będą wyświetlane w statystykach odbiorców, chyba że model został utworzony na podstawie doświadczeń wymienionych powyżej.

## <a name="remove-a-prediction"></a>Usuń przewidywanie

1. W analizach odbiorców przejdź do **Analizy** > **Przewidywania** > **Moje przewidywania**.

2. Wybierz przewidywanie do usunięcia.

3. W kolumnie **akcje** wybierz wielokropek i wybierz opcję **usuń**.

4. Potwierdź usunięcie.

## <a name="troubleshooting"></a>Rozwiązywanie problemów

Jeśli użytkownik nie może zakończyć procesu dołączania Common Data Service z powodu błędu, może podjąć próbę ręcznego ukończenia procesu. Istnieją dwa znane problemy, które mogą wystąpić podczas procesu dołączania:

- Rozwiązanie dodatku karty klienta nie jest zainstalowane.
    1. Wykonaj instrukcje, aby [zainstalować i skonfigurować rozwiązanie](customer-card-add-in.md).

- Nie są przyznawane uprawnienia aplikacji.
    1. Przejdź do [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).
    1. Wybierz **Środowiska**.
    1. Wybierz wielokropek obok środowiska, do którego chcesz dodać uprawnienie i wybierz **Ustawienia**.
    1. Rozwiń **Użytkownicy + uprawnienia** i wybierz **Użytkownicy**.
    1. Wybierz **+ Nowy** i wybierz **Użytkownik**.
    1. Wybierz **Użytkownik aplikacji**, jeśli jeszcze nie został on wybrany i wprowadź następujące informacje:
        - **Nazwa użytkownika:** cihelp@microsoft.com
        - **Identyfikator aplikacji:** 38c77d00-5fcb-4cce-9d93-af4738258e3c
        - **Imię:** Customer
        - **Nazwisko:** Insights
        - **Podstawowy adres e-mail:** cihelp@microsoft.com
    1. Zaznacz **Zapisz i zamknij**.
    1. Wybierz właśnie utworzonego użytkownika.
    1. W górnym pasku menu wybierz **Zarządzaj rolami**.
    1. Wybierz **Administrator systemu**, a następnie wybierz **OK**.
