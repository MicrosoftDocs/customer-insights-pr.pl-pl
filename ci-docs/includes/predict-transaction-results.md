---
ms.openlocfilehash: a67714de5aae80a0080c0e631ae6f8986eb2a003
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9611108"
---
- **Wydajność modelu szkolenia**: oceny A, B lub C wskazują wydajność prognozy i może pomóc w podjęciu decyzji o użyciu wyników przechowywanych w encji wyjściowej.

  Oceny są określane na podstawie następujących reguł:
  - **A** kiedy model dokładnie przewidział co najmniej 50% wszystkich prognoz, a odsetek trafnych prognoz dla klientów, którzy zrezygnowali, jest większy od wskaźnika bazowego o co najmniej 10%.
  - **B** kiedy model dokładnie przewidział co najmniej 50% wszystkich prognoz, a odsetek trafnych prognoz dla klientów, którzy zrezygnowali, jest do 10% większy niż poziom bazowy.
  - **C** kiedy model dokładnie przewidział mniej niż 50% wszystkich prognoz lub odsetek trafnych prognoz dla klientów, którzy zrezygnowali, jest mniejszy niż poziom bazowy.
  - **Linia bazowa** przyjmuje dane wejściowe w oknie czasowym przewidywania dla modelu (na przykład jeden rok) i tworzy różne ułamki czasu, dzieląc je przez 2, aż osiągnie jeden miesiąc lub mniej. Wykorzystuje te ułamki do stworzenia reguły biznesowej dla klientów, którzy nie dokonali zakupów w tym przedziale czasowym. Tych klientów uważa się za utraconych. Jako model bazowy wybrano regułę biznesową opartą na czasie z największą zdolnością przewidywania, kto prawdopodobnie odejdzie.

- **Prawdopodobieństwo rezygnacji (liczba klientów)**: grupy klientów na podstawie ich przewidywanego ryzyka rezygnacji. Opcjonalnie można [utworzyć segmenty klientów](../prediction-based-segment.md) o wysokim ryzyku rezygnacji. Takie segmenty ułatwiają zrozumienie tego, w którym miejscu powinien się znaleźć próg dla członkostwa w segmencie.

- **Czynniki mające największy wpływ**: istnieje wiele czynników branych pod uwagę podczas tworzenia przewidywania. Każdy z czynników ma swoją wagę obliczoną dla zagregowanych prognoz tworzonych przez model. Tych czynników można użyć w celu sprawdzenia poprawności wyników przewidywania. Lub użyj tych informacji później, aby [utworzyć segmenty](../prediction-based-segment.md), które mogą wpłynąć na ryzyko rezygnacji dla klientów.