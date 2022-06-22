---
title: Pozyskaj dane z usługi Azure Synapse Analytics
description: Bazy danych w usłudze Azure Synapse jako źródła danych w programie Dynamics 365 Customer Insights.
ms.date: 03/25/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 6f94cdbcc203fc4518544f7a945bd80e871b36c1
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011440"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Połącz źródło danych usługi Azure Synapse Analytics (wersja zapoznawcza)

Azure Synapse Analytics to usługa analizy dla przedsiębiorstw, która przyspiesza wgląd w szczegółowe dane w magazynach danych i w systemach danych big data. Usługa Azure Synapse Analytics wykorzystuje najlepsze technologie SQL używane w przypadku przetwarzania danych dla przedsiębiorstw, technologie Spark służące do przetwarzania dużych big data, eksplorator danych do analizy dzienników i serii czasowych, potoki integracji danych i ETL/ELT i głęboką integrację z innymi usługami Azure, takimi jak Power BI, Cosmos DB i AzureML.

Aby uzyskać więcej informacji, zobacz [Omówienie usługi Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Wymagania wstępne

> [!IMPORTANT]
> Upewnij się, że zostały ustawione wszystkie **przypisania ról** w odpowiedni sposób.  

**W Customer Insights**:

* Masz rolę użytkownika **Administrator** w rozwiązaniu Customer Insights. Dowiedz się więcej o [uprawnieniach użytkowników w Customer Insights](permissions.md#assign-roles-and-permissions).

**W Azure**:

- Aktywna subskrypcja platformy Azure.

- Jeśli korzystasz z nowego konta Azure Data Lake Storage Gen2, *nazwa główna usługi Customer Insights* potrzebuje uprawnień **Współautor danych Storage Blob**. Dowiedz się więcej o [łączeniu się z usługą Azure Data Lake Storage z nazwą główną usługi dla Customer Insights](connect-service-principal.md). Data Lake Storage Gen2 **musi posiadać** uruchomiony [hierarchiczny obszar nazw](/azure/storage/blobs/data-lake-storage-namespace).

- Na grupie zasobów, w której znajduje się obszarze roboczym Azure Synapse workspace, nazwa *główna usługi* i *użytkownik dla Customer Insights* muszą mieć nadane uprawnienia co najmniej **Odczyt**. Aby uzyskać więcej informacji, zobacz [przypisywanie ról Azure za pomocą portalu Azure](/azure/role-based-access-control/role-assignments-portal).

- *Użytkownik* musi mieć uprawnienia **Współautor danych w usłudze Blob Storage** na koncie Azure Data Lake Storage Gen2, na którym zlokalizowane są dane i połączone z obszarem roboczym Azure Synapse. Więcej informacji na temat [używania portalu Azure w celu przydzielania roli Azure, aby uzyskać dostęp do danych kolejki i danych blob](/azure/storage/common/storage-auth-aad-rbac-portal) oraz [Współautor danych w usłudze Blob Storage — uprawnienia](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Tożsamość zarządzanego obszaru roboczego Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* musi mieć uprawnienia **Współautor danych w usłudze Blob Storage** na koncie Azure Data Lake Storage Gen2, na którym zlokalizowane są dane i połączone z obszarem roboczym Azure Synapse. Więcej informacji na temat [używania portalu Azure w celu przydzielania roli Azure, aby uzyskać dostęp do danych kolejki i danych blob](/azure/storage/common/storage-auth-aad-rbac-portal) oraz [Współautor danych w usłudze Blob Storage — uprawnienia](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- W Azure Synapse workspace, *nazwa główna usługi Customer Insights* ma przypisaną rolę **Administrator Synapse**. Aby uzyskać więcej informacji, zobacz temat [Jak skonfigurować formant dostępu dla obszaru roboczego Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Łączenie się z bazą danych data lake w usłudze Azure Synapse Analytics

1. Przejdź do **Dane** > **Źródła danych**.

1. Wybierz **Dodaj źródła danych**.

1. Wybierz metodę **Azure Synapse Analytics** (wersja zapoznawcza).

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Okno dialogowe łączenia się z danymi analizy Synapse":::
  
1. Wprowadź **Nazwa** dla źródła danych i opcjonalnie **Opis**.

1. Wybierz [dostępne połączenie](connections.md) z usługą Azure Synapse Analytics lub utwórz nowe.

1. Wybierz **Bazę danych** w obszarze roboczym połączonym w wybranym połączeniu usługi Azure Synapse Analytics i wybierz opcję **Dalej**.

1. Wybierz encje do pozyskania z podłączonej bazy danych i wybierz **Dalej**.

1. Opcjonalnie wybierz encje danych, w których chcesz zezwalać na tworzenie profilów danych.

1. Wybierz opcję **Zapisz**, aby zastosować wybór i uruchomić pozyskiwanie danych z nowo utworzonego źródła danych połączonego z tabelami bazy danych lake w usłudze Azure Synapse Analytics. Zostanie otwarta strona **Źródła danych** z nowymi źródło danych **Odświeżania**.
