---
title: Dodatek kart klientów w aplikacjach Dynamics 365
description: Pokaż dane z analizy odbiorców w aplikacjach Dynamics 365 za pomocą tego dodatku.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059601"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="631c6-103">Dodatek kart klientów (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="631c6-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="631c6-104">Zobacz pełen obraz klientów bezpośrednio w aplikacjach Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="631c6-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="631c6-105">Po zainstalowaniu dodatku karta klienta w obsługiwanej aplikacji Dynamics 365 można wybrać opcję wyświetlania danych demograficznych, wglądów i osi czasu aktywności.</span><span class="sxs-lookup"><span data-stu-id="631c6-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="631c6-106">Ten dodatek będzie pobierać dane z usługi Customer Insights, co nie ma wpływu na dane w połączonej aplikacji Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="631c6-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="631c6-107">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="631c6-107">Prerequisites</span></span>

- <span data-ttu-id="631c6-108">Ten dodatek działa tylko w aplikacjach opartych na modelu w Dynamics 365, takich jak Sales lub Customer Service, w wersji 9.0 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="631c6-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="631c6-109">Aby dane usługi Dynamics 365 były mapowane do profili klientów w ramach analizy odbiorców, muszą być [pobierane z Dynamics 365 przy użyciu łącznika Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="631c6-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="631c6-110">Wszystkich użytkowników usługi Dynamics 365 z dodatku karta klienta należy [dodać jako użytkowników](permissions.md) w analizie odbiorców, aby dane stały się widoczne.</span><span class="sxs-lookup"><span data-stu-id="631c6-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="631c6-111">[Funkcje wyszukiwania i filtrowania skonfigurowane](search-filter-index.md) w analizie odbiorców są wymagane do wyszukiwania danych.</span><span class="sxs-lookup"><span data-stu-id="631c6-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="631c6-112">Każdy formant dodatku zależy od określonych danych w analizie odbiorców:</span><span class="sxs-lookup"><span data-stu-id="631c6-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="631c6-113">Kontrola miar: wymagane są [skonfigurowane miary](measures.md).</span><span class="sxs-lookup"><span data-stu-id="631c6-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="631c6-114">Kontrola danych: wymaga danych generowanych przy użyciu [prognoz](predictions.md) lub [niestandardowych modeli](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="631c6-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="631c6-115">Kontrola demograficzna: pola demograficzne (takie jak wiek czy płeć) są dostępne w ujednoliconym profilu klienta.</span><span class="sxs-lookup"><span data-stu-id="631c6-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="631c6-116">Kontrola wzbogacenia: Wymaga czynnych [wzbogaceń](enrichment-hub.md) zastosowanych dla profilów klienta.</span><span class="sxs-lookup"><span data-stu-id="631c6-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="631c6-117">Kontrolka osi czasu: wymagane są [skonfigurowane działania](activities.md).</span><span class="sxs-lookup"><span data-stu-id="631c6-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="631c6-118">Zainstaluj dodatek kart klientów</span><span class="sxs-lookup"><span data-stu-id="631c6-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="631c6-119">Dodatek Karta klienta to rozwiązanie dla aplikacji Customer Engagement w Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="631c6-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="631c6-120">Aby zainstalować rozwiązanie, przejdź do AppSource i wyszukaj **Karta klienta Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="631c6-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="631c6-121">Wybierz [Dodatek kart klientów w AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) i wybierz **Pobierz teraz**.</span><span class="sxs-lookup"><span data-stu-id="631c6-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="631c6-122">Aby zainstalować rozwiązanie, konieczne może być zalogowanie się przy użyciu poświadczeń administracyjnych do aplikacji Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="631c6-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="631c6-123">Może upłynąć trochę czasu zanim rozwiązanie zostanie zainstalowane w środowisku użytkownika.</span><span class="sxs-lookup"><span data-stu-id="631c6-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="631c6-124">Konfigurowanie dodatku kart klientów</span><span class="sxs-lookup"><span data-stu-id="631c6-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="631c6-125">Jako administrator, przejdź do sekcji **Ustawienia** w Dynamics 365 i wybierz **Rozwiązania**.</span><span class="sxs-lookup"><span data-stu-id="631c6-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="631c6-126">Wybierz łącze **Wyświetlana nazwa** dla rozwiązania **Dynamics 365 Customer Insights, Dodatek kart klientów (wersja zapoznawcza)**.</span><span class="sxs-lookup"><span data-stu-id="631c6-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="631c6-127">![Wybierz nazwę wyświetlaną](media/select-display-name.png "Wybierz nazwę wyświetlaną")</span><span class="sxs-lookup"><span data-stu-id="631c6-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="631c6-128">Wybierz **Zaloguj** i wprowadź poświadczenia dla konta administracyjnego używanego do konfigurowania Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="631c6-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="631c6-129">Sprawdź, czy w przypadku wybrania przycisku **Zaloguj** nie jest blokowane okno uwierzytelniania w wyskakujących okienkach przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="631c6-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="631c6-130">Wybierz środowisko Customer Insights, z którego chcesz pobrać dane.</span><span class="sxs-lookup"><span data-stu-id="631c6-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="631c6-131">Zdefiniuj mapowanie pól na rekordy w aplikacji Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="631c6-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="631c6-132">W zależności od danych w aplikacji Customer Insights można zamapować następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="631c6-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="631c6-133">Aby zmapować z kontaktem, wybierz pole w encji Customer, które jest zgodne z identyfikatorem Twojej encji kontaktu.</span><span class="sxs-lookup"><span data-stu-id="631c6-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="631c6-134">Aby zmapować z kontem, wybierz pole w encji Customer, które jest zgodne z identyfikatorem Twojej encji konta.</span><span class="sxs-lookup"><span data-stu-id="631c6-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="631c6-135">![Pole identyfikatora kontaktu](media/contact-id-field.png "Pole identyfikatora kontaktu")</span><span class="sxs-lookup"><span data-stu-id="631c6-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="631c6-136">Wybierz **Zapisz konfigurację**, aby zapisać ustawienia.</span><span class="sxs-lookup"><span data-stu-id="631c6-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="631c6-137">Następnie należy przypisać role zabezpieczeń w Dynamics 365, aby użytkownicy mogli dostosować i wyświetlić kartę klienta.</span><span class="sxs-lookup"><span data-stu-id="631c6-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="631c6-138">W Dynamics 365, przejdź do **Ustawienia** > **Zabezpieczenia** > **Użytkownicy**.</span><span class="sxs-lookup"><span data-stu-id="631c6-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="631c6-139">Wybierz użytkowników, aby edytować role użytkowników i wybierz **Zarządzaj rolami**.</span><span class="sxs-lookup"><span data-stu-id="631c6-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="631c6-140">Przypisz rolę **Konfiguratora karty Customer Insights** do klientów, którzy będą dostosowywać zawartość widoczną na karcie dla całej organizacji.</span><span class="sxs-lookup"><span data-stu-id="631c6-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="631c6-141">Dodaj kontrolki karty klienta do formularzy</span><span class="sxs-lookup"><span data-stu-id="631c6-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="631c6-142">Aby dodać formanty karty klienta do formularza Kontakt, przejdź do **Ustawienia** > **Dostosowania** w Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="631c6-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="631c6-143">Wybierz **Dostosuj system**.</span><span class="sxs-lookup"><span data-stu-id="631c6-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="631c6-144">Przeglądaj do encji **Kontakt**, rozwiń ją i wybierz **Formularze**.</span><span class="sxs-lookup"><span data-stu-id="631c6-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="631c6-145">Wybierz formularz kontaktu, do którego chcesz dodać formanty karty klienta.</span><span class="sxs-lookup"><span data-stu-id="631c6-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="631c6-146">![Wybierz formularz Kontaktu](media/contact-active-forms.png "Wybierz formularz Kontaktu")</span><span class="sxs-lookup"><span data-stu-id="631c6-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="631c6-147">Aby dodać formant, w edytorze formularzy przeciągnij dowolne pole z **Eksplorator pól** do miejsca, gdzie ma się pojawić formant.</span><span class="sxs-lookup"><span data-stu-id="631c6-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="631c6-148">Zaznacz pole na formularzu, który został przed chwilą dodany, i wybierz **Zmień właściwości**.</span><span class="sxs-lookup"><span data-stu-id="631c6-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="631c6-149">Przejdź do karty **Formanty** i wybierz opcję **Dodaj formant**.</span><span class="sxs-lookup"><span data-stu-id="631c6-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="631c6-150">Wybierz jeden z dostępnych formantów niestandardowych i wybierz **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="631c6-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="631c6-151">W oknie dialogowym **Właściwości pola** wyczyść pole wyboru **Wyświetl etykietę w formularzu**.</span><span class="sxs-lookup"><span data-stu-id="631c6-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="631c6-152">Wybierz opcję **Web** dla formantu.</span><span class="sxs-lookup"><span data-stu-id="631c6-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="631c6-153">W przypadku formantu Wzbogacenie wybierz, który typ wzbogacenia chcesz wyświetlić konfigurując pole **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="631c6-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="631c6-154">Dodaj oddzielną kontrolkę wzbogacania dla każdego typu wzbogacania.</span><span class="sxs-lookup"><span data-stu-id="631c6-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="631c6-155">Wybierz **Zapisz** i **Opublikuj**, aby opublikować zaktualizowany formularz kontaktu.</span><span class="sxs-lookup"><span data-stu-id="631c6-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="631c6-156">Przejdź do opublikowanego formularza kontaktu.</span><span class="sxs-lookup"><span data-stu-id="631c6-156">Go to the published contact form.</span></span> <span data-ttu-id="631c6-157">Zobaczysz ostatnio dodany formant.</span><span class="sxs-lookup"><span data-stu-id="631c6-157">You'll see the newly added control.</span></span> <span data-ttu-id="631c6-158">Może zaistnieć konieczność zalogowania się w czasie, gdy zostanie on użyty podczas pierwszego korzystania z programu.</span><span class="sxs-lookup"><span data-stu-id="631c6-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="631c6-159">Aby dostosować dane, które mają być wyświetlane w formancie, wybierz przycisk edytuj w prawym górnym rogu.</span><span class="sxs-lookup"><span data-stu-id="631c6-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="631c6-160">Zaktualizuj dodatek karty klienta</span><span class="sxs-lookup"><span data-stu-id="631c6-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="631c6-161">Dodatek karty klienta nie aktualizuje się automatycznie.</span><span class="sxs-lookup"><span data-stu-id="631c6-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="631c6-162">Aby uaktualnić do najnowszej wersji, wykonaj tę procedurę w aplikacji Dynamics 365, która ma zainstalowany dodatek.</span><span class="sxs-lookup"><span data-stu-id="631c6-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="631c6-163">W aplikacji Dynamics 365 przejdź do **Ustawienia** > **Dostosowywanie** i wybierz **Rozwiązania**.</span><span class="sxs-lookup"><span data-stu-id="631c6-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="631c6-164">W tabeli dodatków zwróć uwagę na kartę **CustomerInsightsCustomerCard** i zaznacz wiersz.</span><span class="sxs-lookup"><span data-stu-id="631c6-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="631c6-165">Na pasku akcji wybierz opcję **Zastosuj uaktualnienie rozwiązania**.</span><span class="sxs-lookup"><span data-stu-id="631c6-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Uaktualnianie rozwiązania w obszarze Dostosowywanie aplikacji Dynamics 365":::

1. <span data-ttu-id="631c6-167">Po rozpoczęciu procesu uaktualniania będzie widzieć wskaźnik ładowania do momentu ukończenia uaktualniania.</span><span class="sxs-lookup"><span data-stu-id="631c6-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="631c6-168">Jeśli nie ma nowszej wersji, aktualizacja wyświetli komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="631c6-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
