---
title: Rozpoznawanie zdarzeń internetowych z uprzednio uwierzytelnionych odwiedzających użytkowników z funkcji nieznanej do znanej
description: Funkcja nieznana do znanej umożliwia powiązanie zdarzeń w witrynie internetowej z odwiedzającymi, którzy uwierzytelnili się wcześniej.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: d1bbc3315b55e2ee233dc672456e0c27e4ad0fbd5937af09cc790c96ee274000
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036796"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Rozpoznawanie zdarzeń internetowych z uprzednio uwierzytelnionych odwiedzających użytkowników

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Funkcja **Nieznana do znanej** w możliwości analizy zaangażowania umożliwia kojarzenie zdarzeń w witrynie internetowej z odwiedzającymi, którzy uwierzytelnili się wcześniej. Jeśli funkcja jest wyłączona, użytkownicy, którzy uwierzytelnili się podczas wcześniejszej wizyty, a następnie opuścili stronę, nie zostaną zidentyfikowani, jeśli nie uwierzytelnią się ponownie po powrocie. 

Na przykład osoba odwiedziła witrynę internetową w zeszłym tygodniu, zalogowała się do swojego konta użytkownika na stronie i przeglądała katalog produktów. Osoba powraca w następnym tygodniu, aby przeglądać więcej produktów bez logowania się na swoje konto. Właściciel witryny korzystający z funkcji **nieznanej do znanej** wiedziałby, że ta sama osoba wróciła i co zrobiła na stronie. Pozwala to na bardziej precyzyjne raportowanie i analizę działań na stronie internetowej.

## <a name="enable-unknown-to-known"></a>Włącz funkcję nieznane do znane

Tylko [administrator obszaru roboczego](user-roles.md) może włączyć tę funkcję. 

1. W szczegółowych statystykach dotyczących zaangażowania przejdź do **Administrator** > **Obszar roboczy**. 
2. Wybierz kartę **Ustawienia**.
3. W sekcji **Nieznany do znanego** ustaw przełącznik na **Włączone**.

![Włącz funkcję nieznane do znane](media/U2Ktoggle.png "Włącz funkcję nieznane do znane")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>Dodawanie kodu JavaScript do wstawki śledzenia witryny

Witryna internetowa może przechwytywać **identyfikator użytkownika authId** za pomocą następującego przykładu JavaScript przy użyciu [zestawu SDK witryny szczegółowych danych dotyczących zaangażowania](advanced-SDK-implementation.md). Aby funkcja **nieznana do znanej** działała, musisz przechwycić authId *i* włączyć userMapping:True we wstawce JavaScript, jak w poniższym przykładzie.

```
[…]
window, document
{
src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js",
name:"myproject",
cfg:{
ingestionKey:<paste your ingestion key>",
autoCapture:{
view:true,
click:true
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]