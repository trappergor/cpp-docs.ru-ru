---
title: Ошибка компилятора C3909
ms.date: 11/04/2016
f1_keywords:
- C3909
helpviewer_keywords:
- C3909
ms.assetid: 0a443132-e53f-42dc-a58b-f086da3e7bfd
ms.openlocfilehash: 435288ba657bd22ba29c6681014ae15baa051cec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50636466"
---
# <a name="compiler-error-c3909"></a>Ошибка компилятора C3909

aWinRT или объявление управляемого события должно находиться в управляемом типе или типе WinRT

Событие среды выполнения Windows или управляемое событие было объявлено в собственном типе. Чтобы устранить эту ошибку, объявите события в типах среды выполнения Windows или управляемых типах.

Дополнительные сведения см. в разделе [событий](../../windows/event-cpp-component-extensions.md).

В следующем примере показано возникновение ошибки C3909 и приводятся сведения по ее устранению.

```
// C3909.cpp
// compile with: /clr /c
delegate void H();
class X {
   event H^ E;   // C3909 - use ref class X instead
};

ref class Y {
   static event H^ E {
      void add(H^) {}
      void remove( H^ h ) {}
      void raise( ) {}
   }
};
```