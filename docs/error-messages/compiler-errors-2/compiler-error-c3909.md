---
title: Ошибка компилятора C3909
ms.date: 11/04/2016
f1_keywords:
- C3909
helpviewer_keywords:
- C3909
ms.assetid: 0a443132-e53f-42dc-a58b-f086da3e7bfd
ms.openlocfilehash: 69613a1058bd5178ea4c03931664dd00bad7a101
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749000"
---
# <a name="compiler-error-c3909"></a>Ошибка компилятора C3909

Авинрт или объявление управляемого события должно выполняться в WinRT или управляемом типе

Событие среды выполнения Windows или управляемое событие было объявлено в собственном типе. Чтобы устранить эту ошибку, объявите события в типах среды выполнения Windows или управляемых типах.

Дополнительные сведения см. в разделе [event](../../extensions/event-cpp-component-extensions.md).

В следующем примере показано возникновение ошибки C3909 и приводятся сведения по ее устранению.

```cpp
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
