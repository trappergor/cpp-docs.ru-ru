---
title: Ошибка компилятора C3910
ms.date: 11/04/2016
f1_keywords:
- C3910
helpviewer_keywords:
- C3910
ms.assetid: cfcbe620-b463-463b-95ea-2d60ad33ebb5
ms.openlocfilehash: 186cd67d77e9aafbfe6a7d9dc18afb2bdbd94f0c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406630"
---
# <a name="compiler-error-c3910"></a>Ошибка компилятора C3910

«событие»: необходимо определить член «метод»

Событие был определен, но не содержит указанный обязательный метод доступа.

Дополнительные сведения см. в разделе [событий](../../extensions/event-cpp-component-extensions.md).

Следующий пример приводит к возникновению ошибки C3910:

```
// C3910.cpp
// compile with: /clr /c
delegate void H();
ref class X {
   event H^ E {
      // uncomment the following lines
      // void add(H^) {}
      // void remove( H^ h ) {}
      // void raise( ) {}
   };   // C3910

   event H^ E2; // OK data member
};
```