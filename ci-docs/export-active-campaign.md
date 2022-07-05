---
title: Eksportowanie segmentów do ActiveCampaign
description: Dowiedz się, jak skonfigurować połączenie i wyeksportować je do usługi ActiveCampaign.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: eb6f2bb69bb30c319e17390562b3f33512f33ff1
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054721"
---
# <a name="export-segments-to-activecampaign-preview"></a>Eksportowanie segmentów do ActiveCampaign (wersja zapoznawcza)

Eksportuj segmenty ujednoliconych profili klientów do ActiveCampaign i wykorzystaj je w działaniach marketingowych.

## <a name="prerequisites"></a>Wymagania wstępne

- Użytkownik ma konto [ActiveCampaign](https://www.activecampaign.com/) i odpowiednie uprawnienia administratora.
- Masz [skonfigurowane segmenty](segments.md) w Customer Insights.
- Ujednolicone profile klientów w wyeksportowanych segmentach zawierają pole z adresem e-mail.

## <a name="known-limitations"></a>Znane ograniczenia

- W przypadku eksportu do usługi ActiveCampaign można wyeksportować do 1 mln profilów klientów, co może potrwać do 90 minut.
- Eksportowanie do usługi ActiveCampaign jest ograniczone do segmentów.
- Liczba profilów klientów, które można eksportować do usługi ActiveCampaign, zależy od kontraktu z usługą ActiveCampaign i jest ograniczona.

## <a name="set-up-connection-to-activecampaign"></a>Skonfiguruj połączenie z aplikacjami usługi ActiveCampaign

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **ActiveCampaign**, aby skonfigurować połączenie.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Domyślnie – tylko administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wprowadź [klucz interfejsu API ActiveCampaign i nazwę hosta REST punktu końcowego](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key). Nazwa hosta punktu końcowego REST jest tylko nazwą hosta, bez https://. 

1. Wybierz **Zgadzam się**, aby potwierdzić **Prywatność danych i zgodność z przepisami**.

1. Wybierz opcję **Połącz**, aby zainicjować połączenie z ActiveCampaign.

1. Wybierz **Dodaj siebie jako eksportowanie użytkowników** i przekaż poświadczenia Customer Insights.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj miejsce docelowe**, aby utworzyć nowy eksport.

1. W polu **Połączenie do eksportu** wybierz połączenie z sekcji ActiveCampaign. Jeśli nie widać nazwy tej sekcji, nie ma dostępnych połączeń tego typu dla tego użytkownika.

1. Wprowadź [**Identyfikator listy usługi ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).    

1. W sekcji **Dopasowywanie danych** w polu **E-mail** wybierz pole reprezentujące adres e-mail klienta. Jest on niezbędny do eksportu segmentów do ActiveCampaign. Opcjonalnie możesz wyeksportować Imię, Nazwisko i Telefon, aby stworzyć bardziej spersonalizowane wiadomości e-mail. Wybierz opcję Dodaj atrybut, aby zamapować te pola.

1. Wybierz pozycję **Zapisz**.

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab). Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Prywatność danych i zgodność z przepisami

Włączenie Dynamics 365 Customer Insights w celu przekazywania danych do usługi ActiveCampaign umożliwia przesyłanie danych poza granice obszaru zgodności dla Dynamics 365 Customer Insights, w tym potencjalnie poufne dane, takie jak dane osobiste. Microsoft będzie przekazywać takie dane zgodnie z Twoimi instrukcjami, ale to Ty jesteś odpowiedzialny za zapewnienie, że ActiveCampaign spełnia wszelkie zobowiązania dotyczące prywatności i bezpieczeństwa, jakie możesz mieć. Aby uzyskać więcej informacji, zobacz temat [Oświadczenie o ochronie prywatności firmy Microsoft.](https://go.microsoft.com/fwlink/?linkid=396732).

Administrator Dynamics 365 Customer Insights w dowolnym momencie może usunąć tę lokalizację docelową eksportu, aby przestać używać tej funkcji.
