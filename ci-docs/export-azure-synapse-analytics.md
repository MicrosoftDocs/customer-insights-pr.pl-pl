---
title: Eksportowanie danych do usługi Azure Synapse Analytics (wersja zapoznawcza)
description: Dowiedz się, jak konfigurować połączenie z usługą Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f9c9ee55f2874ae1dcaf82f2ff17ed0fbbb7804d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196407"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Eksportowanie danych do usługi Azure Synapse Analytics (wersja zapoznawcza)

Azure Synapse to usługa analityczna, która przyspiesza czas uzyskania wglądu w magazyny danych i systemy big data. Możesz pobierać dane Customer Insights i wykorzystywać je w [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Wymagania wstępne

> [!NOTE]
> Upewnij się, że zostały ustawione wszystkie **przypisania ról** w odpowiedni sposób.

- W Customer Insights Twoje konto użytkownika Azure Active Directory (AD) musi mieć rolę [Administratora](permissions.md#assign-roles-and-permissions).

W Azure:

- Aktywna subskrypcja platformy Azure.

- Jeśli korzystasz z nowego konta Azure Data Lake Storage Gen2, [nazwa główna usługi Customer Insights](connect-service-principal.md) ma uprawnienia **Współautor danych Storage Blob**. Data Lake Storage Gen2 **musi posiadać** uruchomiony [hierarchiczny obszar nazw](/azure/storage/blobs/data-lake-storage-namespace).

- W grupie zasobów, w której znajduje się obszar roboczy usługi Azure Synapse workspace, *nazwa główna usługi* i użytkownik *Azure AD  z uprawnieniami administratora w Customer Insights* muszą mieć przypisane co najmniej [uprawnienia](/azure/role-based-access-control/role-assignments-portal)  **Czytelnik**.

- *Użytkownik Azure AD z uprawnieniami administratora w Customer Insights* ma uprawnienia **Współautora danych Storage Blob** na koncie Azure Data Lake Storage Gen2, gdzie znajdują się dane i gdzie są one połączone z Azure Synapse workspace. Więcej informacji na temat [używania portalu Azure w celu przydzielania roli Azure, aby uzyskać dostęp do danych kolejki i danych blob](/azure/storage/common/storage-auth-aad-rbac-portal) oraz [Współautor danych w usłudze Blob Storage — uprawnienia](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Tożsamość zarządzanego obszaru roboczego Azure Synapse workspace](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* ma uprawnienia **Współautor danych w usłudze Blob Storage** na koncie Azure Data Lake Storage Gen2, na którym zlokalizowane są dane i połączone z obszarem roboczym Azure Synapse workspace. Więcej informacji na temat [używania portalu Azure w celu przydzielania roli Azure, aby uzyskać dostęp do danych kolejki i danych blob](/azure/storage/common/storage-auth-aad-rbac-portal) oraz [Współautor danych w usłudze Blob Storage — uprawnienia](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- W obszarze roboczym Azure Synapse workspace *zasada obsługi dla Customer Insights* ma [przypisane role](/azure/synapse-analytics/security/how-to-set-up-access-control) **Administrator Synapse**.

## <a name="set-up-connection-to-azure-synapse"></a>Konfiguruj połączenie z Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz **Azure Synapse Analytics**.

1. W polu **Wyświetlana nazwa** nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Domyślnie – tylko administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wybierz lub wyszukaj subskrypcję, w której chcesz korzystać z danych funkcji Customer Insights. Po wybraniu subskrypcji można również wybrać opcję **Obszar roboczy**, **Konto magazynu** i **Kontener**.

1. Przejrzyj zasady [Prywatność danych i zgodność z przepisami](connections.md#data-privacy-and-compliance) i wybierz opcję **Wyrażam zgodę**.

1. Aby zakończyć połączenie, wybierz **Zapisz**.

## <a name="configure-an-export"></a>Konfigurowanie eksportu

A[!INCLUDE [export-permission-include](includes/export-permission.md)] by skonfigurować eksport z udostępnionym połączeniem, potrzebujesz co najmniej uprawnień **Współautor** w Customer Insights.

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz opcję **Dodaj eksport**.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji Azure Synapse Analytics. Skontaktuj się z administratorem, jeśli nie jest dostępne żadne połączenie.

1. Podaj rozpoznawalną **wyświetlaną nazwę** eksportowi i **nazwę bazy danych**. Eksport spowoduje utworzenie nowej [bazy danych lake Azure Synapse](/azure/synapse-analytics/database-designer/concepts-lake-database) w obszarze roboczym zdefiniowanym w połączeniu.

1. Wybierz encje do wyeksportowania do usługi Azure Synapse Analytics.
   > [!NOTE]
   > Źródła danych oparte na [folderze Common Data Model](connect-common-data-model.md) nie są obsługiwane.

1. Wybierz pozycję **Zapisz**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Aby wysyłać zapytania do danych, które zostały wyeksportowane do Synapse Analytics, musisz mieć dostęp do **Czytelnik danych obiektów blob magazynu** do docelowego magazynu w obszarze roboczym eksportu.

## <a name="update-an-export"></a>Aktualizowanie eksportu

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz pozycję **Edytuj** dla eksportu, który chcesz zaktualizować.

   - **Dodawanie** encji do wyboru i **usuwanie** ich. Jeśli encje zostaną usunięte z wybranej bazy danych, nie zostaną usunięte z bazy danych Synapse Analytics. Jednak odświeżenie przyszłych danych nie spowoduje zaktualizowania usuniętych encji z tej bazy danych.

   - **Zmiana nazwy bazy danych** spowoduje utworzenie nowej bazy danych Synapse Analytics. Baza danych o nazwie, która została wcześniej skonfigurowana, nie będzie otrzymywać żadnych aktualizacji w kolejnych odświeżeniach.

[!INCLUDE [footer-include](includes/footer-banner.md)]
