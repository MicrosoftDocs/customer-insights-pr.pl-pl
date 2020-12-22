---
title: Bot dla Microsoft Teams
description: Wyszukaj ujednolicone profile klientów w Microsoft Teams za pomocą bota.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 45ea23fbefe5f1d44c3961183b76d2cc5c45355e
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406581"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="96ab7-103">Bot Teams dla Dynamics 365 Customer Insights (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="96ab7-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="96ab7-104">Połącz się z Microsoft Teams, aby umożliwić botom przeglądanie ujednoliconych profilów klientów w kanałach Teams.</span><span class="sxs-lookup"><span data-stu-id="96ab7-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="96ab7-105">![Bot Teams ukazujący rekord klienta](media/teams-bot.png "Bot Teams ukazujący rekord klienta")</span><span class="sxs-lookup"><span data-stu-id="96ab7-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="96ab7-106">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="96ab7-106">Prerequisites</span></span>

<span data-ttu-id="96ab7-107">Aby można było skonfigurować program bot muszą zostać spełnione następujące wymagania wstępne:</span><span class="sxs-lookup"><span data-stu-id="96ab7-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="96ab7-108">Istnieje co najmniej jedno [dodane źródło danych](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="96ab7-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="96ab7-109">Zakończono [proces unifikacji](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="96ab7-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="96ab7-110">Pola są dodawane do [indeksu wyszukiwania i filtru](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="96ab7-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="96ab7-111">Customer Insights i Teams są w tej samej organizacji.</span><span class="sxs-lookup"><span data-stu-id="96ab7-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="96ab7-112">Skonfiguruj program bot</span><span class="sxs-lookup"><span data-stu-id="96ab7-112">Configure the bot</span></span>

1. <span data-ttu-id="96ab7-113">W analizach odbiorców przejdź do **Administrator** > **Lokalizacje docelowe eksportu**.</span><span class="sxs-lookup"><span data-stu-id="96ab7-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="96ab7-114">Na kafelku Microsoft Teams wybierz **Konfiguracja**.</span><span class="sxs-lookup"><span data-stu-id="96ab7-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="96ab7-115">Nastąpi przekierowanie do obszaru **Aplikacje** w Teams.</span><span class="sxs-lookup"><span data-stu-id="96ab7-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="96ab7-116">Możesz również otworzyć Teams i wybrać **Aplikacje** w lewym dolnym rogu lub [pobrać je z AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).</span><span class="sxs-lookup"><span data-stu-id="96ab7-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="96ab7-117">Wyszukaj **Customer Insights** i wybierz aplikację.</span><span class="sxs-lookup"><span data-stu-id="96ab7-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="96ab7-118">Wybierz **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="96ab7-118">Select **Add**.</span></span>
1. <span data-ttu-id="96ab7-119">Po zalogowaniu się w Customer Insights w Teams zobaczysz komunikat powitalny i będziesz mógł rozpocząć pracę.</span><span class="sxs-lookup"><span data-stu-id="96ab7-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="96ab7-120">Rzeczy, które możesz zrobić za pomocą programu bot</span><span class="sxs-lookup"><span data-stu-id="96ab7-120">Things you can do with the bot</span></span>

<span data-ttu-id="96ab7-121">Bot zawiera funkcje wyszukiwania ujednoliconych profilów klientów.</span><span class="sxs-lookup"><span data-stu-id="96ab7-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="96ab7-122">Wprowadź **wyszukaj** a następnie nazwisko, adres e-mail lub dowolne inne pole w profilu ujednoliconego klienta, który jest dodawany do indeksu wyszukiwania i filtru.</span><span class="sxs-lookup"><span data-stu-id="96ab7-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="96ab7-123">Zostanie wyświetlona karta zawierająca maksymalnie 15 pól z profilu wynikowego klienta.</span><span class="sxs-lookup"><span data-stu-id="96ab7-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="96ab7-124">Wiele pasujących elementów zwraca listę wyników, w których można wybrać profil.</span><span class="sxs-lookup"><span data-stu-id="96ab7-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="96ab7-125">Aby wyszukać dokładne dopasowanie można dodać termin wyszukiwania objęty znakami cudzysłowu.</span><span class="sxs-lookup"><span data-stu-id="96ab7-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="96ab7-126">Jeśli Twoja organizacja utrzymuje wiele środowisk Customer Insights w tej samej organizacji, możesz wprowadzić **switchinstance**, aby wybrać środowisko, z którym chcesz połączyć bota.</span><span class="sxs-lookup"><span data-stu-id="96ab7-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="96ab7-127">Wprowadź **pomoc**, aby wyświetlić listę dostępnych poleceń dla programu bot.</span><span class="sxs-lookup"><span data-stu-id="96ab7-127">Enter **help** to see a list of available commands for the bot.</span></span>  
