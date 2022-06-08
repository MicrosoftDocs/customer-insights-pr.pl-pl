---
title: Używanie ujednoliconych profilów w usłudze Dynamics 365 Marketing
description: Dowiedz się, jak zintegrować ujednolicone profile i segmenty z Dynamics 365 Marketing.
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4cc3cbde97d0f9da198652e86c0843476393b646
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833321"
---
# <a name="work-with-unified-customer-profiles-in-dynamics-365-marketing"></a>Praca z ujednoliconymi profilami klientów w usłudze Dynamics 365 Marketing

Aplikacja [Dynamics 365 Marketing](/dynamics365/marketing/overview) podnosi poziom obsługi klienta, umożliwiając organizowanie spersonalizowanych procesów pozyskiwania we wszystkich punktach kontaktu, aby wzmocnić relacje i zdobyć lojalność. Aplikacja Dynamics 365 Marketing bezproblemowo współpracuje z aplikacjami Dynamics 365 Sales, Dynamics 365 Customer Insights, Microsoft Teams oraz innymi produktami i umożliwia podejmowanie szybszych i lepszych decyzji przy użyciu mocy danych i AI.

Połączenie danych Customer Insights z Marketing umożliwia:

- Wybieranie ujednoliconych profilów i segmentów jako docelowych. Dzięki temu możesz zaangażować każdego klienta, niezależnie od lokalizacji danych klienta.
- Podstawowa zawartość dynamiczna (taka jak spersonalizowane tokeny) w wiadomościach e-mail, wiadomościach SMS i powiadomieniach push dotyczących miar, takich jak stan lojalności, data odnowienia subskrypcji, konto nadrzędne lub inne miary przechwycone w ujednoliconym profilu Customer Insights.
- Wczytywać dane Marketing do Customer Insights i łączyć je z danymi klientów z innych źródeł.
- Zastosuj narzędzia do czyszczenia i wzbogacania danych Customer Insights oraz narzędzia do dopasowywania rozmytego.

## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>Korzystaj z rozbudowanych profili klientów w marketingu w czasie rzeczywistym

Marketing w czasie rzeczywistym umożliwia tworzenie [niestandardowych wyzwalaczy](/dynamics365/marketing/real-time-marketing-custom-triggers), które uruchamiają procesy pozyskiwania klientów w oparciu o dowolne działania klienta. Im bardziej spersonalizowane będą dane, tym bardziej odpowiednie i spersonalizowane będą procesy. To właśnie sprawia, że połączenie Marketing i Customer Insights jest tak skuteczne. Możesz [ujednolicić dane](data-unification.md) z dowolnego źródła, a następnie użyć ich do napędzania hiperspersonalizowanych procesów pozyskiwania klientów.

Dowiedz się więcej: [Używanie profilów i segmentów aplikacji Customer Insights w marketingu w czasie rzeczywistym](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>Używanie ujednoliconych segmentów z wychodzącymi procesami pozyskiwania klientów

Customer Insights pozwala udoskonalić dane z wielu źródeł i połączyć je w zagregowane segmenty klientów. Łącząc [Customer Insights z marketingiem wychodzącym](export-dynamics365-marketing.md), segmenty te będą automatycznie pojawiać się *i* odświeżać automatycznie w projektancie pozyskiwania klientów.

Dowiedz się więcej: [Użyj segmentów z Dynamics 365 Customer Insights razem z Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>Pobieranie danych z własnych Azure Data Lake Storage

Nie jesteś ograniczony do magazynu w chmurze, jeśli chcesz używać danych Customer Insights z Marketing. Jeśli masz już własną konfigurację usługi Azure Data Lake Storage, możesz połączyć się z Customer Insights, a następnie udostępnić dane w aplikacji Marketing tak samo, jak w przypadku konfiguracji opartej na chmurze.

Więcej informacji: [Włączanie udostępniania danych Dataverse z własnego Azure Data Lake Storage](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)
