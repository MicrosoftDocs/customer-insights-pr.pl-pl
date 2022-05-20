---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755557"
---
Po pobraniu danych rozpocznij proces ujednolicania danych, aby stworzyć jednolity profil klienta. Aby uzyskać więcej informacji, zobacz [Ujednolicenie danych](../data-unification.md).

### <a name="select-source-fields"></a>Wybierz pola źródłowe

1. Po przyjęciu danych zmapuj kontakty z danych e-commerce i lojalności na popularne typy danych. Przejdź do sekcji **Dane** > **Ujednolicanie**.

1. Wybierz podmioty, które reprezentują profil klienta - **eCommerceContacts** i **loyCustomers**.

   ![ujednolicić źródła danych e-commerce i lojalności.](../media/unify-ecommerce-loyalty.png)

1. Wybierz opcję **ContactId** jako klucz podstawowy dla opcji **eCommerceContacts** i **LoyaltyID** jako klucz podstawowy dla **loyCustomers**.

1. Wybierz **Dalej**. Pomiń zduplikowane rekordy i wybierz opcję **Dalej**.

### <a name="match-conditions"></a>Warunki dopasowywania

1. Wybierz **eCommerceContacts : eCommerce** jako główną encję i dołącz wszystkie rekordy.

1. Wybierz **loyCustomers : LoyaltyScheme** i uwzględnij wszystkie rekordy.

1. Dodawanie reguły:
   - Wybierz **FullName** zarówno dla eContacts, jak i loyCustomers.
   - Wybierz **Typ (Telefon, Nazwisko, Adres, ...)** dla **Normalizuj**.
   - Ustawianie **Poziomu dokładności**: **Podstawowe** i **Wartość**: **Wysokie**.
   - Jako nazwę wpisz **Nazwisko, E-mail**.

1. Dodaj drugi warunek dla adresu e-mail:
   - Wybierz **E-mail** zarówno dla eContacts, jak i loyCustomers.
   - Pozostaw puste pole Normalizuj.
   - Ustawianie **Poziomu dokładności**: **Podstawowe** i **Wartość**: **Wysokie**.

   ![Należy ujednolicić regułę dotyczącą nazwy i adresu e-mail.](../media/unify-match-rule.png)

1. Wybierz pozycję **Gotowe**.

1. Wybierz **Dalej**.

### <a name="unify-fields"></a>Ujednolicanie pól

1. Zmień nazwę **ContactId** dla encji **loyCustomers** na **ContactIdLOYALTY**, aby odróżnić go od innych pozyskanych identyfikatorów.

1. Wybierz **Dalej**, aby przejrzeć, a następnie wybierz **Utwórz profile klientów**.
