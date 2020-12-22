---
title: Zainstaluj i skonfiguruj Dodatek kart klientów
description: Zainstaluj i skonfiguruj dodatek kart klientów dla Dynamics 365 Customer Insights.
ms.date: 08/04/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: aab5deaf89b4b019f6688a1bca950ec2277ad5fb
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644056"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="d3703-103">Dodatek kart klientów (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="d3703-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="d3703-104">Zobacz pełen obraz klientów bezpośrednio w aplikacjach Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d3703-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="d3703-105">Zobacz dane demograficzne, wyniki analiz, i osi czasu działania dzięki użyciu dodatku kart klientów.</span><span class="sxs-lookup"><span data-stu-id="d3703-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d3703-106">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="d3703-106">Prerequisites</span></span>

- <span data-ttu-id="d3703-107">Aplikacja Dynamics 365 (na przykład Centrum sprzedaży lub Centrum obsługi klienta) w wersji 9.0 lub nowszej z włączoną funkcją ujednolicony interfejs.</span><span class="sxs-lookup"><span data-stu-id="d3703-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="d3703-108">Profile klientów [pobierane z aplikacji Dynamics 365 z użyciem programu Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="d3703-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="d3703-109">Użytkownicy dodatku karty klienta muszą być [dodawani jako użytkownicy](permissions.md) w statystykach odbiorców.</span><span class="sxs-lookup"><span data-stu-id="d3703-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="d3703-110">[Skonfigurowane funkcje wyszukiwania i filtrowania](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="d3703-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="d3703-111">Kontrola demograficzna: pola demograficzne, takie jak wiek czy płeć, są dostępne w ujednoliconym profilu klienta.</span><span class="sxs-lookup"><span data-stu-id="d3703-111">Demographic control: Demographic fields, such as age or gender are available in the unified customer profile.</span></span>
- <span data-ttu-id="d3703-112">Kontrola wzbogacenia: Wymaga czynnych [wzbogaceń](enrichment-hub.md) zastosowanych dla profilów klienta.</span><span class="sxs-lookup"><span data-stu-id="d3703-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="d3703-113">Kontrola analiz: Wymaga danych wygenerowanych przy użyciu usługi Azure Machine Learning ([przewidywania](predictions.md) lub [modele niestandardowe](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="d3703-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="d3703-114">Kontrola miar: wymagane są [skonfigurowane miary](measures.md).</span><span class="sxs-lookup"><span data-stu-id="d3703-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="d3703-115">Kontrolka osi czasu: wymagane są [skonfigurowane działania](activities.md).</span><span class="sxs-lookup"><span data-stu-id="d3703-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="d3703-116">Zainstaluj dodatek kart klientów</span><span class="sxs-lookup"><span data-stu-id="d3703-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="d3703-117">Dodatek Karta klienta to rozwiązanie dla aplikacji Customer Engagement w Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d3703-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="d3703-118">Aby zainstalować rozwiązanie, przejdź do AppSource i wyszukaj **Karta klienta Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="d3703-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="d3703-119">Wybierz [Dodatek kart klientów w AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) i wybierz **Pobierz teraz**.</span><span class="sxs-lookup"><span data-stu-id="d3703-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="d3703-120">Aby zainstalować rozwiązanie, konieczne może być zalogowanie się przy użyciu poświadczeń administracyjnych do aplikacji Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d3703-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="d3703-121">Może upłynąć trochę czasu zanim rozwiązanie zostanie zainstalowane w środowisku użytkownika.</span><span class="sxs-lookup"><span data-stu-id="d3703-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="d3703-122">Konfigurowanie dodatku kart klientów</span><span class="sxs-lookup"><span data-stu-id="d3703-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="d3703-123">Jako administrator, przejdź do sekcji **Ustawienia** w Dynamics 365 i wybierz **Rozwiązania**.</span><span class="sxs-lookup"><span data-stu-id="d3703-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="d3703-124">Wybierz łącze **Wyświetlana nazwa** dla rozwiązania **Dynamics 365 Customer Insights, Dodatek kart klientów (wersja zapoznawcza)**.</span><span class="sxs-lookup"><span data-stu-id="d3703-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d3703-125">![Wybierz nazwę wyświetlaną](media/select-display-name.png "Wybierz nazwę wyświetlaną")</span><span class="sxs-lookup"><span data-stu-id="d3703-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="d3703-126">Wybierz **Zaloguj** i wprowadź poświadczenia dla konta administracyjnego używanego do konfigurowania Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d3703-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d3703-127">Sprawdź, czy w przypadku wybrania przycisku **Zaloguj** nie jest blokowane okno uwierzytelniania w wyskakujących okienkach przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="d3703-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="d3703-128">Wybierz środowisko, z którego chcesz pobrać dane.</span><span class="sxs-lookup"><span data-stu-id="d3703-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="d3703-129">Zdefiniuj, które pole jest mapowane na rekordy w aplikacji Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d3703-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="d3703-130">Aby zmapować z kontaktem, wybierz pole w encji Customer, które jest zgodne z identyfikatorem Twojej encji kontaktu.</span><span class="sxs-lookup"><span data-stu-id="d3703-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="d3703-131">Aby zmapować z kontem, wybierz pole w encji Customer, które jest zgodne z identyfikatorem Twojej encji konta.</span><span class="sxs-lookup"><span data-stu-id="d3703-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d3703-132">![Pole identyfikatora kontaktu](media/contact-id-field.png "Pole identyfikatora kontaktu")</span><span class="sxs-lookup"><span data-stu-id="d3703-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="d3703-133">Wybierz **Zapisz konfigurację**, aby zapisać ustawienia.</span><span class="sxs-lookup"><span data-stu-id="d3703-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="d3703-134">Następnie należy przypisać role zabezpieczeń w Dynamics 365, aby użytkownicy mogli dostosować i wyświetlić kartę klienta.</span><span class="sxs-lookup"><span data-stu-id="d3703-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="d3703-135">W Dynamics 365, przejdź do **Ustawienia** > **Zabezpieczenia** > **Użytkownicy**.</span><span class="sxs-lookup"><span data-stu-id="d3703-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="d3703-136">Wybierz użytkowników, aby edytować role użytkowników i wybierz **Zarządzaj rolami**.</span><span class="sxs-lookup"><span data-stu-id="d3703-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="d3703-137">Przypisz rolę **Konfiguratora karty Customer Insights** do klientów, którzy będą dostosowywać zawartość widoczną na karcie dla całej organizacji.</span><span class="sxs-lookup"><span data-stu-id="d3703-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="d3703-138">Dodaj kontrolki karty klienta do formularzy</span><span class="sxs-lookup"><span data-stu-id="d3703-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="d3703-139">Aby dodać formanty karty klienta do formularza Kontakt, przejdź do **Ustawienia** > **Dostosowania** w Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d3703-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="d3703-140">Wybierz **Dostosuj system**.</span><span class="sxs-lookup"><span data-stu-id="d3703-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="d3703-141">Przeglądaj do encji **Kontakt**, rozwiń ją i wybierz **Formularze**.</span><span class="sxs-lookup"><span data-stu-id="d3703-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="d3703-142">Wybierz formularz kontaktu, do którego chcesz dodać formanty karty klienta.</span><span class="sxs-lookup"><span data-stu-id="d3703-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d3703-143">![Wybierz formularz Kontaktu](media/contact-active-forms.png "Wybierz formularz Kontaktu")</span><span class="sxs-lookup"><span data-stu-id="d3703-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="d3703-144">Aby dodać formant, w edytorze formularzy przeciągnij dowolne pole z **Eksplorator pól** do miejsca, gdzie ma się pojawić formant.</span><span class="sxs-lookup"><span data-stu-id="d3703-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="d3703-145">Zaznacz pole na formularzu, który został przed chwilą dodany, i wybierz **Zmień właściwości**.</span><span class="sxs-lookup"><span data-stu-id="d3703-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="d3703-146">Przejdź do karty **Formanty** i wybierz opcję **Dodaj formant**.</span><span class="sxs-lookup"><span data-stu-id="d3703-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="d3703-147">Wybierz jeden z dostępnych formantów niestandardowych i wybierz **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="d3703-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="d3703-148">W oknie dialogowym **Właściwości pola** wyczyść pole wyboru **Wyświetl etykietę w formularzu**.</span><span class="sxs-lookup"><span data-stu-id="d3703-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="d3703-149">Wybierz opcję **Web** dla formantu.</span><span class="sxs-lookup"><span data-stu-id="d3703-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="d3703-150">W przypadku formantu Wzbogacenie wybierz, który typ wzbogacenia chcesz wyświetlić konfigurując pole **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="d3703-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="d3703-151">Należy dodać osobny formant wzbogacania dla każdego typu wzbogacenia.</span><span class="sxs-lookup"><span data-stu-id="d3703-151">You need to add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="d3703-152">Wybierz **Zapisz** i **Opublikuj**, aby opublikować zaktualizowany formularz kontaktu.</span><span class="sxs-lookup"><span data-stu-id="d3703-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="d3703-153">Przejdź do opublikowanego formularza kontaktu.</span><span class="sxs-lookup"><span data-stu-id="d3703-153">Go to the published contact form.</span></span> <span data-ttu-id="d3703-154">Zobaczysz ostatnio dodany formant.</span><span class="sxs-lookup"><span data-stu-id="d3703-154">You'll see the newly added control.</span></span> <span data-ttu-id="d3703-155">Może zaistnieć konieczność zalogowania się w czasie, gdy zostanie on użyty podczas pierwszego korzystania z programu.</span><span class="sxs-lookup"><span data-stu-id="d3703-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="d3703-156">Aby dostosować dane, które mają być wyświetlane w formancie, wybierz przycisk edytuj w prawym górnym rogu.</span><span class="sxs-lookup"><span data-stu-id="d3703-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>