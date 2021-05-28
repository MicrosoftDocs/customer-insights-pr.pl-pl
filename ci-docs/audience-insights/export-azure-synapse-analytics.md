---
title: Eksportowanie danych usługi Customer Insights do usługi Azure Synapse Analytics
description: Dowiedz się, jak skonfigurować połączenie i eksport do usługi Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977390"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Eksportuj dane do Azure Synapse Analytics

Azure Synapse to usługa analityczna, która przyspiesza czas uzyskania wglądu w magazyny danych i systemy big data. Możesz pobierać dane Customer Insights i wykorzystywać je w [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Wymagania wstępne

Aby skonfigurować połączenie Customer Insights z Azure Synapse należy spełnić następujące wymagania wstępne.

> [!NOTE]
> Upewnij się, że zostały ustawione wszystkie **przypisania ról** w odpowiedni sposób.  

## <a name="prerequisites-in-customer-insights"></a>Wymagania Customer Insights

* Masz rolę użytkownika **Administrator** w rozwiązaniu analiza odbiorców. Więcej informacji o [ustawianiu uprawnień użytkowników w analizie odbiorców](permissions.md#assign-roles-and-permissions)

W Azure: 

- Aktywna subskrypcja platformy Azure.

- Jeśli jest potrzebne nowe konto Azure Data Lake Storage Gen2, *nazwa główna usługi analizy odbiorców* potrzebuje uprawnień **Współautor danych w usłudze Blob Storage**. Dowiedz się więcej o [łączeniu się z kontem Azure Data Lake Storage Gen2 za pomocą nazwy głównej usługi Azure w analizie odbiorców](connect-service-principal.md). Data Lake Storage Gen2 **musi posiadać** uruchomiony [hierarchiczny obszar nazw](/azure/storage/blobs/data-lake-storage-namespace).

- W grupie zasobów, w której znajduje się obszar roboczy Azure Synapse, *nazwa główna usługi* i *użytkownik w analizie odbiorców* muszą posiadać uprawnienia na poziomie co najmniej **Odczyt**. Aby uzyskać więcej informacji, zobacz [przypisywanie ról Azure za pomocą portalu Azure](/azure/role-based-access-control/role-assignments-portal).

- *Użytkownik* musi mieć uprawnienia **Współautor danych w usłudze Blob Storage** na koncie Azure Data Lake Storage Gen2, na którym zlokalizowane są dane i połączone z obszarem roboczym Azure Synapse. Więcej informacji na temat [używania portalu Azure w celu przydzielania roli Azure, aby uzyskać dostęp do danych kolejki i danych blob](/azure/storage/common/storage-auth-aad-rbac-portal) oraz [Współautor danych w usłudze Blob Storage — uprawnienia](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Tożsamość zarządzanego obszaru roboczego Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* musi mieć uprawnienia **Współautor danych w usłudze Blob Storage** na koncie Azure Data Lake Storage Gen2, na którym zlokalizowane są dane i połączone z obszarem roboczym Azure Synapse. Więcej informacji na temat [używania portalu Azure w celu przydzielania roli Azure, aby uzyskać dostęp do danych kolejki i danych blob](/azure/storage/common/storage-auth-aad-rbac-portal) oraz [Współautor danych w usłudze Blob Storage — uprawnienia](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- W obszarze roboczym Azure Synapse jest rola *nazwa główna usługi analizy odbiorców* musi posiadać przypisaną rolę **Administrator Synapse**. Aby uzyskać więcej informacji, zobacz temat [Jak skonfigurować formant dostępu dla obszaru roboczego Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Skonfiguruj połączenie i eksport do Azure Synapse

### <a name="configure-a-connection"></a>Konfigurowanie połączenia

1. Przejdź do **Admin** > **Połączenia**.

1. Wybierz opcję **Dodaj połączenie** i wybierz opcję **Azure Synapse Analytics**, aby skonfigurować połączenie, lub wybierz opcję **Konfiguruj** w kafelku **Azure Synapse Analytics**, aby skonfigurować połączenie.

1. W polu Wyświetlana nazwa nadaj połączeniu rozpoznawalną nazwę. Wyświetlana nazwa i typ połączenia opisują to połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe połączenia.

1. Określ, kto może używać tego połączenia. Jeśli nie podejmiesz działania, ustawieniem domyślnym będą administratorzy. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wybierz lub wyszukaj subskrypcję, w której chcesz korzystać z danych funkcji Customer Insights. Po wybraniu subskrypcji można również wybrać opcję **Obszar roboczy**, **Konto magazynu** i **Kontener**.

1. Aby zapisać połączenie, wybierz **Zapisz**.

### <a name="configure-an-export"></a>Konfigurowanie eksportu

Ten eksport można skonfigurować, jeśli użytkownik ma dostęp do połączenia tego typu. Aby uzyskać więcej informacji, zobacz temat [Uprawnienia wymagane do konfigurowania eksportu](export-destinations.md#set-up-a-new-export).

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz **Dodaj eksport**, aby utworzyć nowy eksport.

1. W polu **Połączenie dla eksportu** wybierz połączenie z sekcji usługi **Azure Synapse Analytics**. Jeśli nie widać nazwy tej sekcji, nie ma dostępnych [połączeń](connections.md) tego typu dla tego użytkownika.

1. Podaj rozpoznawalną **wyświetlaną nazwę** eksportowi i **nazwę bazy danych**.

1. Wybierz encje do wyeksportowania do Azure Synapse Analytics.

1. Wybierz pozycję **Zapisz**.

Zapisanie eksportu nie uruchamia natychmiastowo eksportu.

Eksport jest uruchamiany z każdym [zaplanowanym odświeżeniem](system.md#schedule-tab). Można również [eksportować dane na żądanie](export-destinations.md#run-exports-on-demand).

### <a name="update-an-export"></a>Aktualizowanie eksportu

1. Przejdź do **Dane** > **Eksporty**.

1. Wybierz pozycję **Edytuj** dla eksportu, który chcesz zaktualizować.

   - **Dodawanie** encji do wyboru i **usuwanie** ich. Jeśli encje zostaną usunięte z wybranej bazy danych, nie zostaną usunięte z bazy danych Synapse Analytics. Jednak odświeżenie przyszłych danych nie spowoduje zaktualizowania usuniętych encji z tej bazy danych.

   - **Zmiana nazwy bazy danych** spowoduje utworzenie nowej bazy danych Synapse Analytics. Baza danych o nazwie, która została wcześniej skonfigurowana, nie będzie otrzymywać żadnych aktualizacji w kolejnych odświeżeniach.
