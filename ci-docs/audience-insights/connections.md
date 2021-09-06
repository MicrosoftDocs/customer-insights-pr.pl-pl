---
title: Połączenia z innymi usługami z aplikacji Customer Insights.
description: Udostępnianie danych w innych usługach.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 37c5d152a4cc91a90df8db387d25923ed150e238bc6b54c54f7bba59fbd48c82
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033231"
---
# <a name="connections-preview-overview"></a>Omówienie (podgląd) połączeń

Połączenia to klucz do włączenia udostępniania danych do i z funkcji Customer Insights. Każde połączenie ustanawia udostępnianie danych w określonej usłudze. Połączenia są podstawą do [konfigurowania wzbogaceń innych firm](enrichment-hub.md) i [konfigurowania eksportów](export-destinations.md). To samo połączenie może być używane wiele razy. Na przykład jedno połączenie z usługą Dynamics 365 Marketing działa dla wielu eksportów, a jedno połączenie Leadspace może zostać użyte dla kilku wzbogaceń.

Przejdź do połączeń **Admin** > **Połączenia**, aby utworzyć i wyświetlić połączenia.

Na karcie **Połączenia** widać wszystkie aktywne połączenia. Na liście zostanie wyświetlony wiersz dla każdego połączenia. 

Uzyskaj szybkie omówienie, opis i dowiedz się, co można zrobić z każdą opcją rozszerzania na karcie **Odkryj**.

### <a name="exports"></a>Eksporty

Tylko administratorzy mogą konfigurować nowe połączenia, ale mogą udzielać współautorom dostęp do korzystania z istniejących połączeń. Administratorzy określają, gdzie mogą się znaleźć dane, współautorzy definiują ładunek i częstotliwość określania ich potrzeb. Aby uzyskać więcej informacji, zobacz [Zezwalanie współautorom na używanie połączenia w celu eksportowania](#allow-contributors-to-use-a-connection-for-exports).

### <a name="enrichments"></a>Wzbogacenia

Tylko administratorzy mogą konfigurować nowe połączenia, ale utworzone połączenia są zawsze dostępne zarówno dla administratorów, jak i współautorów. Administratorzy zarządzają poświadczeniami i wyrażają zgodę na przenoszenie danych. Połączenia mogą być następnie używane do wzbogacania przez administratorów i współautorów.

## <a name="add-a-new-connection"></a>Dodaj nowe połączenie

Aby dodawać połączenia, trzeba mieć [uprawnienia administratora](permissions.md). W przypadku łączenia się z innymi usługami Microsoft założono, że obie usługi są w tej samej organizacji.

1. Przejdź do **Admin** > **Połączenia (wersja zapoznawcza)**.

1. Przejdź do karty **Połączenia**.

1. Wybrać **Dodaj połączenie**, aby utworzyć nowe połączenie. Wybierz z menu rozwijanego typ połączenia, które chcesz utworzyć.

1. Podaj wymagane szczegóły w okienku **Konfigurowanie połączenia**. 
   1. **Wyświetlana nazwa** i typ połączenia opisują połączenie. Zaleca się wybranie nazwy objaśniającej cel i miejsce docelowe tego połączenia.
   1. Dokładnie jakie pola będzie zależeć od tego, z jaką usługą jest nawiązywana połączenie. Szczegółowe informacje o określonym typie połączenia można znaleźć w artykule dotyczących usługi docelowej.

1. Aby utworzyć połączenie, wybierz **Zapisz**.

Możesz również wybrać **Konfiguruj** na kafelku na karcie **Odnajdź**.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Zezwalaj współautorom na używanie połączenia do eksportowania

Podczas konfigurowania lub edytowania połączenia eksportowania należy wybrać użytkowników, którzy mogą korzystać z tego konkretnego połączenia w celu zdefiniowania [eksportów](export-destinations.md). Domyślnie połączenie jest dostępne dla użytkowników, którzy mają rolę administratora. To ustawienie można zmienić w obszarze **Określ, kto może korzystać z tego połączenia** i zezwolić użytkownikom z rolą współautora na korzystanie z tego połączenia.

- Współautorzy nie mogą wyświetlać ani edytować połączenia. Podczas tworzenia eksportu będą widzieć tylko wyświetlaną nazwę i typ.
- Udostępniając połączenie, można umożliwić współautorom korzystanie z połączenia. Współautorzy będą widzieć udostępnione połączenia podczas skonfigurowania eksportu. Mogą zarządzać każdym eksportem, który korzysta z tego określonego połączenia.
- To ustawienie można zmienić, zachowując przy tym eksporty, które zostały już zdefiniowane przez współautorów.

## <a name="edit-a-connection"></a>Edytowanie połączenia

1. Przejdź do **Admin** > **Połączenia (wersja zapoznawcza)**.

1. Przejdź do karty **Połączenia**.

1. Wybierz pionowy wielokropek dla połączenia, które chcesz edytować.

1. Zaznacz **Edytuj**.

1. Zmień wartości, które chcesz zaktualizować i wybierz **Zapisz**.

## <a name="remove-a-connection"></a>Usuwanie połączenia

Jeśli usuwane połączenie jest używane przez wzbogacanie lub eksportowanie, należy je najpierw odłączyć lub usunąć. Okno dialogowe usuwania przeprowadzi do odpowiedniego wzbogacenia lub eksportu. 

Odłączone wzbogacenia i eksporty stają się nieaktywne. Można je ponownie aktywować, dodając do nich inne połączenie na stronie [Wzbogacenia](enrichment-hub.md) lub [Eksporty](export-destinations.md).

1. Przejdź do **Admin** > **Połączenia (wersja zapoznawcza)**.

1. Przejdź do karty **Połączenia**.

1. Wybierz pionowy wielokropek dla połączenia, które chcesz usunąć.

1. Wybierz **Usuń** z menu rozwijanego. Pojawia się okno dialogowe potwierdzenia.

   1. Jeśli są dostępne wzbogacenia lub eksporty używające tego połączenia, wybierz przycisk, aby wyświetlić informacje o połączeniu.
      - **Eksport:** można usunąć lub odłączyć eksport, aby można było usunąć połączenie. Aby odłączyć eksport, administratorzy mogą używać akcji **Odłącz**. Ta akcja jest dostępna dla pojedynczego i wielu wybranych eksportów. Odłączenie spowoduje zachowanie konfiguracji eksportu, ale nie zostanie on uruchomiony, dopóki nie zostanie dodane do niego inne połączenie.
      - **Wzbogacenia:** można usunąć lub dezaktywować wzbogacenia, aby można było usunąć połączenie. 
   1. Gdy połączenie nie ma więcej zależności, wróć do opcji **Admin** > **Połączenia** i spróbuj ponownie usunąć połączenie.

1. Aby potwierdzić usunięcie, wybierz opcję **Usuń**.

